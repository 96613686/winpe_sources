# __imp_load_DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker

- ea: `0x18000ebfc`
- end: `0x18000ec08`
- name: `__imp_load_DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ea62`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker` at `0x18000ebfc`

## pseudocode

```c
__int64 load_DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000ebfc  lea     rax, __imp_DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker
0x18000ec03  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
