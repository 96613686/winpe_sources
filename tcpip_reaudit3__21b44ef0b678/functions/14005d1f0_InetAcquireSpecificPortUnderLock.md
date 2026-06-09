# InetAcquireSpecificPortUnderLock

- ea: `0x14005d1f0`
- end: `0x14005d613`
- name: `InetAcquireSpecificPortUnderLock`
- size: `1059`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, __int16, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14005c758`

## callees

- `0x14005d1f0`
- `0x14005e190`
- `0x14005e300`
- `0x14005e360`
- `0x14005e5a0`
- `0x14005e5c4`
- `0x14005ea60`
- `0x140060600`
- `0x14014f600`
- `0x1401528fc`
- `0x140152cc8`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!RtlClearBit` at `0x1401c51c0`
- `ntoskrnl!RtlClearBit` at `0x1401c51c0`
- `ntoskrnl!RtlSetBit` at `0x14005d351`
- `ntoskrnl!RtlSetBit` at `0x14005d351`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005d5ed`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005d5ed`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d2bb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d50c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d2bb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d50c`
- `ntoskrnl!PsGetProcessId` at `0x14005d5ff`
- `ntoskrnl!PsGetProcessId` at `0x14005d5ff`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d42b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d535`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d554`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d587`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d42b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d535`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d554`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d587`

## pseudocode

```c

```
