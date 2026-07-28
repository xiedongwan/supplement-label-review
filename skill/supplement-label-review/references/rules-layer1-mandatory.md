# Layer 1 — Universal Mandatory Rules

Applies to **every** US dietary supplement label. No gating conditions.

Each rule: `ID | Citation | Requirement (verbatim-anchored) | How to evaluate | Verdict logic | Correction template`

---

## Group A — Statement of Identity (PDP)

### A1. "Dietary Supplement" must appear in the statement of identity
**Citation:** 21 CFR 101.3(g)
**Regulation says:** "Dietary supplements shall be identified by the term 'dietary supplement' as a part of the statement of identity, except that the word 'dietary' may be deleted and replaced by the name of the dietary ingredients in the product (e.g., calcium supplement) or an appropriately descriptive term indicating the type of dietary ingredients that are in the product (e.g., herbal supplement with vitamins)."

**Evaluate:** Look on the PDP for the exact phrase "Dietary Supplement", OR a permitted variant of the form "[ingredient] Supplement" (e.g., "Calcium Supplement", "Herbal Supplement", "Mushroom Supplement").

**Verdict logic:**
- PASS — "Dietary Supplement" or a compliant `[ingredient] supplement` variant is present on the PDP.
- FAIL — PDP says "Food Supplement", "Nutritional Supplement", "Supplement" alone, or omits it entirely. **"Food Supplement" is an EU/UK term and is NOT a permitted US variant** — the permitted variants must retain the word "supplement" preceded by the dietary ingredient name or descriptor, not replace "dietary" with "food".
- NEEDS-INFO — text is present but illegible in the supplied image.

**Correction template:**
> Replace `{found_text}` on the principal display panel with `Dietary Supplement`. If space requires a shorter form, `{primary_ingredient} Supplement` is also permitted under 101.3(g).

---

### A2. Statement of identity must be prominent, bold, and parallel to the base
**Citation:** 21 CFR 101.3(a), (d)
**Regulation says:** "The principal display panel of a food in package form shall bear as one of its principal features a statement of the identity of the commodity." … "This statement of identity shall be presented in bold type on the principal display panel, shall be in a size reasonably related to the most prominent printed matter on such panel, and shall be in lines generally parallel to the base on which the package rests as it is designed to be displayed."

**Evaluate:** Check (a) bold type, (b) size relative to the largest text on the PDP, (c) orientation parallel to the package base.

**Verdict logic:**
- PASS — bold, horizontally parallel to base, visually comparable in scale to the brand name.
- FAIL — rotated 90°, set in light/thin weight, or dwarfed by the brand mark.
- NEEDS-INFO — cannot determine relative type size from image resolution; ask for the print file or a measured value.

⚠️ **Common reviewer error:** 101.3(d) says "**a size reasonably related to** the most prominent printed matter." It does **NOT** state a numeric fraction. There is no "at least 1/2 the size" rule in 101.3(d) — that figure appears in some third-party checklists but is not in the regulation. Report this as a qualitative judgment, not a measured pass/fail.

**Correction template:**
> Set `{statement_of_identity}` in bold, in lines parallel to the package base, at a size reasonably related to `{most_prominent_text}`. Current treatment: {observed}.

---

## Group B — Net Quantity of Contents (PDP)

### B1. Net quantity must appear on the PDP
**Citation:** 21 CFR 101.7(a), (e)
**Regulation says:** "The principal display panel of a food in package form shall bear a declaration of the net quantity of contents." … "The declaration shall be located on the principal display panel of the label, and with respect to packages bearing alternate principal panels it shall be duplicated on each principal display panel."

**Verdict logic:**
- PASS — a net quantity statement appears on the PDP (and on each alternate PDP if the package has more than one).
- FAIL — absent from the PDP, or present only on a side/back panel.

---

### B2. Net quantity must sit in the bottom 30% of the PDP
**Citation:** 21 CFR 101.7(f)
**Regulation says:** "It shall be placed on the principal display panel within the bottom 30 percent of the area of the label panel in lines generally parallel to the base on which the package rests as it is designed to be displayed: *Provided,* That on packages having a principal display panel of 5 square inches or less, the requirement for placement within the bottom 30 percent of the area of the label panel shall not apply when the declaration of net quantity of contents meets the other requirements of this part."

**Evaluate:** Measure vertical position of the declaration as a fraction of PDP height.

**Verdict logic:**
- PASS — within the lower 30% band; OR PDP area ≤ 5 in² (exemption applies).
- FAIL — above the 30% band on a PDP larger than 5 in².
- NEEDS-INFO — PDP area unknown (needed to apply the ≤5 in² exemption).

