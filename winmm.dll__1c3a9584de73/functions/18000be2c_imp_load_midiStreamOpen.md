# __imp_load_midiStreamOpen

- ea: `0x18000be2c`
- end: `0x18000be38`
- name: `__imp_load_midiStreamOpen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000bb01`

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!midiStreamOpen` at `0x18000be2c`

## pseudocode

```c
__int64 load_midiStreamOpen()
{
  return _tailMerge_api_ms_win_mm_mme_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000be2c  lea     rax, __imp_midiStreamOpen
0x18000be33  jmp     __tailMerge_api_ms_win_mm_mme_l1_1_0_dll
```
