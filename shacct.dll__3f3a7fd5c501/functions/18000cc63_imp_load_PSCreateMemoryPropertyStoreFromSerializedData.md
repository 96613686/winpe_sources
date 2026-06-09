# __imp_load_PSCreateMemoryPropertyStoreFromSerializedData

- ea: `0x18000cc63`
- end: `0x18000cc6f`
- name: `__imp_load_PSCreateMemoryPropertyStoreFromSerializedData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000cb8a`

## import_xrefs

- `PROPSYS!__imp_PSCreateMemoryPropertyStoreFromSerializedData` at `0x18000cc63`

## pseudocode

```c
__int64 load_PSCreateMemoryPropertyStoreFromSerializedData()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x18000cc63  lea     rax, __imp_PSCreateMemoryPropertyStoreFromSerializedData
0x18000cc6a  jmp     __tailMerge_propsys_dll
```
