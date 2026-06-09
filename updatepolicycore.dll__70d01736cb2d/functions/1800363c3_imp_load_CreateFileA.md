# __imp_load_CreateFileA

- ea: `0x1800363c3`
- end: `0x1800363cf`
- name: `__imp_load_CreateFileA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18003624d`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800363c3`

## pseudocode

```c
__int64 load_CreateFileA()
{
  return _tailMerge_api_ms_win_core_file_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800363c3  lea     rax, __imp_CreateFileA
0x1800363ca  jmp     __tailMerge_api_ms_win_core_file_l1_1_0_dll
```
