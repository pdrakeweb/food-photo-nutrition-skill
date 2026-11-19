# food-photo-nutrition-skill

The default skill for recording nutrition: a food photo, a text-only food report, or a nutrition label photo. It evaluates calories and macros, logs them to MyFitnessPal, verifies the log, and validates the logged values after.

## How it works

1. **Saved foods.** Before estimating, the agent checks `references/saved-foods.md`. An item matching a saved food by item, brand, and preparation reuses the verified values as `tracked` instead of being re-estimated.
2. **Automatic approach.** The agent gives its normal in-model estimate of each item on the plate, using the tableware as scale (Pfaltzgraff Filigree dinner plate, 10.5 inches; Oneida Flight dinner fork, 7 3/8 inches; cereal bowl, about 2.4 cups to the brim). For a text-only report it estimates from Pete's stated quantities instead.
3. **Council.** The automatic estimate is the input to a three-seat council, not the final answer. The seats are Dimensions Estimator (plate and fork as scale, area and depth to volume), Portions Estimator (standard servings, USDA and MyFitnessPal reference values, explicit cooking-fat assumptions), and Photo Comparator (plated reference photos with stated weights and calories). Two rounds, research on. See `references/seats.md`.
4. **Judge.** Only when the council confidence is low, the approaches disagree materially, or the user asks. The Judge rules with the proper values.
5. **Confirm (only when asked), then log, verify, validate, and calibrate.** When Pete explicitly asks for an estimate, the proposed MyFitnessPal entries are shown to him for confirmation first, then logged exactly as confirmed. When he reports nutrition without asking for an estimate, the entries are logged directly without asking (Pete, Nov 18, 2026). Either way the diary is read back to verify every entry is present (logging success check, up to 2 retries per entry, never report complete until verified); a post-logging council validates the logged values when a trigger applies (low confidence, new or unusual meal, numbers out of normal, closest-entry substitution) and corrects any material error; and the estimates are recorded against any later measured or known quantities in `references/calibration.md`, so the approaches improve over time. For named-restaurant meals, a macros.menu check runs after the council and before the proposed entries (never before the council), and the council-vs-published variance is recorded in `references/estimate-variance.md` once the entries are logged.

## Precision tags

Every meal is tagged `tracked` (measured or verified against MyFitnessPal or a label), `estimated` (photo estimate, never measured), or `mixed` (both). The tag appears in the meal report and in calibration entries. It labels the provenance of the numbers; it does not change them.

## Label photos

A photo of a nutrition label is a separate input mode: the label's values are read by vision/OCR and count as `tracked` when the label is legible and the serving size is visible. Any unreadable value is named and estimated only for that value, never invented.

## Hard rules

- Never present a photo estimate as a weighed or measured amount. Label every quantity as estimate or measured.
- Never invent a weight. If the amount is unknown, say so and keep the estimate visibly marked as a guess.
- Ask, or check the record, for raw versus cooked, brand or product, and cooking fat or oil.
- Never report logging as complete until the diary readback confirms every confirmed entry is present (logging success check).
- Save every council run log to `~/workspace/council_log_YYYY-MM-DD.md` (pinned path; the Nov 17 dinner log landed in the home directory instead, and the Judge had to adjudicate from the verdict summary only).

## Install

Copy this directory into `~/workspace/custom-skills/food-photo-nutrition/` (or clone the repo there). It depends on the council skill at `~/workspace/custom-skills/council/SKILL.md`.

## Calibration

`references/calibration.md` holds the checked cases. Case 1 is the Nov 17, 2026 dinner: automatic estimate 666 + 474, corrected to 891 after Pete clarified the second helping, council verdict 988 (low confidence), judge verdict 949 (medium-low confidence). Lessons: the generic MyFitnessPal home-fries entry understates pan-fried home fries, raw-versus-cooked sausage basis must be asked, and a photo estimate must never be logged as a weighed amount. Case 2 is the Nov 18, 2026 lunch (Fat Head's half Turkey Club Wrap + fries): blind judge 630, menu-checked final 695 (+10.3%). `references/estimate-variance.md` holds the variance records behind that comparison (n=1, no correction in effect).

## License

MIT. See `LICENSE`.