**Correction template:**
> Move the net quantity declaration into the bottom 30% of the PDP. Measured position: approximately {observed}% from the base.

---

### B3. Net quantity type size scales with PDP area
**Citation:** 21 CFR 101.7(i)(1)–(4)
**Regulation says (verbatim thresholds):**
| PDP area | Minimum type height |
|---|---|
| ≤ 5 in² | 1/16 in |
| > 5 but ≤ 25 in² | 1/8 in |
| > 25 but ≤ 100 in² | 3/16 in |
| > 100 in² | 1/4 in |
| > 400 in² | 1/2 in |

Plus 101.7(h)(2): "Letter heights pertain to upper case or capital letters. When upper and lower case or all lower case letters are used, it is the lower case letter 'o' or its equivalent that shall meet the minimum standards."
Plus 101.7(h)(1): "The ratio of height to width (of the letter) shall not exceed a differential of 3 units to 1 unit."
Plus 101.7(i) closing: where the declaration is blown/embossed/molded rather than printed, add 1/16 inch to the minimums.

**Verdict logic:**
- NEEDS-INFO (default) — requires both the PDP area and a measured cap-height/lowercase-o height. Almost never determinable from a photo.
- FAIL — only if the label is supplied as a vector/print file with measurable dimensions and it falls short.

**Correction template:**
> PDP area is {area} in², so the net quantity declaration requires a minimum type height of {min_height} (measured on the lowercase "o" if mixed case). Please confirm current height from the print file.

---

### B4. Multiunit retail packages must declare count, unit quantity, and total
**Citation:** 21 CFR 101.7(s)
**Regulation says:** "On a multiunit retail package, a statement of the quantity of contents shall appear on the outside of the package and shall include the number of individual units, the quantity of each individual unit, and, in parentheses, the total quantity of contents of the multiunit package in terms of avoirdupois or fluid ounces…" Example given in the regulation: `"6-16 oz bottles—(96 fl oz)"`.

**Applies when:** product is stick packs, sachets, or individually wrapped units inside an outer carton.

**Verdict logic:**
- PASS — all three elements present: unit count, per-unit quantity, and parenthetical total in oz.
- FAIL — any element missing (e.g., only "20 Stick Packs" with no per-unit weight, or total not in parentheses in ounces).
- NEEDS-INFO — cannot read the full declaration.

**Correction template:**
> Revise to the 101.7(s) three-part form: `{count} stick packs × {unit_qty} — (NET WT {total_oz} OZ ({total_g}g))`

⚠️ **Note on "multiunit retail package":** 101.7(s) defines it as containing units "capable of being individually sold in full compliance with all requirements." If the inner sticks are not separately saleable, treat the outer carton as a single package under B1–B3 instead, and evaluate the inner sticks under the small-package provisions of 101.36(i)(2)(iv).

---

### B5. Net weight terminology and abbreviations
**Citation:** 21 CFR 101.7(j)(3), (n)
**Regulation says:** "The term 'net weight' shall be used when stating the net quantity of contents in terms of weight." And 101.7(n) lists the ONLY permitted abbreviations: `wt`, `oz`, `lb`, `gal`, `pt`, `qt`, `fl` ("and none other").

**Verdict logic:**
- PASS — uses "Net Wt." (or "Net Weight") with permitted abbreviations.
- FAIL — uses non-permitted abbreviations (e.g., "grms", "ounces" abbreviated oddly), or omits "net weight" for a weight declaration.

---

### B6. Dual declaration — US customary required, metric permitted
**Citation:** 21 CFR 101.7(b)(1), (p)
**Regulation says:** 101.7(b)(1) "Statements of weight shall be in terms of avoirdupois pound and ounce." 101.7(p) "A separate statement of the net quantity of contents in terms of the metric system is not regarded as a supplemental statement and an accurate statement of the net quantity of contents in terms of the metric system of weight or measure may also appear on the principal display panel or on other panels."

**Verdict logic:**
- PASS — ounces present (metric optional alongside).
- FAIL — **metric only, no avoirdupois ounces.** This is a frequent failure on labels adapted from EU/UK artwork.

⚠️ **Common reviewer error:** metric is *permitted*, not *required*. A label showing only "30g" fails; a label showing only "1.06 OZ" passes; both together is best practice.

---

## Group C — Name and Place of Business (Information Panel)

### C1. Responsible firm name and place of business required
**Citation:** 21 CFR 101.5(a), (b)
**Regulation says:** "The label of a food in packaged form shall specify conspicuously the name and place of business of the manufacturer, packer, or distributor." … "The requirement for declaration of the name … shall be deemed to be satisfied, in the case of a corporation, only by the actual corporate name."

