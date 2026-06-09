# VhdmpiCompleteIrpForEnteredSafeFileReference(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140013bb0`
- end: `0x140013e20`
- name: `?VhdmpiCompleteIrpForEnteredSafeFileReference@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `624`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140013bb0`
- `0x140027524`
- `0x14002e8b0`
- `0x140036284`
- `0x140055b90`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013c12`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013c12`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013c67`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013df9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013c67`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013df9`

## string_xrefs

- `0x140013d3e`: `Log status 0x%08X: File path = %wZ`

## pseudocode

```c

```
