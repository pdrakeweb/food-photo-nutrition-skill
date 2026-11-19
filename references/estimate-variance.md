# Estimate-variance log

Records of how the council's blind estimates compare with what was finally logged, so bias corrections can be built from data instead of guessed from one meal.

## Convention

- One record per confirmed meal. Never for unconfirmed estimates.
- Variance % = (final − estimate) / estimate × 100, per item and per meal.
- Source type: `official` (the restaurant's own published nutrition) or `third-party` (e.g. Macros.menu estimate). Never present a third-party value as the restaurant's own published nutrition.
- Macro-consistency check: protein×4 + carbs×4 + fat×9 should be within ~10% of the stated calories. Flag failures in Notes.
- Correction rule (see SKILL.md): a bias adjustment may be applied only when, for one item category, n ≥ 5 records, at least 4 of 5 point the same direction, and |mean bias| > 5%. The adjustment is a stated, dated log entry — never silent, never from one meal.
- Retrospective records (backfill, Nov 18, 2026): records #2–#6 below were reconstructed from the primary records (calibration.md, council logs, dated memory files) for meals Nov 16–17, 2026. They use a compact table because no council/Judge/automatic values exist for them: Item | Category | Type | Quantity (est → final, var %) | Estimate (cal) | Final (cal) | Var % (cal). Type is `size` (amount/volume wrong) or `rate` (calorie rate/basis wrong, amount right). Quantity variance and calorie variance are recorded separately where they differ. "Estimate" is the first logged / first estimated value, stated per row. Do not invent per-item seat values for backfill records.
- A scale-reference record (#6, the Filigree bowl) is not a meal; it is logged separately because the vessel error affected more than one meal's estimates.

## Running statistics

Recomputed Nov 18, 2026 after the retrospective backfill (records #2–#6) and Record #7 (Nov 18 dinner). "Final vs first estimate" throughout; Record #1's first estimate is the Judge blind value, backfill records' first estimate is the first logged / first estimated value stated per row.

- Records: 7 meal records (#1–#5, #7, #8) + 1 scale-reference record (#6, not a meal). No correction in effect — no category has n ≥ 5 (max n=2).
- Meal-level mean variance, final vs first estimate: +15.8% (range −33.1% to +50.0%, n=7). By source type: third-party +10.3% (n=1, Record #1); Pete-confirmed / MyFitnessPal home meals +16.8% (range −33.1% to +50.0%, n=6).
- By category, final vs first estimate (calorie variance; n = item rows): wraps/sandwiches +15.4% (n=1); fries/sides +4.6% (range +1.7% to +7.4%, n=2); condiments 0.0% (n=1); fruit −62.6% (n=1); pasta/grains +4.1% (n=2, range −16.8% to +25.0%); cereal/granola +50.0% (n=1); cheese +94.6% (range −5.2% to +194.4%, n=2); sauce +142.7% (n=2, range +82.0% to +203.3%); eggs +1.6% (n=1); meat/sausage +23.5% (n=1, rate/basis error, amount unverified); vegetables +17.3% (n=1); crackers +50.0% (n=1).
- Portion-fraction errors (meal-level rows, no item category): second helping −46.4% (n=1, Record #5).
- Size errors by quantity (where recorded): granola +50.0%, grapes −62.5%, pasta +25.0%, feta +200.0%, home fries (plate 1) −26.7%, bowl brim −57.8%. Directions are mixed — no consistent under- or over-estimation direction in the size errors so far. The Nov 18 meal's +10.3% does not generalise to a systematic underestimate: meal-level mean across 5 meals is +2.4%.

## Record #1 — Nov 18, 2026 lunch, Fatheads Brewery (half Turkey Club Wrap + fries + ketchup)

Photo: `~/workspace/user/files/45927_7_kmr5.jpg`. Scale: Filigree dinner plate 10.5". Council log: `~/workspace/council_log_2026-11-18.md`. Calibration: Case 2 in `references/calibration.md`. Confidence: medium. Meal precision tag: `estimated`.

Official menu (fatheads.com, North Olmsted): Turkey Club Wrap = smoked turkey, bacon, roasted red pepper, cheddar, chopped romaine, tomato & chipotle mayo; all wraps served with a side of fries. Fatheads publishes description only — no official nutrition. Published values below are Macros.menu, third-party estimate, crawled Jan 27, 2026.

| Item | Category | Automatic | Dimensions (R2) | Portions (R2) | Photo Comparator (R2) | Judge blind | Published / third-party | Final logged | Var final vs Judge | Var final vs automatic | Var published vs Judge |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Turkey Club Wrap, 0.5 wrap | wraps/sandwiches | ~300 | meal-level only | meal-level only | meal-level only | 260 (220–300) | 300 (whole 600; 35g protein, 50g carbs, 30g fat) | 300 | +15.4% | 0.0% | +15.4% |
| French Fries, side | fries/sides | ~340 | meal-level only | meal-level only | meal-level only | 340 (250–420) | 365 (4g protein, 63g carbs, 17g fat) | 365 | +7.4% | +7.4% | +7.4% |
| Ketchup, ~2 tbsp | condiments | ~35 | meal-level only | meal-level only | meal-level only | 30 (20–40) | no entry found | 30 | 0.0% | −14.3% | n/a |
| Meal total | — | ~675 (580–800) | 625–720 central (510–850) | ~675 (615–735) | ~590 (450–725) | 630 (490–760) | 695 (300 + 365 + 30; ketchup has no published value) | 695 | +10.3% | +3.0% | +10.3% |

Notes:
- Per-item seat centrals were not recorded (seats reported meal-level only) — record meal-level seat values instead; do not invent per-item seat splits.
- Wrap identity resolved by the menu check: smoked turkey + bacon + chipotle mayo, not ham. That is the stated reason the final (300) sits at the top of the Judge range.
- Fries macros inconsistent: 4×4 + 63×4 + 17×9 = ~421 cal vs 365 stated (+15%, outside the ~10% band). Calories used (365); carbs not taken literally — final used ~50g carbs.
- Wrap macros consistent: 35×4 + 50×4 + 30×9 = 610 cal vs 600 stated (+1.7%, inside band).
- Final = Pete-confirmed values, Nov 18, 2026 ("go ahead and log it"). MyFitnessPal readback confirmed Nov 18: calories match exactly (695 cal). Logged entries were the closest database entries (no exact Fat Head's entries): Market Sandwich Turkey Club Wrap 0.5 wrap 300, French Fries 1 serving medium 365, Portland Ketchup Company Organic Ketchup 2 tbsp 30. MyFitnessPal lunch macros are 85g carbs, 30g fat, 18g protein — vs the council final 83g carbs, 32g fat, 22g protein (protein −4g, fat −2g, carbs +2g, from the closest-entry substitution, not a calorie change).

## Record #2 — Nov 16, 2026 lunch, home (RETROSPECTIVE backfill)

Source: `memory/2026-11-16.md` (food-logging section; grapes correction) and `references/saved-foods.md` (red grapes, corrected by Pete from 4 cups on the stems). No council ran on this meal; no automatic estimate recorded. Meal precision tag: `tracked` rates, portions as corrected by Pete.

| Item | Category | Type | Quantity est → final (var %) | Estimate (cal) | Final (cal) | Var % (cal) |
|---|---|---|---|---|---|---|
| Red grapes | fruit | size | 4 cups on the stem → 1.5 cups off the stem (−62.5%) | 417 (4 cups) | 156 (1.5 cups) | −62.6% |
| Meal total | — | size | — | 788 | 527 | −33.1% |

Notes:
- The error was stem vs edible volume, not a miscount of what was eaten: ~3–4 cups on the stems held only ~1.5 cups off the stems. Other lunch items unchanged (Oikos Pro vanilla yogurt 130, Cheez-It Grooves Bold Cheddar ~30 crackers 234, Coke Zero 7). Durable rule from this correction: grapes on the stem do not count, only what comes off the stem.
- Final = Pete-corrected MyFitnessPal entry (red grapes 1.5 cups = 156 cal at 104 cal/cup).

## Record #3 — Nov 16, 2026 dinner, home (RETROSPECTIVE backfill)

Source: `memory/2026-11-16.md` (food-logging section; dinner corrected) and `references/saved-foods.md` (Barilla Protein+ pasta 238 cal / 1.25 cups). No council ran on this meal. Meal total is approximate: the 1-cup pasta figure is ~190 cal (238 / 1.25).

| Item | Category | Type | Quantity est → final (var %) | Estimate (cal) | Final (cal) | Var % (cal) |
|---|---|---|---|---|---|---|
| Barilla Protein+ pasta, cooked | pasta/grains | size | 1 cup → 1.25 cups (+25.0%) | ~190 (1 cup) | 238 (1.25 cups) | +25.0% |
| Athenos crumbled feta | cheese | size | 1 tbsp → 3 tbsp (+200.0%) | 18 (1 tbsp) | 53 (3 tbsp) | +194.4% |
| Homemade cream-cheese alfredo | sauce | rate | 1/3 cup → 1/3 cup (0.0%) | ~150 (quick estimate) | 273 (1/3 cup) | +82.0% |
| Meal total | — | mixed | — | ~637 | 720 | +13.0% |

Notes:
- Feta was corrected after Pete's salad photo showed more feta than logged, and Pete agreed (1 tbsp → 3 tbsp).
- Alfredo amount (1/3 cup) was right; the calorie rate was wrong — the cream-cheese recipe is far denser than the ~150 cal quick estimate. This is a rate error, not a size error.
- Meal total first-logged ≈ 637 (pasta ~190 + alfredo 273 + garden salad 76 + dressing 80 + feta 18); final 720 (238 + 273 + 76 + 80 + 53). The +13.0% is approximate because the 1-cup pasta figure is ~190.
- Salad greens are NOT given a variance row here (see "could not verify" in the backfill handoff): the fork-scale recalculation put the salad at ~3.5 cups vs 1 cup logged, but the reference file later flags that scale as suspect and no MyFitnessPal change was made (differential ~−30 cal, within noise).

## Record #4 — Nov 17, 2026 breakfast, home (RETROSPECTIVE backfill)

Source: `memory/2026-11-17.md` (food-logging section, ~10:05–10:22 EST) — Quaker Simply Granola, Oats, Honey, Raisins & Almonds with 2% milk, photo. No council ran on this meal. Quick estimate ~300 cal was the automatic estimate for the meal.

| Item | Category | Type | Quantity est → final (var %) | Estimate (cal) | Final (cal) | Var % (cal) |
|---|---|---|---|---|---|---|
| Quaker Simply Granola | cereal/granola | size | 0.5 cup → ~0.75 cup (+50.0%) | 210 (0.5 cup) | 315 (0.75 cup) | +50.0% |
| Meal total | — | size | — | 272 (granola 210 + milk 62) | 377 (granola 315 + milk 62) | +38.6% |

Notes:
- Pete corrected the amount ~10:22 EST: granola was almost 3/4 cup, not 1/2 cup. Milk (0.5 cup 2%, 62 cal) unchanged. Final vs the ~300 cal quick estimate: +25.7%.
- Final = Pete-corrected MyFitnessPal entry (0.75 cup = 1.5 servings = 315 cal at 420 cal/cup), confirmed in the diary.

## Record #5 — Nov 17, 2026 dinner, home (RETROSPECTIVE backfill)

Source: `references/calibration.md` Case 1; `~/council_log_2026-11-17.md` (council verdict, confidence LOW); `memory/2026-11-17.md` (Judge verdict, medium-low). Council + Judge ran on this meal; the Judge's figures are the final logged values.

| Item | Category | Type | Quantity est → final (var %) | Estimate (cal) | Final (cal) | Var % (cal) |
|---|---|---|---|---|---|---|
| Scrambled eggs, plate 1 | eggs | size | 2 large → 2 large (0.0%) | 182 | 185 | +1.6% |
| Cheddar cheese, plate 1 | cheese | size | 1 oz → 1 oz (0.0%) | 116 | 110 | −5.2% |
| Home fries, plate 1 | fries/sides | size | 1.5 cups → ~1.1 cups (−26.7%) | 236 (1.5 cups at 157 cal/cup) | 240 (~1.1 cups at ~215 cal/cup) | +1.7% |
| Turkey sausage, plate 1 | meat/sausage | rate | 3 oz → 3 oz (0.0%; amount is Pete's unweighed guess, kept) | 132 (raw basis) | 163 (Jimmy Dean Fully Cooked patties, MyFitnessPal) | +23.5% |
| Second helping (plate 2, whole) | — | size (fraction) | ~2/3 of a full repeat plate → whole small helping as served (fraction basis not comparable) | 474 | 254 | −46.4% |
| Meal total | — | mixed | — | 1,140 (666 + 474) | 949 | −16.8% |

Notes:
- Second helping, step by step: first logged 474 cal as ~2/3 of a full repeat plate; Pete corrected it to the whole small helping as served, 225 cal (eggs 0.7, cheddar 0.3 oz, home fries 0.33 cup, sausage 1 oz, shredded cheddar 0.25 oz); the Judge then revised plate 2 to 254 cal (eggs 65, cheddar 60, home fries 75, sausage 54). Final vs Pete-corrected 225: +12.9%.
- Home fries plate 1 is the two-errors-cancel case: volume was overestimated (−26.7%) while the rate was underestimated (157 vs ~215 cal/cup, +36.9%), so calories barely moved (+1.7%). The council central implied ~1.2 cups; the Judge settled ~1.1 cups. Plate 2 home fries: 0.33 cup at 157 (52 cal) → 0.35 cup at 217 Ginnie's (75 cal).
- Sausage: the 3 oz amount was never verified — Pete's unweighed guess, kept per his instruction. The error is rate/basis only: raw 44 cal/oz logged vs Jimmy Dean Fully Cooked 54 cal/oz (label: 130 cal per 3 links / 68 g / 2.4 oz). Judge proper figure 160 cal; MyFitnessPal patties entry 163 cal is what was logged.
- Meal total, step by step: first logged 1,140 → Pete-corrected 891 → Judge-final 949. Final vs Pete-corrected: +6.5%. Council verdict was 988 cal, +4.1% vs the Judge-final 949.
- Final = Judge figures applied to MyFitnessPal Nov 17, 19:40–19:45 EST (dinner 949 cal, day 2,271 cal, 139 cal remaining vs 2,410 goal).

## Record #6 — Filigree cereal/salad bowl capacity (RETROSPECTIVE backfill, scale reference — not a meal)

Source: `~/workspace/user/reference/flight-silverware-plates.md` (§ "The salad/cereal bowl") and `memory/2026-11-16.md` (22:23 cross-check; correction the same evening). No calories — this is a vessel-size error that affected later food estimates.

| Measure | Estimate (first) | Corrected (final) | Var % |
|---|---|---|---|
| Bowl rim diameter | ~7.5" (fork-scale photo measurement) | 6" (standard Filigree soup/cereal bowl, Pete's direct observation) | −20.0% |
| Bowl brim volume | ~45 oz (8 3/4" Individual Salad Bowl match) | ~19 oz (~2.4 cups to the brim) | −57.8% |
| Bowl practical volume | ~4 cups / ~33 oz (geometric estimate from the 8 3/4" match) | Basis mismatch — the corrected figure is a brim volume (2.4 cups), not a practical volume; no % computed | n/a |

Notes:
- Timeline: Nov 16, 22:23 EST the bowl was identified as the 8 3/4" Individual Salad Bowl (~4 cups practical, ~45 oz brim), with a pasta cross-check (~1.6 cups filling it ~2/3 → ~3–3.5 cups total) taken as consistent. Later the same evening Pete rejected it ("No way those hold 4 cups, not even close") and corrected it from his own fill: ~1.6 cups (1.25 cups pasta + 1/3 cup sauce) at ~2/3 full → ~2.4 cups (~19 oz) to the brim. The 45 oz brim / ~33 oz practical estimate is withdrawn. Pete confirmed: "Yeah, that sounds about right." A tape measure across the rim would settle it definitively (6" = standard, 6 5/8" = Super soup/cereal bowl).
- Meals affected: Nov 16 dinner (the pasta fill was the cross-check that first seemed to confirm the wrong size) and the Nov 16 salad volume estimate (~3.5 cups, which used the same overstated fork scale and was later flagged suspect in the reference file).
- The skill's scale reference now uses ~2.4 cups to the brim for this bowl.

## Record #7 — Nov 18, 2026 dinner, home (Barilla Protein+ penne + alfredo + green beans)

Photo: `workspace/user/files/45940_12_wz4f.jpg`. Scale: Filigree dinner plate 10.5", Flight fork 7 3/8". Council log: `~/workspace/council_log_2026-11-18.md`. Confidence: medium. Meal precision tag: `mixed`.

No Judge — gate not met (seats converged). No published/third-party value — home meal; saved-food rates used.

| Item | Category | Automatic | Dimensions (R2) | Portions (R2) | Photo Comparator (R2) | Judge blind | Published / third-party | Final logged | Var final vs Judge | Var final vs automatic | Var published vs Judge |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Penne, Barilla Protein+, 1.75 cups | pasta/grains | ~400 | 338 | 390 | not recorded per-item | none | none | 333 | n/a | −16.8% | n/a |
| Alfredo sauce, 2/3 cup | sauce | ~180 | 150 | 155 | not recorded per-item | none | none | 546 | n/a | +203.3% | n/a |
| Green beans with butter, 1.25 cups | vegetables | ~75 | 115 | 110 | not recorded per-item | none | none | 88 | n/a | +17.3% | n/a |
| Meal total | — | ~650 (550–800) | ~600 (485–860) | ~655 (555–850) | ~665 (555–850) | none | none | 967 | n/a | +48.8% | n/a |

Notes:
- Variance final vs council synthesis (640 cal): penne −10.0%, sauce +252.3%, beans −20.0%, meal +51.1%.
- The sauce variance is driven by Pete's corrections (identity unknown white sauce → alfredo; volume 1/3 → 2/3 cup), not estimator error on a fixed basis.
- Penne: Pete confirmed Barilla Protein+ and "a little less" than 2 cups; logged 1.75 cups at the tracked 190 cal/cup.
- Beans: closest cup-based buttered entry (Birds Eye, 70 cal/cup) vs ~73 target, so 88 vs 90 target.
- MyFitnessPal dinner macros 81g carbs, 64g fat, 33g protein; macro-consistency 33×4 + 81×4 + 64×9 = 1,032 vs 967 stated (+6.7%, inside the ~10% band).
- Final = Pete-confirmed values, Nov 18, 2026 ("Log it"), MyFitnessPal readback: penne 333, sauce 546, beans 88, meal 967.

## Record #8 — Nov 18, 2026 snack, home (Cheez-It Grooves Sharp White Cheddar, 25 crackers)

Text-only report, no photo. Council log: `~/workspace/council_log_2026-11-18.md` (pre-logging verdict 21:29; post-logging validation same file). Confidence: medium. Meal precision tag: `estimated`.

No Judge in the validation council — gate not met (seats converged, no material disagreement). The Judge blind value below is from the pre-logging council (21:29).

| Item | Category | Automatic | Dimensions (R2) | Portions (R2) | Photo Comparator (R2) | Judge blind | Published / third-party | Final logged | Var final vs Judge | Var final vs automatic | Var published vs Judge |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Cheez-It Grooves Sharp White Cheddar, 25 crackers | crackers | ~130 | ~195 | ~194 | ~194 | ~194 (190–200) | ~194 (label 140 cal per 18 crackers / 29 g, scaled ×25/18; cheezit.com, official, Nov 2026) | 195 | +0.5% | +50.0% | 0.0% |
| Meal total | — | ~130 | ~195 | ~194 | ~194 | ~194 (190–200) | ~194 | 195 | +0.5% | +50.0% | 0.0% |

Notes:
- The automatic estimate (~130) was wrong on the serving basis: it took the label as 140 cal per 27 crackers (30 g) — that serving belongs to Cheez-It Original, not Grooves. Grooves serving is 18 crackers (29 g) = 140 cal. The Nov 16 Bold Cheddar MFP entry (234 cal / 30 crackers) was correct per label all along; the Nov 16 automatic estimate (160) was the error — the same serving-basis mistake, a day earlier.
- Validation council (post-logging) confirmed: all three seats CONFIRM, positions unchanged in round 2. Logged 195 vs label-scaled ~194 (+0.5%); meal total +0.5% vs the ~194 verdict.
- Sugar: MFP shows 0 g vs ~2.8 g scaled from the current label (2 g per 18 crackers). Database data-quality note, not a material error: ~2.8 g sugars ≈ 11 kcal, inside the 26 g carbs. The non-Grooves wrong-product inference (0 g sugar matches the non-Grooves White Cheddar profile) is refuted by the calories: a non-Grooves profile would log ~150 cal for 25 crackers, not 195; fat (8 g vs ~8.3 g) and sodium (334 mg vs ~333 mg) also track Grooves. Sugars figure is contested across sources (1 g Mar 2025 label capture, 2 g current label, 3 g stale Jul 2018 USDA record).
- Carbs: MFP 26 g vs 27.8 g scaled (−6.5%). Macro-consistency: 3×4 + 26×4 + 8×9 = 188 vs 195 stated (+3.7%, inside the ~10% band).
- Count stated by Pete (25 crackers), not weighed — the estimate is conditional on the count at ~7.8 cal per cracker. Open NEEDs (weighed mass, photo, physical box label) would change the verdict only if they showed a different product or count.
- Final = Pete-reported values logged directly (log-without-asking rule, Nov 18, 2026), MyFitnessPal readback: "Kellogg's Cheez It - Cheez It Grooves Sharp White Cheddar, 25.02 Cracker Chips (29 g)", 1.39 servings, 195 cal; Snacks subtotal 195; day 2,248 cal, 162 remaining vs 2,410 goal.
