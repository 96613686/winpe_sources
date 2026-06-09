# __imp_load_GdipCreatePen1

- ea: `0x1800038dd`
- end: `0x1800038e9`
- name: `__imp_load_GdipCreatePen1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000383a`

## import_xrefs

- `gdiplus!GdipCreatePen1` at `0x1800038dd`

## pseudocode

```c
__int64 load_GdipCreatePen1()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800038dd  lea     rax, __imp_GdipCreatePen1
0x1800038e4  jmp     __tailMerge_gdiplus_dll
```
