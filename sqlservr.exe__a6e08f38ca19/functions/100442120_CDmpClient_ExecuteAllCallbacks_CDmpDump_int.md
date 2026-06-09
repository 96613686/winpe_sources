# CDmpClient::ExecuteAllCallbacks(CDmpDump *,int)

- ea: `0x100442120`
- end: `0x10044228d`
- name: `?ExecuteAllCallbacks@CDmpClient@@QEAAJPEAVCDmpDump@@H@Z`
- size: `365`
- prototype: `__int64 __fastcall(CDmpClient *__hidden this, struct CDmpDump *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x100443a60`

## callees

- `0x1004414b0`
- `0x100442120`
- `0x100442730`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x100442150`
- `KERNEL32!WaitForSingleObject` at `0x100442150`
- `KERNEL32!GetLastError` at `0x10044215d`
- `KERNEL32!GetLastError` at `0x10044215d`
- `KERNEL32!GetTickCount64` at `0x10044217f`
- `KERNEL32!GetTickCount64` at `0x1004421e6`
- `KERNEL32!GetTickCount64` at `0x10044217f`
- `KERNEL32!GetTickCount64` at `0x1004421e6`
- `KERNEL32!ReleaseMutex` at `0x100442260`
- `KERNEL32!ReleaseMutex` at `0x100442260`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x10044223b`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x10044223b`

## string_xrefs

- `0x10044221b`: `CDmpClient::ExecuteAllCallbacks completed. Time elapsed: %I64d seconds.`

## pseudocode

```c

```
