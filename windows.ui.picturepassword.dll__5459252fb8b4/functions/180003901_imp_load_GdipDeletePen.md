# __imp_load_GdipDeletePen

- ea: `0x180003901`
- end: `0x18000390d`
- name: `__imp_load_GdipDeletePen`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000383a`

## import_xrefs

- `gdiplus!GdipDeletePen` at `0x180003901`

## pseudocode

```c
__int64 load_GdipDeletePen()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x180003901  lea     rax, __imp_GdipDeletePen
0x180003908  jmp     __tailMerge_gdiplus_dll
```
