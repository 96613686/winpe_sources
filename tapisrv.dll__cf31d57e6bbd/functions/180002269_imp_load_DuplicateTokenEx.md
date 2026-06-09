# __imp_load_DuplicateTokenEx

- ea: `0x180002269`
- end: `0x180002275`
- name: `__imp_load_DuplicateTokenEx`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!DuplicateTokenEx` at `0x180002269`

## pseudocode

```c
__int64 load_DuplicateTokenEx()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002269  lea     rax, __imp_DuplicateTokenEx
0x180002270  jmp     __tailMerge_advapi32_dll
```
