# __imp_load_mmioRenameA

- ea: `0x18000c36d`
- end: `0x18000c379`
- name: `__imp_load_mmioRenameA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c2a6`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioRenameA` at `0x18000c36d`

## pseudocode

```c
__int64 load_mmioRenameA()
{
  return _tailMerge_api_ms_win_mm_misc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000c36d  lea     rax, __imp_mmioRenameA
0x18000c374  jmp     __tailMerge_api_ms_win_mm_misc_l1_1_0_dll
```
