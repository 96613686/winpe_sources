# __imp_load_CreateDirectoryJunctionsForSystemWorker

- ea: `0x18000f94e`
- end: `0x18000f95a`
- name: `__imp_load_CreateDirectoryJunctionsForSystemWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x18000f712`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateDirectoryJunctionsForSystemWorker` at `0x18000f94e`

## pseudocode

```c
__int64 load_CreateDirectoryJunctionsForSystemWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000f94e  lea     rax, __imp_CreateDirectoryJunctionsForSystemWorker
0x18000f955  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
