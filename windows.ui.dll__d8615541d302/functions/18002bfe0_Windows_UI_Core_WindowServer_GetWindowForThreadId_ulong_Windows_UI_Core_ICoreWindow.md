# Windows::UI::Core::WindowServer::GetWindowForThreadId(ulong,Windows::UI::Core::ICoreWindow * *)

- ea: `0x18002bfe0`
- end: `0x18002c0a2`
- name: `?GetWindowForThreadId@WindowServer@Core@UI@Windows@@SAHKPEAPEAUICoreWindow@234@@Z`
- size: `194`
- prototype: `__int64 __fastcall(unsigned int, struct Windows::UI::Core::ICoreWindow **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002bf60`

## callees

- `0x18002bfe0`
- `0x180050360`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002c007`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002c007`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002c071`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002c098`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002c071`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002c098`

## string_xrefs

- `0x18002c04f`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c

```
