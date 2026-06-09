# OSF_CASSOCIATION::FindOrCreateToken(void *,_LUID *,RPC_TOKEN * *,int *)

- ea: `0x18008e840`
- end: `0x18008e94e`
- name: `?FindOrCreateToken@OSF_CASSOCIATION@@QEAAJPEAXPEAU_LUID@@PEAPEAVRPC_TOKEN@@PEAH@Z`
- size: `270`
- prototype: `int(OSF_CASSOCIATION *__hidden this, void *, struct _LUID *, struct RPC_TOKEN **, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18008e6ec`

## callees

- `0x180021ce0`
- `0x180021e70`
- `0x18004f480`
- `0x180053ffc`
- `0x18008e840`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18008e90e`
- `ntdll!RtlLeaveCriticalSection` at `0x18008e90e`
- `ntdll!RtlEnterCriticalSection` at `0x18008e867`
- `ntdll!RtlEnterCriticalSection` at `0x18008e867`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008e92d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008e92d`

## pseudocode

```c

```
