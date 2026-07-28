# Layer 2 — Conditional Modules

Each module runs **only** when its gate condition is met. Do not emit these rules otherwise — firing organic rules at a non-organic product produces noise, not compliance.

---

# MODULE: IMPORT
**Gate:** product is manufactured outside the United States.

## IMP1. Country of origin marking required
**Citation:** 19 CFR 134.11 (implementing 19 U.S.C. 1304)
**Regulation says:** "Unless excepted by law, section 304, Tariff Act of 1930, as amended (19 U.S.C. 1304), requires that **every article of foreign origin (or its container) imported into the United States shall be marked in a conspicuous place as legibly, indelibly, and permanently as the nature of the article (or container) will permit, in such manner as to indicate to an ultimate purchaser in the United States the English name of the country of origin** of the article, at the time of importation into the Customs territory of the United States."

**Evaluate:** Locate a country-of-origin statement. Check it is (a) conspicuous, (b) legible, (c) permanent, (d) in English.

**Verdict logic:**
- PASS — origin marked conspicuously in English.
- FAIL — absent, in a non-English form, or printed so small/low-contrast it is not conspicuous.
- NEEDS-INFO — marking present but conspicuousness is borderline.

⚠️ **"Conspicuous" is a legal standard, not a formality.** Origin text buried beside a barcode in the smallest type on the pack is a defensible CBP finding of non-conspicuousness even though the words are technically present. Do not mark PASS on presence alone — assess prominence.

---

## IMP2. ⭐ Origin marking near a US or third-country address
**Citation:** 19 CFR 134.46
**Regulation says:** "In any case in which the words '**United States**,' or '**American**,' the letters '**U.S.A.**,' any variation of such words or letters, or **the name of any city or location in the United States**, or the name of **any foreign country or locality other than the country or locality in which the article was manufactured or produced** appear on an imported article or its container, and those words, letters or names may mislead or deceive the ultimate purchaser as to the actual country of origin of the article, there shall appear **legibly and permanently in close proximity to such words, letters or name, and in at least a comparable size**, the name of the country of origin preceded by '**Made in**,' '**Product of**,' or other words of similar meaning."

**Evaluate:**
1. Does any US place name appear on the label? (Distributor address, "Sacramento, CA", "Made in California", brand names containing a US locality.)
2. Does any **third-country** place name appear? (A London or Berlin address on goods manufactured in China triggers this rule identically — the rule covers "any foreign country or locality other than the country … in which the article was manufactured.")
3. If yes to either: is the origin statement (a) in close proximity to that address, (b) at least comparable in size, and (c) introduced by wording that identifies the country as the origin?

**Verdict logic — evaluate the three elements separately:**
- PASS — no competing place name; OR the origin statement is adjacent, comparably sized, and introduced by wording that conveys origin.
- FAIL — the origin marking sits elsewhere on the pack (different panel, different column, or separated by intervening material), or is materially smaller than the competing address, or does not identify the country as the origin at all.
- NEEDS-INFO — relative sizes not measurable.

⚠️ **The prefix requirement is a meaning test, not a phrase list.** The regulation reads "preceded by 'Made in,' 'Product of,' **or other words of similar meaning**." Do **not** fail a label merely because it uses different wording. Phrasings that convey origin and are therefore acceptable include:

- `Product of China` / `Made in China` — the two named in the text
- `Country of Origin: China` — explicit and unambiguous; **passes**
- `Manufactured in China`, `Produced in China`, `Grown in China` — all convey origin

Wording that does **not** satisfy the rule, because it describes something other than the article's origin:

- `Imported from China` — describes the shipping route, not where the article was made
- `Packed in China`, `Distributed from China` — describes an activity, not origin
- A bare `China` with no introductory wording

When a label uses acceptable-but-unnamed wording such as "Country of Origin:", grade it **PASS** and, if useful, note that "Product of {country}" is the phrasing the regulation names explicitly. Do not manufacture a failure out of a preference.

**Correction template:**
> `{address}` appears on the {panel}. Under 19 CFR 134.46, place the origin statement in close proximity and at comparable size, prefixed appropriately:
> ```
> {qualifier}: {firm}
> {street address}
> {city}, {ST} {ZIP}
> Product of {country}
> ```

