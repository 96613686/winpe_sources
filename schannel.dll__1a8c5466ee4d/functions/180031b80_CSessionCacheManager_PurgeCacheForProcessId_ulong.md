# CSessionCacheManager::PurgeCacheForProcessId(ulong)

- ea: `0x180031b80`
- end: `0x180031c85`
- name: `?PurgeCacheForProcessId@CSessionCacheManager@@QEAAXK@Z`
- size: `261`
- prototype: `void __fastcall(CSessionCacheManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004d320`

## callees

- `0x180031b80`
- `0x180031c90`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180031c14`
- `ntdll!RtlReleaseResource` at `0x180031c22`
- `ntdll!RtlReleaseResource` at `0x180031c14`
- `ntdll!RtlReleaseResource` at `0x180031c22`
- `ntdll!RtlAcquireResourceShared` at `0x180031bd7`
- `ntdll!RtlAcquireResourceShared` at `0x180031c00`
- `ntdll!RtlAcquireResourceShared` at `0x180031bd7`
- `ntdll!RtlAcquireResourceShared` at `0x180031c00`
- `ntdll!RtlConvertSharedToExclusive` at `0x180031c64`
- `ntdll!RtlConvertSharedToExclusive` at `0x180031c64`

## pseudocode

```c

```
