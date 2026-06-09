# __imp_load_CreateDirectoryJunctionsForUserProfileWorker

- ea: `0x18000ec32`
- end: `0x18000ec3e`
- name: `__imp_load_CreateDirectoryJunctionsForUserProfileWorker`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x18000ea62`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateDirectoryJunctionsForUserProfileWorker` at `0x18000ec32`

## pseudocode

```c
__int64 load_CreateDirectoryJunctionsForUserProfileWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000ec32  lea     rax, __imp_CreateDirectoryJunctionsForUserProfileWorker
0x18000ec39  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
