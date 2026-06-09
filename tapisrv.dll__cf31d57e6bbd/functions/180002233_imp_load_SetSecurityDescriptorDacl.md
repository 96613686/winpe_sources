# __imp_load_SetSecurityDescriptorDacl

- ea: `0x180002233`
- end: `0x18000223f`
- name: `__imp_load_SetSecurityDescriptorDacl`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180002233`

## pseudocode

```c
__int64 load_SetSecurityDescriptorDacl()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002233  lea     rax, __imp_SetSecurityDescriptorDacl
0x18000223a  jmp     __tailMerge_advapi32_dll
```
