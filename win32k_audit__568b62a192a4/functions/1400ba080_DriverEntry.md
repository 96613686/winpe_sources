# DriverEntry

- ea: `0x1400ba080`
- end: `0x1400ba2fe`
- name: `DriverEntry`
- size: `638`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1400ba010`

## callees

- `0x140003330`
- `0x1400057b8`
- `0x14000b828`
- `0x14000f89c`
- `0x14001313c`
- `0x1400186c0`
- `0x140018994`
- `0x14001af8c`
- `0x14001ba10`
- `0x14001c7c0`
- `0x14001c8d0`
- `0x1400272cc`
- `0x14006d6f0`
- `0x1400ba080`
- `0x1400ba304`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400ba236`
- `ntoskrnl!KeInitializeEvent` at `0x1400ba236`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba2aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba2aa`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba10b`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba1bd`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba10b`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba1bd`
- `ntoskrnl!PsEstablishWin32Callouts` at `0x1400ba274`
- `ntoskrnl!PsEstablishWin32Callouts` at `0x1400ba274`
- `ntoskrnl!PsUnEstablishWin32Callouts` at `0x1400ba1e3`
- `ntoskrnl!PsUnEstablishWin32Callouts` at `0x1400ba1e3`
- `ntoskrnl!KeBugCheckEx` at `0x1400ba20f`
- `ntoskrnl!KeBugCheckEx` at `0x1400ba20f`

## pseudocode

```c

```
