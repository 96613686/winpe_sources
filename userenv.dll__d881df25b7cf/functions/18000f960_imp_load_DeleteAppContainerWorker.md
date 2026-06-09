# __imp_load_DeleteAppContainerWorker

- ea: `0x18000f960`
- end: `0x18000f96c`
- name: `__imp_load_DeleteAppContainerWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f79d`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-2!DeleteAppContainerWorker` at `0x18000f960`

## pseudocode

```c
__int64 load_DeleteAppContainerWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_2_dll();
}

```

## disassembly

```asm
0x18000f960  lea     rax, __imp_DeleteAppContainerWorker
0x18000f967  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_2_dll
```
