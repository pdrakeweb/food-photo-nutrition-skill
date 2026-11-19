# Calibration cases

Meals where the estimates can be checked against what Pete later confirmed or measured. Each case records what was estimated and what turned out to be true, so the three approaches can be refined over time. Add a new case for every meal with measured or known quantities, and note which approach was closest.

## Case 1 — Nov 17, 2026 dinner (scrambled eggs, cheddar, home fries, turkey sausage)

Photos: `~/workspace/user/files/45913_5_ftky.jpg` (first plate) and `~/workspace/user/files/45914_6_yj6y.jpg` (second helping). Scale: Filigree dinner plate 10.5 inches, Flight dinner fork 7 3/8 inches. Day context: breakfast 697 cal, lunch 625 cal, daily goal 2,410 cal.

### Precision tags

- Meal tag: `mixed`. The sausage rate (54 kcal/oz, label-verified) and the home-fries rate (217 kcal/cup, MyFitnessPal entry) are `tracked` in the final figures; the egg and cheddar rates are `tracked` (USDA / MyFitnessPal); every portion volume was `estimated` from the photos, never weighed.
- As first logged, the whole meal was `estimated`: eggs, cheddar, home fries (generic 157 kcal/cup rate), and sausage (raw basis) were all photo estimates.
- Final per-item tags: eggs `tracked` rate / `estimated` portion; cheddar `tracked` rate / `estimated` portion; home fries `tracked` (Ginnie's entry); sausage `tracked` (label-verified rate).

### What was estimated (automatic approach, then logged to MyFitnessPal)

- First plate 666 cal: scrambled eggs 2 large 182, cheddar cheese 1 oz 116, home fries 1.5 cup 236, turkey sausage raw 3 oz 132.
- Second helping first logged 474 cal as about two-thirds of the first plate plus a shredded cheddar sprinkle. That fraction was wrong.
- The 3 oz sausage figure was a photo estimate, never a weighed amount, and it was logged as if it were measured. That was the error Pete called out.

### What Pete confirmed

- The cubes are turkey sausage, not steak. The plate is dinner-plate size.
- The second plate WAS the whole small helping as served, not two-thirds of a full repeat.
- The sausage is precooked turkey sausage, probably Jimmy Dean or similar, NOT raw. Pete did not eat the whole hash and does not know the total amount cooked. Keep the 3 oz as a guess.
- Corrected second helping 225 cal: eggs 0.7 large 64, cheddar 0.3 oz 35, home fries 0.33 cup 52, turkey sausage raw 1 oz 44, shredded cheddar 0.25 oz 30. Corrected dinner 891 cal, day 2,213 cal, 197 cal remaining.

### Council verdict (confidence LOW)

- Dinner 988 cal (range 841 to 1,183), day about 2,310 cal. First plate 725 (eggs 185, cheddar 110, home fries 280, sausage 150). Second helping 263 (eggs 65, cheddar 60, home fries 78, sausage 60).
- Main driver: the home-fries rate. Logged at 157 kcal per cup from the generic MyFitnessPal entry. The council supported 220 to 250 kcal per cup for pan-fried home fries.
- The council used the raw sausage basis (49 kcal per oz) because the raw-versus-cooked question was still open. That basis was wrong.

### Sausage swap in MyFitnessPal (19:35 EST Nov 17)

- Raw entries deleted: 3 oz 132 plus 1 oz 44, total 176 cal.
- Added Jimmy Dean Fully Cooked Turkey Sausage Patties: 3 oz 163 plus 1 oz 54, total 217 cal. Dinner 932 cal, day 2,254 cal, 156 cal remaining.

### Judge verdict (confidence medium-low)

- Proper dinner 949 cal (range 800 to 1,110), day 2,271 cal (range 2,132 to 2,442), about 139 cal under goal. First plate 695 (eggs 185, cheddar 110, home fries 240, sausage 160). Second helping 254 (eggs 65, cheddar 60, home fries 75, sausage 54).
- Against current MyFitnessPal (932 cal): plus 17 cal. Against the council (988 cal): minus 39 cal, almost all home fries. The Judge puts the first plate at about 1.1 cups of home fries (not 1.5) at about 215 kcal per cup.
- Sausage verified: Jimmy Dean Fully Cooked links are 130 cal per 3 links (68 g, 2.4 oz), which is 54 kcal per oz. Proper figures are 3 oz 160 cal and 1 oz 54 cal. The MyFitnessPal patties entry (163 and 54) is 3 cal high on the first plate and exact on the second.
- Judge limitation: the council log file was not found on disk at the workspace path the Judge looked for, so the Judge adjudicated from the verdict summary only. The log did exist at `~/council_log_2026-11-17.md`, in the home directory rather than the workspace. The skill now pins the log path.
- Judge figures applied to MyFitnessPal 19:40–19:45 EST Nov 17: dinner 949 cal, day 2,271 cal, 139 cal remaining. The home-fries entries now use the Ginnie's Home Made entry (217 cal/cup), 1.1 cup on plate 1 and 0.35 cup on plate 2.

### Lessons from this case

- Never log a photo estimate as a weighed amount. The 3 oz sausage was a guess and should have been labelled one from the start.
- Ask raw versus cooked and brand before logging meat. The raw-versus-cooked basis moves sausage by about 10 kcal per oz and was the largest avoidable error after home fries.
- Confirm whether a second helping is the whole serving as plated or a fraction of a full plate. The two-thirds assumption overstated the second helping by 249 cal.
- The generic MyFitnessPal home-fries entry (157 kcal per cup) understates pan-fried home fries. Council research supports 220 to 250 kcal per cup. The Judge settled near 215 kcal per cup with a smaller volume.
- Save every council log to the pinned workspace path so the Judge can read the full record.

### Reference values established by this case

- Scrambled egg: about 91 kcal per egg (USDA).
- Cheddar cheese: 113 to 114 kcal per oz (USDA FDC 173414).
- Home fries, pan-fried: 220 to 250 kcal per cup (council research), Judge about 215 kcal per cup. Generic MyFitnessPal entry 157 kcal per cup is low.
- Turkey sausage, raw: 49 kcal per oz (USDA FDC 174600). Cooked generic: 55 to 56 kcal per oz.
- Jimmy Dean Fully Cooked turkey sausage links: 130 cal per 3 links (68 g, 2.4 oz), 54 kcal per oz. Label values beat the generic entry.

### Variance record

- Record #5 in `references/estimate-variance.md` (retrospective backfill, Nov 18, 2026): meal −16.8% final vs first logged; second helping −46.4%; home fries plate 1 quantity −26.7% but calories +1.7% (volume and rate errors cancelled); sausage +23.5% (rate/basis, amount unverified).

## Backfill pointers — Nov 16 meals and Nov 17 breakfast (no full case written)

Numbers live in `references/estimate-variance.md`; the stories live in the dated memory files. No full calibration case was written for these meals — the pointers below are the cross-reference, not a duplicate narrative.

- Nov 16 lunch (grapes): variance Record #2 — grapes 4 cups on the stem / 417 cal → 1.5 cups off the stem / 156 cal (−62.6%); meal 788 → 527 cal (−33.1%). Source: `memory/2026-11-16.md` food-logging section.
- Nov 16 dinner (pasta, feta, alfredo): variance Record #3 — pasta 1 → 1.25 cups (+25.0%); feta 1 → 3 tbsp (+194.4%); alfredo rate ~150 → 273 cal (+82.0%, rate error); meal ~637 → 720 cal (+13.0%, approximate). Source: `memory/2026-11-16.md` food-logging section.
- Nov 17 breakfast (granola): variance Record #4 — granola 0.5 → ~0.75 cup (+50.0%); meal 272 → 377 cal (+38.6%). Source: `memory/2026-11-17.md` food-logging section.
- Filigree bowl capacity: variance Record #6 (scale reference, not a meal) — brim ~45 oz → ~19 oz (−57.8%). Source: `~/workspace/user/reference/flight-silverware-plates.md`.

## Case 2 — Nov 18, 2026 lunch (Fat Head's half Turkey Club Wrap + fries + ketchup)

Photo: `~/workspace/user/files/45927_7_kmr5.jpg`. Scale: Filigree dinner plate 10.5 inches. Day context: breakfast 391 cal, daily goal 2,410 cal. Council log: `~/workspace/council_log_2026-11-18.md`. Variance record: #1 in `references/estimate-variance.md`.

### Precision tags

- Meal tag: `estimated`. Nothing was weighed or measured; the wrap and fries values are third-party estimates Pete confirmed for logging (see below), not label-verified.
- Per-item tags: wrap `third-party` (Macros.menu estimate, Pete-confirmed); fries `third-party` (same source; macros inconsistent, see below); ketchup `estimated`.

### What was estimated

- Automatic approach (before council): wrap ~300, fries ~340, ketchup ~35, meal ~675 cal (580–800).
- Council, 2 rounds: Dimensions R2 meal 625–720 central (range 510–850); Portions R2 meal ~675 (615–735); Photo Comparator R2 meal ~590 (450–725). Material disagreements: fry cooking method (seasoned ~180 vs restaurant ~300 kcal/100g) and hidden-layer fry weight.
- Judge verdict (blind, confidence medium): wrap 260 (220–300), fries 340 (250–420), ketchup 30 (20–40), meal ~630 cal (490–760). Macros protein ~17g, carbs ~80g, fat ~29g, sugar ~10g.

### Menu check (after the council, per Pete's clarification)

- Pete clarified: half turkey club wrap and fries from Fatheads Brewery. Checked only after the council numbers were set.
- Official menu (fatheads.com, North Olmsted): Turkey Club Wrap = smoked turkey, bacon, roasted red pepper, cheddar, chopped romaine, tomato & chipotle mayo; all wraps served with a side of fries. Fatheads publishes description only — no official nutrition.
- Macros.menu (third-party, crawled Jan 27, 2026): whole Turkey Club Wrap 600 cal (35g protein, 50g carbs, 30g fat), half = 300 cal; French Fries 365 cal (4g protein, 63g carbs, 17g fat).
- Revisions, with reasons: wrap 260 → 300 cal (+40, top of Judge range) — the menu resolves the meat identity (smoked turkey + bacon, not ham) and the sauce (chipotle mayo). Fries 340 → 365 cal (+25, within Judge range). Ketchup unchanged at 30 cal.
- Fries macros inconsistent: 4×4 + 63×4 + 17×9 = ~421 cal vs 365 stated (+15%). Calories used (365); carbs not taken literally — final used ~50g carbs. Wrap macros consistent (610 vs 600, +1.7%).

### What Pete confirmed

- Final: wrap 300, fries 365, ketchup 30, meal 695 cal. Macros protein ~22g, carbs ~83g, fat ~32g, sugar ~10g. Day total 391 + 695 = 1,086 cal, 1,324 remaining vs 2,410 goal.
- Pete said "go ahead and log it" — logged to MyFitnessPal the same day. Readback confirmed: calories match exactly (695 cal, day 1,086, 1,324 remaining). Logged entries were the closest database entries (no exact Fat Head's entries): Market Sandwich Turkey Club Wrap 0.5 wrap 300, French Fries 1 serving medium 365, Portland Ketchup Company Organic Ketchup 2 tbsp 30. MyFitnessPal lunch macros are 85g carbs, 30g fat, 18g protein — vs the council final 83g carbs, 32g fat, 22g protein (protein −4g, fat −2g, carbs +2g, from the closest-entry substitution, not a calorie change).
- Variance (final vs blind Judge): meal +10.3% (+65 cal); wrap +15.4%; fries +7.4%; ketchup 0%. Final vs automatic estimate: meal +3.0%. Recorded as variance record #1; n=1, no correction in effect.

### Lessons from this case

- The blind council was low on both main items but inside its own ranges — wrap at the top of its range, fries in the middle. A single +10% meal gap is observation, not a correction.
- A restaurant menu description can resolve an open identity question (meat, sauce) that moves the number; that is the legitimate use of the post-council check.
- Third-party menu macros can be internally inconsistent — always run the protein×4 + carbs×4 + fat×9 check before using them.

## Case 3 — Nov 18, 2026 dinner (Barilla Protein+ penne, alfredo, green beans with butter)

Photo: `~/workspace/user/files/45940_12_wz4f.jpg`. Scale: Filigree dinner plate 10.5 inches, Flight dinner fork 7 3/8 inches. Day context: breakfast 391 cal, lunch 695 cal, daily goal 2,410 cal. Council log: `~/workspace/council_log_2026-11-18.md`. Variance record: #7 in `references/estimate-variance.md`.

### Precision tags

- Meal tag: `mixed`. The penne rate is `tracked` (saved food, MyFitnessPal-verified 190 cal/cup); the alfredo rate is `tracked` (saved food, MyFitnessPal-verified 273 cal per 1/3 cup); the beans rate is `estimated` (closest entry 70 cal/cup vs ~73 target).
- Quantities Pete-stated: penne "a little less" than 2 cups, estimated at 1.75 cups; sauce 2/3 cup and beans 1.25 cups as Pete stated.

### What was estimated

- Automatic approach (before council): penne ~400, sauce ~180, beans ~75, meal ~650 cal (550–800). The sauce was an unknown white sauce, estimated at ~1/3 cup.
- Council, 2 rounds, no Judge (gate not met — seats converged): Dimensions R2 meal ~600 (485–860); Portions R2 meal ~655 (555–850); Photo Comparator R2 meal ~665 (555–850). Council synthesis: meal ~640 cal (555–850), confidence medium. Per-item synthesis: penne ~370, sauce ~155, beans ~110.

### Pete's corrections

- Penne is a little less than 2 cups, and it is Barilla Protein+ pasta.
- The sauce is alfredo, more like 2/3 cup — not the ~1/3 cup of unknown white sauce in the estimate.
- Green beans 1.25 cups.
- Revised before logging: penne 1.75 cups 333, alfredo 2/3 cup 546, beans 1.25 cups 90, meal ~969 cal.

### Logged (MyFitnessPal readback)

- "Steffin Barilla - Cooked Protein Plus Pasta 03.17.17", 1.75 cups, 333 cal.
- "Homemade - Alfredo Sauce With Cream Cheese", 0.67 cup, 546 cal (verified 410 cal per 0.5 cup before adding; found via database search, not My Foods).
- "Birds Eye - Butter Sauced Green Beans", 1.25 cups, 88 cal.
- Dinner 967 cal (81g carbs, 64g fat, 33g protein); day 2,053 cal, 357 remaining vs 2,410 goal.
- Two earlier alfredo attempts (549 and 547 cal) were deleted and the exact 546-cal entry kept.

### Lessons from this case

- The success-check gap: the browser logged only the pasta first and Pete caught the missing entries live. The skill's new logging success check exists because of this meal — a partial log must be caught by the skill's own flow, not by Pete.
- Sauce identity plus volume dominate: 1/3 cup of an unknown white sauce at ~155 vs 2/3 cup alfredo at 546 is a ~390 cal swing. Confirm sauce identity and volume before finalizing.
- Do not infer cooked protein from the dry-basis label: my rough macro guess was ~45g protein vs MyFitnessPal's 33g. Use the logged entry's macros.

### Reference values established by this case

- Barilla Protein+ cooked penne: 190 cal/cup (MyFitnessPal-verified Nov 18, 144 g/cup).
- Homemade cream-cheese alfredo: 273 cal per 1/3 cup (MyFitnessPal-verified Nov 18, 410 cal per 0.5 cup).
- Birds Eye Butter Sauced Green Beans: 70 cal/cup (closest cup-based buttered beans entry, Nov 18).

### Variance record

- Record #7 in `references/estimate-variance.md`: meal +48.8% final vs automatic (penne −16.8%, sauce +203.3%, beans +17.3%); meal +51.1% final vs council synthesis (640 cal). The sauce variance is driven by Pete's corrections, not estimator error on a fixed basis.

## Case 4 — Nov 18, 2026 snack (Cheez-It Grooves Sharp White Cheddar, 25 crackers)

Text-only report, no photo. Day context: breakfast 391 cal, lunch 695 cal, dinner 967 cal, daily goal 2,410 cal. Council log: `~/workspace/council_log_2026-11-18.md` (pre-logging verdict 21:29; post-logging validation same file). Variance record: #8 in `references/estimate-variance.md`.

### Precision tags

- Meal tag: `estimated`. Count stated by Pete (25 crackers), not weighed; no saved-food match for this flavor (the Bold Cheddar entry does not transfer).
- The logged calorie rate is label-verified (140 cal per 18 crackers / 29 g); the portion is `estimated` (counted, not weighed). The sugar field (0 g) is a database gap, not a verified value.

### What was estimated

- Automatic approach (quick estimate to Pete): ~130 cal — wrong serving basis (140 cal per 27 crackers / 30 g, which is Cheez-It Original, not Grooves).
- Council, 2 rounds + Judge: ~194 cal (190–200), fat ~8.3 g, carbs ~27.8 g, protein ~2.8 g, sugar ~2.8 g (1.4–4.2 g, contested). Confidence medium.
- Proposed entry: 25 crackers, 1.39 servings of the 18-cracker / 140 cal entry, ~194 cal.

### Logged (MyFitnessPal readback)

- "Kellogg's Cheez It - Cheez It Grooves Sharp White Cheddar, 25.02 Cracker Chips (29 g)", 1.39 servings, 195 cal (26 g carbs, 8 g fat, 3 g protein, 0 g sugar, 334 mg sodium).
- Snacks subtotal 195; day 2,248 cal, 162 remaining vs 2,410 goal. Breakfast, lunch, dinner untouched.
- Logged directly under Pete's Nov 18 log-without-asking rule (he reported nutrition without explicitly asking for an estimate); exact-flavor entry found, no closest-entry substitution.

### Post-logging validation

- Validation council (research + 3 seats, 2 rounds, no Judge — gate not met): all three seats CONFIRM, positions unchanged in round 2. Logged 195 vs label-scaled ~194 (+0.5%). Confidence medium.
- Sugar: MFP 0 g vs ~2.8 g scaled — database data-quality note, not a material error (~11 kcal). Wrong-product inference refuted: non-Grooves White Cheddar would be ~150 cal for 25 crackers, not 195; fat and sodium track Grooves.
- Carbs 26 g vs 27.8 g scaled (−6.5%). Macro-consistency 188 vs 195 (+3.7%, inside band).

### Lessons from this case

- Grooves serving is 18 crackers / 29 g = 140 cal — NOT 27 crackers / 30 g. The 27-cracker serving belongs to Cheez-It Original. Check the serving basis for the exact product before estimating packaged crackers; the flavor and the product line both matter.
- The Nov 16 Bold Cheddar MFP entry (234 cal / 30 crackers) was correct per label all along; the Nov 16 automatic estimate (160) was the error — the same serving-basis mistake, a day earlier. One wrong premise repeated across two days.
- A 0 g sugar field in a MyFitnessPal entry is not evidence of a wrong product when calories, fat, carbs, protein, and sodium all track the label — check the calorie-bearing fields first; sugar is a sub-component of carbs and cannot move the calorie verdict by more than ~11 kcal here.
- The sugars figure for this product is contested across sources (1 g / 2 g / 3 g) and has changed over time; the current manufacturer label (2 g) is the authority, and the physical box in hand outranks all of them.

### Reference values established by this case

- Cheez-It Grooves (both flavors): 140 cal per 18 crackers (29 g), ~7.8 cal per cracker; 6 g fat, 20 g carbs, 2 g protein, 2 g total sugars, 240 mg sodium per serving (current label, cheezit.com, Nov 2026).
- Sharp White Cheddar sodium 240 mg per serving vs Bold Cheddar 270 mg — the flavors differ mainly on sodium.
- Non-Grooves Cheez-It White Cheddar: 150 cal per 25 crackers (30 g), 0 g sugars — different product, different serving; do not confuse with Grooves.

### Variance record

- Record #8 in `references/estimate-variance.md`: final vs automatic +50.0% (195 vs ~130); final vs Judge +0.5% (195 vs ~194); meal +50.0% vs the automatic estimate, +0.5% vs the council verdict.
