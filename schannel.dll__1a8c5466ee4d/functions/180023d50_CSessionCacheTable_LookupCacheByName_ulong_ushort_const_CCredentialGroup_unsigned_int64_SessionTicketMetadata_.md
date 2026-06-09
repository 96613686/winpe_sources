# CSessionCacheTable::LookupCacheByName(ulong,ushort const *,CCredentialGroup *,unsigned __int64,SessionTicketMetadata *,CSessionCacheItem * *)

- ea: `0x180023d50`
- end: `0x180024151`
- name: `?LookupCacheByName@CSessionCacheTable@@QEAAEKPEBGPEAVCCredentialGroup@@_KPEAUSessionTicketMetadata@@PEAPEAVCSessionCacheItem@@@Z`
- size: `1025`
- prototype: `unsigned __int8 __usercall@<al>(CSessionCacheTable *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, struct CCredentialGroup *@<r9>, unsigned __int64, struct SessionTicketMetadata *, struct CSessionCacheItem **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180023430`

## callees

- `0x180006010`
- `0x18000cb90`
- `0x180023d50`
- `0x18005c3a0`
- `0x180091010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180023dd0`
- `ntdll!RtlAcquireResourceExclusive` at `0x180024016`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023dd0`
- `ntdll!RtlAcquireResourceExclusive` at `0x180024016`
- `ntdll!RtlReleaseResource` at `0x180023e25`
- `ntdll!RtlReleaseResource` at `0x180023fab`
- `ntdll!RtlReleaseResource` at `0x180023fcb`
- `ntdll!RtlReleaseResource` at `0x180024028`
- `ntdll!RtlReleaseResource` at `0x1800240b0`
- `ntdll!RtlReleaseResource` at `0x1800240ea`
- `ntdll!RtlReleaseResource` at `0x18008c826`
- `ntdll!RtlReleaseResource` at `0x180023e25`
- `ntdll!RtlReleaseResource` at `0x180023fab`
- `ntdll!RtlReleaseResource` at `0x180023fcb`
- `ntdll!RtlReleaseResource` at `0x180024028`
- `ntdll!RtlReleaseResource` at `0x1800240b0`
- `ntdll!RtlReleaseResource` at `0x1800240ea`
- `ntdll!RtlReleaseResource` at `0x18008c826`
- `ntdll!RtlAcquireResourceShared` at `0x180023e11`
- `ntdll!RtlAcquireResourceShared` at `0x180023e11`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180023f90`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180024083`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180023f90`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180024083`

## pseudocode

```c

```
