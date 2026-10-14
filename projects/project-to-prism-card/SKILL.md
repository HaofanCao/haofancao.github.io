---
name: project-to-prism-card
description: Migrate an external project or repository into the PRISM Projects page. Use when Codex needs to read a project thoroughly, extract the real goal and contributions, prepare preview and walkthrough assets under public/projects, and add or update a project card entry in content/projects.toml that matches the current CardPage layout.
---

# Project To PRISM Card

Read the source project before writing anything. Minimum reading set:

- main `README`
- key docs explaining pipeline or method
- core scripts or modules
- any released outputs, metrics, or example assets

Do not write a project card from the title alone.

## Workflow

1. Understand the project end-to-end.
2. Extract five things only:
   - one-line practical goal
   - short subtitle
   - one-sentence summary for `content`
   - one short expandable explanation for `details`
   - 3 to 5 tags
3. Collect visual assets:
   - one small preview image or SVG
   - three walkthrough images when available
4. Copy assets into `public/projects/`.
5. Record the real image aspect ratio for the preview.
6. Add or update one `[[items]]` block in `content/projects.toml`.
7. Verify the asset paths and TOML parsing.

## Current Card Layout

The current PRISM project card supports these fields in `content/projects.toml`:

- `title`
- `subtitle`
- `date`
- `image`
- `image_label`
- `image_aspect`
- `content`
- `details_label`
- `details`
- `link`
- `link_label`
- `gallery_title`
- `gallery`
- `tags`

The current visual rules are:

- keep the preview small; it is a thumbnail, not a hero image
- put the homepage button under the preview
- keep tags on the same horizontal row as the preview button
- keep `content` to one short sentence
- move explanation into collapsed `details`
- move walkthrough images into collapsed `gallery`

## Writing Rules

- Write the project goal first, not the model name first.
- Prefer `built for X practical target` over generic claims like `advanced deep learning project`.
- Keep `content` to one sentence.
- Keep `details` to two short sentences or one short paragraph.
- Only include metrics that are real and already supported by repo artifacts.
- Do not oversell. Make the contribution concrete.

## Asset Rules

- Put all copied assets under `public/projects/`.
- Use stable filenames such as:
  - `project-slug-preview.svg`
  - `project-slug-origin.jpg`
  - `project-slug-detect.jpg`
  - `project-slug-final.jpg`
- Set `image_aspect` to the source aspect ratio, for example `2000 / 920`.
- Use `object-contain` style previews by preserving whitespace around diagrams only when the source already needs it.

## Validation

After editing:

1. parse `content/projects.toml`
2. confirm every referenced asset exists under `public/projects/`
3. confirm the preview looks like a thumbnail, not a dominant panel
4. confirm the summary is readable without opening `details`

## Template

Use the template in [assets/project-item-template.toml](c:/Users/GaGut/Desktop/GaGuterl/Homepage/PRISM_v0/public/projects/project-to-prism-card/assets/project-item-template.toml).
