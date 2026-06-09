# SHExePathFromPid(ulong,ushort *,uint)

- ea: `0x180087a88`
- end: `0x180087b5f`
- name: `?SHExePathFromPid@@YAJKPEAGI@Z`
- size: `215`
- prototype: `__int64 __fastcall(DWORD dwProcessId, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18003dcf0`

## callees

- `0x1800162f0`
- `0x180054130`
- `0x180087a88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087b20`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180087ae4`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180087ae4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180087ab9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180087ab9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087b12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087b12`

## pseudocode

```c

```
