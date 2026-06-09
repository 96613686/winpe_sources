# VhdmpiReportLoopbackSurfaceAndQueueIrp(_VHD_VIRTUAL_DISK *,_VHD_SURFACE *,_IRP *)

- ea: `0x1400358f8`
- end: `0x140035b85`
- name: `?VhdmpiReportLoopbackSurfaceAndQueueIrp@@YAXPEAU_VHD_VIRTUAL_DISK@@PEAU_VHD_SURFACE@@PEAU_IRP@@@Z`
- size: `653`
- prototype: `void(struct _VHD_VIRTUAL_DISK *, struct _VHD_SURFACE *, struct _IRP *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400bc254`

## callees

- `0x140019bdc`
- `0x14001e350`
- `0x140023980`
- `0x14002f8bc`
- `0x1400358f8`
- `0x140035b8c`
- `0x140035fac`
- `0x140036284`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x1400359d0`
- `ntoskrnl!KeSetTimer` at `0x1400359d0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400359f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035add`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400359f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035add`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035a12`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035b00`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035a12`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035b00`
- `storport!StorPortNotification` at `0x140035aaa`
- `storport!StorPortNotification` at `0x140035aaa`

## string_xrefs

- `0x140035a40`: `Surface %p ready for enumeration.`

## pseudocode

```c

```
