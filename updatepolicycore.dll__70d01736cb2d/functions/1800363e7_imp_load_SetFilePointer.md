# __imp_load_SetFilePointer

- ea: `0x1800363e7`
- end: `0x1800363f3`
- name: `__imp_load_SetFilePointer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18003624d`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800363e7`

## pseudocode

```c
__int64 load_SetFilePointer()
{
  return _tailMerge_api_ms_win_core_file_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800363e7  lea     rax, __imp_SetFilePointer
0x1800363ee  jmp     __tailMerge_api_ms_win_core_file_l1_1_0_dll
```
