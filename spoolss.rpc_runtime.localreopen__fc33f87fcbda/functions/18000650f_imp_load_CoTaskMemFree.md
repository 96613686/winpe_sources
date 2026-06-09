# __imp_load_CoTaskMemFree

- ea: `0x18000650f`
- end: `0x18000651b`
- name: `__imp_load_CoTaskMemFree`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000646c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000650f`

## pseudocode

```c
__int64 load_CoTaskMemFree()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x18000650f  lea     rax, __imp_CoTaskMemFree
0x180006516  jmp     __tailMerge_ole32_dll
```