**Verdict logic:**
- PASS — actual corporate/business name plus place of business present.
- FAIL — absent, or shows only a brand name that is not the legal entity name.
- NEEDS-INFO — cannot confirm whether the displayed name is the registered corporate name.

---

### C2. Qualifying phrase required when the firm is not the manufacturer
**Citation:** 21 CFR 101.5(c)
**Regulation says:** "Where the food is not manufactured by the person whose name appears on the label, the name shall be qualified by a phrase that reveals the connection such person has with such food; such as 'Manufactured for ______', 'Distributed by ______', or any other wording that expresses the facts."

**Verdict logic:**
- PASS — a connective phrase is present ("Distributed by", "Manufactured for", "Imported by", etc.).
- FAIL — bare company name with no qualifier, when the firm did not manufacture the product.
- NEEDS-INFO — unknown whether the named firm is the actual manufacturer.

**Correction template:**
> Prefix the firm block with the qualifier that states the true relationship: `Distributed by: {firm}` or `Manufactured for: {firm}`.

---

### C3. Street address required unless the firm is listed in a current directory
**Citation:** 21 CFR 101.5(d)
**Regulation says:** "The statement of the place of business shall include the street address, city, State, and ZIP code; however, the street address may be omitted if it is shown in a current city directory or telephone directory."

**Verdict logic:**
- PASS — full street address, city, state, ZIP present.
- NEEDS-INFO (**default when street address is missing**) — the omission is only lawful if the firm appears in a current city or telephone directory. This is a fact the reviewer cannot see on the label. **Do not report as FAIL without confirming directory status.**
- FAIL — street address missing AND user has confirmed the firm is not directory-listed; or state/ZIP missing (those have no exemption).

**Correction template:**
> Either (a) confirm `{firm}` is listed in a current city or telephone directory, or (b) add the street address:
> ```
> {qualifier}: {firm}
> {street address}
> {city}, {ST} {ZIP}
> ```

---

## Group D — Supplement Facts Panel

### D1. The panel must be titled "Supplement Facts", not "Nutrition Facts" or "Nutrition Information"
**Citation:** 21 CFR 101.36(a), (e)(1)
**Regulation says:** 101.36(a) "The label of a dietary supplement that is offered for sale shall bear nutrition labeling in accordance with this regulation…" 101.36(e)(1) "The title, 'Supplement Facts,' shall be set in a type size larger than all other print size in the nutrition label and, unless impractical, shall be set full width of the nutrition label. The title and all headings shall be bolded."

**Verdict logic:**
- PASS — panel is headed "Supplement Facts".
- FAIL — headed "Nutrition Facts" (that is the 101.9 conventional-food panel), "Nutrition Information" (EU/UK convention), "Nutritional Information", or any other variant.
- FAIL — title is not the largest type in the panel, or not bolded.

⚠️ This is the single most common failure on labels adapted from EU/UK artwork. An EU "NUTRITION INFORMATION" table with per-100g columns is structurally a different document from a Supplement Facts panel and cannot be patched — it must be rebuilt.

**Correction template:**
> Replace the `{found_title}` table with a compliant Supplement Facts panel per 101.36. The EU per-100g column format is not permitted; US format requires "Amount Per Serving" and "% Daily Value" columns.

---

### D2. Serving Size and Servings Per Container subheadings
**Citation:** 21 CFR 101.36(b)(1)(i), (ii)
**Regulation says:** "The subheading 'Serving Size' shall be placed under the heading 'Supplement Facts' and aligned on the left side of the nutrition label. … Serving size for dietary supplements shall be expressed using a term that is appropriate for the form of the supplement, such as 'tablets,' 'capsules,' 'packets,' or 'teaspoonfuls.'" … "The subheading 'Servings Per Container' shall be placed under the subheading 'Serving Size' and aligned on the left side of the nutrition label, **except that this information need not be provided when it is stated in the net quantity of contents declaration.**"

**Verdict logic:**
- PASS — both present and left-aligned; OR Serving Size present and servings count already appears in the net quantity declaration.
- FAIL — Serving Size missing, or expressed in a unit inappropriate to the dosage form.
- NEEDS-INFO — alignment not determinable.

---

### D3. Non-RDI ingredients require a symbol and "Daily Value not established" footnote
**Citation:** 21 CFR 101.36(b)(3)(iv)
**Regulation says:** "Other dietary ingredients shall bear a symbol (e.g., an asterisk) in the column under the heading of '% Daily Value' that refers to the same symbol placed at the bottom of the nutrition label and followed by the statement 'Daily Value not established,' except that when the heading '% Daily Value' is not used, the symbol shall follow the quantitative amount by weight for each dietary ingredient listed."

