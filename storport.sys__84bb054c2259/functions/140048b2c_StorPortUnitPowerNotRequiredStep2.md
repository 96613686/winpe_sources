# StorPortUnitPowerNotRequiredStep2

- ea: `0x140048b2c`
- end: `0x140048da2`
- name: `StorPortUnitPowerNotRequiredStep2`
- size: `630`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140048a40`
- `0x1400a6f70`

## callees

- `0x1400016cc`
- `0x140048b2c`
- `0x140066a60`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140048b87`
- `ntoskrnl!KeCancelTimer` at `0x140048b87`
- `ntoskrnl!IoQueueWorkItem` at `0x140048c33`
- `ntoskrnl!IoQueueWorkItem` at `0x140048c33`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140048b54`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140048c80`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140048b54`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140048c80`
- `ntoskrnl!PoRequestPowerIrp` at `0x140048c69`
- `ntoskrnl!PoRequestPowerIrp` at `0x140048cb0`
- `ntoskrnl!PoRequestPowerIrp` at `0x140048c69`
- `ntoskrnl!PoRequestPowerIrp` at `0x140048cb0`
- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x140048d3b`
- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x140048d3b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048bff`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048bff`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140048bf3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140048cd9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140048bf3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140048cd9`

## pseudocode

```c

```
