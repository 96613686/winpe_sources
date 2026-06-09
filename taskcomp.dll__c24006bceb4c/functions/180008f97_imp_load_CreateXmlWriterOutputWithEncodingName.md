# __imp_load_CreateXmlWriterOutputWithEncodingName

- ea: `0x180008f97`
- end: `0x180008fa3`
- name: `__imp_load_CreateXmlWriterOutputWithEncodingName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180008f06`

## import_xrefs

- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180008f97`

## pseudocode

```c
__int64 load_CreateXmlWriterOutputWithEncodingName()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x180008f97  lea     rax, __imp_CreateXmlWriterOutputWithEncodingName
0x180008f9e  jmp     __tailMerge_xmllite_dll
```