**Verdict logic:**
- PASS — each non-RDI ingredient carries a symbol in the %DV column, and the footnote "Daily Value not established" appears below the last heavy bar, inside the box.
- FAIL — symbol present but footnote missing, footnote present but symbols missing, or footnote text differs from the statutory wording.

**Correction template:**
> Add `†` (or `*`) in the % Daily Value column for each of: {ingredients}. Place `† Daily Value not established.` below the final heavy bar, inside the panel box.

---

### D4. Heavy bars in three required positions
**Citation:** 21 CFR 101.36(e)(6)
**Regulation says:** "A heavy bar shall be placed: (i) Beneath the subheading 'Servings Per Container' except that if 'Servings Per Container' is not required and, as a result, not declared, the bar shall be placed beneath the subheading 'Serving Size,' (ii) Beneath the last dietary ingredient to be listed under paragraph (b)(2)(i) of this section, if any, and (iii) Beneath the last other dietary ingredient to be listed under paragraph (b)(3) of this section, if any."

**Verdict logic:**
- PASS — heavy bars present at each applicable position.
- FAIL — heavy bar missing at a required position, or rendered as a hairline.
- NEEDS-INFO — cannot distinguish heavy bar from hairline at supplied resolution.

⚠️ **Common reviewer error — read carefully.** Two things third-party checklists routinely get wrong:
1. **There is no heavy bar directly beneath the "Supplement Facts" title.** The first heavy bar goes beneath *Servings Per Container* (or beneath *Serving Size* if servings-per-container is not declared) — i.e. below the serving information block, not immediately under the title.
2. **21 CFR 101.36 does not specify any point-size for the heavy bar.** There is no "3 pt to 5 pt" requirement anywhere in 101.36. That figure comes from the *graphic specifications in appendix B to part 101*, which 101.36(e)(10) invokes only as encouragement: "In the interest of uniformity of presentation, FDA **urges** that the information be presented using the graphic specifications set forth in appendix B to part 101, as applicable." Report bar thickness as a **recommendation**, not a mandatory failure.

**Correction template:**
> Add a heavy bar beneath `{position}`. Appendix B to Part 101 (recommended, not mandatory) illustrates a bar substantially heavier than the hairlines separating ingredients — typically ~3 pt at standard panel scale.

---

### D5. Light bar beneath the column headings
**Citation:** 21 CFR 101.36(e)(7)
**Regulation says:** "A light bar shall be placed beneath the headings 'Amount Per Serving' and '% Daily Value.'"

**Verdict logic:** PASS / FAIL / NEEDS-INFO on presence of a light rule under the heading row.

---

### D6. Hairline rules between ingredients
**Citation:** 21 CFR 101.36(e)(5)
**Regulation says:** "A hairline rule that is centered between the lines of text shall separate each dietary ingredient required in paragraph (b)(2) and (b)(3) of this section from the dietary ingredient above and beneath it."

**Exception — 101.36(i)(2)(v):** "Where there is not sufficient space on a small or intermediate-sized package for a nutrition label that meets minimum type size requirements of 4.5 points if hairlines are used…, the hairlines may be omitted and replaced by a row of dots."

**Verdict logic:**
- PASS — hairlines between each ingredient row; or dots used on a qualifying small package.
- FAIL — no separation between ingredient rows on a standard package.

---

### D7. Panel enclosed in a box
**Citation:** 21 CFR 101.36(e)(2)
**Regulation says:** "The nutrition information shall be enclosed in a box by using hairlines."

**Verdict logic:** PASS / FAIL on presence of a bounding box.

---

### D8. Minimum type size inside the panel
**Citation:** 21 CFR 101.36(e), (e)(4), and (i)(2)
**Regulation says:** "…information other than the title, headings, and footnotes shall be in uniform type size no smaller than 8 point. Type size no smaller than 6 point may be used for column headings … and for footnotes."
**Small/intermediate package overrides — 101.36(i)(2):**
- (i) total surface area available to bear labeling **< 12 in²** → no smaller than **4.5 point**
- (ii) **12–40 in²** → no smaller than **6 point**; may drop to 4.5 point if <20 in² with more than 8 dietary ingredients, or 20–40 in² with more than 16 dietary ingredients.
- (iv) inner container enclosed in outer packaging: "the type size of the nutrition label on the primary (inner) container may be as small as needed … provided that the primary container is securely enclosed in outer packaging, the nutrition labeling on the outer packaging meets the applicable type size requirements, and such outer packaging is not intended to be separated from the primary container under conditions of retail sale."

