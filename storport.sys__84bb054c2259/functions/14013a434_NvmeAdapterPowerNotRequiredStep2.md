# NvmeAdapterPowerNotRequiredStep2

- ea: `0x14013a434`
- end: `0x14013a614`
- name: `NvmeAdapterPowerNotRequiredStep2`
- size: `480`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14013a400`
- `0x14013a620`

## callees

- `0x14013a434`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14013a505`
- `ntoskrnl!IoQueueWorkItem` at `0x14013a505`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013a464`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013a556`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013a464`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013a556`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013a538`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013a5ad`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013a538`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013a5ad`
- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x14013a5f7`
- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x14013a5f7`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013a4c3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013a4c3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013a4b7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013a5dd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013a4b7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013a5dd`

## pseudocode

```c

```
