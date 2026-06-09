# __imp_load_midiOutOpen

- ea: `0x18000bd1e`
- end: `0x18000bd2a`
- name: `__imp_load_midiOutOpen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000bb01`

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!midiOutOpen` at `0x18000bd1e`

## pseudocode

```c
__int64 load_midiOutOpen()
{
  return _tailMerge_api_ms_win_mm_mme_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000bd1e  lea     rax, __imp_midiOutOpen
0x18000bd25  jmp     __tailMerge_api_ms_win_mm_mme_l1_1_0_dll
```
