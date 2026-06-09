# __imp_load_CreateSecurityPage

- ea: `0x180002a54`
- end: `0x180002a60`
- name: `__imp_load_CreateSecurityPage`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800029b1`

## import_xrefs

- `ACLUI!__imp_CreateSecurityPage` at `0x180002a54`

## pseudocode

```c
__int64 load_CreateSecurityPage()
{
  return _tailMerge_aclui_dll();
}

```

## disassembly

```asm
0x180002a54  lea     rax, __imp_CreateSecurityPage
0x180002a5b  jmp     __tailMerge_aclui_dll
```
