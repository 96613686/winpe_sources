# ScStartServicesInStartList(CServiceRecord *,utl::unordered_set<CServiceRecord *,utl::hash<CServiceRecord *>,utl::equal_to<CServiceRecord *>,utl::allocator<CServiceRecord *>> &,ulong,ulong,_STRING_PTRSW *,ulong)

- ea: `0x140006900`
- end: `0x140006deb`
- name: `?ScStartServicesInStartList@@YAKPEAVCServiceRecord@@AEAV?$unordered_set@PEAVCServiceRecord@@U?$hash@PEAVCServiceRecord@@@utl@@U?$equal_to@PEAVCServiceRecord@@@3@V?$allocator@PEAVCServiceRecord@@@3@@utl@@KKPEAU_STRING_PTRSW@@K@Z`
- size: `1259`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting, service_task`

## callers

- `0x140010064`
- `0x14001761c`

## callees

- `0x140002890`
- `0x140003e54`
- `0x1400050c0`
- `0x140005600`
- `0x140005824`
- `0x1400059fc`
- `0x140006900`
- `0x140006df4`
- `0x1400070d0`
- `0x140007130`
- `0x140007180`
- `0x140007770`
- `0x140007960`
- `0x1400188fc`
- `0x14001f99c`
- `0x14003f9b0`
- `0x14004b1c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140006a57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140006a57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140006a7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140006c40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140006a7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140006c40`
- `ntdll!RtlReleaseResource` at `0x140006b9f`
- `ntdll!RtlReleaseResource` at `0x140006b9f`
- `ntdll!RtlAcquireResourceShared` at `0x140006950`
- `ntdll!RtlAcquireResourceShared` at `0x140006950`

## pseudocode

```c

```
