# __imp_load_mixerOpen

- ea: `0x18000c29a`
- end: `0x18000c2a6`
- name: `__imp_load_mixerOpen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000bb01`

## import_xrefs

- `api-ms-win-mm-mme-l1-1-0!mixerOpen` at `0x18000c29a`

## pseudocode

```c
__int64 load_mixerOpen()
{
  return _tailMerge_api_ms_win_mm_mme_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000c29a  lea     rax, __imp_mixerOpen
0x18000c2a1  jmp     __tailMerge_api_ms_win_mm_mme_l1_1_0_dll
```
