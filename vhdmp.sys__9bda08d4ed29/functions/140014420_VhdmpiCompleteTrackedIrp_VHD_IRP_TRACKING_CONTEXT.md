# VhdmpiCompleteTrackedIrp(_VHD_IRP_TRACKING_CONTEXT *)

- ea: `0x140014420`
- end: `0x140014677`
- name: `?VhdmpiCompleteTrackedIrp@@YA_NPEAU_VHD_IRP_TRACKING_CONTEXT@@@Z`
- size: `599`
- prototype: `bool __fastcall(struct _VHD_IRP_TRACKING_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002ea94`

## callees

- `0x140014420`
- `0x140027524`
- `0x14002e8b0`
- `0x140036284`
- `0x140055b90`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001445f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001445f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400144aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001465d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400144aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001465d`

## string_xrefs

- `0x140014595`: `Log status 0x%08X: File path = %wZ`

## pseudocode

```c

```
