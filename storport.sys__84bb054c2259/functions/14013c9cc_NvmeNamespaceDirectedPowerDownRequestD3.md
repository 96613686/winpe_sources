# NvmeNamespaceDirectedPowerDownRequestD3

- ea: `0x14013c9cc`
- end: `0x14013cb95`
- name: `NvmeNamespaceDirectedPowerDownRequestD3`
- size: `457`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14013c890`
- `0x14013cba0`

## callees

- `0x14013c9cc`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14013ca7f`
- `ntoskrnl!IoQueueWorkItem` at `0x14013ca7f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013c9fc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013cad0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013c9fc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14013cad0`
- `ntoskrnl!PoFxCompleteDirectedPowerDown` at `0x14013cb78`
- `ntoskrnl!PoFxCompleteDirectedPowerDown` at `0x14013cb78`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013cab2`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013cb0c`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013cab2`
- `ntoskrnl!PoRequestPowerIrp` at `0x14013cb0c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013ca3d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013ca3d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013ca31`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013cb24`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013cb5e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013ca31`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013cb24`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14013cb5e`

## pseudocode

```c

```
