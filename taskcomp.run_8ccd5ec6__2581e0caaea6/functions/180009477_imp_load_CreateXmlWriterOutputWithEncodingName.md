# __imp_load_CreateXmlWriterOutputWithEncodingName

- ea: `0x180009477`
- end: `0x180009483`
- name: `__imp_load_CreateXmlWriterOutputWithEncodingName`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800093e6`

## import_xrefs

- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x180009477`

## pseudocode

```c
__int64 load_CreateXmlWriterOutputWithEncodingName()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x180009477  lea     rax, __imp_CreateXmlWriterOutputWithEncodingName
0x18000947e  jmp     __tailMerge_xmllite_dll
```
