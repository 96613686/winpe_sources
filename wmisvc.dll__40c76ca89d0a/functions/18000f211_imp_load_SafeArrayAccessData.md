# __imp_load_SafeArrayAccessData

- ea: `0x18000f211`
- end: `0x18000f21d`
- name: `__imp_load_SafeArrayAccessData`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000f180`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000f211`

## pseudocode

```c
__int64 load_SafeArrayAccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x18000f211  lea     rax, __imp_SafeArrayAccessData
0x18000f218  jmp     __tailMerge_oleaut32_dll
```
