# TcpUnbindListenerWorkQueueRoutine

- ea: `0x140125fe0`
- end: `0x140126257`
- name: `TcpUnbindListenerWorkQueueRoutine`
- size: `631`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400e8d04`

## callees

- `0x14000a8f0`
- `0x14001ea80`
- `0x140071ac0`
- `0x14007cf70`
- `0x1400b5cd4`
- `0x1400b6bc4`
- `0x1400f44bc`
- `0x140125fe0`
- `0x1401c0fd0`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14012607d`
- `ntoskrnl!KfRaiseIrql` at `0x14012607d`
- `ntoskrnl!KeLowerIrql` at `0x140126139`
- `ntoskrnl!KeLowerIrql` at `0x140126139`
- `ntoskrnl!ExRundownCompleted` at `0x140126035`
- `ntoskrnl!ExRundownCompleted` at `0x140126035`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140126026`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140126026`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14012604a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14012604a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14012614a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401261e7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14012614a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401261e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140126219`
- `ntoskrnl!ExFreePoolWithTag` at `0x140126219`

## pseudocode

```c

```
