# VhdmpiProcessRawScsiCommand(_VHD_HANDLE_CONTEXT *,_IRP *)

- ea: `0x1400479f8`
- end: `0x140047c42`
- name: `?VhdmpiProcessRawScsiCommand@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_IRP@@@Z`
- size: `586`
- prototype: `int(struct _VHD_HANDLE_CONTEXT *, struct _IRP *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14001a608`
- `0x140047638`

## callees

- `0x14000d680`
- `0x14000fd30`
- `0x1400108ac`
- `0x140019b44`
- `0x14001e350`
- `0x14002678c`
- `0x140046a58`
- `0x1400479f8`
- `0x140048a70`
- `0x140048d24`
- `0x14005de00`
- `0x14005e100`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140047ad5`
- `ntoskrnl!IoFreeMdl` at `0x140047ad5`
- `ntoskrnl!MmUnlockPages` at `0x140047ac5`
- `ntoskrnl!MmUnlockPages` at `0x140047ac5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140047aa1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140047aa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047aea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047aea`

## pseudocode

```c

```
