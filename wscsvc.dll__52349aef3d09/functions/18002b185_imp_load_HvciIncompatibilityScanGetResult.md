# __imp_load_HvciIncompatibilityScanGetResult

- ea: `0x18002b185`
- end: `0x18002b191`
- name: `__imp_load_HvciIncompatibilityScanGetResult`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002b0ac`

## import_xrefs

- `VbsApi!HvciIncompatibilityScanGetResult` at `0x18002b185`

## pseudocode

```c
__int64 load_HvciIncompatibilityScanGetResult()
{
  return _tailMerge_vbsapi_dll();
}

```

## disassembly

```asm
0x18002b185  lea     rax, __imp_HvciIncompatibilityScanGetResult
0x18002b18c  jmp     __tailMerge_vbsapi_dll
```
