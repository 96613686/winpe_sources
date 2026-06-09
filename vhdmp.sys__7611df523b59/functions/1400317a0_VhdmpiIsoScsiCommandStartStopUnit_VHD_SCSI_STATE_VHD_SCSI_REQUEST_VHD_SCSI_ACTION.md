# VhdmpiIsoScsiCommandStartStopUnit(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,VHD_SCSI_ACTION *)

- ea: `0x1400317a0`
- end: `0x140031922`
- name: `?VhdmpiIsoScsiCommandStartStopUnit@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@PEAUVHD_SCSI_ACTION@@@Z`
- size: `386`
- prototype: `unsigned __int8 __fastcall(struct VHD_SCSI_STATE *, struct VHD_SCSI_REQUEST *, struct VHD_SCSI_ACTION *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140023560`
- `0x1400317a0`
- `0x140035e94`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400317d5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031898`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400317d5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031898`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031818`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400318b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140031818`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400318b5`

## string_xrefs

- `0x14003188f`: `VhdmpiIsoScsiCommandStartStopUnit: eject`
- `0x1400318fd`: `VhdmpiIsoScsiCommandStartStopUnit`
- `0x1400318e6`: `VhdmpiIsoScsiCommandStartStopUnit: load`

## pseudocode

```c

```
