# __imp_load_DeleteDC

- ea: `0x180001d62`
- end: `0x180001d6e`
- name: `__imp_load_DeleteDC`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c1d`

## import_xrefs

- `GDI32!DeleteDC` at `0x180001d62`

## pseudocode

```c
__int64 load_DeleteDC()
{
  return _tailMerge_gdi32_dll();
}

```

## disassembly

```asm
0x180001d62  lea     rax, __imp_DeleteDC
0x180001d69  jmp     __tailMerge_gdi32_dll
```
