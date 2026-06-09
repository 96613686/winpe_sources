# ScRegisterServicesForTriggerAction(ulong)

- ea: `0x14002bf90`
- end: `0x14002c1cb`
- name: `?ScRegisterServicesForTriggerAction@@YAXK@Z`
- size: `571`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task`

## callers

- `0x140039bd4`

## callees

- `0x140003310`
- `0x140003e54`
- `0x140004c98`
- `0x140005464`
- `0x140007130`
- `0x14000bebc`
- `0x14001c87c`
- `0x140020d84`
- `0x1400265ac`
- `0x14002bf90`
- `0x14003ab5c`
- `0x1400575b0`
- `0x14007b640`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14002bfd6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14002bfd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002bff7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14002bff7`
- `ntdll!RtlReleaseResource` at `0x14002c1b0`
- `ntdll!RtlReleaseResource` at `0x14002c1b0`
- `ntdll!RtlAcquireResourceShared` at `0x14002bfc9`
- `ntdll!RtlAcquireResourceShared` at `0x14002bfc9`
- `ntdll!NtClose` at `0x14002c106`
- `ntdll!NtClose` at `0x14002c19b`
- `ntdll!NtClose` at `0x14002c106`
- `ntdll!NtClose` at `0x14002c19b`
- `ntdll!RtlNtStatusToDosError` at `0x14002c10e`
- `ntdll!RtlNtStatusToDosError` at `0x14002c1a3`
- `ntdll!RtlNtStatusToDosError` at `0x14002c10e`
- `ntdll!RtlNtStatusToDosError` at `0x14002c1a3`

## pseudocode

```c

```
