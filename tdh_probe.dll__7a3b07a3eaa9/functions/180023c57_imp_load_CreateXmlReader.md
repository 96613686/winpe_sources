# __imp_load_CreateXmlReader

- ea: `0x180023c57`
- end: `0x180023c63`
- name: `__imp_load_CreateXmlReader`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180023b17`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x180023c57`

## pseudocode

```c
__int64 load_CreateXmlReader()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x180023c57  lea     rax, __imp_CreateXmlReader
0x180023c5e  jmp     __tailMerge_xmllite_dll
```
