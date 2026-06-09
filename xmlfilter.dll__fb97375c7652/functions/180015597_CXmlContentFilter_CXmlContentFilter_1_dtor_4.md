# _CXmlContentFilter::CXmlContentFilter_::_1_::dtor$4

- ea: `0x180015597`
- end: `0x1800155a3`
- name: `_CXmlContentFilter::CXmlContentFilter_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000fe38`

## pseudocode

```c
void __fastcall CXmlContentFilter::CXmlContentFilter_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  CSaxContentHandler::~CSaxContentHandler(*(CSaxContentHandler **)(a2 + 72));
}

```

## disassembly

```asm
0x180015597  mov     rcx, [rdx+48h]; this
0x18001559e  jmp     ??1CSaxContentHandler@@IEAA@XZ; CSaxContentHandler::~CSaxContentHandler(void)
```
