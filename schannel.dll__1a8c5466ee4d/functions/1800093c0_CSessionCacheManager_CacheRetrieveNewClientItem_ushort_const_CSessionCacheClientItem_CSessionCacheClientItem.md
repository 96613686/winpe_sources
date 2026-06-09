# CSessionCacheManager::CacheRetrieveNewClientItem(ushort const *,CSessionCacheClientItem * *,CSessionCacheClientItem *)

- ea: `0x1800093c0`
- end: `0x1800096b8`
- name: `?CacheRetrieveNewClientItem@CSessionCacheManager@@QEAAKPEBGPEAPEAVCSessionCacheClientItem@@PEAV2@@Z`
- size: `760`
- prototype: `unsigned int __fastcall(CSessionCacheManager *__hidden this, const unsigned __int16 *, struct CSessionCacheClientItem **, struct CSessionCacheClientItem *)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180009324`
- `0x18000b620`
- `0x180023430`
- `0x180050f90`

## callees

- `0x180008240`
- `0x1800093c0`
- `0x18000ad90`
- `0x180014240`
- `0x180021eb0`
- `0x18005a148`
- `0x180091010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800094ec`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800094ec`
- `ntdll!RtlReleaseResource` at `0x1800095b7`
- `ntdll!RtlReleaseResource` at `0x1800095b7`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180009540`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x1800095cf`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180009540`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x1800095cf`

## pseudocode

```c

```
