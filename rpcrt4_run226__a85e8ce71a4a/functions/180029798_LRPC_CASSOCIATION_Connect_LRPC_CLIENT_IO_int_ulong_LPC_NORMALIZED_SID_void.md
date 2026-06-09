# LRPC_CASSOCIATION::Connect(LRPC_CLIENT_IO *,int,ulong,LPC_NORMALIZED_SID *,void *)

- ea: `0x180029798`
- end: `0x180029c6f`
- name: `?Connect@LRPC_CASSOCIATION@@QEAAJPEAVLRPC_CLIENT_IO@@HKPEAVLPC_NORMALIZED_SID@@PEAX@Z`
- size: `1239`
- prototype: `__int64 __fastcall(LRPC_CASSOCIATION *this, struct LRPC_CLIENT_IO *, int, unsigned int, PSID *, void *)`
- caller_count: `2`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180028d70`
- `0x1800b90e0`

## callees

- `0x180021ce0`
- `0x180021e70`
- `0x180022870`
- `0x1800283bc`
- `0x180029798`
- `0x180029c78`
- `0x18002f460`
- `0x180030254`
- `0x180032620`
- `0x180033a38`
- `0x18004fcf8`
- `0x18005db5c`
- `0x1800636e8`
- `0x180087cbc`
- `0x18008ae48`
- `0x18008fc98`
- `0x1800a2494`
- `0x1800d2010`

## import_xrefs

- `ntdll!NtClose` at `0x180029aff`
- `ntdll!NtClose` at `0x180029aff`
- `ntdll!RtlLeaveCriticalSection` at `0x1800297f1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800298bf`
- `ntdll!RtlLeaveCriticalSection` at `0x1800297f1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800298bf`
- `ntdll!RtlEnterCriticalSection` at `0x1800297d2`
- `ntdll!RtlEnterCriticalSection` at `0x1800297d2`

## pseudocode

```c

```
