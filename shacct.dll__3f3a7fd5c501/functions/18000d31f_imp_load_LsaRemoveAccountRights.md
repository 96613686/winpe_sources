# __imp_load_LsaRemoveAccountRights

- ea: `0x18000d31f`
- end: `0x18000d32b`
- name: `__imp_load_LsaRemoveAccountRights`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000d107`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaRemoveAccountRights` at `0x18000d31f`

## pseudocode

```c
__int64 load_LsaRemoveAccountRights()
{
  return _tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000d31f  lea     rax, __imp_LsaRemoveAccountRights
0x18000d326  jmp     __tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll
```
