# __imp_load_ProcessGroupPolicyCompletedExWorker

- ea: `0x18000fa33`
- end: `0x18000fa3f`
- name: `__imp_load_ProcessGroupPolicyCompletedExWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f712`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!ProcessGroupPolicyCompletedExWorker` at `0x18000fa33`

## pseudocode

```c
__int64 load_ProcessGroupPolicyCompletedExWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000fa33  lea     rax, __imp_ProcessGroupPolicyCompletedExWorker
0x18000fa3a  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
