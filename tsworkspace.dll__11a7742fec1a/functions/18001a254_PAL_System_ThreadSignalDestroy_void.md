# PAL_System_ThreadSignalDestroy(void *)

- ea: `0x18001a254`
- end: `0x18001a377`
- name: `?PAL_System_ThreadSignalDestroy@@YAJPEAX@Z`
- size: `291`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800182a0`

## callees

- `0x180001180`
- `0x18001a254`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a368`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a368`
- `USER32!DestroyWindow` at `0x18001a2e8`
- `USER32!DestroyWindow` at `0x18001a2e8`

## string_xrefs

- `0x18001a28c`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18001a316`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18001a273`: `PAL_System_ThreadSignalDestroy`
- `0x18001a2fd`: `PAL_System_ThreadSignalDestroy`

## pseudocode

```c

```
