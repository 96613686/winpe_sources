# __imp_load_waveInOpen

- ea: `0x18000bd66`
- end: `0x18000bd72`
- name: `__imp_load_waveInOpen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000bb01`

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!waveInOpen` at `0x18000bd66`

## pseudocode

```c
__int64 load_waveInOpen()
{
  return _tailMerge_api_ms_win_mm_mme_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000bd66  lea     rax, __imp_waveInOpen
0x18000bd6d  jmp     __tailMerge_api_ms_win_mm_mme_l1_1_0_dll
```
