# __imp_load_ConvertStringSecurityDescriptorToSecurityDescriptorW

- ea: `0x18001edc3`
- end: `0x18001edcf`
- name: `__imp_load_ConvertStringSecurityDescriptorToSecurityDescriptorW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001ed44`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001edc3`

## pseudocode

```c
__int64 load_ConvertStringSecurityDescriptorToSecurityDescriptorW()
{
  return _tailMerge_api_ms_win_security_sddl_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001edc3  lea     rax, __imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001edca  jmp     __tailMerge_api_ms_win_security_sddl_l1_1_0_dll
```
