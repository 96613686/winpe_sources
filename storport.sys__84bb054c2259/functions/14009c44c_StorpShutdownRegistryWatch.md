# StorpShutdownRegistryWatch

- ea: `0x14009c44c`
- end: `0x14009c4ec`
- name: `StorpShutdownRegistryWatch`
- size: `160`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x14000ec74`
- `0x1400cef20`
- `0x14018e72c`
- `0x1401a8144`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14009c4d4`
- `ntoskrnl!ExDeleteResourceLite` at `0x14009c4d4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14009c459`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14009c459`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14009c46e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14009c46e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009c495`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009c495`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009c4c5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009c4c5`
- `ntoskrnl!ZwClose` at `0x14009c47e`
- `ntoskrnl!ZwClose` at `0x14009c47e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009c4a1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009c4a1`

## pseudocode

```c

```
