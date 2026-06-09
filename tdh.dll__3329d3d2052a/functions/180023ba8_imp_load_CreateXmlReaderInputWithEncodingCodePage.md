# __imp_load_CreateXmlReaderInputWithEncodingCodePage

- ea: `0x180023ba8`
- end: `0x180023bb4`
- name: `__imp_load_CreateXmlReaderInputWithEncodingCodePage`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180023b17`

## import_xrefs

- `XmlLite!CreateXmlReaderInputWithEncodingCodePage` at `0x180023ba8`

## pseudocode

```c
__int64 load_CreateXmlReaderInputWithEncodingCodePage()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x180023ba8  lea     rax, __imp_CreateXmlReaderInputWithEncodingCodePage
0x180023baf  jmp     __tailMerge_xmllite_dll
```
