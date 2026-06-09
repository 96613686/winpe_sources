# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x1800d9100`
- end: `0x1800d91ec`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `236`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a5274`
- `0x1800d9034`

## callees

- `0x1800088e8`
- `0x180041a18`
- `0x1800d9100`
- `0x1800d9530`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800d9139`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800d9139`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800d9184`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800d9184`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d916e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d916e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d9195`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d9195`

## pseudocode

```c

```
