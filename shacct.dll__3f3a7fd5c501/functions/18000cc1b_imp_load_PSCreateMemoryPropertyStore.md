# __imp_load_PSCreateMemoryPropertyStore

- ea: `0x18000cc1b`
- end: `0x18000cc27`
- name: `__imp_load_PSCreateMemoryPropertyStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000cb8a`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000cc1b`

## pseudocode

```c
__int64 load_PSCreateMemoryPropertyStore()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x18000cc1b  lea     rax, __imp_PSCreateMemoryPropertyStore
0x18000cc22  jmp     __tailMerge_propsys_dll
```
