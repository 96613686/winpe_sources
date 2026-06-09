# StorPortAdapterPowerNotRequiredStep2

- ea: `0x140044298`
- end: `0x1400444a5`
- name: `StorPortAdapterPowerNotRequiredStep2`
- size: `525`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140044200`
- `0x1400a67e0`

## callees

- `0x140044298`
- `0x1400680d8`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14004446d`
- `ntoskrnl!IoQueueWorkItem` at `0x14004446d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400442bc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044421`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400442bc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044421`
- `ntoskrnl!PoRequestPowerIrp` at `0x14004431b`
- `ntoskrnl!PoRequestPowerIrp` at `0x14004440a`
- `ntoskrnl!PoRequestPowerIrp` at `0x14004431b`
- `ntoskrnl!PoRequestPowerIrp` at `0x14004440a`
- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x140044379`
- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x140044379`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400443d5`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400443d5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044339`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400443c9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044339`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400443c9`

## pseudocode

```c

```
