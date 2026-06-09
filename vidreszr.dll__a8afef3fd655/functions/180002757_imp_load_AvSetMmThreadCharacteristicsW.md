# __imp_load_AvSetMmThreadCharacteristicsW

- ea: `0x180002757`
- end: `0x180002763`
- name: `__imp_load_AvSetMmThreadCharacteristicsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800026c6`

## import_xrefs

- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180002757`

## pseudocode

```c
__int64 load_AvSetMmThreadCharacteristicsW()
{
  return _tailMerge_avrt_dll();
}

```

## disassembly

```asm
0x180002757  lea     rax, __imp_AvSetMmThreadCharacteristicsW
0x18000275e  jmp     __tailMerge_avrt_dll
```
