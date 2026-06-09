# ScReadServiceManagedAccount(HKEY__ *,_TRI_BOOL *)

- ea: `0x14001a350`
- end: `0x14001a4e5`
- name: `?ScReadServiceManagedAccount@@YAKPEAUHKEY__@@PEAW4_TRI_BOOL@@@Z`
- size: `405`
- prototype: `unsigned int __fastcall(HKEY KeyHandle, enum _TRI_BOOL *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x14000b2e4`
- `0x1400108c0`
- `0x140068b60`

## callees

- `0x140019014`
- `0x14001a350`
- `0x14001f99c`
- `0x140092420`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14001a41a`
- `ntdll!RtlNtStatusToDosError` at `0x14001a41a`
- `ntdll!RtlInitUnicodeString` at `0x14001a384`
- `ntdll!RtlInitUnicodeString` at `0x14001a384`
- `ntdll!RtlFreeHeap` at `0x14001a412`
- `ntdll!RtlFreeHeap` at `0x14001a412`
- `ntdll!NtQueryValueKey` at `0x14001a3e1`
- `ntdll!NtQueryValueKey` at `0x14001a3e1`
- `ntdll!RtlAllocateHeap` at `0x14001a3ac`
- `ntdll!RtlAllocateHeap` at `0x14001a3ac`

## string_xrefs

- `0x14001a370`: `ServiceAccountManaged`
- `0x14001a483`: `ServiceAccountManaged`

## pseudocode

```c

```
