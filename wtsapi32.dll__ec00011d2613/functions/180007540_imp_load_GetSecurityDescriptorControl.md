# __imp_load_GetSecurityDescriptorControl

- ea: `0x180007540`
- end: `0x18000754c`
- name: `__imp_load_GetSecurityDescriptorControl`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007375`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180007540`

## pseudocode

```c
__int64 load_GetSecurityDescriptorControl()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x180007540  lea     rax, __imp_GetSecurityDescriptorControl
0x180007547  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
