# VhdmpiAllocateAndInitializeMirrorSrbExtension(_VHD_SRB_EXTENSION *,_VHD_SRB_EXTENSION * *)

- ea: `0x140034550`
- end: `0x140034668`
- name: `?VhdmpiAllocateAndInitializeMirrorSrbExtension@@YAJPEAU_VHD_SRB_EXTENSION@@PEAPEAU1@@Z`
- size: `280`
- prototype: `__int64 __fastcall(struct _VHD_SRB_EXTENSION *, struct _VHD_SRB_EXTENSION **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140011f10`

## callees

- `0x14002636c`
- `0x140034550`
- `0x1400348c0`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140034602`
- `ntoskrnl!IoFreeMdl` at `0x140034602`
- `ntoskrnl!IoAllocateMdl` at `0x1400345a8`
- `ntoskrnl!IoAllocateMdl` at `0x1400345a8`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400345d3`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400345d3`

## pseudocode

```c

```
