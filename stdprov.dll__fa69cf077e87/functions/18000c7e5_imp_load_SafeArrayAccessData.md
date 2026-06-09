# __imp_load_SafeArrayAccessData

- ea: `0x18000c7e5`
- end: `0x18000c7f1`
- name: `__imp_load_SafeArrayAccessData`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c530`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000c7e5`

## pseudocode

```c
__int64 load_SafeArrayAccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000c7e5  lea     rax, __imp_SafeArrayAccessData
0x18000c7ec  jmp     __tailMerge_oleaut32_dll
```
