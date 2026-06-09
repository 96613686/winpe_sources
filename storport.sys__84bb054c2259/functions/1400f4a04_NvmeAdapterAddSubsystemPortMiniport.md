# NvmeAdapterAddSubsystemPortMiniport

- ea: `0x1400f4a04`
- end: `0x1400f4d43`
- name: `NvmeAdapterAddSubsystemPortMiniport`
- size: `831`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400a0970`

## callees

- `0x1400f4130`
- `0x1400f4a04`
- `0x1400f76c0`
- `0x1400fa14c`
- `0x1400fa1d0`
- `0x1400faa90`
- `0x14014b400`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f4c14`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f4c14`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400f4c2d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400f4c2d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f4c6c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f4c6c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f4d0b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f4d0b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f4c78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f4c78`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f4a46`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f4a46`

## pseudocode

```c

```
