# CSessionCacheTable::PurgeCacheEntries(ulong,_LUID *,ulong,long *,ushort const *)

- ea: `0x180044108`
- end: `0x180044387`
- name: `?PurgeCacheEntries@CSessionCacheTable@@QEAAKKPEAU_LUID@@KPEAJPEBG@Z`
- size: `639`
- prototype: `unsigned int __fastcall(CSessionCacheTable *__hidden this, unsigned int, struct _LUID *, unsigned int, int *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180044090`

## callees

- `0x180044108`
- `0x180091010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180044159`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800441bd`
- `ntdll!RtlAcquireResourceExclusive` at `0x180044159`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800441bd`
- `ntdll!RtlReleaseResource` at `0x18004416a`
- `ntdll!RtlReleaseResource` at `0x1800441f1`
- `ntdll!RtlReleaseResource` at `0x18004416a`
- `ntdll!RtlReleaseResource` at `0x1800441f1`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x1800442b1`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x1800442b1`

## pseudocode

```c

```
