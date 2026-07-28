---
name: supplement-label-review
description: Review a US dietary supplement label against FDA, USDA organic, and CBP import regulations, and produce an interactive HTML compliance checklist. Use whenever the user supplies packaging artwork, a label photo, a dieline, or label copy for a dietary supplement and wants it checked for compliance, or asks about Supplement Facts panel requirements, structure/function claims, the DSHEA disclaimer, net quantity declarations, botanical plant-part declarations, country-of-origin marking, or USDA organic labeling. Triggers on phrases like "review my label", "is this label FDA compliant", "check my packaging", "label review", "Supplement Facts", "DSHEA", or any request to audit supplement packaging before print.
---

# Dietary Supplement Label Review

Evaluate a US dietary supplement label rule-by-rule against source regulation text, and deliver an interactive HTML checklist the user can work through with their designer.

## What this skill is not

This produces a structured regulatory review, not legal advice. Every output carries a disclaimer. Do not tell the user their label "is compliant" — say which rules pass, which fail, and which cannot be determined from what was supplied.

---

## Core principle: three verdicts, never two

Most label review fails by forcing a binary. A photograph cannot establish type size, PDP area, directory listings, or whether a firm holds organic certification. Guessing at these is worse than useless — a confident wrong "PASS" means the user prints it.

Every rule resolves to exactly one of:

| Verdict | Meaning | When to use |
|---|---|---|
| **PASS** | Requirement met, visibly and verifiably | The evidence is actually in front of you |
| **FAIL** | Requirement not met | You can see the violation |
| **NEEDS-INFO** | Cannot determine from what was supplied | Anything requiring measurement, documentation, or an external fact |

**Default to NEEDS-INFO when uncertain.** A review that honestly says "I need you to measure this" is more valuable than one that guesses. Expect a meaningful share of NEEDS-INFO on any photo-based review, and say so up front rather than apologising for it later.

Never emit a fourth state. Do not write "partially compliant" — decompose it into separate rules that each pass or fail.

---

## Workflow

### Step 0 — Intake (three gating questions)

Before evaluating anything, call `AskUserQuestion` with exactly these three. They determine which modules run; everything else can be resolved later as NEEDS-INFO.

1. **Product category** — general supplement / mushroom or fungal / botanical or herbal / vitamin or mineral
   → gates Layer 3

2. **Manufactured outside the US?** — yes, imported / no, US-made / not sure
   → gates the IMPORT module. If yes, ask the country in the same pass or resolve it from the label.

3. **Organic claims or USDA seal on the label?** — yes and certified / yes but not yet certified / no organic claims
   → gates the ORGANIC module. "Yes but not yet certified" is an immediate FAIL on ORG0 — surface it before anything else, since displaying the seal without certification carries civil penalties.

Ask for anything obviously missing at the same time — most often the information panel, when only the front of the pack was supplied.

Do not ask about type sizes, PDP dimensions, or COAs here. Those surface as NEEDS-INFO in the report, where they read as an action list rather than an interrogation.

### Step 1 — Read the label

Examine every supplied view. Transcribe, panel by panel:

- **PDP** — brand, statement of identity, net quantity, front-panel claims, badges, seals
- **Information panel** — Supplement Facts, ingredient list, firm block, disclaimer, certifier, origin
- **Other panels** — marketing copy, directions, storage, warnings, lot/date
- **Inner units** — stick packs, sachets, or blisters have their own labelling obligations

State plainly which panels you were given and which you were not. Rules about a panel you never saw are NEEDS-INFO, not PASS.

### Step 2 — Load the rule libraries

Read the reference files for the modules that apply:

- `references/rules-layer1-mandatory.md` — **always**
- `references/rules-layer2-conditional.md` — IMPORT / ORGANIC / CLAIMS-SUBSTANTIATION modules per Step 0
- `references/rules-layer3-mushroom.md` — mushroom or fungal products

Each rule carries its citation, the regulation text it rests on, evaluation instructions, verdict logic, and a correction template. Follow them; do not improvise a requirement that is not in the file.

### Step 3 — Evaluate rule by rule

Work through every applicable rule. For each, record:

- Rule ID and citation
- What you observed on the label (quote it)
- Verdict
- For FAIL: the specific correction, using the rule's template
- For NEEDS-INFO: precisely what the user must supply or measure

Two discipline points:

**Cite the regulation, not a summary of it.** The rule files quote source text so findings rest on what the CFR says. When a commonly-repeated requirement is not actually in the regulation, the rule file flags it with ⚠️ — carry that nuance into the report rather than repeating folklore.

