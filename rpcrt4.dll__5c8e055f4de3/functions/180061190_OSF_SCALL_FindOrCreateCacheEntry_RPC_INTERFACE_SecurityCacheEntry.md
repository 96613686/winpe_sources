# OSF_SCALL::FindOrCreateCacheEntry(RPC_INTERFACE *,SecurityCacheEntry * *)

- ea: `0x180061190`
- end: `0x180061267`
- name: `?FindOrCreateCacheEntry@OSF_SCALL@@UEAAJPEAVRPC_INTERFACE@@PEAPEAVSecurityCacheEntry@@@Z`
- size: `215`
- prototype: `int(OSF_SCALL *__hidden this, struct RPC_INTERFACE *, struct SecurityCacheEntry **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180021e70`
- `0x1800605b0`
- `0x180061190`
- `0x1800616c4`
- `0x180072fd4`
- `0x1800735a0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800611df`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800611df`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18006123b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18006123b`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800611c4`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800611c4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180061222`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180061222`

## pseudocode

```c

```
