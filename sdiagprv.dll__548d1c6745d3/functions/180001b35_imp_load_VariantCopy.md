# __imp_load_VariantCopy

- ea: `0x180001b35`
- end: `0x180001b41`
- name: `__imp_load_VariantCopy`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800019f0`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180001b35`

## pseudocode

```c
__int64 load_VariantCopy()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x180001b35  lea     rax, __imp_VariantCopy
0x180001b3c  jmp     __tailMerge_oleaut32_dll
```
