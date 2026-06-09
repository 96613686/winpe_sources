# VhdmpiProcessRawScsiCommand(_VHD_HANDLE_CONTEXT *,_IRP *)

- ea: `0x140047608`
- end: `0x140047852`
- name: `?VhdmpiProcessRawScsiCommand@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_IRP@@@Z`
- size: `586`
- prototype: `int(struct _VHD_HANDLE_CONTEXT *, struct _IRP *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14001a1e8`
- `0x140047248`

## callees

- `0x14000d080`
- `0x1400122b0`
- `0x140012e2c`
- `0x1400196a4`
- `0x14001df30`
- `0x14002636c`
- `0x140046668`
- `0x140047608`
- `0x140048680`
- `0x140048934`
- `0x14005da00`
- `0x14005dd00`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400476e5`
- `ntoskrnl!IoFreeMdl` at `0x1400476e5`
- `ntoskrnl!MmUnlockPages` at `0x1400476d5`
- `ntoskrnl!MmUnlockPages` at `0x1400476d5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400476b1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400476b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400476fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400476fa`

## pseudocode

```c

```