**Apply the whole rule, including its flexibility clauses.** Regulations frequently name examples and then admit equivalents — "or other words of similar meaning," "or an appropriately descriptive term," "reasonably related," "such as." These clauses are part of the requirement, not decoration. Failing a label for using an unlisted-but-equivalent form is a false positive, and false positives cost the user real money in reprints. Where a rule turns on a meaning test, ask whether the label achieves the regulation's purpose — not whether it matches the example verbatim.

**A finding must be able to survive its own explanation.** If the note or correction concedes that most of the requirement is satisfied, the verdict is wrong. Write the finding, then read it back: if it says "this is mostly fine, but," downgrade it to PASS with an advisory note. Do not grade FAIL on a stylistic preference and then soften it in prose — that produces a report the user cannot triage, because the severity label no longer means anything.

**Never assert enforcement history you have not verified.** Phrases like "the agency has been strict about this" or "CBP has issued rulings on this point" carry weight precisely because they sound researched. If a source has not been checked in this session, do not write it. State what the regulation says and stop.

**Report labeling compliance only.** This skill grades a label against labeling regulations. Do not open sections for state-law exposure (Prop 65), customs process (facility registration, Prior Notice), litigation theory, or operational readiness (lot coding). They are real concerns and they are somebody else's checklist — including them dilutes the report and invites the user to treat a business risk as a legal defect.

Two narrow exceptions, both reported **inside** a normal rule finding rather than as separate items:

- Where a rule's own text makes non-labeling exposure part of the analysis — MSH1 (Import Alert 25-05) turns on how the label describes the product, so the detention consequence belongs in that finding's note.
- Where a claim on the label requires documentation to be lawful — the finding is NEEDS-INFO against the claim, not a general advisory about testing.

### Step 4 — Build the checklist

Read `references/checklist-template.html` and populate it. The template carries a
worked item example in an HTML comment — follow its structure exactly.

Section order is **FAIL → NEEDS-INFO → PASS**. Actionable work comes first; passing
items are evidence, not tasks.

Four structural rules the template enforces:

**Regulation name and link live in the "What the regulation requires" block.** Not in
a tag row under the title. Each block opens with a plain-English name for the
regulation, the CFR citation, and a source link, then quotes the text. The tag row
under the title carries only the verdict and risk level. A reader should be able to
see *what body of law this is* before reading what it says.

**Pass items carry no checkbox.** They are not tasks. They keep their observation,
regulation block, note, and a text field for the user's own comments.

**Progress counts only actionable items** — anything with a checkbox. A report reading
"3 of 22 action items resolved" is useful; "3 of 54" is not, because 32 of those were
never work.

**The Pass section is collapsed by default**, inside a `<details>` fold labelled with
the count. Opening the report shows what needs doing; the evidence trail is one click
away and its open/closed state persists.

Write to the outputs directory and present with `mcp__cowork__present_files`.

#### Naming regulations in the requirement block

Give the section's actual subject, not a restatement of the finding:

| Citation | Name to use |
|---|---|
| 21 CFR 101.2 | Information panel of package form food |
| 21 CFR 101.3 | Identity labeling of food in packaged form |
| 21 CFR 101.4 | Food; designation of ingredients |
| 21 CFR 101.4(h) | Botanical ingredient names — plant part and Latin binomial |
| 21 CFR 101.5 | Name and place of business of manufacturer, packer, or distributor |
| 21 CFR 101.7 | Declaration of net quantity of contents |
| 21 CFR 101.13 | Nutrient content claims — general principles |
| 21 CFR 101.36 | Nutrition labeling of dietary supplements (Supplement Facts) |
| 21 CFR 101.91 | Gluten-free labeling of food |
| 21 CFR 101.93 | Certain types of statements for dietary supplements (DSHEA) |
| 21 CFR 111 | Current Good Manufacturing Practice for dietary supplements |
| 19 CFR 134.11 | Country of origin marking required |
| 19 CFR 134.46 | Marking when a name other than the country of origin appears |
| 7 CFR 205.301 | Organic product composition |
| 7 CFR 205.303 | Packaged products labeled "100 percent organic" or "organic" |
| FD&C Act §403(a)(1) | Misbranding — false or misleading labeling |
| FD&C Act §403(w) | Major food allergen labeling (FALCPA / FASTER Act) |
| Import Alert 25-05 | Detention without physical examination — dried fungus from HK/PRC |

Link targets: `https://www.ecfr.gov/current/title-21/section-101.36` and the
equivalent for other titles. For statutes and import alerts, link the governing
source rather than eCFR.

Write to the outputs directory and present with `mcp__cowork__present_files`.

---

## What belongs in a "Note"

The note field carries **judgment that does not fit in rule-and-fix**. Use it for:

- **Correcting folklore.** Where a widely repeated "requirement" is not in the
  regulation — the phantom "3–5 pt heavy bar," the phantom "½ the size" rule for the
  statement of identity. The rule files mark these ⚠️; carry the correction through.
- **Declaring your own uncertainty.** When a finding is arguable, say so and say
  which way a reviewer might go. When a regulation is internally inconsistent — as
  101.93(d) is between symbol-linking and each-panel — say that plainly rather than
  asserting one reading.
- **Explaining why a PASS matters.** A pass that avoided a real trap deserves a
  sentence, especially where the same product category commonly fails.
- **Connecting findings.** When two items share a root cause, say so in both.

Do not use notes to hedge a clear finding, restate the correction, or pad. If a note
says nothing the fix did not already say, delete it.

---

### Step 5 — Verify before delivering

Re-read your own findings against the rule files:

- Does every FAIL cite a requirement that is actually in the quoted regulation text?
- Did any NEEDS-INFO get upgraded to PASS or FAIL without evidence?
- Are the ⚠️ nuances reflected rather than flattened?
- Do the corrections say specifically what to change, not just what is wrong?
- Does every FAIL survive reading its own note back — or does the note concede the
  requirement is substantially met?
- Did any flexibility clause ("or other words of similar meaning," "reasonably
  related," "such as") get read as a closed list?
- Does any finding assert enforcement history that was not verified this session?
- Did any non-labeling concern (state law, customs process, litigation theory) leak
  in as its own finding?
- Does every requirement block carry a regulation name, citation, and working link?
- Do Pass items have no checkbox, and does the progress count exclude them?
- Is the disclaimer present?

---

## Rules that are commonly reported wrong

These are the traps. The rule files carry the detail; this is the index.

**No numeric ratio for the statement of identity.** 21 CFR 101.3(d) says "a size reasonably related to the most prominent printed matter." There is no "at least 1/2" rule in the regulation. (A2)

**No point-size for the heavy bar.** 21 CFR 101.36 specifies no thickness. The "3–5 pt" figure comes from Appendix B to Part 101, which 101.36(e)(10) invokes with "FDA **urges**" — a recommendation. Report it as such. (D4)

**The first heavy bar is not under the title.** It goes beneath "Servings Per Container" (or "Serving Size" if servings-per-container is not declared), per 101.36(e)(6)(i). (D4)

**Country-of-origin presence is not compliance.** 19 CFR 134.46 is a *proximity and comparable-size* rule triggered by any competing US **or third-country** address on the pack. Origin text elsewhere on the label does not satisfy it. (IMP2)

**The DSHEA disclaimer must appear on each panel bearing a claim.** 21 CFR 101.93(d): "the disclaimer shall appear on each panel or page where there such is a statement." Cross-panel asterisk linking alone does not satisfy the text as written. Also check the boldface requirement in 101.93(e), and singular vs. plural wording in 101.93(c). (F2, F3, F1)

**Plant part goes inside the Supplement Facts panel.** 101.36(d)(1) requires it "regardless of whether they are listed in an ingredient statement or in the nutrition label." A front-panel badge does not satisfy it. (E1)

**The Latin binomial is conditionally required**, not universally — 101.4(h)(2) excepts names standardized in *Herbs of Commerce*. (E2)

**Metric alone fails; metric alongside ounces is fine.** 101.7(b)(1) requires avoirdupois; 101.7(p) permits metric additionally. (B6)

**Missing street address is NEEDS-INFO, not FAIL.** 101.5(d) permits omission if the firm is in a current city or telephone directory — a fact not visible on the label. (C3)

**Imagery can create a disease claim.** 101.93(g)(2)(iv)(E) names "pictures, vignettes, symbols, or other means." Screening only the words misses it. (F4)

**"No allergens" cannot be concluded from the label.** Allergens enter through excipients, carriers, and substrate. Sesame became a major allergen on January 1, 2023. (H1, MSH10)

---

## Output conventions

Write findings so a packaging designer can act on them without a regulatory background:

- Quote what is on the label, then state what it must become
- Give replacement text, not a description of replacement text
- Mark risk as HIGH (misbranding / detention / recall exposure), MEDIUM (technical violation, enforcement discretion likely), or LOW (best practice)
- Keep commercial risk visually separate from compliance findings

Required disclaimer, verbatim:

> **This review is a structured regulatory analysis, not legal advice.** Findings are based on the cited Code of Federal Regulations text as retrieved from eCFR. Regulations change, and application depends on facts not visible on packaging artwork. Have final artwork reviewed by a qualified regulatory consultant or attorney before commercial printing.