⚠️ **The failure mode this rule exists to catch is placement, not phrasing.** A reviewer sees "Country of origin: China" somewhere on the pack and passes it — but 134.46 is a *proximity and size* rule triggered by a competing address. Origin text on a different panel, in a different column, or in markedly smaller type does not satisfy it no matter how it is worded. Note the trigger is not limited to US addresses: a UK or EU distributor address on Chinese-made goods triggers the identical requirement.

⚠️ **Do not overcorrect into phrasing pedantry.** Having identified placement as the real issue, it is tempting to also fail acceptable wording. The regulation's "or other words of similar meaning" clause is part of the rule and must be applied. If placement and size are satisfied and the wording conveys origin, the label **passes** — say so plainly rather than grading FAIL on a stylistic preference. A finding whose own explanation concedes "most of this is fine" is a finding that should have been a PASS.

---

## IMP3. US agent / importer identification
**Citation:** 21 CFR 101.5(a), (c) applied to imports
**Rule:** The 101.5 firm block must identify a firm the US consumer can reach. For imported product the practical forms are "Imported by", "Distributed by", or "Manufactured for" followed by the US entity.

**Verdict logic:**
- PASS — a US entity with a US address appears with an appropriate qualifier.
- FAIL — only a foreign address appears (e.g., a London address on product sold in the US), with no US importer or distributor identified.
- NEEDS-INFO — a US entity is named but the qualifier phrase is missing or ambiguous.

⚠️ A label carrying only a foreign address fails both this rule and, in combination, IMP2. Labels adapted from a UK or EU SKU almost always fail here.

---

## IMP4. Foreign-market label conventions that do not transfer to the US
**Citation:** composite — 21 CFR 101.3(g), 101.36(a), 101.9, 101.7(b)(1)
**Rule:** Screen for artifacts of EU/UK/other non-US labelling systems, each of which maps to a specific US failure:

| Foreign convention | US status | Rule violated |
|---|---|---|
| "Food Supplement" | Not permitted as the statement of identity | 101.3(g) → A1 |
| "Nutrition Information" panel with per-100g column | Wrong panel entirely | 101.36(a) → D1 |
| "Typical Values" / "per 100g" columns | Not a US format | 101.36(b) → D1 |
| Metric-only net quantity | Avoirdupois required | 101.7(b)(1) → B6 |
| "Energy" in kJ/kcal as primary | US uses Calories | 101.36(b)(2) |
| British spellings in claims ("fibre") | Claim term must match US regulatory term | 101.13 → I1 |
| "Best Before" (BBE) date format | Not required by FDA, but must not conflict | — advisory |
| E-numbers for additives | Must use US common or usual names | 101.4(b) |

**Verdict logic:** FAIL for each artifact found; cross-reference the mapped Layer 1 rule.

---

## IMP5. FDA Food Facility Registration and Prior Notice
**Citation:** 21 CFR Part 1 Subparts H and I (FSMA)
**Rule:** Not a label attribute, but a prerequisite for lawful import. The foreign manufacturing facility must be registered with FDA, and Prior Notice must be filed for each shipment.

**Verdict logic:** NEEDS-INFO (always). Surface as an action item, never as a label pass/fail.

---

# MODULE: ORGANIC
**Gate:** the label bears the USDA organic seal, the word "organic", or a certifier mark.

## ⛔ ORG0. Gate check — certification must actually exist
**Citation:** 7 CFR 205.300 et seq.; OFPA 7 U.S.C. 6519
**Rule:** Organic labelling claims may only be made on product from a **certified** operation. Displaying the USDA seal without certification is a federal violation carrying civil penalties per violation.

**Verdict logic:**
- NEEDS-INFO (**always ask first**) — confirm that a valid organic certificate exists, naming the certifying agent, and covering this specific product.
- FAIL — user confirms no certification but the label bears the seal or the word "organic".

⚠️ Run this check **before** any other organic rule. Everything downstream is moot if certification does not exist.

---

