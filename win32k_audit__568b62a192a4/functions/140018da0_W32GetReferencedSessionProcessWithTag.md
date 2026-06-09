# W32GetReferencedSessionProcessWithTag

- ea: `0x140018da0`
- end: `0x140018e8a`
- name: `W32GetReferencedSessionProcessWithTag`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14001be9c`
- `0x14001bf54`
- `0x14001bfbc`
- `0x14001c094`
- `0x14001c164`
- `0x14001c234`

## callees

- `0x140005e50`
- `0x140018da0`

## import_xrefs

- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140018e24`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140018e24`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140018e44`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140018e65`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140018e44`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140018e65`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140018dc5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140018e06`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140018dc5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140018e06`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018e50`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018e71`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018e50`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018e71`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018db0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018df1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018db0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018df1`

## pseudocode

```c

```
