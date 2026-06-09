# CSessionCacheManager::PurgeCacheForCredentialGroup(CCredentialGroup *)

- ea: `0x1800340e0`
- end: `0x180034511`
- name: `?PurgeCacheForCredentialGroup@CSessionCacheManager@@QEAAXPEAVCCredentialGroup@@@Z`
- size: `1073`
- prototype: `void __fastcall(CSessionCacheManager *__hidden this, struct CCredentialGroup *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004d320`

## callees

- `0x1800340e0`
- `0x180091010`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1800341e8`
- `ntdll!RtlEnterCriticalSection` at `0x1800341e8`
- `ntdll!RtlLeaveCriticalSection` at `0x18003440b`
- `ntdll!RtlLeaveCriticalSection` at `0x18003440b`
- `ntdll!RtlAcquireResourceExclusive` at `0x180034244`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800342de`
- `ntdll!RtlAcquireResourceExclusive` at `0x180034244`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800342de`
- `ntdll!RtlReleaseResource` at `0x1800341b1`
- `ntdll!RtlReleaseResource` at `0x1800341cc`
- `ntdll!RtlReleaseResource` at `0x180034295`
- `ntdll!RtlReleaseResource` at `0x180034348`
- `ntdll!RtlReleaseResource` at `0x1800341b1`
- `ntdll!RtlReleaseResource` at `0x1800341cc`
- `ntdll!RtlReleaseResource` at `0x180034295`
- `ntdll!RtlReleaseResource` at `0x180034348`
- `ntdll!RtlAcquireResourceShared` at `0x18003414f`
- `ntdll!RtlAcquireResourceShared` at `0x180034187`
- `ntdll!RtlAcquireResourceShared` at `0x18003414f`
- `ntdll!RtlAcquireResourceShared` at `0x180034187`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800344e9`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800344e9`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x1800343d3`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x1800343d3`

## pseudocode

```c

```
