# __imp_load_GetSidSubAuthority

- ea: `0x1800021fd`
- end: `0x180002209`
- name: `__imp_load_GetSidSubAuthority`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!GetSidSubAuthority` at `0x1800021fd`

## pseudocode

```c
__int64 load_GetSidSubAuthority()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800021fd  lea     rax, __imp_GetSidSubAuthority
0x180002204  jmp     __tailMerge_advapi32_dll
```
