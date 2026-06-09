# ScStartServiceAndDependencies(CServiceRecord *,ulong,_STRING_PTRSW *,ulong,ulong,CServiceRecord *)

- ea: `0x14001761c`
- end: `0x14001796b`
- name: `?ScStartServiceAndDependencies@@YAKPEAVCServiceRecord@@KPEAU_STRING_PTRSW@@KK0@Z`
- size: `847`
- prototype: `__int64 __fastcall(struct CServiceRecord *this, int, struct _STRING_PTRSW *, int, unsigned int, struct CServiceRecord *)`
- caller_count: `10`
- callee_count: `16`
- tags: `loader_planting, service_task`

## callers

- `0x140017560`
- `0x140029908`
- `0x14002ab00`
- `0x1400337a8`
- `0x140034234`
- `0x14003a2f4`
- `0x14004130c`
- `0x14006e700`
- `0x140072790`
- `0x14007e810`

## callees

- `0x140005584`
- `0x140005b4c`
- `0x140005d30`
- `0x140006900`
- `0x140007130`
- `0x14001761c`
- `0x1400188fc`
- `0x14001c87c`
- `0x14001f99c`
- `0x140021a64`
- `0x140033fbc`
- `0x140043dc4`
- `0x140044054`
- `0x14004b1c0`
- `0x140057844`
- `0x140094020`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x14001768b`
- `ntdll!RtlAcquireResourceExclusive` at `0x14001773a`
- `ntdll!RtlAcquireResourceExclusive` at `0x14001768b`
- `ntdll!RtlAcquireResourceExclusive` at `0x14001773a`
- `ntdll!RtlReleaseResource` at `0x1400176d7`
- `ntdll!RtlReleaseResource` at `0x1400176f5`
- `ntdll!RtlReleaseResource` at `0x140017882`
- `ntdll!RtlReleaseResource` at `0x1400178bd`
- `ntdll!RtlReleaseResource` at `0x1400176d7`
- `ntdll!RtlReleaseResource` at `0x1400176f5`
- `ntdll!RtlReleaseResource` at `0x140017882`
- `ntdll!RtlReleaseResource` at `0x1400178bd`

## string_xrefs

- `0x14001769e`: `ServicesActive`
- `0x1400176be`: `ServicesActive`

## pseudocode

```c

```
