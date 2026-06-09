# __imp_load_CoTaskMemAlloc

- ea: `0x180047702`
- end: `0x18004770e`
- name: `__imp_load_CoTaskMemAlloc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180047454`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x180047702`

## pseudocode

```c
__int64 load_CoTaskMemAlloc()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180047702  lea     rax, __imp_CoTaskMemAlloc
0x180047709  jmp     __tailMerge_ole32_dll
```
