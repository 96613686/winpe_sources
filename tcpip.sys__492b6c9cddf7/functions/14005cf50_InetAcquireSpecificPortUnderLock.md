# InetAcquireSpecificPortUnderLock

- ea: `0x14005cf50`
- end: `0x14005d373`
- name: `InetAcquireSpecificPortUnderLock`
- size: `1059`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, __int16, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14005c4b8`

## callees

- `0x14005cf50`
- `0x14005def0`
- `0x14005e060`
- `0x14005e0c0`
- `0x14005e300`
- `0x14005e324`
- `0x14005e7c0`
- `0x140060360`
- `0x14014f4c0`
- `0x1401527bc`
- `0x140152b88`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!RtlClearBit` at `0x1401c5080`
- `ntoskrnl!RtlClearBit` at `0x1401c5080`
- `ntoskrnl!RtlSetBit` at `0x14005d0b1`
- `ntoskrnl!RtlSetBit` at `0x14005d0b1`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005d34d`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005d34d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d01b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d26c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d01b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d26c`
- `ntoskrnl!PsGetProcessId` at `0x14005d35f`
- `ntoskrnl!PsGetProcessId` at `0x14005d35f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d18b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d295`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d2b4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d2e7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d18b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d295`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d2b4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d2e7`

## pseudocode

```c

```
