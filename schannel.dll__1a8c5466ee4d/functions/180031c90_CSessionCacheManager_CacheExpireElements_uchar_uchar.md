# CSessionCacheManager::CacheExpireElements(uchar,uchar)

- ea: `0x180031c90`
- end: `0x180032067`
- name: `?CacheExpireElements@CSessionCacheManager@@AEAAEEE@Z`
- size: `983`
- prototype: `unsigned __int8 __fastcall(CSessionCacheManager *__hidden this, unsigned __int8, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180031b50`
- `0x180031b80`

## callees

- `0x180031c90`
- `0x180091010`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180031cdd`
- `ntdll!RtlEnterCriticalSection` at `0x180031cdd`
- `ntdll!RtlLeaveCriticalSection` at `0x180031ff5`
- `ntdll!RtlLeaveCriticalSection` at `0x180031ff5`
- `ntdll!RtlAcquireResourceExclusive` at `0x180031d4c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180031e19`
- `ntdll!RtlAcquireResourceExclusive` at `0x180031d4c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180031e19`
- `ntdll!RtlReleaseResource` at `0x180031dad`
- `ntdll!RtlReleaseResource` at `0x180031e83`
- `ntdll!RtlReleaseResource` at `0x180031dad`
- `ntdll!RtlReleaseResource` at `0x180031e83`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180031f0e`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180031f0e`

## pseudocode

```c

```
