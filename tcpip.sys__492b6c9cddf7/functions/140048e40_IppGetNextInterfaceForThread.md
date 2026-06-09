# IppGetNextInterfaceForThread

- ea: `0x140048e40`
- end: `0x140049135`
- name: `IppGetNextInterfaceForThread`
- size: `757`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140048cf0`
- `0x14004931c`
- `0x140049a00`
- `0x14004b7e0`
- `0x140064f60`
- `0x1400e1cb0`
- `0x1400ef300`

## callees

- `0x140048e40`
- `0x1401bfe60`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140048e92`
- `ntoskrnl!KfRaiseIrql` at `0x140048f78`
- `ntoskrnl!KfRaiseIrql` at `0x140048e92`
- `ntoskrnl!KfRaiseIrql` at `0x140048f78`
- `ntoskrnl!KeLowerIrql` at `0x140048f48`
- `ntoskrnl!KeLowerIrql` at `0x140049041`
- `ntoskrnl!KeLowerIrql` at `0x1400490a9`
- `ntoskrnl!KeLowerIrql` at `0x140048f48`
- `ntoskrnl!KeLowerIrql` at `0x140049041`
- `ntoskrnl!KeLowerIrql` at `0x1400490a9`
- `ntoskrnl!IoQueueWorkItem` at `0x140049102`
- `ntoskrnl!IoQueueWorkItem` at `0x140049102`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140048ed4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140048fbc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140048ed4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140048fbc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140048ee9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140048fd2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140048ee9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140048fd2`
- `ntoskrnl!KeTestSpinLock` at `0x140048eb8`
- `ntoskrnl!KeTestSpinLock` at `0x140048f9f`
- `ntoskrnl!KeTestSpinLock` at `0x140048eb8`
- `ntoskrnl!KeTestSpinLock` at `0x140048f9f`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140048e7a`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140048e7a`

## pseudocode

```c

```
