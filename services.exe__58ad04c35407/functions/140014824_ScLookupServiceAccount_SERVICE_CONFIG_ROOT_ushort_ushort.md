# ScLookupServiceAccount(_SERVICE_CONFIG_ROOT *,ushort *,ushort * *)

- ea: `0x140014824`
- end: `0x140014a84`
- name: `?ScLookupServiceAccount@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEAGPEAPEAG@Z`
- size: `608`
- prototype: `unsigned int __fastcall(struct _SERVICE_CONFIG_ROOT *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1400381d4`
- `0x14003ae4c`
- `0x14003c510`
- `0x1400644c0`
- `0x14006e990`

## callees

- `0x140004c58`
- `0x140008b90`
- `0x14000c310`
- `0x140014824`
- `0x140015020`
- `0x1400188fc`
- `0x140028114`
- `0x14004b1c0`
- `0x140057fb0`
- `0x140058030`
- `0x1400646ec`

## import_xrefs

- `ntdll!NtClose` at `0x140014891`
- `ntdll!NtClose` at `0x140014891`
- `ntdll!RtlNtStatusToDosError` at `0x140014899`
- `ntdll!RtlNtStatusToDosError` at `0x140014899`
- `ntdll!RtlFreeHeap` at `0x140014926`
- `ntdll!RtlFreeHeap` at `0x1400149e3`
- `ntdll!RtlFreeHeap` at `0x140014926`
- `ntdll!RtlFreeHeap` at `0x1400149e3`

## pseudocode

```c

```
