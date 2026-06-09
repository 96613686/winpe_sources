# __imp_load_AddAppContainerAccessWorker

- ea: `0x18000f876`
- end: `0x18000f882`
- name: `__imp_load_AddAppContainerAccessWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f79d`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-2!AddAppContainerAccessWorker` at `0x18000f876`

## pseudocode

```c
__int64 load_AddAppContainerAccessWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_2_dll();
}

```

## disassembly

```asm
0x18000f876  lea     rax, __imp_AddAppContainerAccessWorker
0x18000f87d  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_2_dll
```
