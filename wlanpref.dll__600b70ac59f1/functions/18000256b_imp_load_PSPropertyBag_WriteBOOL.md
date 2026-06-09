# __imp_load_PSPropertyBag_WriteBOOL

- ea: `0x18000256b`
- end: `0x180002577`
- name: `__imp_load_PSPropertyBag_WriteBOOL`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024ec`

## import_xrefs

- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x18000256b`

## pseudocode

```c
__int64 load_PSPropertyBag_WriteBOOL()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x18000256b  lea     rax, __imp_PSPropertyBag_WriteBOOL
0x180002572  jmp     __tailMerge_propsys_dll
```
