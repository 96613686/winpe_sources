# __imp_load_DeriveAppContainerSidFromAppContainerNameWorker

- ea: `0x18000f852`
- end: `0x18000f85e`
- name: `__imp_load_DeriveAppContainerSidFromAppContainerNameWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000f712`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeriveAppContainerSidFromAppContainerNameWorker` at `0x18000f852`

## pseudocode

```c
__int64 load_DeriveAppContainerSidFromAppContainerNameWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000f852  lea     rax, __imp_DeriveAppContainerSidFromAppContainerNameWorker
0x18000f859  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
