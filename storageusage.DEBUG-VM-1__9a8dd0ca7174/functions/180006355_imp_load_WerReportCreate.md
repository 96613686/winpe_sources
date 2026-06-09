# __imp_load_WerReportCreate

- ea: `0x180006355`
- end: `0x180006361`
- name: `__imp_load_WerReportCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000628e`

## import_xrefs

- `wer!WerReportCreate` at `0x180006355`

## pseudocode

```c
__int64 load_WerReportCreate()
{
  return _tailMerge_wer_dll();
}

```

## disassembly

```asm
0x180006355  lea     rax, __imp_WerReportCreate
0x18000635c  jmp     __tailMerge_wer_dll
```
