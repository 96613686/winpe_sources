# __imp_load_CoTaskMemRealloc

- ea: `0x1400020a1`
- end: `0x1400020ad`
- name: `__imp_load_CoTaskMemRealloc`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x140002010`

## import_xrefs

- `ole32!CoTaskMemRealloc` at `0x1400020a1`

## pseudocode

```c
__int64 load_CoTaskMemRealloc()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x1400020a1  lea     rax, __imp_CoTaskMemRealloc
0x1400020a8  jmp     __tailMerge_ole32_dll
```
