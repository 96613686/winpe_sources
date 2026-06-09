# __imp_load_AdjustTokenPrivileges

- ea: `0x180002341`
- end: `0x18000234d`
- name: `__imp_load_AdjustTokenPrivileges`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!AdjustTokenPrivileges` at `0x180002341`

## pseudocode

```c
__int64 load_AdjustTokenPrivileges()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002341  lea     rax, __imp_AdjustTokenPrivileges
0x180002348  jmp     __tailMerge_advapi32_dll
```
