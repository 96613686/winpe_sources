# __imp_load_SetSecurityDescriptorOwner

- ea: `0x180002221`
- end: `0x18000222d`
- name: `__imp_load_SetSecurityDescriptorOwner`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180002221`

## pseudocode

```c
__int64 load_SetSecurityDescriptorOwner()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002221  lea     rax, __imp_SetSecurityDescriptorOwner
0x180002228  jmp     __tailMerge_advapi32_dll
```
