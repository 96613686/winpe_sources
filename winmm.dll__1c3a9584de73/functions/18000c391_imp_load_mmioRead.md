# __imp_load_mmioRead

- ea: `0x18000c391`
- end: `0x18000c39d`
- name: `__imp_load_mmioRead`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c2a6`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioRead` at `0x18000c391`

## pseudocode

```c
__int64 load_mmioRead()
{
  return _tailMerge_api_ms_win_mm_misc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000c391  lea     rax, __imp_mmioRead
0x18000c398  jmp     __tailMerge_api_ms_win_mm_misc_l1_1_0_dll
```
