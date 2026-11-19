# Food photo nutrition

## When to use this skill

- This skill is the default for ALL nutrition recording — any time food is recorded, whatever the input: a food photo, a text-only food report, or a nutrition-label photo. Do not record nutrition without it. Do not answer a food report with a bare estimate when this skill applies.

- This skill depends on the council skill at `~/workspace/custom-skills/council/SKILL.md`. Read that skill in full before the council step.

## Input modes

- Plated meal photo: the default. Estimate each item on the plate, using the tableware as scale, then run the council as below.

- Text-only food report: Pete states the food and quantities in words, with no photo. Use his stated quantities in place of the photo-estimation step — no photo sizing is needed. The rest of the flow is unchanged: quick estimate, his confirmation, logging with the success check, post-logging validation. For validation of a text-only report, the Portions Estimator carries the check (reference values against Pete's stated quantities); the Dimensions Estimator checks the stated quantities for volume/weight plausibility; the Photo Comparator has no photo to match and says so.

- Nutrition label photo: when Pete photographs a nutrition label instead of a plated meal, read the label's values (calories, macros, serving size) by vision/OCR and use them as `tracked` data instead of estimating. Label values count as tracked only when the label is legible and the serving size is visible. If any value is unreadable, say which one and fall back to estimating only that value (tagged `estimated`). Never invent a label value.

## The default flow

Effort order, every meal: (a) quick report to Pete first — his standing rule is a quick calorie estimate first, then correction after MyFitnessPal confirms the real numbers; (b) log with moderate effort — single-pass browser logging plus the success check; (c) validate after with high effort when a trigger applies (see "Post-logging validation") — the full council against the logged facts, and correct if needed.

- Check `references/saved-foods.md` first. If an item on the plate matches a saved food by item, brand, and preparation, use the saved values with the tag the entry carries (`tracked`, or `third-party` where the entry carries that tag — never relabel a third-party value as tracked). If it does not match, estimate fresh and, once the value is verified in MyFitnessPal, add or update the saved entry.

- Run the automatic approach next. Give your normal in-model estimate of each item on the plate, with calories and macros (protein, carbs, fat, sugar) where you can determine them, using the tableware as scale. For a text-only report, estimate from Pete's stated quantities instead of the photo. Report the quick estimate to Pete first.

- Treat the automatic estimate as the input to the council, not the final answer. The council checks and revises it.

- Run the council next with the custom panel in `references/seats.md`, 2 rounds, research on. Give the council the automatic estimate, the photos, the tableware reference, and any facts Pete stated.

- Send the council findings to a Judge only when the council confidence is low, the approaches disagree materially, or Pete asks. Give the Judge the brief and every round of the debate and nothing else from the session. The Judge rules with the proper values.

- Restaurant check (macros.menu) next, for named-restaurant meals only — after the council, never before. See "Restaurant check — macros.menu" below.

- Before logging anything to MyFitnessPal, show Pete the proposed entries (food, quantity, calories) and get his confirmation or corrections. Log exactly what he confirmed, nothing he has not seen.

- Log the confirmed entries, then run the logging success check (see "Logging success check"). Never report logging as complete until the readback confirms every entry.

- After the success check confirms the entries, run post-logging validation when a trigger applies (see "Post-logging validation"). Correct any material error found, then re-run the success check.

- After the success check confirms the entries (and after any validation correction is applied and re-verified), append a variance record to `references/estimate-variance.md` (see "Estimate-variance log and correction rule") and a calibration entry to `references/calibration.md`. Never for unconfirmed estimates.

- Report the final numbers first, then the ranges and the confidence. Keep narrative to a minimum.

## Restaurant check — macros.menu (after the council, never before)

- When the meal is from a named restaurant, run this check after the council calculation and Judge (if any), and before showing Pete the proposed entries. Never before the council — an early published number anchors the seats.
- Check two sources:
  - The restaurant's official menu (e.g. fatheads.com) for the item description and serving. This is the authoritative description (ingredients, what comes with it). It usually carries no nutrition — record that when true.
  - macros.menu for that restaurant + exact item, for calories and macros.
- Record source type for every value. Never present a Macros.menu value as the restaurant's own published nutrition:
  - `official` — the restaurant's own published nutrition (rare; Fatheads publishes description only).
  - `third-party` — Macros.menu or similar estimate. Default for Macros.menu.
- Macro-consistency check: protein×4 + carbs×4 + fat×9 should be within ~10% of the stated calories. Flag any value outside that band, state which figure was used and why. Example (Nov 18): Macros.menu fries 4g protein + 63g carbs + 17g fat = ~421 cal vs 365 stated (+15%) — inconsistent; calories used, carbs not taken literally.
- Use it as a check, not a replacement. Report council blind vs Macros.menu side by side (see Output), note the delta, and revise the final only with a stated reason — e.g. it resolves an open identity question (smoked turkey + bacon + chipotle mayo), or it sits at/inside the council range. If it contradicts the council range materially, say so and keep the council range visible.
- If no Macros.menu entry exists, record "no entry found" — absence is a finding. Do not substitute a generic entry and call it the restaurant's value.

## Estimate-variance log and correction rule

- After the success check confirms the entries (and after any post-logging validation correction is applied and re-verified), append one record per meal to `references/estimate-variance.md`. Never for unconfirmed estimates. Schema per item: date, meal, item, category, restaurant/home, automatic estimate, each seat central + range, Judge blind estimate + range, published/third-party value + source + source type + date, final logged value, variance % (final vs Judge, final vs automatic, published vs Judge), confidence, precision tag, notes.
- Variance % convention: (final − estimate) / estimate × 100. State it in the log header.
- Running statistics: recompute when a record is added — count, mean variance % and range, split by item category and by source type. With n=1 there is no correction; the log is observation only.
- Correction rule: a bias adjustment may be applied only when, for one item category, n ≥ 5 records, at least 4 of 5 point the same direction, and |mean bias| > 5%. Then the adjustment is a stated, dated entry in the log (category, size, basis, records used) — never silent, never from one meal. Re-examine after 5 more records in that category, or sooner if a new record is >20% off or the category mean flips sign.
- Current state: 6 meal records (#1–#5, #7) + 1 scale-reference record (#6). Meal-level mean variance +10.1% (n=6). No correction in effect — no category has n ≥ 5 (max n=2).

## Precision tags

Tag every logged meal, and each item where it differs, with one of:

- `tracked` — measured or weighed quantities, or values verified against MyFitnessPal or a label.
- `estimated` — photo estimates, never measured.
- `mixed` — a meal combining tracked and estimated items.
- `third-party` — item-level provenance in saved-foods and the variance log only: value from a named third-party estimate (e.g. Macros.menu) that Pete confirmed for logging. Not label-verified, not a weighed measurement. A meal whose items are third-party still carries the meal tag `estimated` unless a measured/tracked item is in it.

The tag appears in the meal report to Pete and in calibration log entries. It labels the provenance of the numbers; it does not change them.

## Scale reference

- Use `~/workspace/user/reference/flight-silverware-plates.md` as the scale for every photo.

- The Filigree dinner plate is 10.5 inches across. The Flight dinner fork is 7 3/8 inches long. The cereal bowl holds about 2.4 cups to the brim.

- Do not guess plate or bowl size from the photo alone. Measure against a visible piece of tableware.

## Hard rules

- Never present a photo estimate as a weighed or measured amount. Label every quantity as estimate or measured.

- Never invent a weight. If the amount is unknown, say so and keep the estimate visibly marked as a guess.

- Ask Pete, or check the record, for raw versus cooked, brand or product, and cooking fat or oil. These three decide the calorie basis and are the most common source of error.

- Give the quick estimate first, show Pete the proposed MyFitnessPal entries and get his confirmation or corrections, then log exactly what he confirmed through the browser with the saved login (account pdrake2300), run the logging success check before reporting logging complete, then run post-logging validation when a trigger applies and correct any material error found.

- Do not log anything to MyFitnessPal that Pete has not seen and confirmed.

- Record each meal in `references/calibration.md` with its precision tag and with what was estimated and what was later measured or confirmed, so future meals refine the approaches. Append a variance record to `references/estimate-variance.md` once the success check confirms the entries (and any validation correction is applied and re-verified).

- Never present a Macros.menu value as the restaurant's own published nutrition. Label its source type (`official` vs `third-party`) every time.

## Logging to MyFitnessPal (website)

No MyFitnessPal API or connector exists for writing diary entries. Logging is through the browser, at myfitnesspal.com/food/diary, with the saved login (account pdrake2300). Grounded in the Nov 16–18 logging in this workspace:

- Open the diary for the correct date and add food under the correct meal (Breakfast / Lunch / Dinner / Snacks). Do not touch other meals.
- Search the database for each item. Check Recent / My Foods first for custom and saved foods (e.g. "Homemade - Pete's Mocha").
- Verify the database entry's calories before adding. If no exact entry exists, use the closest matching entry with the same calorie density. Example (Nov 18 breakfast): no 1/3-cup / 135-cal granola entry, so the 0.67-cup / 270-cal entry was used at 0.25 cup — same 405 cal/cup density.
- Set quantity and serving size explicitly. Quantities can default wrong: the mocha quantity defaulted to 2 and had to be set to 1. To log a fractional amount, set the serving to a whole unit and the quantity to the fraction (e.g. serving 1 cup, quantity 0.25).
- Log exactly the values Pete confirmed and nothing else. If a correction is needed later, delete the wrong entry and add the correct one. Examples (Nov 17): raw sausage entries deleted, Jimmy Dean Fully Cooked patties added; home-fries entries replaced with the Ginnie's entry at the corrected quantities. Do not leave a wrong entry in place.
- After logging, run the logging success check (see "Logging success check"): read back the diary and verify every confirmed entry is present (entry name + quantity + calories), plus the meal subtotal and the day total vs the 2,410 goal. Report the entries as MyFitnessPal shows them. The estimate is not confirmed until that readback lands.
- Unverified: exact button/label names in the diary UI beyond "Recent / My Foods" and the serving/quantity fields as observed above — do not assert UI details not in this record.

## Logging success check

Run after logging, before any completion report. This step exists because of the Nov 18, 2026 dinner: the browser logged only the pasta, and Pete — watching the diary live — caught the missing alfredo and green beans. A partial log must be caught by the skill's own flow, not by Pete.

- After logging, read back the diary for the correct date and meal and verify EVERY confirmed entry is present with matching food, quantity, and calories.
- If any entry is missing or wrong, retry it: delete the wrong entry and re-add the correct one (per "Logging to MyFitnessPal"), then re-verify. Retry limit: 2 retries per entry, then stop and report.
- Never report logging as complete until the readback confirms every entry. If verification fails after retries, report the partial state honestly to Pete: which entries are in, which are missing or wrong — never describe a partial log as done, and never assume progress.
- This applies to the browser logging flow and any future logging route.

## Post-logging validation

Run after the success check confirms the entries are in, when any of these triggers applies: the pre-logging council confidence was low; the meal is new or unusual (unfamiliar items, no saved-food match, first time logging it); the numbers seem out of normal (a meal total or an item far outside the typical range for that meal or food); or a closest-entry substitution was used in logging. This is the high-effort check: the numbers Pete sees in his diary are verified against the facts, not just against what was intended to be logged.

- Run the council with the custom panel in `references/seats.md`, 2 rounds, research on, against the LOGGED facts: the photo, Pete-stated quantities, saved-food rates, and the MyFitnessPal database values actually used. The check that matters most is whether the database entries actually used match the confirmed values — a closest-entry substitution can shift calories and macros, as in the Nov 18 lunch (MyFitnessPal macros 85g carbs / 30g fat / 18g protein vs the council final 83 / 32 / 22).
- Judge only when the council confidence is low or the approaches disagree materially, per the existing Judge gate.
- For photo meals, all three seats apply. For text-only reports, the Portions Estimator carries the validation, the Dimensions Estimator checks stated quantities for volume/weight plausibility, and the Photo Comparator has no photo to match and says so. For label photos, the label values are the check.
- Material error (thresholds approved by Pete, Nov 18, 2026): any item off by more than 100 cal or more than 15%; or the meal total off by more than 10%; or a wrong food identity (wrong item, wrong brand or preparation, raw vs cooked basis).
- If validation finds a material error: correct the MyFitnessPal entries (delete the wrong entry and re-add the correct one), re-run the success check, and report the correction to Pete with before/after numbers and the reason.
- If validation confirms the numbers: say so briefly, no extra narrative.
- Log the validation council to the pinned council log path (`~/workspace/council_log_YYYY-MM-DD.md`), same as the pre-logging council.

## Output

- Give per-item calories and macros with ranges, the meal total, the day total against the 2,410 goal, the confidence level, and the precision tag for the meal (and per item where it differs).

- For restaurant meals, include the side-by-side table: council blind vs published/third-party vs final, per item and meal total, with the delta and the reason for any revision. Label the published source and its source type.

- Name what would change the verdict. A low confidence verdict must name the specific missing information.

- Numbers first, minimal narrative. No idioms.

- State the honest limitation when the council is treated as an audit. All seats and the Judge are the same underlying model, so correlated blind spots survive the debate. Calibration against measured meals is the real check.

## Council log

- Save every council run log to `~/workspace/council_log_YYYY-MM-DD.md`, appending under the date header. Use this exact path.

- The Nov 17 dinner council log landed in the home directory instead of the workspace because the council skill says working directory without naming it, and the Judge then adjudicated from the verdict summary only. Pinning the path here prevents a repeat.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- When Pete reports a meal with actually measured or known quantities, record the measured amounts against the estimates for the same meal in `references/calibration.md` and note which approach was closest. That is how this skill improves.

- When a food is a packaged product, prefer the label values for that exact product over a generic database entry.
