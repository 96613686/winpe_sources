# CDmpClient::ExecuteAllCallbacks(CDmpDump *,int)

- ea: `0x1004823d0`
- end: `0x10048253d`
- name: `?ExecuteAllCallbacks@CDmpClient@@QEAAJPEAVCDmpDump@@H@Z`
- size: `365`
- prototype: `__int64 __fastcall(CDmpClient *__hidden this, struct CDmpDump *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x100483d00`

## callees

- `0x100481760`
- `0x1004823d0`
- `0x1004829e0`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x100482510`
- `KERNEL32!ReleaseMutex` at `0x100482510`
- `KERNEL32!WaitForSingleObject` at `0x100482400`
- `KERNEL32!WaitForSingleObject` at `0x100482400`
- `KERNEL32!GetTickCount64` at `0x10048242f`
- `KERNEL32!GetTickCount64` at `0x100482496`
- `KERNEL32!GetTickCount64` at `0x10048242f`
- `KERNEL32!GetTickCount64` at `0x100482496`
- `KERNEL32!GetLastError` at `0x10048240d`
- `KERNEL32!GetLastError` at `0x10048240d`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x1004824eb`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x1004824eb`

## string_xrefs

- `0x1004824cb`: `CDmpClient::ExecuteAllCallbacks completed. Time elapsed: %I64d seconds.`

## pseudocode

```c

```
