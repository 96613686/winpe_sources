# LoadExtensionDriver

- ea: `0x14009a690`
- end: `0x14009a9a9`
- name: `LoadExtensionDriver`
- size: `793`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140098ba8`

## callees

- `0x14009a690`
- `0x14009a9b0`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14009a966`
- `ntoskrnl!ObfDereferenceObject` at `0x14009a966`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009a719`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009a74f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009a719`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009a74f`
- `ntoskrnl!IofCallDriver` at `0x14009a805`
- `ntoskrnl!IofCallDriver` at `0x14009a805`
- `ntoskrnl!KeInitializeEvent` at `0x14009a79b`
- `ntoskrnl!KeInitializeEvent` at `0x14009a79b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009a830`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009a830`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14009a76d`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14009a76d`
- `ntoskrnl!ZwUnloadDriver` at `0x14009a97c`
- `ntoskrnl!ZwUnloadDriver` at `0x14009a97c`
- `ntoskrnl!ZwLoadDriver` at `0x14009a72a`
- `ntoskrnl!ZwLoadDriver` at `0x14009a72a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14009a7e3`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14009a7e3`

## string_xrefs

- `0x14009a70a`: `\Registry\Machine\System\CurrentControlSet\Services\StorportExt`

## pseudocode

```c

```
