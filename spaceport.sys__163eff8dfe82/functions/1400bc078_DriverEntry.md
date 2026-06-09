# DriverEntry

- ea: `0x1400bc078`
- end: `0x1400bc1f7`
- name: `DriverEntry`
- size: `383`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400bc010`

## callees

- `0x140035bf0`
- `0x1400a43c4`
- `0x1400a73f0`
- `0x1400a7af4`
- `0x1400a7b88`
- `0x1400b3ea0`
- `0x1400bc078`
- `0x1400bc200`

## import_xrefs

- `ntoskrnl!EtwSetInformation` at `0x1400bc111`
- `ntoskrnl!EtwSetInformation` at `0x1400bc111`
- `ntoskrnl!IoReportDetectedDevice` at `0x1400bc1bc`
- `ntoskrnl!IoReportDetectedDevice` at `0x1400bc1bc`

## pseudocode

```c

```