**Verdict logic:**
- NEEDS-INFO (default) — requires measured point sizes and the package's total labeling surface area.
- FAIL — only from a measurable print file.

---

### D9. Typography inside the panel
**Citation:** 21 CFR 101.36(e)(3)
**Regulation says:** All information within the nutrition label shall utilize: "(i) A single easy-to-read type style, (ii) All black or one color type, printed on a white or other neutral contrasting background whenever practical, (iii) Upper- and lowercase letters, except that all uppercase lettering may be utilized for packages that have a total surface area available to bear labeling of less than 12 square inches, (iv) At least one point leading …, and (v) Letters that do not touch."

**Verdict logic:**
- PASS — single type style, single colour, neutral contrasting ground, mixed case.
- FAIL — multiple type styles inside the panel, coloured type, low-contrast ground, or all-caps body text on a package ≥ 12 in².

---

### D10. Extract quantity must be the weight of the extract, and starting-material condition disclosed
**Citation:** 21 CFR 101.36(b)(3)(ii)(B), (C)
**Regulation says:** "(B) For any dietary ingredient that is a liquid extract from which the solvent has not been removed, the quantity listed shall be the volume or weight of the total extract. Information on the condition of the starting material shall be indicated when it is fresh and may be indicated when it is dried. Information may be included on the concentration of the dietary ingredient and the solvent used, e.g., 'fresh dandelion root extract, x (y:z) in 70% ethanol'… (C) For a dietary ingredient that is an extract from which the solvent has been removed, the weight of the ingredient shall be the weight of the dried extract."

Also 101.36(b)(3)(ii): "The quantitative amount by weight shall be the weight of the other dietary ingredient listed and not the weight of any component, or the source, of that dietary ingredient."

**Applies when:** any ingredient name contains "extract".

**Verdict logic:**
- NEEDS-INFO (default) — whether the declared mg is the extract weight or the raw starting-material equivalent is not visible on the label.
- FAIL — label declares an amount that is explicitly a raw-herb equivalent in the amount column rather than the extract weight.

**Correction template:**
> Confirm that `{ingredient} — {amount}` is the weight of the finished dried extract, not the raw starting material. If expressing a ratio, use the 101.36(b)(3)(ii)(B) form.

---

### D11. Source ingredients and "Other ingredients" list placement
**Citation:** 21 CFR 101.36(d) and 101.4(g)
**Regulation says (101.36(d)):** "The source ingredient that supplies a dietary ingredient may be identified within the nutrition label in parentheses immediately following or indented beneath the name of a dietary ingredient and preceded by the words 'as' or 'from'… When a source ingredient is not identified within the nutrition label, it shall be listed in an ingredient statement in accordance with § 101.4(g), which shall appear outside and immediately below the nutrition label or, if there is insufficient space below the nutrition label, immediately contiguous and to the right of the nutrition label."

**Regulation says (101.4(g)):** "…shall be preceded by the word 'Ingredients,' unless some ingredients (i.e., sources) are identified within the nutrition label in accordance with § 101.36(d), in which case the ingredients listed outside the nutrition label shall be in a list preceded by the words 'Other ingredients.' Ingredients in dietary supplements that are not dietary ingredients or that do not contain dietary ingredients, such as excipients, fillers, artificial colors, artificial sweeteners, flavors, or binders, shall be included in the ingredient list."

**Verdict logic:**
- PASS — non-dietary ingredients (excipients, flow agents, flavours, anticaking agents) appear in an "Other ingredients" list immediately below or contiguous-right of the panel.
- PASS — no such list needed because the product genuinely contains only the dietary ingredients declared in the panel.
- FAIL — excipients visible in the formulation but absent from any ingredient list; or list placed on a different panel.
- NEEDS-INFO — cannot confirm from the label whether excipients exist in the formulation.

---

## Group E — Botanical / Fungal Ingredient Identification

### E1. Plant part must be declared for botanicals (including fungi)
**Citation:** 21 CFR 101.4(h)(1), applied via 101.36(d)(1)
**Regulation says (101.4(h)):** "The common or usual name of ingredients of dietary supplements that are botanicals **(including fungi and algae)** shall be consistent with the names standardized in *Herbs of Commerce*, 1992 edition… The listing of these names on the label shall be followed by statements of: (1) The part of the plant (e.g., root, leaves) from which the dietary ingredient is derived (e.g., 'Garlic bulb' or 'Garlic (bulb)'), **except that this designation is not required for algae**. The name of the part of the plant shall be expressed in English (e.g., 'flower' rather than 'flos')."

