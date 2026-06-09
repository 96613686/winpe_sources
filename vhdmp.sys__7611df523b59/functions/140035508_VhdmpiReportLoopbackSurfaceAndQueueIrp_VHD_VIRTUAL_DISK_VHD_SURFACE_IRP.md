# VhdmpiReportLoopbackSurfaceAndQueueIrp(_VHD_VIRTUAL_DISK *,_VHD_SURFACE *,_IRP *)

- ea: `0x140035508`
- end: `0x140035795`
- name: `?VhdmpiReportLoopbackSurfaceAndQueueIrp@@YAXPEAU_VHD_VIRTUAL_DISK@@PEAU_VHD_SURFACE@@PEAU_IRP@@@Z`
- size: `653`
- prototype: `void(struct _VHD_VIRTUAL_DISK *, struct _VHD_SURFACE *, struct _IRP *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400bc264`

## callees

- `0x1400197bc`
- `0x14001df30`
- `0x140023560`
- `0x14002f3fc`
- `0x140035508`
- `0x14003579c`
- `0x140035bbc`
- `0x140035e94`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x1400355e0`
- `ntoskrnl!KeSetTimer` at `0x1400355e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035605`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400356ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035605`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400356ed`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035622`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035710`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035622`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035710`
- `storport!StorPortNotification` at `0x1400356ba`
- `storport!StorPortNotification` at `0x1400356ba`

## string_xrefs

- `0x140035650`: `Surface %p ready for enumeration.`

## pseudocode

```c

```
