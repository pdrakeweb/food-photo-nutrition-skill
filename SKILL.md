# Food photo nutrition

## When to use this skill

- Use this skill for any food photo Pete sends, or any food report that includes a photo.

- This skill is the default for evaluating food photos. Do not answer a food photo with a bare estimate when this skill applies.

- A text-only food report with no photo is out of scope. Use the plain estimate and MyFitnessPal flow for it.

- This skill depends on the council skill at `~/workspace/custom-skills/council/SKILL.md`. Read that skill in full before the council step.

## The default flow

- Run the automatic approach first. Give your normal in-model estimate of each item on the plate, with calories and macros (protein, carbs, fat, sugar) where you can determine them, using the tableware as scale.

- Treat the automatic estimate as the input to the council, not the final answer. The council checks and revises it.

- Run the council next with the custom panel in `references/seats.md`, 2 rounds, research on. Give the council the automatic estimate, the photos, the tableware reference, and any facts Pete stated.

- Send the council findings to a Judge only when the council confidence is low, the approaches disagree materially, or Pete asks. Give the Judge the brief and every round of the debate and nothing else from the session. The Judge rules with the proper values.

- Report the final numbers first, then the ranges and the confidence. Keep narrative to a minimum.

## Scale reference

- Use `~/workspace/user/reference/flight-silverware-plates.md` as the scale for every photo.

- The Filigree dinner plate is 10.5 inches across. The Flight dinner fork is 7 3/8 inches long. The cereal bowl holds about 2.4 cups to the brim.

- Do not guess plate or bowl size from the photo alone. Measure against a visible piece of tableware.

## Hard rules

- Never present a photo estimate as a weighed or measured amount. Label every quantity as estimate or measured.

- Never invent a weight. If the amount is unknown, say so and keep the estimate visibly marked as a guess.

- Ask Pete, or check the record, for raw versus cooked, brand or product, and cooking fat or oil. These three decide the calorie basis and are the most common source of error.

- Give the quick estimate first, then log the meal to MyFitnessPal through the browser with the saved login (account pdrake2300), then correct the estimate with the numbers MyFitnessPal confirms.

- Record each meal in `references/calibration.md` with what was estimated and what was later measured or confirmed, so future meals refine the approaches.

## Output

- Give per-item calories and macros with ranges, the meal total, the day total against the 2,410 goal, and the confidence level.

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
