# food-photo-nutrition-skill

A skill for evaluating the calories and macros in a food photo.

## How it works

1. **Automatic approach.** The agent gives its normal in-model estimate of each item on the plate, using the tableware as scale (Pfaltzgraff Filigree dinner plate, 10.5 inches; Oneida Flight dinner fork, 7 3/8 inches; cereal bowl, about 2.4 cups to the brim).
2. **Council.** The automatic estimate is the input to a three-seat council, not the final answer. The seats are Dimensions Estimator (plate and fork as scale, area and depth to volume), Portions Estimator (standard servings, USDA and MyFitnessPal reference values, explicit cooking-fat assumptions), and Photo Comparator (plated reference photos with stated weights and calories). Two rounds, research on. See `references/seats.md`.
3. **Judge.** Only when the council confidence is low, the approaches disagree materially, or the user asks. The Judge rules with the proper values.
4. **Log and calibrate.** The meal is logged to MyFitnessPal (estimate first, then corrected with the confirmed numbers), and the estimates are recorded against any later measured or known quantities in `references/calibration.md`, so the approaches improve over time.

## Hard rules

- Never present a photo estimate as a weighed or measured amount. Label every quantity as estimate or measured.
- Never invent a weight. If the amount is unknown, say so and keep the estimate visibly marked as a guess.
- Ask, or check the record, for raw versus cooked, brand or product, and cooking fat or oil.
- Save every council run log to `~/workspace/council_log_YYYY-MM-DD.md` (pinned path; the Nov 17 dinner log landed in the home directory instead, and the Judge had to adjudicate from the verdict summary only).

## Install

Copy this directory into `~/workspace/custom-skills/food-photo-nutrition/` (or clone the repo there). It depends on the council skill at `~/workspace/custom-skills/council/SKILL.md`.

## Calibration

`references/calibration.md` holds the checked cases. Case 1 is the Nov 17, 2026 dinner: automatic estimate 666 + 474, corrected to 891 after Pete clarified the second helping, council verdict 988 (low confidence), judge verdict 949 (medium-low confidence). Lessons: the generic MyFitnessPal home-fries entry understates pan-fried home fries, raw-versus-cooked sausage basis must be asked, and a photo estimate must never be logged as a weighed amount.

## License

MIT. See `LICENSE`.
