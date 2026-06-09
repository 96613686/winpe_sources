# __imp_load_LookupPrivilegeValueW

- ea: `0x18000942f`
- end: `0x18000943b`
- name: `__imp_load_LookupPrivilegeValueW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009368`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000942f`

## pseudocode

```c
__int64 load_LookupPrivilegeValueW()
{
  return _tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll();
}

```

## disassembly

```asm
0x18000942f  lea     rax, __imp_LookupPrivilegeValueW
0x180009436  jmp     __tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll
```
