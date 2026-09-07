# Style System

## Shared constants

- Brand blue: `#326FF7`, visually dominant on every asset.
- Supporting pale blues: `#EAF3FF`, `#D6E7FF`, and `#AFCBFF`.
- Cyan accent: `#43D7E8`, limited to roughly 5–10% of colored area.
- White is used for papers, inactive slots, highlights, and calm negative space.
- Neutral shadow: cool blue-gray at low opacity. It may sit below the object but must fade to transparent.
- Composition: centered concrete scene, square footprint, generous transparent outer margin, localized pale-blue abstract ground shape, no full background panel.
- Camera: front view with a slight side angle and shallow depth; avoid dramatic perspective.
- Emotion: calm, orderly, capable, and gently anticipatory.

## Concrete narrative scene candidate

- Flat vector financial illustration with clean simplified shapes and medium detail density.
- Optional recurring character: a man about 30 years old, short dark hair, calm simplified facial features, natural adult proportions, `#1ED6FF` cyan top, dark navy trousers, and unobtrusive shoes.
- Keep his identity, head-to-body ratio, face construction, clothing colors, and line treatment stable; freely change pose, facing direction, scale, and role to fit each scene.
- Build recognizable settings from counters, desks, calendar/timeline boards, bank/institution façades, report screens, cards, and document trays.
- Use scene objects to show retrieval, evaluation, sparse records, and later observation. Do not fall back to a freestanding abstract ring as the whole scene.
- Do not require the character, model screen, data pipeline, completion badge, or monitoring orbit in every image. Use the minimum cues needed for the current meaning.
- In a multi-image set, require different dominant silhouettes and object families. Repeated visual systems come from palette, drawing, perspective, shadow, ground shape, and density rather than repeated props.
- Reserve `#326FF7` for major architecture, boards, terminals, and data paths. Cyan outside the shirt is limited to key observation nodes.

## Color blending and surface cleanliness

- Treat each object as one coherent color volume. Use one broad, smooth gradient from light-facing pale blue or white into a restrained blue shadow; never build form from scattered blue patches.
- Keep hue transitions continuous across adjacent faces. Prefer long feathered transitions over abrupt bands, mottled shading, cloudy stains, speckles, or watercolor-like blooms.
- Limit each object to one base hue, one light value, and one shadow value. Reserve saturated `#326FF7` for deliberate focal surfaces rather than repeated edge strips.
- Use soft ambient occlusion only where objects touch. Do not add blue halos around every edge or multiple overlapping cast shadows.
- Keep white and pale-blue areas clean and luminous. Remove dirty gray, violet contamination, cyan noise, chromatic aberration, grain, and high-frequency texture.
- The pale-blue ground shape should be a single quiet low-contrast gradient with soft feathered edges, not several overlapping blobs.
- At thumbnail size, the scene should read as three to five large color masses rather than many alternating blue-white fragments.

## Micro-element discipline

- Build the image from meaningful scene objects, not decorative detail confetti.
- Never place tiny colored dots, LEDs, badges, location pins, floating particles, sparkles, orbit beads, detached rings, or miniature geometric accents merely to balance the composition or suggest technology.
- Do not put small glowing marks on folders, trays, clocks, counters, devices, or empty slots unless that mark is the specific record being counted.
- A small element is allowed only when it directly represents the requested sparse data. It must be visibly anchored to the corresponding timeline, institution slot, chart, or application surface and remain countable at `240×240`.
- Prefer one clear business object or a simple empty slot over a symbolic indicator. Leave quiet negative space instead of filling gaps with accents.

## Concept directions

Use the same report-folder subject for an apples-to-apples first review.

### A. Minimal blue linework

- Crisp navy-blue outlines with consistent 2–3 px-equivalent weight at final UI size.
- White fills, flat `#326FF7` emphasis, and tiny cyan completion accents.
- Almost no gradient; use only a faint contact shadow.
- Best for compact enterprise interfaces and maximum visual restraint.

### B. Soft flat gradient

- Rounded vector-like silhouettes with no dark contour.
- Pale-blue surfaces, restrained linear gradients, and slightly translucent secondary shapes.
- Soft ambient shadow, low contrast, and a calm editorial empty-state feeling.
- Avoid decorative plants, landscapes, clouds, and unrelated lifestyle motifs.

### C. Rounded 2.5D

- Softly extruded, rounded objects with simplified toy-like geometry.
- Matte or satin material, controlled white highlights, and compact isometric depth.
- Brand-blue main surfaces, white inserts, pale-blue sides, and tiny cyan data tokens.
- Avoid glassy plastic, metallic chrome, excessive bloom, photorealism, or deep cinematic shadows.

## Production style lock

After the user approves A, B, or C, copy that direction here as the sole production anchor and remove ambiguity from future prompts. Lock outline, radii, proportions, projection, camera elevation, material, gradients, light direction, shadow softness, color ratios, token size/count, and negative-space margin. All assets in one set must use the same locked values; change subject geometry only.

For narrative-scene reviews, generate several scenes in the concrete candidate above before locking it. Preserve the same character and visual system while changing the setting, action, and principal props.

## Transparency gate

- Output must be RGBA with alpha outside the subject and its soft contact shadow.
- All four corner pixels must have alpha `0`.
- No white rectangle, pale scenic blob, halo, checkerboard, or opaque floor plane.
- Fine pale-blue edges must remain intact without white or gray fringe.
