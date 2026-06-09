# StorpWatchForRegistryChanges

- ea: `0x14009ce20`
- end: `0x14009cf0a`
- name: `StorpWatchForRegistryChanges`
- size: `234`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14008e7b0`
- `0x1400cda60`
- `0x1400ff080`
- `0x1401c0fd0`

## callees

- `0x14009ce20`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14009ce34`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14009ce34`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14009ce4b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14009ce4b`
- `ntoskrnl!KeSetEvent` at `0x14009cef4`
- `ntoskrnl!KeSetEvent` at `0x14009cef4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009cecb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009cecb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009ced7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009ced7`
- `ntoskrnl!ZwNotifyChangeKey` at `0x14009ce91`
- `ntoskrnl!ZwNotifyChangeKey` at `0x14009ce91`

## pseudocode

```c

```
