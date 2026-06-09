# __imp_load_GetSecurityDescriptorDacl

- ea: `0x18000231d`
- end: `0x180002329`
- name: `__imp_load_GetSecurityDescriptorDacl`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18000231d`

## pseudocode

```c
__int64 load_GetSecurityDescriptorDacl()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000231d  lea     rax, __imp_GetSecurityDescriptorDacl
0x180002324  jmp     __tailMerge_advapi32_dll
```
