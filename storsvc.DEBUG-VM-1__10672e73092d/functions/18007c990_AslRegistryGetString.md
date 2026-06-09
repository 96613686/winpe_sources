# AslRegistryGetString

- ea: `0x18007c990`
- end: `0x18007cb50`
- name: `AslRegistryGetString`
- size: `448`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180079f08`
- `0x18007a8e8`
- `0x18007cb58`

## callees

- `0x18007c970`
- `0x18007c990`
- `0x18007ceb4`
- `0x18007d3a0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18007c9bf`
- `ntdll!RtlInitUnicodeString` at `0x18007c9bf`
- `ntdll!ZwQueryValueKey` at `0x18007c9e6`
- `ntdll!ZwQueryValueKey` at `0x18007caa5`
- `ntdll!ZwQueryValueKey` at `0x18007c9e6`
- `ntdll!ZwQueryValueKey` at `0x18007caa5`
- `ntdll!RtlAllocateHeap` at `0x18007ca4e`
- `ntdll!RtlAllocateHeap` at `0x18007ca4e`

## string_xrefs

- `0x18007ca18`: `AslRegistryGetString`
- `0x18007ca69`: `AslRegistryGetString`
- `0x18007cad7`: `AslRegistryGetString`
- `0x18007cb1a`: `AslRegistryGetString`

## pseudocode

```c

```
