# __imp_load_GdipCreateBitmapFromScan0

- ea: `0x1800038ef`
- end: `0x1800038fb`
- name: `__imp_load_GdipCreateBitmapFromScan0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000383a`

## import_xrefs

- `gdiplus!GdipCreateBitmapFromScan0` at `0x1800038ef`

## pseudocode

```c
__int64 load_GdipCreateBitmapFromScan0()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800038ef  lea     rax, __imp_GdipCreateBitmapFromScan0
0x1800038f6  jmp     __tailMerge_gdiplus_dll
```
