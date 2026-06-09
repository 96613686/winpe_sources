# __imp_load_mmioOpenW

- ea: `0x18000c37f`
- end: `0x18000c38b`
- name: `__imp_load_mmioOpenW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c2a6`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioOpenW` at `0x18000c37f`

## pseudocode

```c
__int64 load_mmioOpenW()
{
  return _tailMerge_api_ms_win_mm_misc_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000c37f  lea     rax, __imp_mmioOpenW
0x18000c386  jmp     __tailMerge_api_ms_win_mm_misc_l1_1_0_dll
```
