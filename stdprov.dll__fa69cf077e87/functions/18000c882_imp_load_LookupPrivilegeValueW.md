# __imp_load_LookupPrivilegeValueW

- ea: `0x18000c882`
- end: `0x18000c88e`
- name: `__imp_load_LookupPrivilegeValueW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000c803`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000c882`

## pseudocode

```c
__int64 load_LookupPrivilegeValueW()
{
  return _tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll();
}

```

## disassembly

```asm
0x18000c882  lea     rax, __imp_LookupPrivilegeValueW
0x18000c889  jmp     __tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll
```
