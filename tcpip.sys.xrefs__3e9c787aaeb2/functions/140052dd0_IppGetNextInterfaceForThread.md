# IppGetNextInterfaceForThread

- ea: `0x140052dd0`
- end: `0x1400530c5`
- name: `IppGetNextInterfaceForThread`
- size: `757`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140024170`
- `0x14005151c`
- `0x140051c00`
- `0x14007ac50`
- `0x14007c640`
- `0x1400f6880`
- `0x14011edf0`

## callees

- `0x140052dd0`
- `0x1401c1aa0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140052e22`
- `ntoskrnl!KfRaiseIrql` at `0x140052f08`
- `ntoskrnl!KfRaiseIrql` at `0x140052e22`
- `ntoskrnl!KfRaiseIrql` at `0x140052f08`
- `ntoskrnl!KeLowerIrql` at `0x140052ed8`
- `ntoskrnl!KeLowerIrql` at `0x140052fd1`
- `ntoskrnl!KeLowerIrql` at `0x140053039`
- `ntoskrnl!KeLowerIrql` at `0x140052ed8`
- `ntoskrnl!KeLowerIrql` at `0x140052fd1`
- `ntoskrnl!KeLowerIrql` at `0x140053039`
- `ntoskrnl!IoQueueWorkItem` at `0x140053092`
- `ntoskrnl!IoQueueWorkItem` at `0x140053092`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140052e64`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140052f4c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140052e64`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140052f4c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140052e79`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140052f62`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140052e79`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140052f62`
- `ntoskrnl!KeTestSpinLock` at `0x140052e48`
- `ntoskrnl!KeTestSpinLock` at `0x140052f2f`
- `ntoskrnl!KeTestSpinLock` at `0x140052e48`
- `ntoskrnl!KeTestSpinLock` at `0x140052f2f`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140052e0a`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140052e0a`

## pseudocode

```c

```
