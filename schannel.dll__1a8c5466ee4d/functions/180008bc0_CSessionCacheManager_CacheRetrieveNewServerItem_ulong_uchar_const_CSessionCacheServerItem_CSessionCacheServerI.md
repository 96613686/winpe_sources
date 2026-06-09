# CSessionCacheManager::CacheRetrieveNewServerItem(ulong,uchar * const,CSessionCacheServerItem * *,CSessionCacheServerItem *)

- ea: `0x180008bc0`
- end: `0x180008f2b`
- name: `?CacheRetrieveNewServerItem@CSessionCacheManager@@QEAAKKQEAEPEAPEAVCSessionCacheServerItem@@PEAV2@@Z`
- size: `875`
- prototype: `unsigned int __fastcall(CSessionCacheManager *__hidden this, unsigned int, unsigned __int8 *const, struct CSessionCacheServerItem **, struct CSessionCacheServerItem *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006f1c`
- `0x180007b50`
- `0x18007c28c`
- `0x180081d80`

## callees

- `0x180008bc0`
- `0x180008f40`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008ece`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008ece`
- `ntdll!RtlAcquireResourceExclusive` at `0x180008ce8`
- `ntdll!RtlAcquireResourceExclusive` at `0x180008ce8`
- `ntdll!RtlReleaseResource` at `0x180008db4`
- `ntdll!RtlReleaseResource` at `0x180008db4`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180008d37`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180008dcc`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180008d37`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180008dcc`

## pseudocode

```c

```
