# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x180063520`
- end: `0x18006365c`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `316`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180063664`

## callees

- `0x180006a74`
- `0x180063520`
- `0x1800636c8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006359f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006359f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800635b0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800635b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800635c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800635c1`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180063549`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180063549`

## pseudocode

```c

```
