# OSF_SCALL::FindOrCreateCacheEntry(RPC_INTERFACE *,SecurityCacheEntry * *)

- ea: `0x180066510`
- end: `0x180066600`
- name: `?FindOrCreateCacheEntry@OSF_SCALL@@UEAAJPEAVRPC_INTERFACE@@PEAPEAVSecurityCacheEntry@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(OSF_SCALL *this, unsigned int **, struct SecurityCacheEntry **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d99c`
- `0x180023020`
- `0x1800645c0`
- `0x180066510`
- `0x180066608`
- `0x1800a00a4`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180066566`
- `ntdll!RtlReleaseSRWLockShared` at `0x180066566`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800665ce`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800665ce`
- `ntdll!RtlAcquireSRWLockShared` at `0x180066545`
- `ntdll!RtlAcquireSRWLockShared` at `0x180066545`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800665af`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800665af`

## pseudocode

```c

```
