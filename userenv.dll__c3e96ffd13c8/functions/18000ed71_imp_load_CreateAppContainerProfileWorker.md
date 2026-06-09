# __imp_load_CreateAppContainerProfileWorker

- ea: `0x18000ed71`
- end: `0x18000ed7d`
- name: `__imp_load_CreateAppContainerProfileWorker`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ea62`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateAppContainerProfileWorker` at `0x18000ed71`

## pseudocode

```c
__int64 load_CreateAppContainerProfileWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000ed71  lea     rax, __imp_CreateAppContainerProfileWorker
0x18000ed78  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
