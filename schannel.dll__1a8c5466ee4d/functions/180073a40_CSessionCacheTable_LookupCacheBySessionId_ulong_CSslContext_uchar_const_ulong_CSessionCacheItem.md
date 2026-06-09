# CSessionCacheTable::LookupCacheBySessionId(ulong,CSslContext *,uchar const *,ulong,CSessionCacheItem * *)

- ea: `0x180073a40`
- end: `0x180073c12`
- name: `?LookupCacheBySessionId@CSessionCacheTable@@QEAAEKPEAVCSslContext@@PEBEKPEAPEAVCSessionCacheItem@@@Z`
- size: `466`
- prototype: `unsigned __int8(CSessionCacheTable *__hidden this, unsigned int, struct CSslContext *, const unsigned __int8 *, unsigned int, struct CSessionCacheItem **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180058820`

## callees

- `0x18003e4b0`
- `0x18003ed50`
- `0x18005c3a0`
- `0x180073a40`
- `0x180088a48`
- `0x180091010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180073a7b`
- `ntdll!RtlAcquireResourceExclusive` at `0x180073a7b`
- `ntdll!RtlReleaseResource` at `0x180073ac5`
- `ntdll!RtlReleaseResource` at `0x180073b6b`
- `ntdll!RtlReleaseResource` at `0x180073be8`
- `ntdll!RtlReleaseResource` at `0x180073ac5`
- `ntdll!RtlReleaseResource` at `0x180073b6b`
- `ntdll!RtlReleaseResource` at `0x180073be8`
- `ntdll!RtlAcquireResourceShared` at `0x180073ab1`
- `ntdll!RtlAcquireResourceShared` at `0x180073ab1`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180073bde`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180073bde`

## pseudocode

```c

```
