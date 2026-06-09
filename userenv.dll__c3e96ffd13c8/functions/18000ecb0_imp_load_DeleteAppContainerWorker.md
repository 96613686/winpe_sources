# __imp_load_DeleteAppContainerWorker

- ea: `0x18000ecb0`
- end: `0x18000ecbc`
- name: `__imp_load_DeleteAppContainerWorker`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000eaed`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-2!DeleteAppContainerWorker` at `0x18000ecb0`

## pseudocode

```c
__int64 load_DeleteAppContainerWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_2_dll();
}

```

## disassembly

```asm
0x18000ecb0  lea     rax, __imp_DeleteAppContainerWorker
0x18000ecb7  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_2_dll
```
