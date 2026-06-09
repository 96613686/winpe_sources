# __imp_load_SetSecurityDescriptorGroup

- ea: `0x180002137`
- end: `0x180002143`
- name: `__imp_load_SetSecurityDescriptorGroup`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180002137`

## pseudocode

```c
__int64 load_SetSecurityDescriptorGroup()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002137  lea     rax, __imp_SetSecurityDescriptorGroup
0x18000213e  jmp     __tailMerge_advapi32_dll
```
