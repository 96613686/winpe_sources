# VhdmpiCreateErrorLogEntry(_VHD_SRB_EXTENSION *)

- ea: `0x140040f48`
- end: `0x1400410ec`
- name: `?VhdmpiCreateErrorLogEntry@@YAXPEAU_VHD_SRB_EXTENSION@@@Z`
- size: `420`
- prototype: `void __fastcall(struct _VHD_SRB_EXTENSION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000fbf0`

## callees

- `0x140040f48`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140040f93`
- `ntoskrnl!ExAllocatePool2` at `0x140040f93`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040f64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140040f64`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400410c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400410c8`

## pseudocode

```c

```
