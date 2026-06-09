# __imp_load_GetNetEventSymbolicName

- ea: `0x180021cac`
- end: `0x180021cb8`
- name: `__imp_load_GetNetEventSymbolicName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x180021bb5`

## import_xrefs

- `ext-ms-win-core-symbolicnames-l1-1-0!GetNetEventSymbolicName` at `0x180021cac`

## pseudocode

```c
__int64 load_GetNetEventSymbolicName()
{
  return _tailMerge_ext_ms_win_core_symbolicnames_l1_1_0_dll();
}

```

## disassembly

```asm
0x180021cac  lea     rax, __imp_GetNetEventSymbolicName
0x180021cb3  jmp     __tailMerge_ext_ms_win_core_symbolicnames_l1_1_0_dll
```
