# _dynamic_initializer_for__CIASMigrationHelper::m_migActionFunctionTable__

- ea: `0x180001310`
- end: `0x1800013df`
- name: `_dynamic_initializer_for__CIASMigrationHelper::m_migActionFunctionTable__`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180023f68`
- `0x18002d08c`

## string_xrefs

- `0x180001335`: `ReplaceNode`
- `0x180001377`: `RemoveNode`
- `0x180001398`: `RemoveRequiredProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int dynamic_initializer_for__CIASMigrationHelper::m_migActionFunctionTable__()
{
  _bstr_t::_bstr_t((_bstr_t *)&CIASMigrationHelper::m_migActionFunctionTable, L"AddNode");
  qword_180078F58 = (__int64)CIASMigrationHelper::AddNode;
  _bstr_t::_bstr_t((_bstr_t *)&qword_180078F60, L"ReplaceNode");
  qword_180078F68 = (__int64)CIASMigrationHelper::ReplaceNode;
  _bstr_t::_bstr_t((_bstr_t *)&qword_180078F70, L"AddRequiredProperties");
  qword_180078F78 = (__int64)CIASMigrationHelper::AddRequiredProperties;
  _bstr_t::_bstr_t((_bstr_t *)&qword_180078F80, L"RemoveNode");
  qword_180078F88 = (__int64)CIASMigrationHelper::RemoveNode;
  _bstr_t::_bstr_t((_bstr_t *)&qword_180078F90, L"RemoveRequiredProperties");
  qword_180078F98 = (__int64)CIASMigrationHelper::RemoveRequiredProperties;
  qword_180078FA0 = 0;
  qword_180078FA8 = 0;
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__CIASMigrationHelper::m_migActionFunctionTable__);
}

```

## disassembly

```asm
0x180001310  sub     rsp, 28h
0x180001314  lea     rdx, aAddnode; "AddNode"
0x18000131b  lea     rcx, ?m_migActionFunctionTable@CIASMigrationHelper@@1QBUIasFunctionTableItem@@B; this
0x180001322  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180001327  lea     rax, ?AddNode@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; CIASMigrationHelper::AddNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)
0x18000132e  mov     cs:qword_180078F58, rax
0x180001335  lea     rdx, aReplacenode; "ReplaceNode"
0x18000133c  lea     rcx, qword_180078F60; this
0x180001343  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180001348  lea     rax, ?ReplaceNode@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; CIASMigrationHelper::ReplaceNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)
0x18000134f  mov     cs:qword_180078F68, rax
0x180001356  lea     rdx, aAddrequiredpro; "AddRequiredProperties"
0x18000135d  lea     rcx, qword_180078F70; this
0x180001364  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180001369  lea     rax, ?AddRequiredProperties@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; CIASMigrationHelper::AddRequiredProperties(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)
0x180001370  mov     cs:qword_180078F78, rax
0x180001377  lea     rdx, aRemovenode; "RemoveNode"
0x18000137e  lea     rcx, qword_180078F80; this
0x180001385  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000138a  lea     rax, ?RemoveNode@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; CIASMigrationHelper::RemoveNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)
0x180001391  mov     cs:qword_180078F88, rax
0x180001398  lea     rdx, aRemoverequired; "RemoveRequiredProperties"
0x18000139f  lea     rcx, qword_180078F90; this
0x1800013a6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800013ab  lea     rax, ?RemoveRequiredProperties@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; CIASMigrationHelper::RemoveRequiredProperties(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)
0x1800013b2  mov     cs:qword_180078F98, rax
0x1800013b9  mov     cs:qword_180078FA0, 0
0x1800013c4  mov     cs:qword_180078FA8, 0
0x1800013cf  lea     rcx, _dynamic_atexit_destructor_for__CIASMigrationHelper__m_migActionFunctionTable__
0x1800013d6  add     rsp, 28h
0x1800013da  jmp     atexit
```
