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

- `0x140018afc`

## callees

- `0x14001df30`
- `0x14001f58c`
- `0x14002227c`
- `0x140023560`
- `0x140023be4`
- `0x140026ec0`
- `0x140034054`
- `0x140035e94`
- `0x14005da00`
- `0x14005dd00`
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
