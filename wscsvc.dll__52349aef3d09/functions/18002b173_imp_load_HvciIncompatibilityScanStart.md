# __imp_load_HvciIncompatibilityScanStart

- ea: `0x18002b173`
- end: `0x18002b17f`
- name: `__imp_load_HvciIncompatibilityScanStart`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002b0ac`

## import_xrefs

- `VbsApi!HvciIncompatibilityScanStart` at `0x18002b173`

## pseudocode

```c
__int64 load_HvciIncompatibilityScanStart()
{
  return _tailMerge_vbsapi_dll();
}

```

## disassembly

```asm
0x18002b173  lea     rax, __imp_HvciIncompatibilityScanStart
0x18002b17a  jmp     __tailMerge_vbsapi_dll
```
