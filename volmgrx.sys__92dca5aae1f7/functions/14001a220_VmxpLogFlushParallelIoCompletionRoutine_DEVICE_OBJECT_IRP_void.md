# VmxpLogFlushParallelIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14001a220`
- end: `0x14001a33c`
- name: `?VmxpLogFlushParallelIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `284`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400099d8`
- `0x140019430`
- `0x14001a220`
- `0x14001b78c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a246`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a246`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a268`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a28b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a268`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a28b`
- `ntoskrnl!IoFreeIrp` at `0x14001a2cb`
- `ntoskrnl!IoFreeIrp` at `0x14001a2cb`
- `ntoskrnl!IoFreeMdl` at `0x14001a2b4`
- `ntoskrnl!IoFreeMdl` at `0x14001a2b4`
- `ntoskrnl!MmUnlockPages` at `0x14001a2a4`
- `ntoskrnl!MmUnlockPages` at `0x14001a2a4`

## pseudocode

```c

```