**Regulation says (101.36(d)(1)):** "Source ingredients shall be identified in accordance with § 101.4 (i.e., shall be listed by common or usual name, and the listing of botanicals shall specify the part of the plant from which the ingredient is derived) **regardless of whether they are listed in an ingredient statement or in the nutrition label.**"

**Evaluate:** For each botanical/fungal ingredient inside the Supplement Facts panel, check that a plant/fungal part appears as part of the ingredient name.

**Verdict logic:**
- PASS — every botanical ingredient names its part (e.g., "Reishi (*Ganoderma lucidum*) fruiting body extract").
- FAIL — part omitted inside the panel. Marketing copy elsewhere on the pack (e.g., a "100% Fruiting Body" badge) does **not** satisfy this; 101.36(d)(1) requires it wherever the ingredient is listed.
- NEEDS-INFO — the actual part used is unknown to the reviewer.

**Correction template:**
> Revise inside the Supplement Facts panel:
> `{common name} ({Latin binomial}) {part} extract — {amount}`

---

### E2. Latin binomial required unless the common name is in *Herbs of Commerce*
**Citation:** 21 CFR 101.4(h)(2)
**Regulation says:** "The Latin binomial name of the plant, in parentheses, **except that this name is not required when it is available in the reference entitled: *Herbs of Commerce* for the common or usual name listed on the label**, and, when required, the Latin binomial name may be listed before the part of the plant. Any name in Latin form shall be in accordance with internationally accepted rules on nomenclature…"

**Verdict logic:**
- PASS — Latin binomial present, correctly spelled, properly italicised or otherwise consistently styled.
- PASS — binomial absent but the common name is standardized in *Herbs of Commerce* (1992).
- FAIL — binomial present but misspelled or taxonomically wrong.
- NEEDS-INFO — cannot verify the common name against *Herbs of Commerce* (the reference is not freely available online; flag for the user to check).

⚠️ Note: the binomial is *conditionally* required, not universally required. Including it is always safe.

---

### E3. Single-ingredient supplements without an ingredient list
**Citation:** 21 CFR 101.4(h)(3)
**Regulation says:** "On labels of single-ingredient dietary supplements that do not include an ingredient list, the identification of the Latin binomial name, when needed, and the part of the plant may be prominently placed on the principal display panel or information panel, or included in the nutrition label."

**Applies when:** product is a single botanical with no separate ingredient statement.

**Verdict logic:** PASS if binomial + part appear in any of the three permitted locations.

---

## Group F — Claims and DSHEA Disclaimer

### F1. Structure/function claims trigger the DSHEA disclaimer
**Citation:** 21 CFR 101.93(b), (c)
**Regulation says (c)(1), singular:** "This statement has not been evaluated by the Food and Drug Administration. This product is not intended to diagnose, treat, cure, or prevent any disease."
**Regulation says (c)(2), plural:** "These statements have not been evaluated by the Food and Drug Administration. This product is not intended to diagnose, treat, cure, or prevent any disease."

**Evaluate:** Identify every structure/function claim on the pack (words like "supports", "promotes", "maintains", "helps", plus single-word benefit callouts such as "Immunity", "Focus", "Clarity", "Energy", "Digestion"). Then confirm the disclaimer is present.

**Verdict logic:**
- PASS — disclaimer present, wording matches the statute exactly, and singular/plural form matches the number of claims.
- FAIL — disclaimer absent while S/F claims are present; or wording paraphrased; or singular form used with multiple claims.
- FAIL — claims present but no linking symbol (see F2).

⚠️ **Singular vs plural matters.** One claim → "This statement has not been evaluated…". Two or more → "These statements have not been evaluated…". Many labels use the plural form with a single claim.

**Correction template:**
> Add the statutory disclaimer verbatim, in a box on the information panel:
> `{singular_or_plural_text}`

---

### F2. Disclaimer placement and symbol linking
**Citation:** 21 CFR 101.93(d)
**Regulation says:** "The disclaimer shall be placed adjacent to the statement with no intervening material or linked to the statement with a symbol (e.g., an asterisk) at the end of each such statement that refers to the same symbol placed adjacent to the disclaimer… **On product labels and in labeling (e.g., pamphlets, catalogs), the disclaimer shall appear on each panel or page where there such is a statement.** The disclaimer shall be set off in a box where it is not adjacent to the statement in question."

**Verdict logic:**
- PASS — every S/F claim carries the linking symbol; the disclaimer is boxed; and the disclaimer appears on **each panel** bearing a claim.
- FAIL — claim on the front panel links to a disclaimer that appears only on the back panel **without** the disclaimer also being present on the front panel.
- FAIL — disclaimer not boxed when non-adjacent.

