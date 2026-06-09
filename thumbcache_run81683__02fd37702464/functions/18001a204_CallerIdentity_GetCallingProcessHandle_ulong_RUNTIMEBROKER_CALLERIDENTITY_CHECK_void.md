# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x18001a204`
- end: `0x18001a2ec`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `232`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019954`
- `0x18001a0e8`

## callees

- `0x18000bfd8`
- `0x18001a204`
- `0x18001a2f4`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001a2de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001a2de`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18001a237`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18001a237`

## pseudocode

```c

```
