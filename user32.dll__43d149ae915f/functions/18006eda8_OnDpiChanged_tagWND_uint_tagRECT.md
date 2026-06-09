# OnDpiChanged(tagWND *,uint,tagRECT *)

- ea: `0x18006eda8`
- end: `0x18006ef2c`
- name: `?OnDpiChanged@@YAXPEAUtagWND@@IPEAUtagRECT@@@Z`
- size: `388`
- prototype: `void __fastcall(struct tagWND *, unsigned int, struct tagRECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008ab0`

## callees

- `0x180052e70`
- `0x180069284`
- `0x18006eda8`
- `0x180078a08`
- `0x180078bd8`

## import_xrefs

- `win32u!NtUserSetWindowPos` at `0x18006ef04`
- `win32u!NtUserSetWindowPos` at `0x18006ef04`
- `win32u!NtUserIsTopLevelWindow` at `0x18006eed1`
- `win32u!NtUserIsTopLevelWindow` at `0x18006eed1`
- `win32u!NtUserInvalidateRect` at `0x18006ef13`
- `win32u!NtUserInvalidateRect` at `0x18006ef13`
- `win32u!NtUserEndDeferWindowPosEx` at `0x18006eec5`
- `win32u!NtUserEndDeferWindowPosEx` at `0x18006eec5`
- `GDI32!DeleteObject` at `0x18006ee63`
- `GDI32!DeleteObject` at `0x18006ee63`

## pseudocode

```c

```
