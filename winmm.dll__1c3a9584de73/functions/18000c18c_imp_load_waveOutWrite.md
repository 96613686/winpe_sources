# __imp_load_waveOutWrite

- ea: `0x18000c18c`
- end: `0x18000c198`
- name: `__imp_load_waveOutWrite`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000bb01`

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!waveOutWrite` at `0x18000c18c`

## pseudocode

```c
__int64 load_waveOutWrite()
{
  return _tailMerge_api_ms_win_mm_mme_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000c18c  lea     rax, __imp_waveOutWrite
0x18000c193  jmp     __tailMerge_api_ms_win_mm_mme_l1_1_0_dll
```
