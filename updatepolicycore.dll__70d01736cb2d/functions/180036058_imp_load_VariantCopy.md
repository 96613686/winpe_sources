# __imp_load_VariantCopy

- ea: `0x180036058`
- end: `0x180036064`
- name: `__imp_load_VariantCopy`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002fa54`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180036058`

## pseudocode

```c
__int64 load_VariantCopy()
{
  return _tailMerge_oleaut32_dll();
}

```

## disassembly

```asm
0x180036058  lea     rax, __imp_VariantCopy
0x18003605f  jmp     __tailMerge_oleaut32_dll
```
