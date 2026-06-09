# __imp_load_LookupPrivilegeValueW

- ea: `0x180002a19`
- end: `0x180002a25`
- name: `__imp_load_LookupPrivilegeValueW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000299a`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180002a19`

## pseudocode

```c
__int64 load_LookupPrivilegeValueW()
{
  return _tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll();
}

```

## disassembly

```asm
0x180002a19  lea     rax, __imp_LookupPrivilegeValueW
0x180002a20  jmp     __tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll
```
