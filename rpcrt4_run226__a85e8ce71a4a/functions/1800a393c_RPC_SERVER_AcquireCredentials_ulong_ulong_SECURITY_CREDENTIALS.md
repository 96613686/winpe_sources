# RPC_SERVER::AcquireCredentials(ulong,ulong,SECURITY_CREDENTIALS * *)

- ea: `0x1800a393c`
- end: `0x1800a39c9`
- name: `?AcquireCredentials@RPC_SERVER@@QEAAJKKPEAPEAVSECURITY_CREDENTIALS@@@Z`
- size: `141`
- prototype: `int(RPC_SERVER *__hidden this, unsigned int, unsigned int, struct SECURITY_CREDENTIALS **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005b55c`
- `0x180091ae0`

## callees

- `0x1800467b0`
- `0x1800a393c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800a3988`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a39b3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a3988`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a39b3`
- `ntdll!RtlEnterCriticalSection` at `0x1800a3959`
- `ntdll!RtlEnterCriticalSection` at `0x1800a3959`

## pseudocode

```c

```
