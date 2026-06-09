# VhdmpiCTDeleteMasterMDL(_MDL *,ulong,void *)

- ea: `0x14002c1dc`
- end: `0x14002c23a`
- name: `?VhdmpiCTDeleteMasterMDL@@YAXPEAU_MDL@@KPEAX@Z`
- size: `94`
- prototype: `void __fastcall(PMDL Mdl, unsigned int, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14002bfc4`
- `0x14002c380`
- `0x14002cac4`

## callees

- `0x14002c1dc`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14002c222`
- `ntoskrnl!IoFreeMdl` at `0x14002c222`
- `ntoskrnl!MmUnlockPages` at `0x14002c213`
- `ntoskrnl!MmUnlockPages` at `0x14002c213`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002c1fb`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002c1fb`

## pseudocode

```c

```
