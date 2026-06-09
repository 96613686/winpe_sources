# VhdmpiGetVolumeDriveLetter

- ea: `0x1400d0d04`
- end: `0x1400d0f7b`
- name: `VhdmpiGetVolumeDriveLetter`
- size: `631`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x1400d0b88`
- `0x1400ec068`

## callees

- `0x14005de00`
- `0x1400d0d04`

## import_xrefs

- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d0e4a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d0e4a`
- `ntoskrnl!IofCallDriver` at `0x1400d0e66`
- `ntoskrnl!IofCallDriver` at `0x1400d0e66`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400d0d75`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400d0d75`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d0f50`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d0f50`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d0d58`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d0d58`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d0e90`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d0e90`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0eb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0f24`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0f3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0eb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0f24`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0f3b`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0da4`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0e03`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0ee2`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0da4`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0e03`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0ee2`
- `ntoskrnl!KeInitializeEvent` at `0x1400d0ded`
- `ntoskrnl!KeInitializeEvent` at `0x1400d0ded`

## string_xrefs

- `0x1400d0d3b`: `\Device\MountPointManager`

## pseudocode

```c

```
