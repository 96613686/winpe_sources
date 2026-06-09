# __imp_load_CreateXmlReader

- ea: `0x180008fa9`
- end: `0x180008fb5`
- name: `__imp_load_CreateXmlReader`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180008f06`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x180008fa9`

## pseudocode

```c
__int64 load_CreateXmlReader()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x180008fa9  lea     rax, __imp_CreateXmlReader
0x180008fb0  jmp     __tailMerge_xmllite_dll
```
