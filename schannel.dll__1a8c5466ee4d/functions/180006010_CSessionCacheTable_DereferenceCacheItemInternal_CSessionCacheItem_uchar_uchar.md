# CSessionCacheTable::DereferenceCacheItemInternal(CSessionCacheItem *,uchar,uchar)

- ea: `0x180006010`
- end: `0x1800060b1`
- name: `?DereferenceCacheItemInternal@CSessionCacheTable@@AEAAJPEAVCSessionCacheItem@@EE@Z`
- size: `161`
- prototype: `__int64 __fastcall(CSessionCacheTable *__hidden this, struct CSessionCacheItem *, unsigned __int8, unsigned __int8)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005490`
- `0x180023d50`
- `0x180040c80`
- `0x1800413b0`
- `0x180050f90`
- `0x180075160`
- `0x180075340`
- `0x180075850`

## callees

- `0x180006010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180006039`
- `ntdll!RtlAcquireResourceExclusive` at `0x180006039`
- `ntdll!RtlReleaseResource` at `0x180006097`
- `ntdll!RtlReleaseResource` at `0x180006097`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18000605a`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18000605a`

## pseudocode

```c

```
