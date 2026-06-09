# InetAcquireSpecificPortUnderLock

- ea: `0x1400b2e40`
- end: `0x1400b3263`
- name: `InetAcquireSpecificPortUnderLock`
- size: `1059`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, __int16, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400b23f8`

## callees

- `0x1400b2e40`
- `0x1400b3de0`
- `0x1400b3f50`
- `0x1400b3fb0`
- `0x1400b41f0`
- `0x1400b4214`
- `0x1400b46b0`
- `0x1400b6b20`
- `0x140151200`
- `0x1401547dc`
- `0x140154ba8`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!RtlClearBit` at `0x1401cef5c`
- `ntoskrnl!RtlClearBit` at `0x1401cef5c`
- `ntoskrnl!RtlSetBit` at `0x1400b2fa1`
- `ntoskrnl!RtlSetBit` at `0x1400b2fa1`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400b323d`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400b323d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b2f0b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b315c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b2f0b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b315c`
- `ntoskrnl!PsGetProcessId` at `0x1400b324f`
- `ntoskrnl!PsGetProcessId` at `0x1400b324f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b307b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b3185`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b31a4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b31d7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b307b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b3185`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b31a4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b31d7`

## pseudocode

```c

```
