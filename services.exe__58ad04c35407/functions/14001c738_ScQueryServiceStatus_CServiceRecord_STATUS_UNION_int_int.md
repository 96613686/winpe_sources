# ScQueryServiceStatus(CServiceRecord *,STATUS_UNION,int,int)

- ea: `0x14001c738`
- end: `0x14001c873`
- name: `?ScQueryServiceStatus@@YAKPEAVCServiceRecord@@TSTATUS_UNION@@HH@Z`
- size: `315`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x140021f74`
- `0x140037084`
- `0x140038a8c`
- `0x1400425e8`
- `0x14006d170`

## callees

- `0x140005584`
- `0x14001c738`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001c7cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001c7cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001c83c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001c83c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001c7a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001c7a8`
- `ntdll!RtlAcquireResourceExclusive` at `0x14001c774`
- `ntdll!RtlAcquireResourceExclusive` at `0x14001c774`
- `ntdll!RtlReleaseResource` at `0x14001c7b5`
- `ntdll!RtlReleaseResource` at `0x14001c849`
- `ntdll!RtlReleaseResource` at `0x14001c7b5`
- `ntdll!RtlReleaseResource` at `0x14001c849`
- `ntdll!RtlAcquireResourceShared` at `0x14001c7c2`
- `ntdll!RtlAcquireResourceShared` at `0x14001c7c2`

## pseudocode

```c

```
