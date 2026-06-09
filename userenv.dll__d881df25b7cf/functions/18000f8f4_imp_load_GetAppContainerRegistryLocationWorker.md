# __imp_load_GetAppContainerRegistryLocationWorker

- ea: `0x18000f8f4`
- end: `0x18000f900`
- name: `__imp_load_GetAppContainerRegistryLocationWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f712`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!GetAppContainerRegistryLocationWorker` at `0x18000f8f4`

## pseudocode

```c
__int64 load_GetAppContainerRegistryLocationWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000f8f4  lea     rax, __imp_GetAppContainerRegistryLocationWorker
0x18000f8fb  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
