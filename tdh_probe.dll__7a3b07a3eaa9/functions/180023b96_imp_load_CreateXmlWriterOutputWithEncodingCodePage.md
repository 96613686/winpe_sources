# __imp_load_CreateXmlWriterOutputWithEncodingCodePage

- ea: `0x180023b96`
- end: `0x180023ba2`
- name: `__imp_load_CreateXmlWriterOutputWithEncodingCodePage`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180023b17`

## import_xrefs

- `XmlLite!CreateXmlWriterOutputWithEncodingCodePage` at `0x180023b96`

## pseudocode

```c
__int64 load_CreateXmlWriterOutputWithEncodingCodePage()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x180023b96  lea     rax, __imp_CreateXmlWriterOutputWithEncodingCodePage
0x180023b9d  jmp     __tailMerge_xmllite_dll
```
