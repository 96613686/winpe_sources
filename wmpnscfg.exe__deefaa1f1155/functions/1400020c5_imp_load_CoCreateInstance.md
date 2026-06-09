# __imp_load_CoCreateInstance

- ea: `0x1400020c5`
- end: `0x1400020d1`
- name: `__imp_load_CoCreateInstance`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1400020c5`

## pseudocode

```c
__int64 load_CoCreateInstance()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x1400020c5  lea     rax, __imp_CoCreateInstance
0x1400020cc  jmp     __tailMerge_ole32_dll
```
