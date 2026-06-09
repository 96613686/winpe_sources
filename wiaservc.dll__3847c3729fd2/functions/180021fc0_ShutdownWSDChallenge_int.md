# ShutdownWSDChallenge(int)

- ea: `0x180021fc0`
- end: `0x1800220eb`
- name: `?ShutdownWSDChallenge@@YAJH@Z`
- size: `299`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18001f0d0`
- `0x180026d60`
- `0x180045844`

## callees

- `0x18000ac34`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x180021fc0`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180078010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800220da`
- `KERNEL32!LeaveCriticalSection` at `0x1800220da`
- `KERNEL32!FreeLibrary` at `0x1800220bf`
- `KERNEL32!FreeLibrary` at `0x1800220bf`

## string_xrefs

- `0x180021fcb`: `Shutting down WSD Challenge: Unload DLL %d`
- `0x180022002`: `Shutting down WSD Challenge: Unload DLL %d`

## pseudocode

```c

```
