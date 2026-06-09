# __imp_load_CreateAppContainerWorker

- ea: `0x18000f81c`
- end: `0x18000f828`
- name: `__imp_load_CreateAppContainerWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f79d`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-2!CreateAppContainerWorker` at `0x18000f81c`

## pseudocode

```c
__int64 load_CreateAppContainerWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_2_dll();
}

```

## disassembly

```asm
0x18000f81c  lea     rax, __imp_CreateAppContainerWorker
0x18000f823  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_2_dll
```
