# __imp_load_LsaLookupSids

- ea: `0x1800030b9`
- end: `0x1800030c5`
- name: `__imp_load_LsaLookupSids`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002f31`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x1800030b9`

## pseudocode

```c
__int64 load_LsaLookupSids()
{
  return _tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800030b9  lea     rax, __imp_LsaLookupSids
0x1800030c0  jmp     __tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll
```
