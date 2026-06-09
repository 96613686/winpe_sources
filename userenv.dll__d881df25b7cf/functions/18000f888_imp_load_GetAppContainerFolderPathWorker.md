# __imp_load_GetAppContainerFolderPathWorker

- ea: `0x18000f888`
- end: `0x18000f894`
- name: `__imp_load_GetAppContainerFolderPathWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f712`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!GetAppContainerFolderPathWorker` at `0x18000f888`

## pseudocode

```c
__int64 load_GetAppContainerFolderPathWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000f888  lea     rax, __imp_GetAppContainerFolderPathWorker
0x18000f88f  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
