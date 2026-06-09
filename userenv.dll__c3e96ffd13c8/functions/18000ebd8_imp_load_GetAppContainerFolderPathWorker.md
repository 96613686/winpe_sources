# __imp_load_GetAppContainerFolderPathWorker

- ea: `0x18000ebd8`
- end: `0x18000ebe4`
- name: `__imp_load_GetAppContainerFolderPathWorker`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ea62`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!GetAppContainerFolderPathWorker` at `0x18000ebd8`

## pseudocode

```c
__int64 load_GetAppContainerFolderPathWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000ebd8  lea     rax, __imp_GetAppContainerFolderPathWorker
0x18000ebdf  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
