# __imp_load_GetNTStatusSymbolicName

- ea: `0x180021c34`
- end: `0x180021c40`
- name: `__imp_load_GetNTStatusSymbolicName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x180021bb5`

## import_xrefs

- `ext-ms-win-core-symbolicnames-l1-1-0!GetNTStatusSymbolicName` at `0x180021c34`

## pseudocode

```c
__int64 load_GetNTStatusSymbolicName()
{
  return _tailMerge_ext_ms_win_core_symbolicnames_l1_1_0_dll();
}

```

## disassembly

```asm
0x180021c34  lea     rax, __imp_GetNTStatusSymbolicName
0x180021c3b  jmp     __tailMerge_ext_ms_win_core_symbolicnames_l1_1_0_dll
```
