# RenderLayer(MATRIXDATA *,HBITMAP__ *,Gdiplus::Graphics *,Gdiplus::Pen *,Gdiplus::Pen *,HDC__ *,HBITMAP__ *)

- ea: `0x1805114e0`
- end: `0x1805118dc`
- name: `?RenderLayer@@YAJPEAUMATRIXDATA@@PEAUHBITMAP__@@PEAVGraphics@Gdiplus@@PEAVPen@4@3PEAUHDC__@@1@Z`
- size: `1020`
- prototype: `int(struct MATRIXDATA *, HBITMAP, struct Gdiplus::Graphics *, struct Gdiplus::Pen *, struct Gdiplus::Pen *, HDC, HBITMAP)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180510e30`

## callees

- `0x180114c58`
- `0x180249490`
- `0x180510c3c`
- `0x180510d84`
- `0x180510de8`
- `0x18051122c`
- `0x1805114e0`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180511598`
- `GDI32!CreateCompatibleDC` at `0x180511598`
- `GDI32!SelectObject` at `0x1805115bd`
- `GDI32!SelectObject` at `0x1805115d4`
- `GDI32!SelectObject` at `0x1805116de`
- `GDI32!SelectObject` at `0x1805116f7`
- `GDI32!SelectObject` at `0x1805115bd`
- `GDI32!SelectObject` at `0x1805115d4`
- `GDI32!SelectObject` at `0x1805116de`
- `GDI32!SelectObject` at `0x1805116f7`
- `GDI32!DeleteDC` at `0x180511706`
- `GDI32!DeleteDC` at `0x180511706`
- `GDI32!GdiAlphaBlend` at `0x180511683`
- `GDI32!GdiAlphaBlend` at `0x180511683`
- `GDI32!BitBlt` at `0x1805116ca`
- `GDI32!BitBlt` at `0x1805116ca`
- `GDI32!GetObjectW` at `0x18051153e`
- `GDI32!GetObjectW` at `0x1805117ee`
- `GDI32!GetObjectW` at `0x18051153e`
- `GDI32!GetObjectW` at `0x1805117ee`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x1805115fd`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x1805115fd`
- `gdiplus!GdipSetWorldTransform` at `0x1805117c0`
- `gdiplus!GdipSetWorldTransform` at `0x1805117c0`
- `gdiplus!GdipShearMatrix` at `0x18051177c`
- `gdiplus!GdipShearMatrix` at `0x18051177c`
- `gdiplus!GdipScaleMatrix` at `0x18051175b`
- `gdiplus!GdipScaleMatrix` at `0x18051175b`
- `gdiplus!GdipTranslateMatrix` at `0x1805117ad`
- `gdiplus!GdipTranslateMatrix` at `0x1805117ad`
- `gdiplus!GdipDeleteMatrix` at `0x180511866`
- `gdiplus!GdipDeleteMatrix` at `0x180511866`
- `gdiplus!GdipCreateMatrix` at `0x180511720`
- `gdiplus!GdipCreateMatrix` at `0x180511720`
- `gdiplus!GdipDisposeImage` at `0x180511854`
- `gdiplus!GdipDisposeImage` at `0x180511854`

## pseudocode

```c

```
