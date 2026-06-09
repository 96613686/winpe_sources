# __imp_load_CreateAppContainerFromPolicyWorker

- ea: `0x18000f8d0`
- end: `0x18000f8dc`
- name: `__imp_load_CreateAppContainerFromPolicyWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f79d`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-2!CreateAppContainerFromPolicyWorker` at `0x18000f8d0`

## pseudocode

```c
__int64 load_CreateAppContainerFromPolicyWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_2_dll();
}

```

## disassembly

```asm
0x18000f8d0  lea     rax, __imp_CreateAppContainerFromPolicyWorker
0x18000f8d7  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_2_dll
```
