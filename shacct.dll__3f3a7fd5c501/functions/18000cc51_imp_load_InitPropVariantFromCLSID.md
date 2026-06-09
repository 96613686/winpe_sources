# __imp_load_InitPropVariantFromCLSID

- ea: `0x18000cc51`
- end: `0x18000cc5d`
- name: `__imp_load_InitPropVariantFromCLSID`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000cb8a`

## import_xrefs

- `PROPSYS!InitPropVariantFromCLSID` at `0x18000cc51`

## pseudocode

```c
__int64 load_InitPropVariantFromCLSID()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x18000cc51  lea     rax, __imp_InitPropVariantFromCLSID
0x18000cc58  jmp     __tailMerge_propsys_dll
```
