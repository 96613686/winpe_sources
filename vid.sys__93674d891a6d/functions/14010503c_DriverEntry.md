# DriverEntry

- ea: `0x14010503c`
- end: `0x1401052cb`
- name: `DriverEntry`
- size: `655`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x140015724`

## callees

- `0x140006b68`
- `0x14000a010`
- `0x140020ac8`
- `0x140021c60`
- `0x140021db0`
- `0x140021e00`
- `0x14002f724`
- `0x1400840e4`
- `0x140084178`
- `0x14008455c`
- `0x14009b7a4`
- `0x14009b7f8`
- `0x14010503c`
- `0x1401052d4`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x1401050da`
- `ntoskrnl!EtwActivityIdControl` at `0x1401050ed`
- `ntoskrnl!EtwActivityIdControl` at `0x14010528b`
- `ntoskrnl!EtwActivityIdControl` at `0x1401050da`
- `ntoskrnl!EtwActivityIdControl` at `0x1401050ed`
- `ntoskrnl!EtwActivityIdControl` at `0x14010528b`
- `ntoskrnl!InitSafeBootMode` at `0x14010515f`
- `winhvr!WinHvReportPresentHypervisor` at `0x14010517c`
- `winhvr!WinHvReportPresentHypervisor` at `0x14010517c`

## pseudocode

```c

```
