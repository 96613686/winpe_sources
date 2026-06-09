# _CXmlContentFilter::Load_::_1_::dtor$0_0

- ea: `0x18001500c`
- end: `0x180015018`
- name: `_CXmlContentFilter::Load_::_1_::dtor$0_0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004520`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::Load_::_1_::dtor_0_0(__int64 a1, __int64 a2)
{
  return _com_ptr_t<_com_IIID<ISAXXMLReader,&_GUID const IID_ISAXXMLReader>>::~_com_ptr_t<_com_IIID<ISAXXMLReader,&_GUID const IID_ISAXXMLReader>>((__int64 *)(a2 + 152));
}

```

## disassembly

```asm
0x18001500c  lea     rcx, [rdx+98h]
0x180015013  jmp     ??1?$_com_ptr_t@V?$_com_IIID@UISAXXMLReader@@$1?IID_ISAXXMLReader@@3U_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<ISAXXMLReader,&_GUID const IID_ISAXXMLReader>>::~_com_ptr_t<_com_IIID<ISAXXMLReader,&_GUID const IID_ISAXXMLReader>>(void)
```
