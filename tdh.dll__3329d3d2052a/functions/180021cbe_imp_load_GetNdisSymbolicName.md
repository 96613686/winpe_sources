# __imp_load_GetNdisSymbolicName

- ea: `0x180021cbe`
- end: `0x180021cca`
- name: `__imp_load_GetNdisSymbolicName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x180021bb5`

## import_xrefs

- `ext-ms-win-core-symbolicnames-l1-1-0!GetNdisSymbolicName` at `0x180021cbe`

## pseudocode

```c
__int64 load_GetNdisSymbolicName()
{
  return _tailMerge_ext_ms_win_core_symbolicnames_l1_1_0_dll();
}

```

## disassembly

```asm
0x180021cbe  lea     rax, __imp_GetNdisSymbolicName
0x180021cc5  jmp     __tailMerge_ext_ms_win_core_symbolicnames_l1_1_0_dll
```
