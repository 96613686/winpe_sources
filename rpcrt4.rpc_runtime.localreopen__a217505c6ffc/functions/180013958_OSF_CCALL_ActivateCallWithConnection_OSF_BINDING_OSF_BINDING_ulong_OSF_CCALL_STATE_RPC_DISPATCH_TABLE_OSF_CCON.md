# OSF_CCALL::ActivateCallWithConnection(OSF_BINDING *,OSF_BINDING *,ulong,OSF_CCALL_STATE,RPC_DISPATCH_TABLE *,OSF_CCONNECTION *,CSECURITY_CONTEXT *)

- ea: `0x180013958`
- end: `0x180013ad6`
- name: `?ActivateCallWithConnection@OSF_CCALL@@QEAAJPEAVOSF_BINDING@@0KW4OSF_CCALL_STATE@@PEAURPC_DISPATCH_TABLE@@PEAVOSF_CCONNECTION@@PEAVCSECURITY_CONTEXT@@@Z`
- size: `382`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001208c`
- `0x1800131cc`

## callees

- `0x180013958`
- `0x180022e80`
- `0x18006112c`
- `0x180061ba8`
- `0x18009fbf4`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180013a63`
- `ntdll!RtlLeaveCriticalSection` at `0x180013ac5`
- `ntdll!RtlLeaveCriticalSection` at `0x180013a63`
- `ntdll!RtlLeaveCriticalSection` at `0x180013ac5`
- `ntdll!RtlEnterCriticalSection` at `0x180013a48`
- `ntdll!RtlEnterCriticalSection` at `0x180013a48`

## pseudocode

```c

```
