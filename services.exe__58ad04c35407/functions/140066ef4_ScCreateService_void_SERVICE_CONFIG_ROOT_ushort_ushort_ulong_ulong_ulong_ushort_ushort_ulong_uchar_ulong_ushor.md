# ScCreateService(void *,_SERVICE_CONFIG_ROOT *,ushort *,ushort *,ulong,ulong,ulong,ushort *,ushort *,ulong *,uchar *,ulong,ushort *,uchar *,ulong,ushort,unsigned __int64,ulong,CServiceRecord *,CServiceRecord * *)

- ea: `0x140066ef4`
- end: `0x140067cb0`
- name: `?ScCreateService@@YAKPEAXPEAU_SERVICE_CONFIG_ROOT@@PEAG2KKK22PEAKPEAEK24KG_KKPEAVCServiceRecord@@PEAPEAV2@@Z`
- size: `3516`
- prototype: `unsigned int(void *, struct _SERVICE_CONFIG_ROOT *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned __int8 *, unsigned int, unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned __int16, unsigned __int64, unsigned int, struct CServiceRecord *, struct CServiceRecord **)`
- caller_count: `2`
- callee_count: `48`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140029908`
- `0x140067cb8`

## callees

- `0x140003e54`
- `0x140004428`
- `0x140004c58`
- `0x140004c98`
- `0x140007130`
- `0x14000c120`
- `0x140011a78`
- `0x140011ba0`
- `0x140012770`
- `0x140013b0c`
- `0x140014074`
- `0x140014bc4`
- `0x140015020`
- `0x140015868`
- `0x140015a28`
- `0x140015b14`
- `0x14001c87c`
- `0x14001f99c`
- `0x14001fb18`
- `0x140020d84`
- `0x1400238c0`
- `0x140023cb4`
- `0x140024988`
- `0x1400275b8`
- `0x140028114`
- `0x14002e930`
- `0x140030238`
- `0x140038648`
- `0x1400406c8`
- `0x1400427c0`
- `0x140043dc4`
- `0x14004b1c0`
- `0x1400628a8`
- `0x14006456c`
- `0x1400647d8`
- `0x140064a90`
- `0x1400661a0`
- `0x14006654c`
- `0x140066ef4`
- `0x1400685a4`
- `0x14006afd0`
- `0x140070fc0`
- `0x140073c38`
- `0x140078c04`
- `0x14007cafc`
- `0x14007cdb8`
- `0x140086930`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140067bcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140067bcc`
- `ntdll!RtlAcquireResourceExclusive` at `0x140067344`
- `ntdll!RtlAcquireResourceExclusive` at `0x140067344`
- `ntdll!RtlReleaseResource` at `0x140067c6c`
- `ntdll!RtlReleaseResource` at `0x140067c6c`
- `ntdll!NtClose` at `0x140067bde`
- `ntdll!NtClose` at `0x140067bde`
- `ntdll!RtlNtStatusToDosError` at `0x140067be6`
- `ntdll!RtlNtStatusToDosError` at `0x140067be6`
- `ntdll!RtlFreeHeap` at `0x140067bc2`
- `ntdll!RtlFreeHeap` at `0x140067bc2`
- `ntdll!RtlAllocateHeap` at `0x1400672ea`
- `ntdll!RtlAllocateHeap` at `0x1400672ea`

## pseudocode

```c

```
