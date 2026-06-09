# __imp_load_GetNdisOidSymbolicName

- ea: `0x180021c46`
- end: `0x180021c52`
- name: `__imp_load_GetNdisOidSymbolicName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x180021bb5`

## import_xrefs

- `ext-ms-win-core-symbolicnames-l1-1-0!GetNdisOidSymbolicName` at `0x180021c46`

## pseudocode

```c
__int64 load_GetNdisOidSymbolicName()
{
  return _tailMerge_ext_ms_win_core_symbolicnames_l1_1_0_dll();
}

```

## disassembly

```asm
0x180021c46  lea     rax, __imp_GetNdisOidSymbolicName
0x180021c4d  jmp     __tailMerge_ext_ms_win_core_symbolicnames_l1_1_0_dll
```
