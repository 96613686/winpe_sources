# ScReadErrorControl(HKEY__ *,ulong *)

- ea: `0x14000b958`
- end: `0x14000bac1`
- name: `?ScReadErrorControl@@YAKPEAUHKEY__@@PEAK@Z`
- size: `361`
- prototype: `unsigned int __fastcall(HKEY KeyHandle, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000b2e4`
- `0x1400108c0`
- `0x140068b60`

## callees

- `0x14000b958`
- `0x140019014`
- `0x14001f99c`
- `0x140092420`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14000ba32`
- `ntdll!RtlNtStatusToDosError` at `0x14000ba32`
- `ntdll!RtlInitUnicodeString` at `0x14000b991`
- `ntdll!RtlInitUnicodeString` at `0x14000b991`
- `ntdll!RtlFreeHeap` at `0x14000ba2a`
- `ntdll!RtlFreeHeap` at `0x14000ba2a`
- `ntdll!NtQueryValueKey` at `0x14000b9f5`
- `ntdll!NtQueryValueKey` at `0x14000b9f5`
- `ntdll!RtlAllocateHeap` at `0x14000b9b5`
- `ntdll!RtlAllocateHeap` at `0x14000b9b5`

## pseudocode

```c

```
