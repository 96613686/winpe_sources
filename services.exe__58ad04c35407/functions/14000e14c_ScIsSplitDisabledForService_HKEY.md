# ScIsSplitDisabledForService(HKEY__ *)

- ea: `0x14000e14c`
- end: `0x14000e27e`
- name: `?ScIsSplitDisabledForService@@YAHPEAUHKEY__@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(HKEY KeyHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x14000dc1c`

## callees

- `0x14000e14c`
- `0x14001f99c`
- `0x140092420`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14000e208`
- `ntdll!RtlNtStatusToDosError` at `0x14000e208`
- `ntdll!RtlInitUnicodeString` at `0x14000e180`
- `ntdll!RtlInitUnicodeString` at `0x14000e180`
- `ntdll!RtlFreeHeap` at `0x14000e200`
- `ntdll!RtlFreeHeap` at `0x14000e200`
- `ntdll!NtQueryValueKey` at `0x14000e1d2`
- `ntdll!NtQueryValueKey` at `0x14000e1d2`
- `ntdll!RtlAllocateHeap` at `0x14000e19f`
- `ntdll!RtlAllocateHeap` at `0x14000e19f`

## pseudocode

```c

```
