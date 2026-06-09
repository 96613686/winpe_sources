# __imp_load_UpdateAppContainerProfileWorker

- ea: `0x18000f89a`
- end: `0x18000f8a6`
- name: `__imp_load_UpdateAppContainerProfileWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000f712`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!UpdateAppContainerProfileWorker` at `0x18000f89a`

## pseudocode

```c
__int64 load_UpdateAppContainerProfileWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000f89a  lea     rax, __imp_UpdateAppContainerProfileWorker
0x18000f8a1  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
