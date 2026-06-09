# ScDeleteFlagIsSet(HKEY__ *)

- ea: `0x140030590`
- end: `0x140030677`
- name: `?ScDeleteFlagIsSet@@YAHPEAUHKEY__@@@Z`
- size: `231`
- prototype: `__int64 __fastcall(HKEY KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400108c0`

## callees

- `0x14001f99c`
- `0x140030590`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14003065d`
- `ntdll!RtlNtStatusToDosError` at `0x14003065d`
- `ntdll!RtlInitUnicodeString` at `0x1400305b8`
- `ntdll!RtlInitUnicodeString` at `0x1400305b8`
- `ntdll!RtlFreeHeap` at `0x140030655`
- `ntdll!RtlFreeHeap` at `0x140030655`
- `ntdll!NtQueryValueKey` at `0x14003063b`
- `ntdll!NtQueryValueKey` at `0x14003063b`
- `ntdll!RtlAllocateHeap` at `0x1400305da`
- `ntdll!RtlAllocateHeap` at `0x1400305da`

## string_xrefs

- `0x1400305ad`: `DeleteFlag`

## pseudocode

```c

```
