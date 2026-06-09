# VhdmpiAllocateAndInitializeMirrorSrbExtension(_VHD_SRB_EXTENSION *,_VHD_SRB_EXTENSION * *)

- ea: `0x140034a10`
- end: `0x140034b28`
- name: `?VhdmpiAllocateAndInitializeMirrorSrbExtension@@YAJPEAU_VHD_SRB_EXTENSION@@PEAPEAU1@@Z`
- size: `280`
- prototype: `__int64 __fastcall(struct _VHD_SRB_EXTENSION *, struct _VHD_SRB_EXTENSION **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140013240`

## callees

- `0x14002678c`
- `0x140034a10`
- `0x140034cb8`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140034ac2`
- `ntoskrnl!IoFreeMdl` at `0x140034ac2`
- `ntoskrnl!IoAllocateMdl` at `0x140034a68`
- `ntoskrnl!IoAllocateMdl` at `0x140034a68`
- `ntoskrnl!IoBuildPartialMdl` at `0x140034a93`
- `ntoskrnl!IoBuildPartialMdl` at `0x140034a93`

## pseudocode

```c

```
