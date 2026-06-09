# NvmeAdapterDirectedPowerDownRequestD3

- ea: `0x140139360`
- end: `0x14013955b`
- name: `NvmeAdapterDirectedPowerDownRequestD3`
- size: `507`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1401392c0`
- `0x140139570`

## callees

- `0x14003e538`
- `0x140139360`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x140139424`
- `ntoskrnl!IoQueueWorkItem` at `0x140139424`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140139390`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140139475`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140139390`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140139475`
- `ntoskrnl!PoFxCompleteDirectedPowerDown` at `0x140139536`
- `ntoskrnl!PoFxCompleteDirectedPowerDown` at `0x140139536`
- `ntoskrnl!PoRequestPowerIrp` at `0x140139457`
- `ntoskrnl!PoRequestPowerIrp` at `0x1401394cc`
- `ntoskrnl!PoRequestPowerIrp` at `0x140139457`
- `ntoskrnl!PoRequestPowerIrp` at `0x1401394cc`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401393e2`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401393e2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401393d6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401394e4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013951c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401393d6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401394e4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013951c`

## pseudocode

```c

```
