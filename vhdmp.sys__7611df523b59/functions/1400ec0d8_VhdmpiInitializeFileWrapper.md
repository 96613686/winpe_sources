# VhdmpiInitializeFileWrapper

- ea: `0x1400ec0d8`
- end: `0x1400ecb1a`
- name: `VhdmpiInitializeFileWrapper`
- size: `2626`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, __int64, _OWORD *, int, const UNICODE_STRING *, __int16, UNICODE_STRING *SourceString)`
- caller_count: `4`
- callee_count: `27`
- tags: ``

## callers

- `0x14004c0fc`
- `0x1400a44d0`
- `0x1400c5f98`
- `0x1400e565c`

## callees

- `0x140001130`
- `0x1400191d4`
- `0x140020874`
- `0x140023040`
- `0x14002335c`
- `0x140023560`
- `0x140026a00`
- `0x14002e0cc`
- `0x14002e138`
- `0x14002e210`
- `0x140035e94`
- `0x14005d7c0`
- `0x14005dd00`
- `0x14009d9a4`
- `0x14009e0d0`
- `0x14009e1c0`
- `0x14009e358`
- `0x1400ac4f8`
- `0x1400ca1c0`
- `0x1400d0d74`
- `0x1400e4f98`
- `0x1400e6464`
- `0x1400e6680`
- `0x1400e713c`
- `0x1400ebb80`
- `0x1400ec0d8`
- `0x1400ecb20`

## import_xrefs

- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400ec5ad`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400ec5ad`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400ec2ca`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400ec2ca`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400ec940`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400ec940`
- `ntoskrnl!ObfReferenceObject` at `0x1400ec2e0`
- `ntoskrnl!ObfReferenceObject` at `0x1400eca2f`
- `ntoskrnl!ObfReferenceObject` at `0x1400ec2e0`
- `ntoskrnl!ObfReferenceObject` at `0x1400eca2f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400ec5f9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400ec632`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400ec5f9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400ec632`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ec4ca`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ec4ca`
- `FSDEPENDS!DependentFSCheckFileHandle` at `0x1400ec857`
- `FSDEPENDS!DependentFSCheckFileHandle` at `0x1400ec857`

## string_xrefs

- `0x1400ec7fe`: `Filewrapper flags for '%wZ': IsABC: %d, IsReFS: %d, IsSparse: %d, IsSmb: %d, IsCsv: %d, IsLoopback: %d, OnReadOnlyVolume: %d, SupportsReFSDuplicateExtents: %d, SupportsReFSSparseVDL: %d`

## pseudocode

```c

```
