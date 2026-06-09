# SmbCamGetToken

- ea: `0x140072e44`
- end: `0x140072f21`
- name: `SmbCamGetToken`
- size: `221`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14008d8a8`

## callees

- `0x140038680`
- `0x140072d44`
- `0x140072e44`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140072e7e`
- `ntoskrnl!ExAllocatePool2` at `0x140072e7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072ee4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072ee4`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x140072eff`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x140072eff`
- `ntoskrnl!PsRevertToSelf` at `0x140072ebd`
- `ntoskrnl!PsRevertToSelf` at `0x140072ebd`

## pseudocode

```c

```
