# FreePerSessionWin32kCall

- ea: `0x1400272cc`
- end: `0x140027396`
- name: `FreePerSessionWin32kCall`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001aea0`
- `0x1400ba080`

## callees

- `0x1400272cc`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002736b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002736b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140027377`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140027377`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400272e7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400272e7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400272fc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400272fc`
- `ntoskrnl!MmUnloadSystemImage` at `0x140027338`
- `ntoskrnl!MmUnloadSystemImage` at `0x140027338`

## pseudocode

```c

```
