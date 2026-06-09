# _CXmlContentFilter::CXmlContentFilter_::_1_::dtor$1

- ea: `0x180015581`
- end: `0x180015591`
- name: `_CXmlContentFilter::CXmlContentFilter_::_1_::dtor$1`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004520`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::CXmlContentFilter_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return _com_ptr_t<_com_IIID<ISAXXMLReader,&_GUID const IID_ISAXXMLReader>>::~_com_ptr_t<_com_IIID<ISAXXMLReader,&_GUID const IID_ISAXXMLReader>>((__int64 *)(*(_QWORD *)(a2 + 64) + 80LL));
}

```

## disassembly

```asm
0x180015581  mov     rcx, [rdx+40h]
0x180015588  add     rcx, 50h ; 'P'
0x18001558c  jmp     ??1?$_com_ptr_t@V?$_com_IIID@UISAXXMLReader@@$1?IID_ISAXXMLReader@@3U_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<ISAXXMLReader,&_GUID const IID_ISAXXMLReader>>::~_com_ptr_t<_com_IIID<ISAXXMLReader,&_GUID const IID_ISAXXMLReader>>(void)
```
