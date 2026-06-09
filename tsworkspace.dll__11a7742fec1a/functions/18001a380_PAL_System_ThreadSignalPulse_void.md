# PAL_System_ThreadSignalPulse(void *)

- ea: `0x18001a380`
- end: `0x18001a44a`
- name: `?PAL_System_ThreadSignalPulse@@YAJPEAX@Z`
- size: `202`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800182b0`

## callees

- `0x1800013f4`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3c7`
- `USER32!PostMessageW` at `0x18001a3a9`
- `USER32!PostMessageW` at `0x18001a3a9`

## string_xrefs

- `0x18001a3e9`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18001a3de`: `PAL_System_ThreadSignalPulse`
- `0x18001a3f4`: `Failed to post thread message. Error %d`

## pseudocode

```c

```
