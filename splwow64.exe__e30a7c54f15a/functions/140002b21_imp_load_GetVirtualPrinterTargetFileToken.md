# __imp_load_GetVirtualPrinterTargetFileToken

- ea: `0x140002b21`
- end: `0x140002b2d`
- name: `__imp_load_GetVirtualPrinterTargetFileToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002aa2`

## import_xrefs

- `Print.PrintSupport.Source!GetVirtualPrinterTargetFileToken` at `0x140002b21`

## pseudocode

```c
__int64 load_GetVirtualPrinterTargetFileToken()
{
  return _tailMerge_print_printsupport_source_dll();
}

```

## disassembly

```asm
0x140002b21  lea     rax, __imp_GetVirtualPrinterTargetFileToken
0x140002b28  jmp     __tailMerge_print_printsupport_source_dll
```
