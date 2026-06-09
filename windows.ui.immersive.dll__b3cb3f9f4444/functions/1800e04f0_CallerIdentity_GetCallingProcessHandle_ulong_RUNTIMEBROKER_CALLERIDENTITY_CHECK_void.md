# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x1800e04f0`
- end: `0x1800e05f5`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `261`
- prototype: `int __high(unsigned int, enum RUNTIMEBROKER_CALLERIDENTITY_CHECK, void **)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800aeb10`
- `0x1800e03b4`
- `0x1800e043c`
- `0x1800e04cc`
- `0x1800e05fc`

## callees

- `0x180013f14`
- `0x18002ff68`
- `0x18003729c`
- `0x1800e04f0`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800e0580`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800e0580`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e0564`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e0564`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0597`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0597`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800e0529`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800e0529`

## pseudocode

```c

```
