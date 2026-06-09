# __imp_load_DeleteAppContainerProfileWorker

- ea: `0x18000f864`
- end: `0x18000f870`
- name: `__imp_load_DeleteAppContainerProfileWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f712`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeleteAppContainerProfileWorker` at `0x18000f864`

## pseudocode

```c
__int64 load_DeleteAppContainerProfileWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000f864  lea     rax, __imp_DeleteAppContainerProfileWorker
0x18000f86b  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
