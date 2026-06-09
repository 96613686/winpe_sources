# __imp_load_LookupAccountSidW

- ea: `0x18000481e`
- end: `0x18000482a`
- name: `__imp_load_LookupAccountSidW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000402a`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000481e`

## pseudocode

```c
__int64 load_LookupAccountSidW()
{
  return _tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll();
}

```

## disassembly

```asm
0x18000481e  lea     rax, __imp_LookupAccountSidW
0x180004825  jmp     __tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll
```
