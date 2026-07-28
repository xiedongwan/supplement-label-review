# supplement-label-review

A Claude skill that reviews US dietary supplement labels against FDA, USDA organic, and CBP import regulations, and produces an interactive HTML compliance checklist.

Every rule is built from **source regulation text retrieved from eCFR** — not from summaries, blog posts, or commercial checklists. Where a widely repeated "requirement" turns out not to exist in the regulation, the rule library says so explicitly.

> **This is not legal advice.** It is a structured regulatory analysis. Regulations change, and application depends on facts not visible on packaging artwork. Have final artwork reviewed by a qualified regulatory consultant or attorney before commercial printing.

> **Not affiliated with the FDA, USDA, or CBP.** These agencies do not endorse or review this tool.

---

## Why this exists

Commercial label reviews vary a lot in quality. Two paid reviews of the same product line produced, between them:

- A correction instructing a designer to label **Chaga as "fruiting body"** — Chaga is a sclerotium, so following the correction would have introduced a *new* inaccuracy into corrected artwork.
- A **"3–5 pt heavy bar"** requirement cited to 21 CFR 101.36. No point size appears anywhere in 101.36; the figure comes from Appendix B to Part 101, which 101.36(e)(10) invokes with "FDA **urges**."
- Instructions to place the first heavy bar **beneath the "Supplement Facts" title**. Per 101.36(e)(6)(i) it goes beneath *Servings Per Container*.
- A **"font must be ½ the size of the most prominent text"** rule cited to 101.3(d), which actually says "reasonably related." No fraction appears in the regulation.
- **Country-of-origin marked compliant on presence alone**, missing that 19 CFR 134.46 is a proximity-and-size rule triggered by a competing address.

This skill encodes the regulations directly so those errors are catchable.

## What it checks

**Layer 1 — always runs (35 rules)**
Statement of identity · net quantity · firm name and address · Supplement Facts panel format · botanical/fungal ingredient identification · structure/function claims and the DSHEA disclaimer · panel placement and legibility · allergens · nutrient content claims

**Layer 2 — conditional modules**
`IMPORT` (19 CFR 134 country-of-origin, US importer identification, foreign-market label artifacts) · `ORGANIC` (7 CFR 205, gated on actual certification) · `CLAIMS-SUBSTANTIATION` (gluten-free, free-from, quantitative composition claims)

**Layer 3 — category modules (12 rules)**
`MUSHROOM` — fruiting body vs. mycelium-on-grain, sclerotial species, β-glucan assay specificity, Cordyceps species identity, Import Alert 25-05, species-specific claim risk

## Three verdicts, not two

A photograph cannot establish type size, PDP area, directory listings, or certification status. Guessing at these is worse than useless — a confident wrong PASS gets printed.

| Verdict | Meaning |
|---|---|
| **PASS** | Requirement met, visibly and verifiably |
| **FAIL** | Requirement not met, and you can see the violation |
| **NEEDS-INFO** | Cannot be determined from what was supplied |

Expect a meaningful share of NEEDS-INFO on any photo-based review. Supplying the print-ready vector file converts most measurement items to PASS or FAIL.

## Design principles

These exist because each was violated at least once during development:

- **Apply the whole rule, including its flexibility clauses.** "Or other words of similar meaning," "reasonably related," "such as" — these are part of the requirement, not decoration. Failing a label for an unlisted-but-equivalent form is a false positive, and false positives cost real money in reprints.
- **A finding must survive its own explanation.** If the note concedes the requirement is substantially met, the verdict is wrong. Downgrade it.
- **Never assert unverified enforcement history.** "The agency has been strict about this" carries weight precisely because it sounds researched. If it wasn't checked, don't write it.
- **Report labeling compliance only.** Prop 65, facility registration, and litigation theory are real concerns and somebody else's checklist. Including them invites treating a business risk as a legal defect.

## Installation

**Claude Desktop / Cowork** — download `supplement-label-review.skill` from [Releases](../../releases) and open it, or click **Save skill** on the file card.

**Claude Code** — clone, then copy the skill itself into your skills directory:

```bash
git clone https://github.com/xiedongwan/supplement-label-review.git
cp -r supplement-label-review/skill/supplement-label-review ~/.claude/skills/
```

The skill lives at `skill/supplement-label-review/` in this repo, so cloning the
repository directly into `~/.claude/skills/` would nest `SKILL.md` too deep for
Claude Code to discover it.

**Build the .skill bundle yourself:**

```bash
cd skill && zip -r ../supplement-label-review.skill supplement-label-review
```

## Usage

Give Claude your packaging artwork and ask for a review:

> Review this supplement label for FDA compliance

The skill asks three gating questions — product category, whether it's imported, and organic certification status — then evaluates every applicable rule and writes an interactive HTML checklist with a checkbox and note field per finding, progress tracking, and a source link on every regulation cited.

## Repository layout

```
skill/supplement-label-review/
├── SKILL.md                              workflow, intake, output conventions
└── references/
    ├── rules-layer1-mandatory.md         35 universal rules
    ├── rules-layer2-conditional.md       IMPORT / ORGANIC / CLAIMS modules
    ├── rules-layer3-mushroom.md          12 mushroom-specific rules
    └── checklist-template.html           interactive report template
```

Each rule carries: ID · citation · quoted regulation text · how to evaluate · three-state verdict logic · correction template · ⚠️ notes where commercial checklists get it wrong.

## Extending to other categories

Layer 3 is the extension point. To add a category — botanicals, marine oils, probiotics — copy `rules-layer3-mushroom.md` as a model and register the gate in `SKILL.md` Step 0. Layers 1 and 2 stay untouched.

## Regulations covered

| Citation | Subject |
|---|---|
| 21 CFR 101.2 | Information panel of package form food |
| 21 CFR 101.3 | Identity labeling of food in packaged form |
| 21 CFR 101.4 | Food; designation of ingredients (incl. 101.4(h) botanicals) |
| 21 CFR 101.5 | Name and place of business |
| 21 CFR 101.7 | Declaration of net quantity of contents |
| 21 CFR 101.13 | Nutrient content claims — general principles |
| 21 CFR 101.36 | Nutrition labeling of dietary supplements |
| 21 CFR 101.91 | Gluten-free labeling of food |
| 21 CFR 101.93 | Certain types of statements for dietary supplements |
| 19 CFR 134.11, 134.46 | Country of origin marking |
| 7 CFR 205.101, 205.301, 205.303, 205.311 | National Organic Program labeling |
| FD&C Act §403(a)(1), §403(w) | Misbranding; major food allergen labeling |
| FDA Import Alert 25-05 | Dried fungus from Hong Kong and the PRC |

Regulation text retrieved from [eCFR](https://www.ecfr.gov). Verify currency before relying on any citation — eCFR is updated continuously.

## Contributing

Corrections to the rule library are especially welcome, and the bar is simple: **quote the regulation.** A pull request that says "this requirement doesn't exist in the cited section" with the section text attached is more valuable than one adding a rule from memory.

If you find a rule that produces a false positive, that's a bug worth reporting — false positives are the expensive failure mode here.

## License

MIT — see [LICENSE](LICENSE).
