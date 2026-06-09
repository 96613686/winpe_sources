# __imp_load_CoTaskMemAlloc

- ea: `0x1800462f2`
- end: `0x1800462fe`
- name: `__imp_load_CoTaskMemAlloc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180046044`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800462f2`

## pseudocode

```c
__int64 load_CoTaskMemAlloc()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x1800462f2  lea     rax, __imp_CoTaskMemAlloc
0x1800462f9  jmp     __tailMerge_ole32_dll
```
