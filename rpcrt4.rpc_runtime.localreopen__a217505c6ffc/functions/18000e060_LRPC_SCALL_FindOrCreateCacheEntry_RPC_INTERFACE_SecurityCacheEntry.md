# LRPC_SCALL::FindOrCreateCacheEntry(RPC_INTERFACE *,SecurityCacheEntry * *)

- ea: `0x18000e060`
- end: `0x18000e368`
- name: `?FindOrCreateCacheEntry@LRPC_SCALL@@UEAAJPEAVRPC_INTERFACE@@PEAPEAVSecurityCacheEntry@@@Z`
- size: `776`
- prototype: `__int64 __fastcall(LRPC_SCALL *__hidden this, struct RPC_INTERFACE *, struct SecurityCacheEntry **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d3bc`
- `0x18000d850`
- `0x18000d8c0`
- `0x18000d99c`
- `0x18000dc54`
- `0x18000e060`
- `0x18000e370`
- `0x18000e488`
- `0x18000e4b0`
- `0x18000ec80`
- `0x180023020`

## import_xrefs

- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000e0f3`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000e0f3`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e127`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e28d`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e127`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e28d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e1da`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e1da`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000e0c6`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000e0c6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e2a2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e2a2`

## pseudocode

```c

```
