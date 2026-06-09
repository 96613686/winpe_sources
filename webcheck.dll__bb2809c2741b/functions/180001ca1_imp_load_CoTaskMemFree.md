# __imp_load_CoTaskMemFree

- ea: `0x180001ca1`
- end: `0x180001cad`
- name: `__imp_load_CoTaskMemFree`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180001bec`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180001ca1`

## pseudocode

```c
__int64 load_CoTaskMemFree()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180001ca1  lea     rax, __imp_CoTaskMemFree
0x180001ca8  jmp     __tailMerge_ole32_dll
```
