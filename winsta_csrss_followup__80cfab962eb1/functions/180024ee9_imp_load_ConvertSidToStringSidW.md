# __imp_load_ConvertSidToStringSidW

- ea: `0x180024ee9`
- end: `0x180024ef5`
- name: `__imp_load_ConvertSidToStringSidW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180024e6a`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180024ee9`

## pseudocode

```c
__int64 load_ConvertSidToStringSidW()
{
  return _tailMerge_api_ms_win_security_sddl_l1_1_0_dll();
}

```

## disassembly

```asm
0x180024ee9  lea     rax, __imp_ConvertSidToStringSidW
0x180024ef0  jmp     __tailMerge_api_ms_win_security_sddl_l1_1_0_dll
```