## ORG1. Composition tier determines what may be claimed
**Citation:** 7 CFR 205.301(a)–(d)
**Regulation says:**
- **(a) "100 percent organic"** — "must contain (by weight or fluid volume, excluding water and salt) **100 percent** organically produced ingredients."
- **(b) "organic"** — "must contain (by weight or fluid volume, excluding water and salt) **not less than 95 percent** organically produced raw or processed agricultural products. Any remaining product ingredients must be organically produced, unless not commercially available in organic form, or must be nonagricultural substances or nonorganically produced agricultural products produced consistent with the National List."
- **(c) "made with organic (specified ingredients)"** — "must contain … **at least 70 percent** organically produced ingredients."
- **(d) less than 70 percent** — "may represent the organic nature of the product only as provided in § 205.305" (i.e., organic ingredients may be identified in the ingredient statement only; **no USDA seal, no organic claim on the PDP**).

**Verdict logic:**
- PASS — the claimed tier matches the actual organic content.
- FAIL — tier claimed exceeds actual content; or a "made with organic" product displays the USDA seal (not permitted at that tier).
- NEEDS-INFO — actual organic percentage unknown.

---

## ORG2. Prohibited practices for organic-labelled product
**Citation:** 7 CFR 205.301(f)(1)–(7)
**Regulation says** products labelled "100 percent organic" or "organic" and all ingredients identified as organic must **not**:
1. Be produced using excluded methods (GMO), per 205.105(e)
2. Be processed using ionizing radiation, per 205.105(f)
3. Be produced using sewage sludge, per 205.105(g)
4. Be processed using processing aids not on the National List (and "100 percent organic" products must use organically produced processing aids)
5. **Contain sulfites, nitrates, or nitrites added during production or handling**
6. Be produced using nonorganic ingredients when organic ingredients are available
7. **Include organic and nonorganic forms of the same ingredient**

**Verdict logic:** NEEDS-INFO (default) — these are process facts, not label attributes. Surface as verification items against the certificate and supplier documentation.

⚠️ Item (7) is a real trap for blends: sourcing one mushroom organically and another conventionally, both listed, breaches this even if the 95% threshold is met.

---

## ORG3. ⭐ Certifier statement placement
**Citation:** 7 CFR 205.303(b)(2)
**Regulation says:** "**On the information panel, below the information identifying the handler or distributor of the product and preceded by the statement, 'Certified organic by * * *,' or similar phrase, identify the name of the certifying agent** that certified the handler of the finished product and may display the business address, Internet address, or telephone number of the certifying agent in such label."

**Evaluate:** Locate the handler/distributor block, then confirm the certifier statement sits directly **below** it, on the information panel, with the required lead-in phrase.

**Verdict logic:**
- PASS — certifier named directly below the firm block, on the information panel, prefixed "Certified organic by".
- FAIL — certifier named in a separate box/column away from the firm block; or above it; or on a different panel; or missing the lead-in phrase.
- NEEDS-INFO — panel relationship not determinable from the supplied views.

**Correction template:**
> Consolidate the firm and certifier blocks on the information panel:
> ```
> {qualifier}: {firm}
> {street address}
> {city}, {ST} {ZIP}
> Certified organic by {certifier name}
> ```

⚠️ Applies to the **"organic"** and **"100 percent organic"** tiers (205.301(a) and (b)). The "made with organic" tier is governed by 205.304 instead.

---

## ORG4. Organic ingredients must be identified in the ingredient statement
**Citation:** 7 CFR 205.303(b)(1)
**Regulation says:** "For products labeled 'organic,' identify each organic ingredient in the ingredient statement with the word, 'organic,' or with an asterisk or other reference mark which is defined below the ingredient statement to indicate the ingredient is organically produced. **Water or salt included as ingredients cannot be identified as organic.**"

**Verdict logic:**
- PASS — each organic ingredient marked with "organic" or a defined reference mark.
- FAIL — organic claim on the PDP but ingredients unmarked in the statement; or water/salt marked as organic.
- N/A — product is "100 percent organic" single-ingredient with no ingredient statement.

---

