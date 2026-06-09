# VhdmpiQueryDependentDisk

- ea: `0x1400a9388`
- end: `0x1400a9a94`
- name: `VhdmpiQueryDependentDisk`
- size: `1804`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140018f9c`

## callees

- `0x14001e350`
- `0x14001f9ac`
- `0x14002269c`
- `0x140023980`
- `0x140024004`
- `0x1400273e4`
- `0x140034514`
- `0x140036284`
- `0x14005de00`
- `0x14005e100`
- `0x1400a9388`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400a9522`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a9522`
- `FSDEPENDS!DependentFSReferenceDependency` at `0x1400a9893`
- `FSDEPENDS!DependentFSReferenceDependency` at `0x1400a9907`
- `FSDEPENDS!DependentFSReferenceDependency` at `0x1400a9893`
- `FSDEPENDS!DependentFSReferenceDependency` at `0x1400a9907`

## string_xrefs

- `0x1400a954d`: `VhdmpiQueryDependentDisk: registration complete failed (0x%08x)`

## pseudocode

```c

```
