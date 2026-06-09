# __imp_load_SafeArrayAccessData

- ea: `0x180001aed`
- end: `0x180001af9`
- name: `__imp_load_SafeArrayAccessData`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800019f0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180001aed`

## pseudocode

```c
__int64 load_SafeArrayAccessData()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x180001aed  lea     rax, __imp_SafeArrayAccessData
0x180001af4  jmp     __tailMerge_oleaut32_dll
```
