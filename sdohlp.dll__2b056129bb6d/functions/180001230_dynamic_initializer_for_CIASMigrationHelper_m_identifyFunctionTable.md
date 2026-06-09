# _dynamic_initializer_for__CIASMigrationHelper::m_identifyFunctionTable__

- ea: `0x180001230`
- end: `0x180001305`
- name: `_dynamic_initializer_for__CIASMigrationHelper::m_identifyFunctionTable__`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180023f68`
- `0x18002d08c`

## string_xrefs

- `0x180001236`: `CompareStringValue`
- `0x180001265`: `CompareIntegerValue`
- `0x18000128d`: `CompareBooleanValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int dynamic_initializer_for__CIASMigrationHelper::m_identifyFunctionTable__()
{
  _bstr_t::_bstr_t((_bstr_t *)&CIASMigrationHelper::m_identifyFunctionTable, L"CompareStringValue");
  qword_180078FB8 = (__int64)CIASMigrationHelper::CompareValues;
  qword_180078FC0 = (__int64)CIASMigrationHelper::CompareStringValues;
  _bstr_t::_bstr_t((_bstr_t *)&qword_180078FC8, L"CompareIntegerValue");
  qword_180078FD0 = (__int64)CIASMigrationHelper::CompareValues;
  qword_180078FD8 = (__int64)CIASMigrationHelper::CompareIntegerValues;
  _bstr_t::_bstr_t((_bstr_t *)&qword_180078FE0, L"CompareBooleanValue");
  qword_180078FE8 = (__int64)CIASMigrationHelper::CompareValues;
  qword_180078FF0 = (__int64)CIASMigrationHelper::CompareBooleanValues;
  _bstr_t::_bstr_t((_bstr_t *)&qword_180078FF8, L"FindAnyValue");
  qword_180079000 = (__int64)CIASMigrationHelper::FindAnyValue;
  qword_180079008 = 0;
  qword_180079010 = 0;
  qword_180079018 = 0;
  qword_180079020 = 0;
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__CIASMigrationHelper::m_identifyFunctionTable__);
}

```

## disassembly

```asm
0x180001230  push    rbx
0x180001232  sub     rsp, 20h
0x180001236  lea     rdx, aComparestringv; "CompareStringValue"
0x18000123d  lea     rcx, ?m_identifyFunctionTable@CIASMigrationHelper@@1QBUIasIdentifyFunction@@B; this
0x180001244  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180001249  lea     rbx, ?CompareValues@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@1P6AJ11W4CompareOperator@@AEAHAEAV_bstr_t@@@ZK@Z; CIASMigrationHelper::CompareValues(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,long (*)(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,CompareOperator,int &,_bstr_t &),ulong)
0x180001250  mov     cs:qword_180078FB8, rbx
0x180001257  lea     rax, ?CompareStringValues@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0W4CompareOperator@@AEAHAEAV_bstr_t@@@Z; CIASMigrationHelper::CompareStringValues(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,CompareOperator,int &,_bstr_t &)
0x18000125e  mov     cs:qword_180078FC0, rax
0x180001265  lea     rdx, aCompareinteger; "CompareIntegerValue"
0x18000126c  lea     rcx, qword_180078FC8; this
0x180001273  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180001278  mov     cs:qword_180078FD0, rbx
0x18000127f  lea     rax, ?CompareIntegerValues@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0W4CompareOperator@@AEAHAEAV_bstr_t@@@Z; CIASMigrationHelper::CompareIntegerValues(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,CompareOperator,int &,_bstr_t &)
0x180001286  mov     cs:qword_180078FD8, rax
0x18000128d  lea     rdx, aCompareboolean; "CompareBooleanValue"
0x180001294  lea     rcx, qword_180078FE0; this
0x18000129b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800012a0  mov     cs:qword_180078FE8, rbx
0x1800012a7  lea     rax, ?CompareBooleanValues@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0W4CompareOperator@@AEAHAEAV_bstr_t@@@Z; CIASMigrationHelper::CompareBooleanValues(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,CompareOperator,int &,_bstr_t &)
0x1800012ae  mov     cs:qword_180078FF0, rax
0x1800012b5  lea     rdx, aFindanyvalue; "FindAnyValue"
0x1800012bc  lea     rcx, qword_180078FF8; this
0x1800012c3  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800012c8  lea     rax, ?FindAnyValue@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@1P6AJ11W4CompareOperator@@AEAHAEAV_bstr_t@@@ZK@Z; CIASMigrationHelper::FindAnyValue(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,long (*)(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,CompareOperator,int &,_bstr_t &),ulong)
0x1800012cf  mov     cs:qword_180079000, rax
0x1800012d6  xor     eax, eax
0x1800012d8  mov     cs:qword_180079008, rax
0x1800012df  mov     cs:qword_180079010, rax
0x1800012e6  mov     cs:qword_180079018, rax
0x1800012ed  mov     cs:qword_180079020, rax
0x1800012f4  lea     rcx, _dynamic_atexit_destructor_for__CIASMigrationHelper__m_identifyFunctionTable__
0x1800012fb  add     rsp, 20h
0x1800012ff  pop     rbx
0x180001300  jmp     atexit
```
