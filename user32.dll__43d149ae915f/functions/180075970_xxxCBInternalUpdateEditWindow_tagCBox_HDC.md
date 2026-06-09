# xxxCBInternalUpdateEditWindow(tagCBox *,HDC__ *)

- ea: `0x180075970`
- end: `0x180075f13`
- name: `?xxxCBInternalUpdateEditWindow@@YAXPEAUtagCBox@@PEAUHDC__@@@Z`
- size: `1443`
- prototype: `void(struct tagCBox *, HDC)`
- caller_count: `5`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x180057fa0`
- `0x1800754c4`
- `0x180075f1c`
- `0x180076044`
- `0x180083c9c`

## callees

- `0x18000cf20`
- `0x18000d9f0`
- `0x1800116d0`
- `0x18003b4a0`
- `0x18003c680`
- `0x180050680`
- `0x1800531d0`
- `0x180075970`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserReleaseDC` at `0x180075ec8`
- `win32u!NtUserReleaseDC` at `0x180075ec8`
- `win32u!NtUserGetDC` at `0x180075b04`
- `win32u!NtUserGetDC` at `0x180075b04`
- `win32u!NtUserGetControlBrush` at `0x180075b43`
- `win32u!NtUserGetControlBrush` at `0x180075b43`
- `ntdll!RtlFreeHeap` at `0x180075ee0`
- `ntdll!RtlFreeHeap` at `0x180097d50`
- `ntdll!RtlFreeHeap` at `0x180075ee0`
- `ntdll!RtlFreeHeap` at `0x180097d50`
- `ntdll!RtlAllocateHeap` at `0x180075a34`
- `ntdll!RtlAllocateHeap` at `0x180075a34`
- `GDI32!SetBkMode` at `0x180075b19`
- `GDI32!SetBkMode` at `0x180075b19`
- `GDI32!SelectObject` at `0x180075b4f`
- `GDI32!SelectObject` at `0x180075c75`
- `GDI32!SelectObject` at `0x180075ea1`
- `GDI32!SelectObject` at `0x180075eb7`
- `GDI32!SelectObject` at `0x180075b4f`
- `GDI32!SelectObject` at `0x180075c75`
- `GDI32!SelectObject` at `0x180075ea1`
- `GDI32!SelectObject` at `0x180075eb7`
- `GDI32!IntersectClipRect` at `0x180075d77`
- `GDI32!IntersectClipRect` at `0x180075d77`
- `GDI32!SetTextAlign` at `0x180075e18`
- `GDI32!SetTextAlign` at `0x180075e18`
- `GDI32!GetTextAlign` at `0x180075e0a`
- `GDI32!GetTextAlign` at `0x180075e0a`
- `GDI32!SetBkColor` at `0x180075c01`
- `GDI32!SetBkColor` at `0x180075c01`
- `GDI32!SetTextColor` at `0x180075c17`
- `GDI32!SetTextColor` at `0x180075c5e`
- `GDI32!SetTextColor` at `0x180075c17`
- `GDI32!SetTextColor` at `0x180075c5e`
- `GDI32!GetBkColor` at `0x180075c44`
- `GDI32!GetBkColor` at `0x180075c44`
- `GDI32!ExtTextOutW` at `0x180075e62`
- `GDI32!ExtTextOutW` at `0x180075e62`
- `GDI32!PatBlt` at `0x180075ba5`
- `GDI32!PatBlt` at `0x180075ba5`

## pseudocode

```c

```
