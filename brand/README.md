# img2threejs brand assets

The mark is an isometric cube — the reconstructed object — with three source
pixels dissolving into it from the lower left: *image → 3D*. The white four-point
glint on the top face is the specular highlight every reconstruction has to earn.

## Files

| File | Size | Use |
| --- | --- | --- |
| `logo-avatar.svg` / `logo-avatar-1024.png` / `logo-avatar-512.png` | square, full-bleed | GitHub org avatar, app icons, social profiles. Corners are **not** pre-rounded — GitHub applies its own rounding. |
| `logo-mark.svg` / `logo-mark.png` | 374 × 346, transparent | READMEs, docs, slides. Trimmed to the artwork with 12px padding, so `width="112"` renders at full size. |
| `banner.svg` / `banner.png` | 1280 × 360 | README headers, social preview, talk slides. |

SVG is the source of truth; the PNGs are rendered from it.

## Palette

| Token | Hex | Where |
| --- | --- | --- |
| Violet | `#8b5cff` | cube top face (start), violet glow |
| Cyan | `#38e8ff` | cube top face (end), cyan glow |
| Teal | `#2bd4c8` → `#118a9c` | cube left face |
| Deep violet | `#6a3cf0` → `#2a1a7a` | cube right face |
| Pixel warm | `#ffd76a` → `#ff8bd0` | source pixels |
| Ink | `#1b1244` → `#0a0918` | badge / banner background |
| Glint | `#f4faff` | specular star |

## Rules

- **Do** keep the cube's 2:1 isometric geometry and the lower-left pixel trail together — they carry the whole story.
- **Do** use the transparent mark on light backgrounds and the badge version anywhere the background is busy.
- **Don't** recolour the faces, rotate the cube, add an outer stroke, or pre-round the avatar corners.
- **Don't** scale the badge below 24px — use the mark alone at small sizes.

## Regenerating the PNGs

Rendered with headless Chrome (no ImageMagick / librsvg needed):

```bash
chrome --headless=new --disable-gpu --hide-scrollbars \
  --window-size=1024,1024 --screenshot=brand/logo-avatar-1024.png \
  file://<wrapper.html embedding logo-avatar.svg at 1024px>
```

For the transparent mark add `--default-background-color=00000000`.
