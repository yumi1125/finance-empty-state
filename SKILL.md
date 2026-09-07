---
name: finance-empty-state
description: Generate consistent transparent empty-state illustrations for financial reports when multi-source retrieval and model evaluation have completed but a specified period, institution type, or behavior dimension has too few valid records to display. Use for banking, consumer-credit, installment, application, limit, performance, and trend-report no-data states; not for system errors, access failures, rejection, or risk warnings.
---

# Finance Empty State

Create a transparent raster illustration that communicates a neutral-positive financial no-data result without relying on text.

## Interpret the state first

Preserve this four-part meaning:

1. Multi-source data retrieval and model evaluation completed successfully.
2. The requested period, institution type, or behavior dimension has no valid statistical result.
3. Sparse activity is the likely explanation; do not imply missing processing, rejection, delinquency, or elevated risk.
4. The state is suitable for periodic re-evaluation as later behavior accumulates.

Treat statements such as “overall performance is good,” “positive signal,” or “no risk indicated” as tone constraints, not as claims to invent a score or approval.

## Build the visual brief

Before generating, define:

```text
business_dimension: application | drawdown | installment | limit | performance | institution_distribution | other
time_scope: exact period if supplied, otherwise unspecified reporting period
institution_scope: bank | non-bank | multi-institution | unspecified
completed_process: multi-source retrieval + model evaluation
absent_measure: the statistic that has no valid records
likely_reason: low behavior frequency / insufficient observations
main_object: one dominant financial or reporting object
supporting_objects: one or two model/data objects
sparse_evidence: two or three visible observations with substantial unused capacity
future_monitoring_cue: a subtle cycle, clock, or forward continuation cue
scene_story: one concrete financial setting with a visible beginning, action, and result
character_role: the man's role in this specific business setting
character_action: one action that makes the absent measure understandable
business_setting: counter | report desk | timeline review | institution analysis | other
scene_logic: where the scene happens -> what the subject is doing -> what visible evidence results
prop_justification: why every object belongs to that exact task
target_size: intended display size
background: transparent
```

Read [references/semantic-library.md](references/semantic-library.md) when choosing objects or translating a new report dimension. Read [references/style-system.md](references/style-system.md) before writing the final prompt. Use [references/prompt-patterns.md](references/prompt-patterns.md) for concept comparisons, production assets, and targeted retries.

## Compose the evidence

- Prefer a concrete narrative scene over an isolated symbolic machine. Make the requested business dimension visually dominant; completion and scarcity cues may be small or implicit when the scene already communicates them.
- Treat the male character as optional. Include him only when a human action materially clarifies the business scene; otherwise let the financial setting and its data carry the meaning.
- When the man appears, let the scene decide whether he is a consumer, reviewer, or observer. Change his pose, facing direction, scale, and placement to fit the composition while preserving recognizable character design.
- Across a set, do not repeat the same analysis screen, pipeline, counter, time ring, result tray, or completion badge merely to show consistency. Unify through visual language, not cloned objects.
- Before generating, state the scene in one causal sentence: “At <recognizable place>, <subject> performs <specific action> with <business object>, revealing <sparse result>.” If this sentence is unclear, redesign the scene.
- Every visible prop must participate in that sentence. Remove decorative furniture, appliances, buttons, platforms, abstract rings, or machines that do not establish place, enable the action, or reveal the result.
- Do not add ornamental micro-elements. Small dots, beads, indicator lights, badges, pins, floating particles, detached markers, status pips, or tiny geometric accents are forbidden unless they are the actual business observations required to explain the absent measure. Any allowed small observation must be countable, attached to a relevant business surface, and indispensable to the scene logic.
- Use spatial cause and effect: the character's gaze and hands connect to the working object; inputs visibly enter the relevant business surface; sparse evidence appears where that action would naturally produce a result.
- Show completion with orderly alignment, a closed processing loop, settled documents, or a restrained blue/teal confirmation marker.
- Show scarcity with only two or three data tokens, widely spaced nodes, mostly unused slots, or a nearly blank chart surface.
- Show future observability with an incomplete time ring whose existing segment is calm and intact; never depict a broken pipeline.
- Keep all semantic evidence readable without labels at approximately `240×240` pixels.

## Generate

- Use the built-in image generation path and request a genuine transparent background.
- Default working canvas is square. For production examples use `1536×1536` when the active tool supports that size; otherwise generate square at the highest practical resolution and preserve aspect ratio.
- Generate distinct assets with separate prompts, not several unrelated subjects in one sheet.
- When included, use the recurring adult male: about 30 years old, short dark hair, simplified calm features, natural adult proportions, cyan `#1ED6FF` top, and dark navy trousers.
- Include no text, letters, numerals, currency symbols, logos, watermarks, UI copy, buttons, or pseudo-text.
- Use a localized pale-blue abstract ground shape behind the scene while keeping the outer canvas transparent.
- Keep surfaces visually clean: one broad smooth gradient per object, continuous light-to-shadow transitions, and only three to five large color masses at thumbnail size. Reject patchy blue shading, hard color bands, dirty gray/violet casts, grain, speckles, repeated saturated edge strips, or overlapping ground blobs.
- Keep a soft blue-gray contact shadow as part of the isolated object, with transparent pixels outside it.

Until a project-specific style has been approved, compare the three concept directions in [references/style-system.md](references/style-system.md) using the same subject and composition. After approval, use only the selected production anchor for every asset in the set.

## Inspect and retry

Inspect the original-resolution output and a `240×240` preview.

- Confirm the image reads as completed-but-sparse, not failed, blocked, rejected, or risky.
- Confirm `#326FF7` or its perceptual equivalent is visibly dominant; white and pale blue support it, and cyan remains a small accent.
- Confirm gradients blend continuously and the scene does not look mottled or assembled from unrelated color patches.
- Confirm the background contains real alpha and all four corners are fully transparent.
- If the generator bakes a pale checkerboard into an RGB image, first retry with a targeted transparency-only edit. If that still fails, run `python3 scripts/remove_checkerboard.py source.png output.png`, then inspect edges and internal white surfaces before approval.
- Reject stray text, pseudo-text, numbers, red warnings, crosses, exclamation marks, locks, 404 imagery, broken devices, severed paths, rejection stamps, or distressed characters.
- Reject unrelated micro-decoration, including tiny colored dots on trays or folders, glowing status lamps, free-standing location pins, floating rings, sparkles, orbit beads, scattered geometric marks, and miniature badges. Removing one of these must not change the business meaning; if it does not, remove it.
- Reject a completely empty container: two or three observations must remain to distinguish low activity from unavailable data.
- Reject any scene where the viewer cannot name the place, the subject's action, and the action's result within five seconds, or where two major props have no plausible relationship.
- For a retry, name one defect, preserve all approved invariants, and change only that defect.

## Save and report

- Save approved project assets inside the current project, using versioned filenames unless replacement is requested.
- Report the final brief, selected style anchor, prompt, output path, and validation result.
