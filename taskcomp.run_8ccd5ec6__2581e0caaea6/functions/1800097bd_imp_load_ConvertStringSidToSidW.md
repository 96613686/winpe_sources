# __imp_load_ConvertStringSidToSidW

- ea: `0x1800097bd`
- end: `0x1800097c9`
- name: `__imp_load_ConvertStringSidToSidW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008fea`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800097bd`

## pseudocode

```c
__int64 load_ConvertStringSidToSidW()
{
  return _tailMerge_api_ms_win_security_sddl_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800097bd  lea     rax, __imp_ConvertStringSidToSidW
0x1800097c4  jmp     __tailMerge_api_ms_win_security_sddl_l1_1_0_dll
```
