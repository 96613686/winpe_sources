# CDriverRecord::StartInternal(ulong,_STRING_PTRSW *,ulong,ulong)

- ea: `0x1400735a0`
- end: `0x140073844`
- name: `?StartInternal@CDriverRecord@@MEAAKKPEAU_STRING_PTRSW@@KK@Z`
- size: `676`
- prototype: `unsigned int __fastcall(CDriverRecord *__hidden this, unsigned int, struct _STRING_PTRSW *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x140003e54`
- `0x14000cee0`
- `0x1400188fc`
- `0x14001a230`
- `0x14001c87c`
- `0x140020d84`
- `0x140026eac`
- `0x14002b304`
- `0x140036514`
- `0x1400735a0`
- `0x14007384c`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x14007382b`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x14007382b`
- `ntdll!RtlNtStatusToDosError` at `0x1400737fb`
- `ntdll!RtlNtStatusToDosError` at `0x1400737fb`
- `ntdll!RtlInitUnicodeString` at `0x1400736a2`
- `ntdll!RtlInitUnicodeString` at `0x1400736a2`
- `ntdll!RtlFreeHeap` at `0x14007381e`
- `ntdll!RtlFreeHeap` at `0x14007381e`
- `ntdll!NtLoadDriver` at `0x1400736d9`
- `ntdll!NtLoadDriver` at `0x1400736d9`
- `ntdll!RtlAllocateHeap` at `0x14007366e`
- `ntdll!RtlAllocateHeap` at `0x14007366e`

## string_xrefs

- `0x14007367c`: `\Registry\Machine\System\CurrentControlSet\Services\`

## pseudocode

```c

```
