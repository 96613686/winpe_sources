# CTransport::CloseAllInternet(bool)

- ea: `0x18002dfcc`
- end: `0x18002e115`
- name: `?CloseAllInternet@CTransport@@AEAAJ_N@Z`
- size: `329`
- prototype: `__int64 __fastcall(CTransport *__hidden this, bool)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d838`
- `0x18002df9c`
- `0x18006c3f4`
- `0x18006ccc8`

## callees

- `0x180019690`
- `0x18001a530`
- `0x18001a9c0`
- `0x18002dfcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e0bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e0bf`
- `WINHTTP!WinHttpCloseHandle` at `0x18002e07e`
- `WINHTTP!WinHttpCloseHandle` at `0x18002e0ae`
- `WINHTTP!WinHttpCloseHandle` at `0x18002e07e`
- `WINHTTP!WinHttpCloseHandle` at `0x18002e0ae`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18002e06d`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18002e06d`

## string_xrefs

- `0x18002dfe7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18002e095`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18002e0e2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18002e102`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`

## pseudocode

```c

```
