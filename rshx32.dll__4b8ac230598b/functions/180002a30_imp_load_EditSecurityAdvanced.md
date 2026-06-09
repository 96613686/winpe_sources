# __imp_load_EditSecurityAdvanced

- ea: `0x180002a30`
- end: `0x180002a3c`
- name: `__imp_load_EditSecurityAdvanced`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800029b1`

## import_xrefs

- `ACLUI!__imp_EditSecurityAdvanced` at `0x180002a30`

## pseudocode

```c
__int64 load_EditSecurityAdvanced()
{
  return _tailMerge_aclui_dll();
}

```

## disassembly

```asm
0x180002a30  lea     rax, __imp_EditSecurityAdvanced
0x180002a37  jmp     __tailMerge_aclui_dll
```
