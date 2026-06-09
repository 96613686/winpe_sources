# __imp_load_ConvertSidToStringSidW

- ea: `0x18000ce1b`
- end: `0x18000ce27`
- name: `__imp_load_ConvertSidToStringSidW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000cd8a`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ce1b`

## pseudocode

```c
__int64 load_ConvertSidToStringSidW()
{
  return _tailMerge_api_ms_win_security_sddl_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000ce1b  lea     rax, __imp_ConvertSidToStringSidW
0x18000ce22  jmp     __tailMerge_api_ms_win_security_sddl_l1_1_0_dll
```
