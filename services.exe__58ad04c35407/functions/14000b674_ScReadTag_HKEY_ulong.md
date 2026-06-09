# ScReadTag(HKEY__ *,ulong *)

- ea: `0x14000b674`
- end: `0x14000b7dd`
- name: `?ScReadTag@@YAKPEAUHKEY__@@PEAK@Z`
- size: `361`
- prototype: `unsigned int __fastcall(HKEY KeyHandle, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000b2e4`
- `0x1400108c0`

## callees

- `0x14000b674`
- `0x140019014`
- `0x14001f99c`
- `0x140092420`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14000b74e`
- `ntdll!RtlNtStatusToDosError` at `0x14000b74e`
- `ntdll!RtlInitUnicodeString` at `0x14000b6ad`
- `ntdll!RtlInitUnicodeString` at `0x14000b6ad`
- `ntdll!RtlFreeHeap` at `0x14000b746`
- `ntdll!RtlFreeHeap` at `0x14000b746`
- `ntdll!NtQueryValueKey` at `0x14000b711`
- `ntdll!NtQueryValueKey` at `0x14000b711`
- `ntdll!RtlAllocateHeap` at `0x14000b6d1`
- `ntdll!RtlAllocateHeap` at `0x14000b6d1`

## pseudocode

```c

```
