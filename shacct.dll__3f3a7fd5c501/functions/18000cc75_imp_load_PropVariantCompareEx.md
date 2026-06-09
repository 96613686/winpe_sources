# __imp_load_PropVariantCompareEx

- ea: `0x18000cc75`
- end: `0x18000cc81`
- name: `__imp_load_PropVariantCompareEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000cb8a`

## import_xrefs

- `PROPSYS!PropVariantCompareEx` at `0x18000cc75`

## pseudocode

```c
__int64 load_PropVariantCompareEx()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x18000cc75  lea     rax, __imp_PropVariantCompareEx
0x18000cc7c  jmp     __tailMerge_propsys_dll
```
