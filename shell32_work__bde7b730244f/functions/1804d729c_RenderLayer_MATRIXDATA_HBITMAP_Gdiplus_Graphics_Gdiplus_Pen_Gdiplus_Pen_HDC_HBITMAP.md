# RenderLayer(MATRIXDATA *,HBITMAP__ *,Gdiplus::Graphics *,Gdiplus::Pen *,Gdiplus::Pen *,HDC__ *,HBITMAP__ *)

- ea: `0x1804d729c`
- end: `0x1804d762b`
- name: `?RenderLayer@@YAJPEAUMATRIXDATA@@PEAUHBITMAP__@@PEAVGraphics@Gdiplus@@PEAVPen@4@3PEAUHDC__@@1@Z`
- size: `911`
- prototype: `int(struct MATRIXDATA *, HBITMAP, struct Gdiplus::Graphics *, struct Gdiplus::Pen *, struct Gdiplus::Pen *, HDC, HBITMAP)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1804d6c50`

## callees

- `0x180107ab4`
- `0x180233280`
- `0x1804d6a84`
- `0x1804d6bb4`
- `0x1804d6c14`
- `0x1804d6ffc`
- `0x1804d729c`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1804d734e`
- `GDI32!CreateCompatibleDC` at `0x1804d734e`
- `GDI32!SelectObject` at `0x1804d736d`
- `GDI32!SelectObject` at `0x1804d737e`
- `GDI32!SelectObject` at `0x1804d7470`
- `GDI32!SelectObject` at `0x1804d7483`
- `GDI32!SelectObject` at `0x1804d736d`
- `GDI32!SelectObject` at `0x1804d737e`
- `GDI32!SelectObject` at `0x1804d7470`
- `GDI32!SelectObject` at `0x1804d7483`
- `GDI32!DeleteDC` at `0x1804d748c`
- `GDI32!DeleteDC` at `0x1804d748c`
- `GDI32!GdiAlphaBlend` at `0x1804d7421`
- `GDI32!GdiAlphaBlend` at `0x1804d7421`
- `GDI32!BitBlt` at `0x1804d7462`
- `GDI32!BitBlt` at `0x1804d7462`
- `GDI32!GetObjectW` at `0x1804d72fa`
- `GDI32!GetObjectW` at `0x1804d7550`
- `GDI32!GetObjectW` at `0x1804d72fa`
- `GDI32!GetObjectW` at `0x1804d7550`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x1804d73a1`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x1804d73a1`
- `gdiplus!GdipSetWorldTransform` at `0x1804d7528`
- `gdiplus!GdipSetWorldTransform` at `0x1804d7528`
- `gdiplus!GdipShearMatrix` at `0x1804d74f0`
- `gdiplus!GdipShearMatrix` at `0x1804d74f0`
- `gdiplus!GdipScaleMatrix` at `0x1804d74d5`
- `gdiplus!GdipScaleMatrix` at `0x1804d74d5`
- `gdiplus!GdipTranslateMatrix` at `0x1804d751b`
- `gdiplus!GdipTranslateMatrix` at `0x1804d751b`
- `gdiplus!GdipDeleteMatrix` at `0x1804d75bc`
- `gdiplus!GdipDeleteMatrix` at `0x1804d75bc`
- `gdiplus!GdipCreateMatrix` at `0x1804d74a0`
- `gdiplus!GdipCreateMatrix` at `0x1804d74a0`
- `gdiplus!GdipDisposeImage` at `0x1804d75b0`
- `gdiplus!GdipDisposeImage` at `0x1804d75b0`

## pseudocode

```c

```
