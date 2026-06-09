# __imp_load_GdipCreateSolidFill

- ea: `0x1800039b5`
- end: `0x1800039c1`
- name: `__imp_load_GdipCreateSolidFill`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000383a`

## import_xrefs

- `gdiplus!GdipCreateSolidFill` at `0x1800039b5`

## pseudocode

```c
__int64 load_GdipCreateSolidFill()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800039b5  lea     rax, __imp_GdipCreateSolidFill
0x1800039bc  jmp     __tailMerge_gdiplus_dll
```
