# __imp_load_OpenPrinterA

- ea: `0x180006c3d`
- end: `0x180006c49`
- name: `__imp_load_OpenPrinterA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006b40`

## import_xrefs

- `WINSPOOL!OpenPrinterA` at `0x180006c3d`

## pseudocode

```c
__int64 load_OpenPrinterA()
{
  return _tailMerge_winspool_drv();
}

```

## disassembly

```asm
0x180006c3d  lea     rax, __imp_OpenPrinterA
0x180006c44  jmp     __tailMerge_winspool_drv
```
