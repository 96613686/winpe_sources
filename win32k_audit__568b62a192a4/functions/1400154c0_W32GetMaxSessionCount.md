# W32GetMaxSessionCount

- ea: `0x1400154c0`
- end: `0x140015518`
- name: `W32GetMaxSessionCount`
- size: `88`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x14001ba4c`
- `0x14001be9c`
- `0x14001bfbc`
- `0x14001c094`
- `0x14001c164`
- `0x14001c234`
- `0x14001c300`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400154f6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400154f6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400154db`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400154db`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015502`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015502`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400154c6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400154c6`

## pseudocode

```c

```
