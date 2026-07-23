# Template Engine — Image Convention

Images for each site live under a folder named after the site's `siteId` from its config.

## Folder structure

```
public/images/
  {vertical}/
    hero-bg.png      ← full-bleed background for the hero section
    hero-side.png    ← side image displayed in split/default hero variants
    header-bg.png    ← background image behind the site header
```

## Referencing images in a config

Each site config has a top-level `images` block with standardized slot names:

```json
"images": {
  "heroBg":   "/images/{vertical}/hero-bg.png",
  "heroSide": "/images/{vertical}/hero-side.png",
  "headerBg": "/images/{vertical}/header-bg.png"
}
```

Set any slot to `null` (or omit it) when no image is needed for that slot.

## Slot reference

| Slot       | Used by                                | Notes                                          |
|------------|----------------------------------------|------------------------------------------------|
| `heroBg`   | `HeroSection` (fullscreen variant)     | Displays with a dark overlay for readability   |
| `heroSide` | `HeroSection` (split / default variant)| Right-column image next to the headline        |
| `headerBg` | `Header`                               | Covers full header bar with a dark tint overlay|

## Adding a new slot

1. Add the named property to the `images` block in the relevant config(s).
2. Consume it in the component with `config?.images?.yourSlot`.
3. Document it in the table above.

## Image guidelines

- **Recommended dimensions:** hero-bg / header-bg at 1600×900 px minimum; hero-side at 800×800 px.
- **Format:** PNG for all images.
- **File size:** keep hero images under 300 KB (compress before committing).
