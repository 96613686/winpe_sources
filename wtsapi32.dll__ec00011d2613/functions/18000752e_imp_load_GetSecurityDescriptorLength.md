# __imp_load_GetSecurityDescriptorLength

- ea: `0x18000752e`
- end: `0x18000753a`
- name: `__imp_load_GetSecurityDescriptorLength`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007375`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000752e`

## pseudocode

```c
__int64 load_GetSecurityDescriptorLength()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000752e  lea     rax, __imp_GetSecurityDescriptorLength
0x180007535  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
