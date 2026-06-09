# W32SessionUninitialize

- ea: `0x14001c8d0`
- end: `0x14001c998`
- name: `W32SessionUninitialize`
- size: `200`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14001aea0`
- `0x1400ba080`

## callees

- `0x140005d20`
- `0x140005d8c`
- `0x14001c67c`
- `0x14001c8d0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001c96d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001c96d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c979`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c979`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c8df`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c8df`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001c8f4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001c8f4`

## pseudocode

```c

```
