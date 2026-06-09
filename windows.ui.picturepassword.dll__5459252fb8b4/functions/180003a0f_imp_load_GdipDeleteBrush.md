# __imp_load_GdipDeleteBrush

- ea: `0x180003a0f`
- end: `0x180003a1b`
- name: `__imp_load_GdipDeleteBrush`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000383a`

## import_xrefs

- `gdiplus!GdipDeleteBrush` at `0x180003a0f`

## pseudocode

```c
__int64 load_GdipDeleteBrush()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x180003a0f  lea     rax, __imp_GdipDeleteBrush
0x180003a16  jmp     __tailMerge_gdiplus_dll
```
