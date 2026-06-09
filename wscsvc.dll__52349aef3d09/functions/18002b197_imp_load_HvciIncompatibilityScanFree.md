# __imp_load_HvciIncompatibilityScanFree

- ea: `0x18002b197`
- end: `0x18002b1a3`
- name: `__imp_load_HvciIncompatibilityScanFree`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002b0ac`

## import_xrefs

- `VbsApi!HvciIncompatibilityScanFree` at `0x18002b197`

## pseudocode

```c
__int64 load_HvciIncompatibilityScanFree()
{
  return _tailMerge_vbsapi_dll();
}

```

## disassembly

```asm
0x18002b197  lea     rax, __imp_HvciIncompatibilityScanFree
0x18002b19e  jmp     __tailMerge_vbsapi_dll
```
