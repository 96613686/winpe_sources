# TSWWinHttpConnectThreadProc(void *)

- ea: `0x18006cb60`
- end: `0x18006ccee`
- name: `?TSWWinHttpConnectThreadProc@@YAKPEAX@Z`
- size: `398`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18000ece0`
- `0x18006c814`
- `0x18006c83c`
- `0x18006cb60`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cba7`
- `KERNEL32!GlobalFree` at `0x18006cc81`
- `KERNEL32!GlobalFree` at `0x18006cc9a`
- `KERNEL32!GlobalFree` at `0x18006cc81`
- `KERNEL32!GlobalFree` at `0x18006cc9a`
- `WINHTTP!WinHttpConnect` at `0x18006cb99`
- `WINHTTP!WinHttpConnect` at `0x18006cb99`
- `WINHTTP!WinHttpCloseHandle` at `0x18006ccb1`
- `WINHTTP!WinHttpCloseHandle` at `0x18006ccb1`

## string_xrefs

- `0x18006cc48`: `TSWGetProxyConfig failed`

## pseudocode

```c

```
