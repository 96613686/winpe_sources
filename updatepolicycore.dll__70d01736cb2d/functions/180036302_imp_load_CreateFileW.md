# __imp_load_CreateFileW

- ea: `0x180036302`
- end: `0x18003630e`
- name: `__imp_load_CreateFileW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18003624d`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036302`

## pseudocode

```c
__int64 load_CreateFileW()
{
  return _tailMerge_api_ms_win_core_file_l1_1_0_dll();
}

```

## disassembly

```asm
0x180036302  lea     rax, __imp_CreateFileW
0x180036309  jmp     __tailMerge_api_ms_win_core_file_l1_1_0_dll
```
