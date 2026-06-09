# __imp_load_?CreateStyleParser@HWNDElement@DirectUI@@UEAAJPEAPEAVDUIXmlParser@2@@Z

- ea: `0x180003bcc`
- end: `0x180003bd8`
- name: `__imp_load_?CreateStyleParser@HWNDElement@DirectUI@@UEAAJPEAPEAVDUIXmlParser@2@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003126`

## import_xrefs

- `DUI70!?CreateStyleParser@HWNDElement@DirectUI@@UEAAJPEAPEAVDUIXmlParser@2@@Z` at `0x180003bcc`

## pseudocode

```c
__int64 load__CreateStyleParser_HWNDElement_DirectUI__UEAAJPEAPEAVDUIXmlParser_2__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180003bcc  lea     rax, __imp_?CreateStyleParser@HWNDElement@DirectUI@@UEAAJPEAPEAVDUIXmlParser@2@@Z; DirectUI::HWNDElement::CreateStyleParser(DirectUI::DUIXmlParser * *)
0x180003bd3  jmp     __tailMerge_dui70_dll
```
