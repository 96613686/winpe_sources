# __imp_load_DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker

- ea: `0x18000f8ac`
- end: `0x18000f8b8`
- name: `__imp_load_DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000f712`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker` at `0x18000f8ac`

## pseudocode

```c
__int64 load_DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000f8ac  lea     rax, __imp_DeriveRestrictedAppContainerSidFromAppContainerSidAndRestrictedNameWorker
0x18000f8b3  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