## ORG5. Percentage statement formatting
**Citation:** 7 CFR 205.303(a)(2)
**Regulation says:** "For products labeled 'organic,' the percentage of organic ingredients in the product; (**The size of the percentage statement must not exceed one-half the size of the largest type size on the panel** on which the statement is displayed and **must appear in its entirety in the same type size, style, and color without highlighting**.)"

**Applies when:** the label states an organic percentage.

**Verdict logic:**
- PASS — percentage statement ≤ half the largest type on its panel, uniform in size/style/colour, not highlighted.
- FAIL — oversized, or set with highlighting or mixed styling.
- NEEDS-INFO — relative size not measurable.

---

## ORG6. Certifier mark may not outrank the USDA seal
**Citation:** 7 CFR 205.303(a)(5)
**Regulation says:** the certifying agent's seal, logo, or mark may be displayed "*Provided further,* That, **such seals or marks are not individually displayed more prominently than the USDA seal**."

**Verdict logic:**
- PASS — certifier mark no more prominent than the USDA seal; or USDA seal not used.
- FAIL — certifier logo larger or more prominent than the USDA seal.

---

## ORG7. USDA seal usage
**Citation:** 7 CFR 205.311
**Rule:** The USDA organic seal must be reproduced in the prescribed form — either the four-colour version, or black-and-white; proportions may not be altered; it may not be printed in arbitrary brand colours.

**Verdict logic:**
- PASS — seal reproduced per specification.
- FAIL — recoloured, distorted, or redrawn.
- NEEDS-INFO — colour fidelity not determinable from image.

---

# MODULE: CLAIMS-SUBSTANTIATION
**Gate:** the label bears any composition, purity, potency, or free-from claim.

## SUB1. Quantitative composition claims require analytical support
**Citation:** FD&C Act §403(a)(1) (misbranding — false or misleading labelling); 21 CFR 111 subpart E (specifications) and subpart J (records)
**Rule:** Claims stating a measured level ("≥20% beta-glucan", "50:1 extract", "1000 mg equivalent") must be supported by a specification and Certificate of Analysis using a stated method.

**Verdict logic:** NEEDS-INFO (always). List each quantitative claim and request the corresponding COA and test method.

⚠️ For **beta-glucan specifically**, the test method matters more than the number. The common iodometric/enzymatic kits that measure cereal β-glucan do not distinguish fungal β-glucan from α-glucan (starch), which is why some mushroom "polysaccharide" figures are inflated. Ask which method was used — the fungal-specific enzymatic assay is the defensible one.

---

## SUB2. "Gluten-Free"
**Citation:** 21 CFR 101.91
**Rule:** "Gluten-free", "no gluten", "free of gluten", "without gluten" may be used only if the food contains **less than 20 ppm gluten**, is not a gluten-containing grain, and is not derived from one unless processed to below 20 ppm.

**Verdict logic:**
- NEEDS-INFO — requires a test report at <20 ppm.
- FAIL — claim present on a product containing a gluten-containing grain.

---

## SUB3. Free-from and negative ingredient claims
**Citation:** FD&C Act §403(a)(1)
**Rule:** "No fillers", "no grain", "no starch", "no additives" must be literally true of the finished product.

**Verdict logic:** NEEDS-INFO — verify against the full formulation including carriers and processing aids.

⚠️ "No grain / no starch" is a specific risk on mushroom products grown on grain substrate — see the MUSHROOM module.

---

## SUB4. "Natural"
**Citation:** none — FDA has not defined "natural" by regulation
**Rule:** FDA has no formal definition; its longstanding informal policy is that "natural" means nothing artificial or synthetic has been included in or added to a food that would not normally be expected. The term remains subject to the general prohibition on misleading labelling and is a frequent target of class-action litigation.

**Verdict logic:** PASS with advisory. Note the litigation exposure rather than a regulatory failure.

---

## SUB5. Vegan / vegetarian
**Citation:** none — not defined by FDA
**Rule:** Not a regulated term. Must be truthful and not misleading; verify no animal-derived excipients (gelatin, magnesium stearate of animal origin, carriers).

**Verdict logic:** NEEDS-INFO — verify against the full formulation.
