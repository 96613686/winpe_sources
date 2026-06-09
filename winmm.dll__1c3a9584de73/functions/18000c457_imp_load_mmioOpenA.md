# __imp_load_mmioOpenA

- ea: `0x18000c457`
- end: `0x18000c463`
- name: `__imp_load_mmioOpenA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c2a6`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioOpenA` at `0x18000c457`

## pseudocode

```c
__int64 load_mmioOpenA()
{
  return _tailMerge_api_ms_win_mm_misc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000c457  lea     rax, __imp_mmioOpenA
0x18000c45e  jmp     __tailMerge_api_ms_win_mm_misc_l1_1_0_dll
```
