# Branding, Character, and Pet Guide

Every second brain created from this template should feel individual while remaining
part of one recognizable character family. Naming and icon creation happen during
guided onboarding, after the owner explains the workspace's purpose.

## Naming

- Ask what the owner wants the second brain to be called.
- If they are unsure, propose three short names grounded in its purpose, personality,
  or a metaphor they already use. Do not invent personal facts.
- Record the confirmed name in `USER.md` under `Workspace Identity`.
- Apply the name to the visible titles in `README.md`, `Dashboard.md`, `Welcome.md`,
  `AGENTS.md`, and `wiki/pages/workspace-profile.md`. Update package metadata when it
  exists. Do not rewrite operating rules merely to force the new name everywhere.

## Shared Character Language

Use `assets/second-brain-template-icon.png` as the local style and character-family
reference. A custom icon should preserve these traits:

- square 1024×1024 transparent PNG with fully transparent corners;
- one centered, connected character silhouette with generous padding;
- an unmistakable face that remains expressive at 64 pixels;
- bold brows, large glossy eyes, and a confident or friendly asymmetric smile;
- premium rounded 3D volume with crisp pearly highlights;
- tactile, highly polished, vaguely iOS-emoji-like rendering;
- a subject and two- or three-color palette derived from the confirmed name;
- no text, letters, numbers, watermark, frame, scenery, background, halo, or shadow.

The character should look like a sibling of the template mascot rather than a themed
badge. Literal names may use their obvious object or mascot. Abstract names should use
a simple visual metaphor approved by the owner. Avoid personal likenesses unless
explicitly requested.

## Icon Generation Workflow

When raster image generation is available:

1. Read the template icon as the character-family reference.
2. Derive one clear subject, face treatment, and palette from the confirmed name and
   purpose. State the concept in one sentence so the owner can correct it.
3. Generate one centered character on a perfectly flat chroma-key background that is
   absent from the character.
4. Remove the chroma key into a true-alpha PNG. Validate transparent corners, clean
   edges on light and dark surfaces, one connected silhouette, and small-size facial
   readability.
5. Save the approved PNG as `assets/<name-slug>-icon.png`, update the README image and
   alt text, and preserve the template icon as a fallback and style reference.
6. Show the final transparent icon to the owner. Iterate only on specific requested
   changes.

Do not substitute a flat SVG, emoji glyph, stock symbol, text-only monogram, or opaque
background image for the glossy transparent character. If image generation or clean
background removal is unavailable, keep the template mascot, finish onboarding, and
add one optional branding follow-up to `NOW.md`. Never require an API key or developer
tooling just to complete setup.

## Prompt Pattern

```text
Use case: logo-brand
Asset type: transparent square second-brain character icon and future pet reference
Input image: the template mascot is a character-family style reference only
Primary request: create a character for “[CONFIRMED NAME]” represented by [SUBJECT]
Face: bold expressive brows, large glossy eyes, confident asymmetric smile
Style: premium rounded glossy 3D emoji-like character with crisp pearly highlights
Composition: one centered connected silhouette, generous padding, readable at 64px
Palette: [TWO OR THREE COLORS DERIVED FROM THE NAME OR PURPOSE]
Background: perfectly flat removable chroma key; no shadow, halo, floor, or scenery
Constraints: 1024x1024; no text, letters, numbers, watermark, detached pieces, frame,
or UI; do not copy the template brain subject; preserve its face grammar, materials,
proportions, polish, transparency, and centered character composition
```

## Optional Animated Pet

After the owner approves the icon, ask once:

> Would you like me to hatch this character as an animated Codex pet too?

Record the choice in `USER.md` as `accepted`, `declined`, or `deferred`. A pet is an
optional follow-up and never blocks onboarding.

When accepted and the `hatch-pet` skill is available:

1. Load and follow that skill completely; do not invent a shortcut spritesheet.
2. Use the approved transparent icon as the canonical identity reference.
3. Preserve the face, material, palette, proportions, and signature silhouette. If the
   icon lacks a compact body or limbs needed for animation, propose the smallest
   identity-preserving adaptation and confirm it with the owner.
4. Produce the complete Codex-compatible v2 pet: all nine standard animation rows,
   all sixteen look directions, deterministic assembly, visual QA, and
   `spriteVersionNumber: 2` packaging.
5. Show the final contact sheet or previews and report the installed pet paths.

If the skill or required runtime is unavailable, explain what is missing and record a
follow-up. Do not claim that a static icon, one-off animation, or partial atlas is a
finished pet.

## Privacy and Sync

An icon name or subject can reveal personal information. Before committing it, confirm
that the owner is comfortable syncing it under the repository's current visibility.
