# __imp_load_LsaLookupSids

- ea: `0x18000d2e9`
- end: `0x18000d2f5`
- name: `__imp_load_LsaLookupSids`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000d107`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupSids` at `0x18000d2e9`

## pseudocode

```c
__int64 load_LsaLookupSids()
{
  return _tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000d2e9  lea     rax, __imp_LsaLookupSids
0x18000d2f0  jmp     __tailMerge_api_ms_win_security_lsapolicy_l1_1_0_dll
```
