# __imp_load_GdipDeleteGraphics

- ea: `0x180003925`
- end: `0x180003931`
- name: `__imp_load_GdipDeleteGraphics`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000383a`

## import_xrefs

- `gdiplus!GdipDeleteGraphics` at `0x180003925`

## pseudocode

```c
__int64 load_GdipDeleteGraphics()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x180003925  lea     rax, __imp_GdipDeleteGraphics
0x18000392c  jmp     __tailMerge_gdiplus_dll
```
