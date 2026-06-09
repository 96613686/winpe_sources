# __imp_load_EditSecurity

- ea: `0x180002a42`
- end: `0x180002a4e`
- name: `__imp_load_EditSecurity`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800029b1`

## import_xrefs

- `ACLUI!__imp_EditSecurity` at `0x180002a42`

## pseudocode

```c
__int64 load_EditSecurity()
{
  return _tailMerge_aclui_dll();
}

```

## disassembly

```asm
0x180002a42  lea     rax, __imp_EditSecurity
0x180002a49  jmp     __tailMerge_aclui_dll
```
