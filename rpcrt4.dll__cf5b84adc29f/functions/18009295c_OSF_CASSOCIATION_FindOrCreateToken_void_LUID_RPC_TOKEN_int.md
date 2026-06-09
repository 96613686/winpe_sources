# OSF_CASSOCIATION::FindOrCreateToken(void *,_LUID *,RPC_TOKEN * *,int *)

- ea: `0x18009295c`
- end: `0x180092a7d`
- name: `?FindOrCreateToken@OSF_CASSOCIATION@@QEAAJPEAXPEAU_LUID@@PEAPEAVRPC_TOKEN@@PEAH@Z`
- size: `289`
- prototype: `int(OSF_CASSOCIATION *__hidden this, void *, struct _LUID *, struct RPC_TOKEN **, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800927e8`

## callees

- `0x18000fd70`
- `0x180022e80`
- `0x180023020`
- `0x18006a25c`
- `0x18009295c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180092a30`
- `ntdll!RtlLeaveCriticalSection` at `0x180092a30`
- `ntdll!RtlEnterCriticalSection` at `0x180092983`
- `ntdll!RtlEnterCriticalSection` at `0x180092983`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180092a56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180092a56`

## pseudocode

```c

```
