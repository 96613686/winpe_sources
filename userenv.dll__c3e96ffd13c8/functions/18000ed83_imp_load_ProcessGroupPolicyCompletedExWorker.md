# __imp_load_ProcessGroupPolicyCompletedExWorker

- ea: `0x18000ed83`
- end: `0x18000ed8f`
- name: `__imp_load_ProcessGroupPolicyCompletedExWorker`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000ea62`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!ProcessGroupPolicyCompletedExWorker` at `0x18000ed83`

## pseudocode

```c
__int64 load_ProcessGroupPolicyCompletedExWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000ed83  lea     rax, __imp_ProcessGroupPolicyCompletedExWorker
0x18000ed8a  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
