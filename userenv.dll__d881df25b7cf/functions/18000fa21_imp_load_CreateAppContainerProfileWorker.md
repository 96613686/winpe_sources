# __imp_load_CreateAppContainerProfileWorker

- ea: `0x18000fa21`
- end: `0x18000fa2d`
- name: `__imp_load_CreateAppContainerProfileWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f712`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateAppContainerProfileWorker` at `0x18000fa21`

## pseudocode

```c
__int64 load_CreateAppContainerProfileWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000fa21  lea     rax, __imp_CreateAppContainerProfileWorker
0x18000fa28  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