⚠️ **Most-missed requirement in the whole regulation.** The "each panel" rule means a front-panel claim generally requires a front-panel disclaimer. Cross-panel asterisk linking alone does not satisfy 101.93(d) as written. Several commercial label-review reports mark cross-panel linking as fully compliant — that reading is not supported by the text.

**Correction template:**
> `{panel}` bears the claim `{claim}` but no disclaimer. Either place the boxed disclaimer on `{panel}` as well, or remove the claim from that panel.

---

### F3. Disclaimer type size and weight
**Citation:** 21 CFR 101.93(e)
**Regulation says:** "The disclaimer in paragraph (c) of this section shall appear in **boldface type** in letters of a typesize **no smaller than one-sixteenth inch**."

**Verdict logic:**
- PASS — boldface, ≥ 1/16 in (measured on the lowercase "o").
- FAIL — set in regular/light weight (visually determinable).
- NEEDS-INFO — type height not measurable from image.

⚠️ The **boldface** requirement is frequently missed even when the wording and placement are correct.

---

### F4. Claims must not be disease claims
**Citation:** 21 CFR 101.93(f), (g)
**Regulation says (f):** "Dietary supplement labels or labeling may … bear statements that describe the role of a nutrient or dietary ingredient intended to affect the structure or function in humans or that characterize the documented mechanism by which a nutrient or dietary ingredient acts to maintain such structure or function, **provided that such statements are not disease claims under paragraph (g)**. If the label or labeling of a product marketed as a dietary supplement bears a disease claim as defined in paragraph (g), **the product will be subject to regulation as a drug**."

**Regulation says (g)(1):** "…a 'disease' is damage to an organ, part, structure, or system of the body such that it does not function properly (e.g., cardiovascular disease), or a state of health leading to such dysfunctioning (e.g., hypertension); except that diseases resulting from essential nutrient deficiencies (e.g., scurvy, pellagra) are not included."

**Screen against the ten (g)(2) criteria.** A statement is a disease claim if it explicitly or implicitly claims the product:
1. Has an effect on a specific disease or class of diseases
2. Has an effect on characteristic signs or symptoms of a disease
3. Has an effect on an abnormal condition associated with a natural state or process, if uncommon or capable of significant/permanent harm
4. Has an effect on a disease through: (A) the product name, (B) a formulation statement citing a drug ingredient, (C) a citation implying disease use, (D) use of the word "disease"/"diseased", (E) **pictures, vignettes, symbols, or other means**
5. Belongs to a class of products intended to treat disease
6. Is a substitute for a disease therapy
7. Augments a disease therapy or drug action
8. Has a role in the body's response to a disease or disease vector
9. Treats/prevents/mitigates adverse events of a disease therapy, where those events are diseases
10. Otherwise suggests an effect on a disease

**Verdict logic:**
- PASS — all claims describe normal structure/function without disease implication.
- FAIL — any claim meets a (g)(2) criterion. Cite which one.
- NEEDS-INFO — borderline; flag for regulatory counsel.

⚠️ Criterion (g)(2)(iv)(E) — **"pictures, vignettes, symbols, or other means"** — means *imagery* can create a disease claim even when the copy is clean. Check for graphics such as anatomical illustrations, medical crosses, before/after depictions, or symptom imagery. Purely verbal claim screening misses this entirely.

---

### F5. 30-day FDA notification for structure/function claims
**Citation:** 21 CFR 101.93(a)(1)–(3)
**Regulation says:** "**No later than 30 days after the first marketing** of a dietary supplement that bears one of the statements listed in section 403(r)(6) of the Federal Food, Drug, and Cosmetic Act, the manufacturer, packer, or distributor of the dietary supplement shall notify the Office of Dietary Supplement Programs (HFS-810), Center for Food Safety and Applied Nutrition, Food and Drug Administration, 5001 Campus Dr., College Park, MD 20740, that it has included such a statement on the label or in the labeling of its product."

Notification must include: firm name and address; the text of the statement; the dietary ingredient that is the subject; the product name including brand. It must be signed by a responsible individual certifying that the firm **has substantiation that the statement is truthful and not misleading**.

**Verdict logic:**
- NEEDS-INFO (always) — this is a filing obligation, not a label attribute. Always surface it as an action item when any S/F claim is present.

**Action template:**
> This label bears structure/function claims, which triggers a mandatory FDA notification within 30 days of first marketing (21 CFR 101.93(a)). Confirm this filing is scheduled, and that substantiation files exist for: {claims}.

---

## Group G — Panel Placement and Legibility

