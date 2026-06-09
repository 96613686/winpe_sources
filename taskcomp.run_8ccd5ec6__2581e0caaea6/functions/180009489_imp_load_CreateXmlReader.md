# __imp_load_CreateXmlReader

- ea: `0x180009489`
- end: `0x180009495`
- name: `__imp_load_CreateXmlReader`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800093e6`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x180009489`

## pseudocode

```c
__int64 load_CreateXmlReader()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x180009489  lea     rax, __imp_CreateXmlReader
0x180009490  jmp     __tailMerge_xmllite_dll
```
