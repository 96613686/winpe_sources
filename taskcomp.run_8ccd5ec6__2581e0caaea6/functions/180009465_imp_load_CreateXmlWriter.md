# __imp_load_CreateXmlWriter

- ea: `0x180009465`
- end: `0x180009471`
- name: `__imp_load_CreateXmlWriter`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800093e6`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x180009465`

## pseudocode

```c
__int64 load_CreateXmlWriter()
{
  return _tailMerge_xmllite_dll();
}

```

## disassembly

```asm
0x180009465  lea     rax, __imp_CreateXmlWriter
0x18000946c  jmp     __tailMerge_xmllite_dll
```
