# __imp_load_PfIuPredictionsDataClose

- ea: `0x180010de8`
- end: `0x180010df4`
- name: `__imp_load_PfIuPredictionsDataClose`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180010d69`

## import_xrefs

- `ext-ms-win-sysmain-pfapi-l1-1-1!PfIuPredictionsDataClose` at `0x180010de8`

## pseudocode

```c
__int64 load_PfIuPredictionsDataClose()
{
  return _tailMerge_ext_ms_win_sysmain_pfapi_l1_1_1_dll();
}

```

## disassembly

```asm
0x180010de8  lea     rax, __imp_PfIuPredictionsDataClose
0x180010def  jmp     __tailMerge_ext_ms_win_sysmain_pfapi_l1_1_1_dll
```
