# __imp_load_ConvertSecurityDescriptorToStringSecurityDescriptorW

- ea: `0x180008b89`
- end: `0x180008b95`
- name: `__imp_load_ConvertSecurityDescriptorToStringSecurityDescriptorW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008b0a`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180008b89`

## pseudocode

```c
__int64 load_ConvertSecurityDescriptorToStringSecurityDescriptorW()
{
  return _tailMerge_api_ms_win_security_sddl_l1_1_0_dll();
}

```

## disassembly

```asm
0x180008b89  lea     rax, __imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180008b90  jmp     __tailMerge_api_ms_win_security_sddl_l1_1_0_dll
```
