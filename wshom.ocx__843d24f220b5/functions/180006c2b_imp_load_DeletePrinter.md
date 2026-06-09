# __imp_load_DeletePrinter

- ea: `0x180006c2b`
- end: `0x180006c37`
- name: `__imp_load_DeletePrinter`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006b40`

## import_xrefs

- `WINSPOOL!DeletePrinter` at `0x180006c2b`

## pseudocode

```c
__int64 load_DeletePrinter()
{
  return _tailMerge_winspool_drv();
}

```

## disassembly

```asm
0x180006c2b  lea     rax, __imp_DeletePrinter
0x180006c32  jmp     __tailMerge_winspool_drv
```
