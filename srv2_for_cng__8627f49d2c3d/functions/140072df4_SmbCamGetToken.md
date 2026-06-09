# SmbCamGetToken

- ea: `0x140072df4`
- end: `0x140072ed1`
- name: `SmbCamGetToken`
- size: `221`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14008d858`

## callees

- `0x140038680`
- `0x140072cf4`
- `0x140072df4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140072e2e`
- `ntoskrnl!ExAllocatePool2` at `0x140072e2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072e94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072e94`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x140072eaf`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x140072eaf`
- `ntoskrnl!PsRevertToSelf` at `0x140072e6d`
- `ntoskrnl!PsRevertToSelf` at `0x140072e6d`

## pseudocode

```c

```
