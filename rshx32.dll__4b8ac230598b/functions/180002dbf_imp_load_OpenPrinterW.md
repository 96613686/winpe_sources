# __imp_load_OpenPrinterW

- ea: `0x180002dbf`
- end: `0x180002dcb`
- name: `__imp_load_OpenPrinterW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002d2e`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x180002dbf`

## pseudocode

```c
__int64 load_OpenPrinterW()
{
  return _tailMerge_winspool_drv();
}

```

## disassembly

```asm
0x180002dbf  lea     rax, __imp_OpenPrinterW
0x180002dc6  jmp     __tailMerge_winspool_drv
```
