# __imp_load_InitializeAcl

- ea: `0x180002191`
- end: `0x18000219d`
- name: `__imp_load_InitializeAcl`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x180002191`

## pseudocode

```c
__int64 load_InitializeAcl()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002191  lea     rax, __imp_InitializeAcl
0x180002198  jmp     __tailMerge_advapi32_dll
```
