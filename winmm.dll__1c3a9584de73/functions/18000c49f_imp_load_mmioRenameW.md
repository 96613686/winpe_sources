# __imp_load_mmioRenameW

- ea: `0x18000c49f`
- end: `0x18000c4ab`
- name: `__imp_load_mmioRenameW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c2a6`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioRenameW` at `0x18000c49f`

## pseudocode

```c
__int64 load_mmioRenameW()
{
  return _tailMerge_api_ms_win_mm_misc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000c49f  lea     rax, __imp_mmioRenameW
0x18000c4a6  jmp     __tailMerge_api_ms_win_mm_misc_l1_1_0_dll
```
