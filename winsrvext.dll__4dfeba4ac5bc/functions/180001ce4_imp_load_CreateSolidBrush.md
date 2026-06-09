# __imp_load_CreateSolidBrush

- ea: `0x180001ce4`
- end: `0x180001cf0`
- name: `__imp_load_CreateSolidBrush`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c1d`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x180001ce4`

## pseudocode

```c
__int64 load_CreateSolidBrush()
{
  return _tailMerge_gdi32_dll();
}

```

## disassembly

```asm
0x180001ce4  lea     rax, __imp_CreateSolidBrush
0x180001ceb  jmp     __tailMerge_gdi32_dll
```
