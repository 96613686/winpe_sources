# W32SessionUninitialize

- ea: `0x14001c980`
- end: `0x14001ca48`
- name: `W32SessionUninitialize`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14001aef0`
- `0x1400ba080`

## callees

- `0x140005d20`
- `0x140005d8c`
- `0x14001c72c`
- `0x14001c980`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001ca1d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001ca1d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ca29`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ca29`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c98f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c98f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001c9a4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001c9a4`

## pseudocode

```c

```
