# __imp_load_HvciIncompatibilityScanInitialize

- ea: `0x18002b161`
- end: `0x18002b16d`
- name: `__imp_load_HvciIncompatibilityScanInitialize`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002b0ac`

## import_xrefs

- `VbsApi!HvciIncompatibilityScanInitialize` at `0x18002b161`

## pseudocode

```c
__int64 load_HvciIncompatibilityScanInitialize()
{
  return _tailMerge_vbsapi_dll();
}

```

## disassembly

```asm
0x18002b161  lea     rax, __imp_HvciIncompatibilityScanInitialize
0x18002b168  jmp     __tailMerge_vbsapi_dll
```
