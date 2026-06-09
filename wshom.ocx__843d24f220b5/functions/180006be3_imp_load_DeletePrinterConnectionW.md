# __imp_load_DeletePrinterConnectionW

- ea: `0x180006be3`
- end: `0x180006bef`
- name: `__imp_load_DeletePrinterConnectionW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006b40`

## import_xrefs

- `WINSPOOL!DeletePrinterConnectionW` at `0x180006be3`

## pseudocode

```c
__int64 load_DeletePrinterConnectionW()
{
  return _tailMerge_winspool_drv();
}

```

## disassembly

```asm
0x180006be3  lea     rax, __imp_DeletePrinterConnectionW
0x180006bea  jmp     __tailMerge_winspool_drv
```
