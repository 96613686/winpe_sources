# ScreenShooter::_PutOnClipboard(HBITMAP__ *)

- ea: `0x180159c6c`
- end: `0x180159d4f`
- name: `?_PutOnClipboard@ScreenShooter@@AEAAJPEAUHBITMAP__@@@Z`
- size: `227`
- prototype: `int(ScreenShooter *__hidden this, HBITMAP)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1801594f0`

## callees

- `0x180047224`
- `0x180159c6c`

## import_xrefs

- `USER32!CopyImage` at `0x180159cf4`
- `USER32!CopyImage` at `0x180159cf4`
- `GDI32!DeleteObject` at `0x180159d23`
- `GDI32!DeleteObject` at `0x180159d23`
- `GDI32!GetObjectW` at `0x180159c97`
- `GDI32!GetObjectW` at `0x180159c97`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180159ca6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180159ca6`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!CloseClipboard` at `0x180159d2d`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!CloseClipboard` at `0x180159d2d`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!SetClipboardData` at `0x180159d0a`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!SetClipboardData` at `0x180159d0a`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!OpenClipboard` at `0x180159caf`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!OpenClipboard` at `0x180159caf`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!EmptyClipboard` at `0x180159cc4`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!EmptyClipboard` at `0x180159cc4`

## pseudocode

```c

```
