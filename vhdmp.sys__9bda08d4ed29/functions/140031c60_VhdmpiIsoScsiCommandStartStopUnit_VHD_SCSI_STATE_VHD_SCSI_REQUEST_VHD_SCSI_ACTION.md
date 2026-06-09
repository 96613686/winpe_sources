# VhdmpiIsoScsiCommandStartStopUnit(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,VHD_SCSI_ACTION *)

- ea: `0x140031c60`
- end: `0x140031de2`
- name: `?VhdmpiIsoScsiCommandStartStopUnit@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@PEAUVHD_SCSI_ACTION@@@Z`
- size: `386`
- prototype: `unsigned __int8 __fastcall(struct VHD_SCSI_STATE *, struct VHD_SCSI_REQUEST *, struct VHD_SCSI_ACTION *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140023980`
- `0x140031c60`
- `0x140036284`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031c95`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031d58`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031c95`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031d58`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031cd8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031d75`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031cd8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031d75`

## string_xrefs

- `0x140031d4f`: `VhdmpiIsoScsiCommandStartStopUnit: eject`
- `0x140031dbd`: `VhdmpiIsoScsiCommandStartStopUnit`
- `0x140031da6`: `VhdmpiIsoScsiCommandStartStopUnit: load`

## pseudocode

```c

```
