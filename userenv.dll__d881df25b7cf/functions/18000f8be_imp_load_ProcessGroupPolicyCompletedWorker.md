# __imp_load_ProcessGroupPolicyCompletedWorker

- ea: `0x18000f8be`
- end: `0x18000f8ca`
- name: `__imp_load_ProcessGroupPolicyCompletedWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f712`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!ProcessGroupPolicyCompletedWorker` at `0x18000f8be`

## pseudocode

```c
__int64 load_ProcessGroupPolicyCompletedWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000f8be  lea     rax, __imp_ProcessGroupPolicyCompletedWorker
0x18000f8c5  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
