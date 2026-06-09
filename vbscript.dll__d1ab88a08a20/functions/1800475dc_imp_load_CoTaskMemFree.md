# __imp_load_CoTaskMemFree

- ea: `0x1800475dc`
- end: `0x1800475e8`
- name: `__imp_load_CoTaskMemFree`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180047454`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x1800475dc`

## pseudocode

```c
__int64 load_CoTaskMemFree()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x1800475dc  lea     rax, __imp_CoTaskMemFree
0x1800475e3  jmp     __tailMerge_ole32_dll
```
