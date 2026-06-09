# __imp_load_ReadFile

- ea: `0x1800363d5`
- end: `0x1800363e1`
- name: `__imp_load_ReadFile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18003624d`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800363d5`

## pseudocode

```c
__int64 load_ReadFile()
{
  return _tailMerge_api_ms_win_core_file_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800363d5  lea     rax, __imp_ReadFile
0x1800363dc  jmp     __tailMerge_api_ms_win_core_file_l1_1_0_dll
```
