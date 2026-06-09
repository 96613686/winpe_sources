# ScReadServiceType(HKEY__ *,ulong *)

- ea: `0x14000b7e4`
- end: `0x14000b94f`
- name: `?ScReadServiceType@@YAKPEAUHKEY__@@PEAK@Z`
- size: `363`
- prototype: `unsigned int __fastcall(HKEY KeyHandle, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x14000b2e4`
- `0x1400108c0`
- `0x140068b60`

## callees

- `0x14000b7e4`
- `0x140019014`
- `0x14001f99c`
- `0x140092420`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14000b8be`
- `ntdll!RtlNtStatusToDosError` at `0x14000b8be`
- `ntdll!RtlInitUnicodeString` at `0x14000b81d`
- `ntdll!RtlInitUnicodeString` at `0x14000b81d`
- `ntdll!RtlFreeHeap` at `0x14000b8b6`
- `ntdll!RtlFreeHeap` at `0x14000b8b6`
- `ntdll!NtQueryValueKey` at `0x14000b881`
- `ntdll!NtQueryValueKey` at `0x14000b881`
- `ntdll!RtlAllocateHeap` at `0x14000b841`
- `ntdll!RtlAllocateHeap` at `0x14000b841`

## pseudocode

```c

```
