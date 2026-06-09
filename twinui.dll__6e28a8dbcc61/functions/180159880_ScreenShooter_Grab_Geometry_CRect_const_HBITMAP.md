# ScreenShooter::_Grab(Geometry::CRect const *,HBITMAP__ * *)

- ea: `0x180159880`
- end: `0x1801599d2`
- name: `?_Grab@ScreenShooter@@CAJPEBUCRect@Geometry@@PEAPEAUHBITMAP__@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(const struct Geometry::CRect *, HBITMAP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18015a414`

## callees

- `0x180047224`
- `0x1800f2c34`
- `0x180159880`

## import_xrefs

- `USER32!GetDC` at `0x1801598a3`
- `USER32!GetDC` at `0x1801598a3`
- `USER32!ReleaseDC` at `0x1801599a4`
- `USER32!ReleaseDC` at `0x1801599a4`
- `GDI32!CreateCompatibleBitmap` at `0x1801598f8`
- `GDI32!CreateCompatibleBitmap` at `0x1801598f8`
- `GDI32!CreateCompatibleDC` at `0x1801598c3`
- `GDI32!CreateCompatibleDC` at `0x1801598c3`
- `GDI32!SelectObject` at `0x18015991f`
- `GDI32!SelectObject` at `0x18015998c`
- `GDI32!SelectObject` at `0x18015991f`
- `GDI32!SelectObject` at `0x18015998c`
- `GDI32!BitBlt` at `0x180159959`
- `GDI32!BitBlt` at `0x180159959`
- `GDI32!DeleteDC` at `0x1801599b2`
- `GDI32!DeleteDC` at `0x1801599b2`

## pseudocode

```c

```
