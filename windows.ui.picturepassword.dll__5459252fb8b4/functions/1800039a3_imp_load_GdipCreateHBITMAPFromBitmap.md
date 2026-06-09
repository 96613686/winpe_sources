# __imp_load_GdipCreateHBITMAPFromBitmap

- ea: `0x1800039a3`
- end: `0x1800039af`
- name: `__imp_load_GdipCreateHBITMAPFromBitmap`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000383a`

## import_xrefs

- `gdiplus!GdipCreateHBITMAPFromBitmap` at `0x1800039a3`

## pseudocode

```c
__int64 load_GdipCreateHBITMAPFromBitmap()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800039a3  lea     rax, __imp_GdipCreateHBITMAPFromBitmap
0x1800039aa  jmp     __tailMerge_gdiplus_dll
```
