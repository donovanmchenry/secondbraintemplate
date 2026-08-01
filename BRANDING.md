# Branding and Icon Guide

Every second brain created from this template should feel individual while remaining
part of one visual family. Naming and icon creation happen during guided onboarding,
after the owner explains the workspace's purpose and before setup is considered done.

## Naming

- Ask what the owner wants the second brain to be called.
- If they are unsure, propose three short names grounded in its purpose, personality,
  or a metaphor they already use. Do not invent personal facts.
- Record the confirmed name in `USER.md` under `Workspace Identity`.
- Apply the name to the visible titles in `README.md`, `Dashboard.md`, `Welcome.md`,
  `AGENTS.md`, and `wiki/pages/workspace-profile.md`. Update package metadata when it
  exists. Do not rewrite operating rules merely to force the new name everywhere.

## Shared Visual Language

Use `assets/second-brain-template-icon.png` as the local style reference. A custom
icon should preserve these family traits:

- square 1024×1024 composition;
- one centered, immediately readable subject with generous padding;
- premium glossy 3D rendering with rounded or beveled forms;
- crisp pearly specular highlights and convincing depth;
- a soft colored halo behind the subject;
- a dark warm-gray or charcoal vignette background;
- bold silhouette that remains legible at 64 pixels;
- no text, letters, numbers, watermark, frame, or UI chrome.

The subject and palette should come from the confirmed name. Literal names may use
their obvious object or mascot. Abstract names should use a simple visual metaphor
approved by the owner. Avoid faces or personal likenesses unless explicitly requested.

## Generation Workflow

When image generation is available:

1. Read the template icon as a style reference.
2. Derive one clear subject and palette from the confirmed name and purpose. State the
   concept in one sentence so the owner can correct a bad interpretation.
3. Generate one strong square icon using the prompt pattern below.
4. Inspect the result for subject clarity, family resemblance, text artifacts,
   unwanted personal details, and small-size legibility.
5. Save the approved project-bound PNG as `assets/<name-slug>-icon.png` and update the
   README image reference and alt text. Preserve the template icon as a fallback and
   style reference.
6. Show the final icon to the owner. Iterate only on specific requested changes.

Use raster image generation for the final custom icon. Do not substitute a flat SVG,
emoji, stock symbol, or text-only monogram for the glossy 3D result.

If image generation is unavailable, keep the neutral template icon, finish the rest
of onboarding, and add one optional branding follow-up to `NOW.md`. Never require an
API key or developer tooling just to complete setup.

## Prompt Pattern

```text
Use case: logo-brand
Asset type: square repository and second-brain icon
Input image: the neutral template icon is a style reference only
Primary request: create an icon for “[CONFIRMED NAME]” represented by [ONE SUBJECT]
Style: premium glossy 3D mascot or object, smooth rounded forms, crisp highlights
Composition: one centered subject, generous square padding, readable at 64px
Backdrop: dark warm charcoal radial gradient with a soft [PALETTE] halo
Palette: [TWO OR THREE COLORS DERIVED FROM THE NAME OR PURPOSE]
Constraints: 1024x1024; no text, letters, numbers, watermark, frame, or UI; do not
copy the template brain subject; preserve only its lighting, polish, halo, vignette,
and centered composition
```

## Privacy and Sync

An icon name or subject can reveal personal information. Before committing it, confirm
that the owner is comfortable syncing it under the repository's current visibility.
