# CProcess::GetNextThreadHandle(void *,ulong,void * *)

- ea: `0x1800599dc`
- end: `0x180059bde`
- name: `?GetNextThreadHandle@CProcess@@QEBAJPEAXKPEAPEAX@Z`
- size: `514`
- prototype: `__int64 __fastcall(CProcess *__hidden this, void *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180059800`
- `0x1800598f4`

## callees

- `0x180025250`
- `0x180025310`
- `0x18002ba28`
- `0x18002ed28`
- `0x1800599dc`
- `0x180059be4`
- `0x18005ba08`
- `0x18008cd90`

## import_xrefs

- `ntdll!NtGetNextThread` at `0x180059a4b`
- `ntdll!NtGetNextThread` at `0x180059ab0`
- `ntdll!NtGetNextThread` at `0x180059a4b`
- `ntdll!NtGetNextThread` at `0x180059ab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059b90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059b9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059bd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059b90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059b9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059bd3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180059a63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180059a63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059ace`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059b69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059ace`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059b69`

## string_xrefs

- `0x180059b03`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x180059b40`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x180059b75`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x180059ba8`: `onecore\com\combase\rpcss\objex\process.cxx`

## pseudocode

```c

```
