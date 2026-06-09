# __imp_load_mmioWrite

- ea: `0x18000c349`
- end: `0x18000c355`
- name: `__imp_load_mmioWrite`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c2a6`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioWrite` at `0x18000c349`

## pseudocode

```c
__int64 load_mmioWrite()
{
  return _tailMerge_api_ms_win_mm_misc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000c349  lea     rax, __imp_mmioWrite
0x18000c350  jmp     __tailMerge_api_ms_win_mm_misc_l1_1_0_dll
```
