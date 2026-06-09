# VhdmpiInitializeFileWrapper

- ea: `0x1400ec068`
- end: `0x1400ecaaa`
- name: `VhdmpiInitializeFileWrapper`
- size: `2626`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, __int64, _OWORD *, int, const UNICODE_STRING *, __int16, UNICODE_STRING *SourceString)`
- caller_count: `4`
- callee_count: `27`
- tags: ``

## callers

- `0x14004c4ec`
- `0x1400a44d0`
- `0x1400c5f88`
- `0x1400e55ec`

## callees

- `0x140001130`
- `0x140019674`
- `0x140020c94`
- `0x140023460`
- `0x14002377c`
- `0x140023980`
- `0x140026e20`
- `0x14002e58c`
- `0x14002e5f8`
- `0x14002e6d0`
- `0x140036284`
- `0x14005dbb0`
- `0x14005e100`
- `0x14009d9a4`
- `0x14009e0d0`
- `0x14009e1c0`
- `0x14009e358`
- `0x1400ac4f8`
- `0x1400ca1b0`
- `0x1400d0d04`
- `0x1400e4f28`
- `0x1400e63f4`
- `0x1400e6610`
- `0x1400e70cc`
- `0x1400ebb10`
- `0x1400ec068`
- `0x1400ecab0`

## import_xrefs

- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400ec53d`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400ec53d`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400ec25a`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400ec25a`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400ec8d0`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400ec8d0`
- `ntoskrnl!ObfReferenceObject` at `0x1400ec270`
- `ntoskrnl!ObfReferenceObject` at `0x1400ec9bf`
- `ntoskrnl!ObfReferenceObject` at `0x1400ec270`
- `ntoskrnl!ObfReferenceObject` at `0x1400ec9bf`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400ec589`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400ec5c2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400ec589`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400ec5c2`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ec45a`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ec45a`
- `FSDEPENDS!DependentFSCheckFileHandle` at `0x1400ec7e7`
- `FSDEPENDS!DependentFSCheckFileHandle` at `0x1400ec7e7`

## string_xrefs

- `0x1400ec78e`: `Filewrapper flags for '%wZ': IsABC: %d, IsReFS: %d, IsSparse: %d, IsSmb: %d, IsCsv: %d, IsLoopback: %d, OnReadOnlyVolume: %d, SupportsReFSDuplicateExtents: %d, SupportsReFSSparseVDL: %d`

## pseudocode

```c

```
