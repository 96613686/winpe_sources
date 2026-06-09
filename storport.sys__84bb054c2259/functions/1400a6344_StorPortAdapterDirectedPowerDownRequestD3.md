# StorPortAdapterDirectedPowerDownRequestD3

- ea: `0x1400a6344`
- end: `0x1400a6558`
- name: `StorPortAdapterDirectedPowerDownRequestD3`
- size: `532`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400a6200`
- `0x1400a6560`

## callees

- `0x1400680d8`
- `0x1400a6344`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x1400a63f8`
- `ntoskrnl!IoQueueWorkItem` at `0x1400a63f8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a6370`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a6441`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a6370`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a6441`
- `ntoskrnl!PoFxCompleteDirectedPowerDown` at `0x1400a6503`
- `ntoskrnl!PoFxCompleteDirectedPowerDown` at `0x1400a6503`
- `ntoskrnl!PoRequestPowerIrp` at `0x1400a642a`
- `ntoskrnl!PoRequestPowerIrp` at `0x1400a647d`
- `ntoskrnl!PoRequestPowerIrp` at `0x1400a642a`
- `ntoskrnl!PoRequestPowerIrp` at `0x1400a647d`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400a63c4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400a63c4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a63b8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a6499`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a64af`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a63b8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a6499`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a64af`

## pseudocode

```c

```
