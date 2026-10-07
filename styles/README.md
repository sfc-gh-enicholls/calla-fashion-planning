# Style photography

Drop a photograph here named after the style code and it appears automatically —
no code change required.

```
public/styles/DN-FLR-002.jpg   Ines Flare Jean      (Mid Vintage)
public/styles/DN-SKN-014.jpg   Mila Skinny Jean     (Indigo Rinse)
public/styles/DN-STR-008.jpg   straight-leg denim
public/styles/DN-WDE-021.jpg   Juno Wide-Leg Jean
```

Run this to list every style code the app will look for:

```bash
npx --yes tsx scripts-calla/list-style-codes.ts
```

## How the fallback works

`src/components/style-product-image.tsx` requests `/styles/<CODE>.jpg` and, if the
file is missing, falls back to a vector garment rendered from the style's own
colourway and leg shape. So a partial set is fine — styles with a photo use it,
the rest render the vector.

## Requirements

- **Format/name:** `<STYLE_CODE>.jpg`, matching the code exactly (case-sensitive).
- **Aspect:** square. The image is rendered with `object-fit: cover`, so a
  non-square photo is cropped from the centre.
- **Size:** 400×400 is ample; these display between 22px and 64px.

## Licensing

Only use imagery cleared for commercial use. Unsplash and Pexels are both fine
(free for commercial use, no attribution required) — but note their websites
block automated download, so files need to be saved manually or fetched with an
API key.

Do **not** use product photography lifted from retailer sites (COS, Arket, Zara
and similar). It is copyrighted, it belongs to companies that may be competitors
of the customer being pitched, and this app is a customer-facing sales asset.

If you add imagery from a source that *does* require attribution, record it in
this file next to the filename.
