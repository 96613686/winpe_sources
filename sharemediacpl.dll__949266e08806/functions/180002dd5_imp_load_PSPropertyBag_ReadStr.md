# __imp_load_PSPropertyBag_ReadStr

- ea: `0x180002dd5`
- end: `0x180002de1`
- name: `__imp_load_PSPropertyBag_ReadStr`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002d56`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadStr` at `0x180002dd5`

## pseudocode

```c
__int64 load_PSPropertyBag_ReadStr()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x180002dd5  lea     rax, __imp_PSPropertyBag_ReadStr
0x180002ddc  jmp     __tailMerge_propsys_dll
```
