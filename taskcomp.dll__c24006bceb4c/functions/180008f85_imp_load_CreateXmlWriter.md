# __imp_load_CreateXmlWriter

- ea: `0x180008f85`
- end: `0x180008f91`
- name: `__imp_load_CreateXmlWriter`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180008f06`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x180008f85`

## pseudocode

```c
__int64 load_CreateXmlWriter()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x180008f85  lea     rax, __imp_CreateXmlWriter
0x180008f8c  jmp     __tailMerge_xmllite_dll
```
