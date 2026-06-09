# __imp_load_CreateCompatibleDC

- ea: `0x180001d2c`
- end: `0x180001d38`
- name: `__imp_load_CreateCompatibleDC`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c1d`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180001d2c`

## pseudocode

```c
__int64 load_CreateCompatibleDC()
{
  return _tailMerge_gdi32_dll();
}

```

## disassembly

```asm
0x180001d2c  lea     rax, __imp_CreateCompatibleDC
0x180001d33  jmp     __tailMerge_gdi32_dll
```
