# __imp_load_GdipCreateEffect

- ea: `0x180003a7b`
- end: `0x180003a87`
- name: `__imp_load_GdipCreateEffect`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000383a`

## import_xrefs

- `gdiplus!GdipCreateEffect` at `0x180003a7b`

## pseudocode

```c
__int64 load_GdipCreateEffect()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x180003a7b  lea     rax, __imp_GdipCreateEffect
0x180003a82  jmp     __tailMerge_gdiplus_dll
```
