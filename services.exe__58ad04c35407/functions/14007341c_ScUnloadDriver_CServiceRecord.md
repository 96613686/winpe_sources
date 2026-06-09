# ScUnloadDriver(CServiceRecord *)

- ea: `0x14007341c`
- end: `0x140073594`
- name: `?ScUnloadDriver@@YAKPEAVCServiceRecord@@@Z`
- size: `376`
- prototype: `unsigned int __fastcall(struct CServiceRecord *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1400731bc`

## callees

- `0x140004c58`
- `0x14000cee0`
- `0x1400188fc`
- `0x14001a230`
- `0x14002b304`
- `0x140036514`
- `0x14007341c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14007354f`
- `ntdll!RtlNtStatusToDosError` at `0x14007354f`
- `ntdll!RtlInitUnicodeString` at `0x14007349d`
- `ntdll!RtlInitUnicodeString` at `0x14007349d`
- `ntdll!RtlFreeHeap` at `0x1400734d2`
- `ntdll!RtlFreeHeap` at `0x140073503`
- `ntdll!RtlFreeHeap` at `0x1400734d2`
- `ntdll!RtlFreeHeap` at `0x140073503`
- `ntdll!NtUnloadDriver` at `0x1400734e4`
- `ntdll!NtUnloadDriver` at `0x1400734e4`
- `ntdll!RtlAllocateHeap` at `0x14007345e`
- `ntdll!RtlAllocateHeap` at `0x14007345e`

## string_xrefs

- `0x140073474`: `\Registry\Machine\System\CurrentControlSet\Services\`

## pseudocode

```c

```
