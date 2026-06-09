# __imp_load_waveOutOpen

- ea: `0x18000bd0c`
- end: `0x18000bd18`
- name: `__imp_load_waveOutOpen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000bb01`

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!waveOutOpen` at `0x18000bd0c`

## pseudocode

```c
__int64 load_waveOutOpen()
{
  return _tailMerge_api_ms_win_mm_mme_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000bd0c  lea     rax, __imp_waveOutOpen
0x18000bd13  jmp     __tailMerge_api_ms_win_mm_mme_l1_1_0_dll
```
