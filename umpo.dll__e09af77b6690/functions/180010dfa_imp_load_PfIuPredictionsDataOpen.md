# __imp_load_PfIuPredictionsDataOpen

- ea: `0x180010dfa`
- end: `0x180010e06`
- name: `__imp_load_PfIuPredictionsDataOpen`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180010d69`

## import_xrefs

- `ext-ms-win-sysmain-pfapi-l1-1-1!PfIuPredictionsDataOpen` at `0x180010dfa`

## pseudocode

```c
__int64 load_PfIuPredictionsDataOpen()
{
  return _tailMerge_ext_ms_win_sysmain_pfapi_l1_1_1_dll();
}

```

## disassembly

```asm
0x180010dfa  lea     rax, __imp_PfIuPredictionsDataOpen
0x180010e01  jmp     __tailMerge_ext_ms_win_sysmain_pfapi_l1_1_1_dll
```
