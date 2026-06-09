# __imp_load_InitializeSecurityDescriptor

- ea: `0x1800021a3`
- end: `0x1800021af`
- name: `__imp_load_InitializeSecurityDescriptor`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800021a3`

## pseudocode

```c
__int64 load_InitializeSecurityDescriptor()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800021a3  lea     rax, __imp_InitializeSecurityDescriptor
0x1800021aa  jmp     __tailMerge_advapi32_dll
```
