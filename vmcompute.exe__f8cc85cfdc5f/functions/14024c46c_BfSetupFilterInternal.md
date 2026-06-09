# BfSetupFilterInternal

- ea: `0x14024c46c`
- end: `0x14024c6df`
- name: `BfSetupFilterInternal`
- size: `627`
- prototype: `__int64 __fastcall(int, int, __int64, const WCHAR *, __int64, DWORD BytesReturned, char)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400a99f0`
- `0x1400d5c38`
- `0x140170930`

## callees

- `0x14024c46c`
- `0x14024c6e8`
- `0x14024c848`
- `0x14024c994`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14024c653`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14024c667`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14024c67b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14024c6a6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14024c6b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14024c653`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14024c667`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14024c67b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14024c6a6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14024c6b5`
- `ntdll!RtlNtStatusToDosError` at `0x14024c630`
- `ntdll!RtlNtStatusToDosError` at `0x14024c630`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14024c691`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14024c691`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14024c4cd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14024c4cd`
- `FLTLIB!FilterConnectCommunicationPort` at `0x14024c5e9`
- `FLTLIB!FilterConnectCommunicationPort` at `0x14024c5e9`
- `FLTLIB!FilterSendMessage` at `0x14024c617`
- `FLTLIB!FilterSendMessage` at `0x14024c617`

## pseudocode

```c

```
