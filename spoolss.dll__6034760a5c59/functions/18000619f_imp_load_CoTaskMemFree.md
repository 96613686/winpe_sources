# __imp_load_CoTaskMemFree

- ea: `0x18000619f`
- end: `0x1800061ab`
- name: `__imp_load_CoTaskMemFree`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800060fc`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000619f`

## pseudocode

```c
__int64 load_CoTaskMemFree()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x18000619f  lea     rax, __imp_CoTaskMemFree
0x1800061a6  jmp     __tailMerge_ole32_dll
```
