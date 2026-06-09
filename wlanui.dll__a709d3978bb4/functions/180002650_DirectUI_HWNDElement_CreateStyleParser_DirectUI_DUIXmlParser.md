# DirectUI::HWNDElement::CreateStyleParser(DirectUI::DUIXmlParser * *)

- ea: `0x180002650`
- end: `0x180002656`
- name: `?CreateStyleParser@HWNDElement@DirectUI@@UEAAJPEAPEAVDUIXmlParser@2@@Z_0`
- size: `6`
- prototype: `int(DirectUI::HWNDElement *__hidden this, struct DirectUI::DUIXmlParser **)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `DUI70!?CreateStyleParser@HWNDElement@DirectUI@@UEAAJPEAPEAVDUIXmlParser@2@@Z` at `0x180002650`

## pseudocode

```c
// attributes: thunk
int __fastcall DirectUI::HWNDElement::CreateStyleParser(
        DirectUI::HWNDElement *this,
        struct DirectUI::DUIXmlParser **a2)
{
  return __imp_?CreateStyleParser@HWNDElement@DirectUI@@UEAAJPEAPEAVDUIXmlParser@2@@Z(this, a2);
}

```

## disassembly

```asm
0x180002650  jmp     cs:__imp_?CreateStyleParser@HWNDElement@DirectUI@@UEAAJPEAPEAVDUIXmlParser@2@@Z
```
