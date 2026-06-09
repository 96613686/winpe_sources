# __imp_load_GdipDeleteEffect

- ea: `0x1800038b9`
- end: `0x1800038c5`
- name: `__imp_load_GdipDeleteEffect`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000383a`

## import_xrefs

- `gdiplus!GdipDeleteEffect` at `0x1800038b9`

## pseudocode

```c
__int64 load_GdipDeleteEffect()
{
  return _tailMerge_gdiplus_dll();
}

```

## disassembly

```asm
0x1800038b9  lea     rax, __imp_GdipDeleteEffect
0x1800038c0  jmp     __tailMerge_gdiplus_dll
```
