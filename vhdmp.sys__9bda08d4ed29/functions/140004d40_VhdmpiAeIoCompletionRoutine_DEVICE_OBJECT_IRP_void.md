# VhdmpiAeIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140004d40`
- end: `0x140004ff7`
- name: `?VhdmpiAeIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `695`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140004d40`
- `0x140005000`
- `0x140006010`
- `0x140016cc0`
- `0x140017000`
- `0x14005dc30`

## import_xrefs

- `ntoskrnl!ExTryQueueWorkItem` at `0x140004f05`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140004f05`
- `ntoskrnl!KeInsertQueue` at `0x140004f20`
- `ntoskrnl!KeInsertQueue` at `0x140004f20`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140004e3c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140004e3c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004eb7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004eb7`

## pseudocode

```c

```
