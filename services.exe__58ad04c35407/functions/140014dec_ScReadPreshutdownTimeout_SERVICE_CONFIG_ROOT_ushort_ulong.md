# ScReadPreshutdownTimeout(_SERVICE_CONFIG_ROOT *,ushort *,ulong *)

- ea: `0x140014dec`
- end: `0x140015019`
- name: `?ScReadPreshutdownTimeout@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEAGPEAK@Z`
- size: `557`
- prototype: `unsigned int __fastcall(struct _SERVICE_CONFIG_ROOT *, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14000a050`
- `0x140038a8c`

## callees

- `0x140003e54`
- `0x140014dec`
- `0x140015020`
- `0x14001f99c`
- `0x140021ef4`
- `0x140092420`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014e52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014e52`
- `ntdll!RtlNtStatusToDosError` at `0x140014f1b`
- `ntdll!RtlNtStatusToDosError` at `0x140014f1b`
- `ntdll!RtlInitUnicodeString` at `0x140014e85`
- `ntdll!RtlInitUnicodeString` at `0x140014e85`
- `ntdll!RtlFreeHeap` at `0x140014f13`
- `ntdll!RtlFreeHeap` at `0x140014f13`
- `ntdll!NtQueryValueKey` at `0x140014edf`
- `ntdll!NtQueryValueKey` at `0x140014edf`
- `ntdll!RtlAllocateHeap` at `0x140014ea8`
- `ntdll!RtlAllocateHeap` at `0x140014ea8`

## pseudocode

```c

```