### G1. Required information must be on the PDP or information panel
**Citation:** 21 CFR 101.2(b)
**Regulation says:** "All information required to appear on the label of any package of food under §§ 101.4, 101.5, 101.8, 101.9, 101.13, 101.17, 101.36, subpart D of part 101, and part 105 of this chapter shall appear either on the principal display panel or on the information panel, unless otherwise specified."

**And 101.2(a):** "The term *information panel* … means that part of the label immediately contiguous and to the right of the principal display panel as observed by an individual facing the principal display panel" (with exceptions for unusable space, alternate PDPs, and top-panel PDPs).

**Verdict logic:**
- PASS — Supplement Facts, ingredient list, and firm block all sit on the PDP or the true information panel.
- FAIL — required elements scattered onto a panel that is neither the PDP nor the panel immediately right of it.

---

### G2. Minimum 1/16 inch type for all required information
**Citation:** 21 CFR 101.2(c)
**Regulation says:** "All information appearing on the principal display panel or the information panel pursuant to this section shall appear prominently and conspicuously, but **in no case may the letters and/or numbers be less than one-sixteenth inch in height** unless an exemption pursuant to paragraph (f) of this section is established."

**Verdict logic:**
- NEEDS-INFO (default) — requires measurement.
- FAIL — from a measurable print file only.

---

### G3. Information panel content must be uninterrupted
**Citation:** 21 CFR 101.2(e)
**Regulation says:** "All information appearing on the information panel pursuant to this section shall appear **in one place without other intervening material**."

**Verdict logic:**
- PASS — required elements grouped contiguously.
- FAIL — marketing copy, graphics, or decorative elements interrupt the block of required information.

⚠️ Frequently violated by designers who interleave lifestyle copy between the Supplement Facts panel and the firm block.

---

## Group H — Allergens

### H1. Major food allergen declaration
**Citation:** FD&C Act §403(w) (21 U.S.C. 343(w)), as amended by FALCPA and the FASTER Act
**Requirement:** If the product contains a major food allergen, the label must declare it either (a) in parentheses following the ingredient's common name, or (b) in a "Contains:" statement immediately after or adjacent to the ingredient list.

**The nine major allergens:** milk, eggs, fish, Crustacean shellfish, tree nuts, peanuts, wheat, soybeans, and **sesame** (added by the FASTER Act, effective January 1, 2023).

**Verdict logic:**
- PASS — no major allergens in the formulation, or all present allergens declared.
- FAIL — an allergen appears in the ingredient list without proper declaration.
- NEEDS-INFO (**default**) — the full formulation including processing aids and carriers is not visible on the label. Confirm against the manufacturer's specification.

⚠️ **Do not conclude "no allergens, compliant" from the label alone.** Allergens can enter via excipients, flow agents, and carriers not visible in the panel. Sesame in particular is newly regulated and often missed on older artwork.

---

## Group I — Nutrient Content Claims

### I1. Nutrient content claims must meet defined thresholds
**Citation:** 21 CFR 101.13, and the definitions in 101.54–101.62
**Rule:** Any claim characterizing the level of a nutrient ("high in", "good source of", "rich in", "excellent source", "low", "free", "reduced") is a nutrient content claim and may be used only if the food meets the regulatory definition for that term.

**Key thresholds:**
- "High", "Rich in", "Excellent source of" → **≥ 20% of the DV** per reference amount (101.54(b))
- "Good source", "Contains", "Provides" → **10–19% of the DV** per reference amount (101.54(c))
- "More", "Added", "Extra", "Plus" → **≥ 10% of the DV more** than the reference food (101.54(e))

**Verdict logic:**
- FAIL — claim used without the product meeting the threshold.
- NEEDS-INFO — actual per-serving nutrient amount unknown.

⚠️ Watch for **British spellings** ("fibre") on labels adapted from UK artwork — the claim must use US spelling to match the regulatory term, and separately must meet the threshold.

⚠️ Also note: a dietary supplement's serving is typically small, so "high in fibre" or "natural source of protein" claims almost never survive the 20%/10% DV test on a 1–2 g stick pack.

---

### I2. Distinguish nutrient content claims from composition claims
**Citation:** 21 CFR 101.13(a), (b)
**Rule:** A statement of the *amount* or *percentage* of a nutrient that does not characterize the level (e.g., "contains 250 mg of X") is not a nutrient content claim. Composition claims about non-nutrients ("100% fruiting body", "≥20% beta-glucan") are not nutrient content claims either — they are subject to the general truthfulness requirement rather than 101.54 thresholds.

**Verdict logic:**
- PASS — composition claim, needs substantiation but no DV threshold.
- NEEDS-INFO — flag that a COA or specification is required to substantiate the stated figure.
