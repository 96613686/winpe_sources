# UbpmpRegistryChangeCallback(void *,uchar,void *)

- ea: `0x180036810`
- end: `0x180036902`
- name: `?UbpmpRegistryChangeCallback@@YAXPEAXE0@Z`
- size: `242`
- prototype: `void __fastcall(void *, unsigned __int8, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180036484`

## callees

- `0x18001af64`
- `0x180036810`
- `0x180037f84`
- `0x180041010`

## import_xrefs

- `ntdll!NtNotifyChangeKey` at `0x180036872`
- `ntdll!NtNotifyChangeKey` at `0x180036872`
- `ntdll!RtlNtStatusToDosError` at `0x180036884`
- `ntdll!RtlNtStatusToDosError` at `0x180036884`

## pseudocode

```c

```
