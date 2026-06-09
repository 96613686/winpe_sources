# __imp_load_UpdateAppContainerProfileWorker

- ea: `0x18000ebea`
- end: `0x18000ebf6`
- name: `__imp_load_UpdateAppContainerProfileWorker`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000ea62`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!UpdateAppContainerProfileWorker` at `0x18000ebea`

## pseudocode

```c
__int64 load_UpdateAppContainerProfileWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000ebea  lea     rax, __imp_UpdateAppContainerProfileWorker
0x18000ebf1  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
