# __imp_load_mmioCreateChunk

- ea: `0x18000c40f`
- end: `0x18000c41b`
- name: `__imp_load_mmioCreateChunk`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c2a6`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioCreateChunk` at `0x18000c40f`

## pseudocode

```c
__int64 load_mmioCreateChunk()
{
  return _tailMerge_api_ms_win_mm_misc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000c40f  lea     rax, __imp_mmioCreateChunk
0x18000c416  jmp     __tailMerge_api_ms_win_mm_misc_l1_1_0_dll
```
