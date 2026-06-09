# RPC_SERVER::AcquireCredentials(ulong,ulong,SECURITY_CREDENTIALS * *)

- ea: `0x1800a6f90`
- end: `0x1800a7030`
- name: `?AcquireCredentials@RPC_SERVER@@QEAAJKKPEAPEAVSECURITY_CREDENTIALS@@@Z`
- size: `160`
- prototype: `int(RPC_SERVER *__hidden this, unsigned int, unsigned int, struct SECURITY_CREDENTIALS **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006aa1c`
- `0x18006baf0`

## callees

- `0x1800585e0`
- `0x1800a6f90`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800a6fe2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a7013`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a6fe2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a7013`
- `ntdll!RtlEnterCriticalSection` at `0x1800a6fad`
- `ntdll!RtlEnterCriticalSection` at `0x1800a6fad`

## pseudocode

```c

```
