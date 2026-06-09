# UbpmpRegistryChangeCallback(void *,uchar,void *)

- ea: `0x1800343b0`
- end: `0x180034495`
- name: `?UbpmpRegistryChangeCallback@@YAXPEAXE0@Z`
- size: `229`
- prototype: `void __fastcall(void *, unsigned __int8, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180034034`

## callees

- `0x18001e9f4`
- `0x1800343b0`
- `0x180035a24`
- `0x18003e010`

## import_xrefs

- `ntdll!NtNotifyChangeKey` at `0x180034412`
- `ntdll!NtNotifyChangeKey` at `0x180034412`
- `ntdll!RtlNtStatusToDosError` at `0x18003441e`
- `ntdll!RtlNtStatusToDosError` at `0x18003441e`

## pseudocode

```c

```
