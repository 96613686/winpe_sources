# __imp_load_DeleteObject

- ea: `0x180001d74`
- end: `0x180001d80`
- name: `__imp_load_DeleteObject`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001c1d`

## import_xrefs

- `GDI32!DeleteObject` at `0x180001d74`

## pseudocode

```c
__int64 load_DeleteObject()
{
  return _tailMerge_gdi32_dll();
}

```

## disassembly

```asm
0x180001d74  lea     rax, __imp_DeleteObject
0x180001d7b  jmp     __tailMerge_gdi32_dll
```
