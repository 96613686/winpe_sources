# VhdmpiCompleteTrackedIrp(_VHD_IRP_TRACKING_CONTEXT *)

- ea: `0x140013f80`
- end: `0x1400141d7`
- name: `?VhdmpiCompleteTrackedIrp@@YA_NPEAU_VHD_IRP_TRACKING_CONTEXT@@@Z`
- size: `599`
- prototype: `char __fastcall(struct _VHD_IRP_TRACKING_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002e5d4`

## callees

- `0x140013f80`
- `0x140027000`
- `0x14002e3f0`
- `0x140035e94`
- `0x1400557a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013fbf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013fbf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001400a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400141bd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001400a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400141bd`

## string_xrefs

- `0x1400140f5`: `Log status 0x%08X: File path = %wZ`

## pseudocode

```c

```
