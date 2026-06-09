# FreePerSessionWin32kCall

- ea: `0x14002737c`
- end: `0x140027446`
- name: `FreePerSessionWin32kCall`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001aef0`
- `0x1400ba080`

## callees

- `0x14002737c`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002741b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002741b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140027427`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140027427`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140027397`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140027397`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400273ac`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400273ac`
- `ntoskrnl!MmUnloadSystemImage` at `0x1400273e8`
- `ntoskrnl!MmUnloadSystemImage` at `0x1400273e8`

## pseudocode

```c

```
