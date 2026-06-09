# __imp_load_CompareFileTime

- ea: `0x1800362cc`
- end: `0x1800362d8`
- name: `__imp_load_CompareFileTime`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003624d`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800362cc`

## pseudocode

```c
__int64 load_CompareFileTime()
{
  return _tailMerge_api_ms_win_core_file_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800362cc  lea     rax, __imp_CompareFileTime
0x1800362d3  jmp     __tailMerge_api_ms_win_core_file_l1_1_0_dll
```
