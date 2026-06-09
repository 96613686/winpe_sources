# VhdmpiGetVolumeDriveLetter

- ea: `0x1400d0d74`
- end: `0x1400d0feb`
- name: `VhdmpiGetVolumeDriveLetter`
- size: `631`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x1400d0bf8`
- `0x1400ec0d8`

## callees

- `0x14005da00`
- `0x1400d0d74`

## import_xrefs

- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d0eba`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d0eba`
- `ntoskrnl!IofCallDriver` at `0x1400d0ed6`
- `ntoskrnl!IofCallDriver` at `0x1400d0ed6`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400d0de5`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400d0de5`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d0fc0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d0fc0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d0dc8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d0dc8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d0f00`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d0f00`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0f22`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0f94`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0fab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0f22`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0f94`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0fab`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0e14`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0e73`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0f52`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0e14`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0e73`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0f52`
- `ntoskrnl!KeInitializeEvent` at `0x1400d0e5d`
- `ntoskrnl!KeInitializeEvent` at `0x1400d0e5d`

## string_xrefs

- `0x1400d0dab`: `\Device\MountPointManager`

## pseudocode

```c

```
