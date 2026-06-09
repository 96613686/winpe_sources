# __imp_load_midiInOpen

- ea: `0x18000bc8e`
- end: `0x18000bc9a`
- name: `__imp_load_midiInOpen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000bb01`

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!midiInOpen` at `0x18000bc8e`

## pseudocode

```c
__int64 load_midiInOpen()
{
  return _tailMerge_api_ms_win_mm_mme_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000bc8e  lea     rax, __imp_midiInOpen
0x18000bc95  jmp     __tailMerge_api_ms_win_mm_mme_l1_1_0_dll
```
