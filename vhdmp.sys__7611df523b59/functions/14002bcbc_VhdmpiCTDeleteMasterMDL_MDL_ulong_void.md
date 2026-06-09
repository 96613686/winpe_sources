# VhdmpiCTDeleteMasterMDL(_MDL *,ulong,void *)

- ea: `0x14002bcbc`
- end: `0x14002bd1a`
- name: `?VhdmpiCTDeleteMasterMDL@@YAXPEAU_MDL@@KPEAX@Z`
- size: `94`
- prototype: `void __fastcall(PMDL Mdl, ULONG, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14002baa4`
- `0x14002be60`
- `0x14002c5a4`

## callees

- `0x14002bcbc`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14002bd02`
- `ntoskrnl!IoFreeMdl` at `0x14002bd02`
- `ntoskrnl!MmUnlockPages` at `0x14002bcf3`
- `ntoskrnl!MmUnlockPages` at `0x14002bcf3`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002bcdb`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002bcdb`

## pseudocode

```c

```
