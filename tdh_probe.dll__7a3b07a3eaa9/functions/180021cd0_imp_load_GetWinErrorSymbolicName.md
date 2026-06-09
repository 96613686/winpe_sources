# __imp_load_GetWinErrorSymbolicName

- ea: `0x180021cd0`
- end: `0x180021cdc`
- name: `__imp_load_GetWinErrorSymbolicName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x180021bb5`

## import_xrefs

- `ext-ms-win-core-symbolicnames-l1-1-0!GetWinErrorSymbolicName` at `0x180021cd0`

## pseudocode

```c
__int64 load_GetWinErrorSymbolicName()
{
  return _tailMerge_ext_ms_win_core_symbolicnames_l1_1_0_dll();
}

```

## disassembly

```asm
0x180021cd0  lea     rax, __imp_GetWinErrorSymbolicName
0x180021cd7  jmp     __tailMerge_ext_ms_win_core_symbolicnames_l1_1_0_dll
```
