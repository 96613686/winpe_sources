# CIASMigrationHelper::SearchForUnsupportedPropertiesInXML(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)

- ea: `0x18004f2cc`
- end: `0x18005003b`
- name: `?SearchForUnsupportedPropertiesInXML@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0@Z`
- size: `3439`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004cdf4`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x18002d08c`
- `0x18002efa0`
- `0x180042a80`
- `0x180047604`
- `0x18004c8d0`
- `0x18004cef4`
- `0x18004cf60`
- `0x18004d11c`
- `0x18004d190`
- `0x18004d1ec`
- `0x18004f2cc`
- `0x180050044`
- `0x180051e7c`
- `0x1800524fc`
- `0x180052588`
- `0x180058010`

## string_xrefs

- `0x18004fd28`: `FindOnePropertyInXML() failed: %!hresult!`
- `0x18004f90a`: `./ReplaceChildrenNode`
- `0x18004f4d8`: `./Path`

## pseudocode

```c
// Hidden C++ exception states: #wind=27 #try_helpers=1
__int64 __fastcall CIASMigrationHelper::SearchForUnsupportedPropertiesInXML(__int64 a1, __int64 a2)
{
  struct IUnknown *v2; // r12
  __int64 v3; // rbx
  __int64 v4; // rdi
  __int64 v5; // r14
  struct IUnknown *v6; // rax
  __int64 v7; // rax
  struct IUnknown *v8; // rsi
  __int64 *v9; // rax
  __int64 v10; // rsi
  __int64 v11; // r15
  struct IUnknown *v13; // rax
  __int64 *v14; // rax
  struct IUnknown *v15; // rax
  __int64 *Node; // rax
  __int64 v17; // rsi
  __int64 v18; // r13
  struct IUnknown *v19; // r15
  __int64 *v20; // rax
  __int64 v21; // r15
  int StringValueFromNode; // r15d
  struct IUnknown *v23; // rax
  __int64 v24; // rax
  __int64 v25; // r15
  struct IUnknown *v26; // r15
  __int64 *v27; // rax
  int DWordValueFromNode; // r15d
  struct IUnknown *v29; // r15
  struct IUnknown *v30; // rax
  struct IUnknown *v31; // rax
  struct IUnknown *v32; // rax
  struct IUnknown *v33; // rcx
  struct IUnknown *v34; // rax
  struct IUnknown *v35; // rcx
  struct IUnknown *v36; // rax
  __int64 *v37; // rax
  __int64 v38; // [rsp+30h] [rbp-128h] BYREF
  struct IUnknown *v39; // [rsp+38h] [rbp-120h]
  __int64 v40; // [rsp+40h] [rbp-118h] BYREF
  struct IUnknown *v41; // [rsp+48h] [rbp-110h] BYREF
  __int64 v42; // [rsp+50h] [rbp-108h] BYREF
  struct IUnknown *v43; // [rsp+58h] [rbp-100h] BYREF
  __int64 v44; // [rsp+60h] [rbp-F8h] BYREF
  __int64 v45; // [rsp+68h] [rbp-F0h] BYREF
  __int64 v46; // [rsp+70h] [rbp-E8h] BYREF
  __int64 v47; // [rsp+78h] [rbp-E0h] BYREF
  __int64 v48; // [rsp+80h] [rbp-D8h] BYREF
  _QWORD v49[2]; // [rsp+88h] [rbp-D0h] BYREF
  __int64 v50; // [rsp+98h] [rbp-C0h]
  _BYTE v51[8]; // [rsp+A0h] [rbp-B8h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-B0h]
  __int64 v53; // [rsp+B0h] [rbp-A8h]
  _BYTE v54[8]; // [rsp+B8h] [rbp-A0h] BYREF
  __int64 v55; // [rsp+C0h] [rbp-98h]
  _BYTE v56[8]; // [rsp+C8h] [rbp-90h] BYREF
  __int64 v57; // [rsp+D0h] [rbp-88h]
  _BYTE v58[8]; // [rsp+D8h] [rbp-80h] BYREF
  __int64 v59; // [rsp+E0h] [rbp-78h]
  __int64 v60; // [rsp+E8h] [rbp-70h]
  __int64 v61; // [rsp+F0h] [rbp-68h]
  __int64 v62; // [rsp+F8h] [rbp-60h]
  int v64; // [rsp+168h] [rbp+10h]
  __int64 v65; // [rsp+170h] [rbp+18h] BYREF
  __int64 v66; // [rsp+178h] [rbp+20h] BYREF

  v64 = a2;
  v2 = 0;
  v3 = 0;
  v45 = 0;
  v4 = 0;
  v44 = 0;
  v5 = 0;
  v42 = 0;
  v6 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a2);
  v7 = MSXML2::IXMLDOMDocument::GetdocumentElement(v6);
  v8 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(v7);
  _bstr_t::_bstr_t((_bstr_t *)&v65, L"/Root/SDO_NAP_Schema_Identifiers");
  v9 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v8);
  v10 = *v9;
  v11 = 0;
  if ( *v9 )
  {
    v3 = *v9;
    v45 = *v9;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v45);
    v11 = v10;
  }
  if ( v66 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
  if ( v11 )
  {
    v13 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v45);
    v14 = (__int64 *)MSXML2::IXMLDOMNode::GetchildNodes(v13);
    if ( *v14 )
    {
      v4 = *v14;
      v44 = *v14;
      _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v44);
    }
    if ( v65 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    if ( v4 )
    {
      v15 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v44);
      Node = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v15);
      if ( *Node )
      {
        v5 = *Node;
        v42 = *Node;
        _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v42);
      }
      if ( v65 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
      if ( v5 )
      {
        do
        {
          v17 = 0;
          v47 = 0;
          v18 = 0;
          v48 = 0;
          v38 = 0;
          v40 = 0;
          v19 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v42);
          _bstr_t::_bstr_t((_bstr_t *)v51, L"./Path");
          v20 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v19);
          v21 = *v20;
          if ( *v20 )
          {
            v17 = *v20;
            v47 = *v20;
            _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v47);
          }
          else
          {
            v21 = 0;
          }
          if ( v52 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
          if ( !v21 )
          {
            _bstr_t::_Free((_bstr_t *)&v40);
            if ( v38 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
            if ( v3 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
            return 2147549183LL;
          }
          StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v47, &v40);
          if ( StringValueFromNode < 0 )
          {
            _bstr_t::_Free((_bstr_t *)&v40);
            if ( v38 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
            if ( v3 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
            return (unsigned int)StringValueFromNode;
          }
          v23 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
          v46 = v40;
          if ( v40 )
            _InterlockedIncrement((volatile signed __int32 *)(v40 + 16));
          v24 = *(_QWORD *)MSXML2::IXMLDOMNode::selectSingleNode(v23);
          v25 = v38;
          if ( v38 != v24 )
          {
            v38 = v24;
            _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v38);
            if ( v25 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          if ( v53 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
          if ( !v38 )
          {
            _bstr_t::_Free((_bstr_t *)&v40);
            if ( v38 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
            if ( v3 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
            return 2147549183LL;
          }
          v26 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v42);
          _bstr_t::_bstr_t((_bstr_t *)v54, L"./TitleResource");
          v27 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v26);
          if ( *v27 )
          {
            v18 = *v27;
            v48 = *v27;
            _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v48);
          }
          if ( v55 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
          if ( !v18 )
          {
            _bstr_t::_Free((_bstr_t *)&v40);
            if ( v38 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
            if ( v3 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
            return 2147549183LL;
          }
          LODWORD(v65) = 0;
          DWordValueFromNode = CIASMigrationHelper::GetDWordValueFromNode(&v48, &v65);
          if ( DWordValueFromNode < 0 )
          {
            _bstr_t::_Free((_bstr_t *)&v40);
            if ( v38 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
            if ( v3 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
            return (unsigned int)DWordValueFromNode;
          }
          v29 = 0;
          v49[0] = 0;
          LODWORD(v66) = 0;
          v43 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v42);
          _bstr_t::_bstr_t((_bstr_t *)v56, L"./ReplaceChildrenNode");
          v30 = *(struct IUnknown **)MSXML2::IXMLDOMNode::selectSingleNode(v43);
          v43 = 0;
          if ( v30 )
          {
            v29 = v30;
            v49[0] = v30;
            _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(v49);
            v43 = v29;
          }
          if ( v57 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
          if ( !v43 )
          {
            if ( v29 )
              ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
            _bstr_t::_Free((_bstr_t *)&v40);
            if ( v38 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
            if ( v3 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
            return 2147549183LL;
          }
          LODWORD(v39) = CIASMigrationHelper::GetBOOLValueFromNode(v49, &v66);
          if ( (int)v39 < 0 )
          {
            if ( v29 )
              ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
            _bstr_t::_Free((_bstr_t *)&v40);
            if ( v38 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
            if ( v3 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
            return (unsigned int)v39;
          }
          v62 = 0;
          v43 = 0;
          v41 = 0;
          v39 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v42);
          _bstr_t::_bstr_t((_bstr_t *)v58, L"./Value_Identifier");
          v31 = *(struct IUnknown **)MSXML2::IXMLDOMNode::selectNodes(v39);
          v39 = 0;
          if ( v31 )
          {
            v2 = v31;
            v43 = v31;
            _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v43);
            v39 = v2;
          }
          if ( v59 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
          if ( !v39 )
          {
            if ( v41 )
              ((void (__fastcall *)(struct IUnknown *))v41->lpVtbl->Release)(v41);
            if ( v2 )
              ((void (__fastcall *)(struct IUnknown *))v2->lpVtbl->Release)(v2);
            if ( v29 )
              ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
            _bstr_t::_Free((_bstr_t *)&v40);
            if ( v38 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            if ( v17 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
            if ( v3 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
            return 2147549183LL;
          }
          v32 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v43);
          v33 = *(struct IUnknown **)MSXML2::IXMLDOMNodeList::nextNode(v32);
          v39 = v41;
          if ( v41 != v33 )
          {
            v41 = v33;
            _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v41);
            if ( v39 )
              ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->Release)(v39);
          }
          if ( v60 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          while ( v41 )
          {
            LODWORD(v39) = CIASMigrationHelper::FindOnePropertyInXML(
                             a1,
                             v64,
                             (unsigned int)&v38,
                             (unsigned int)&v41,
                             v66,
                             v65);
            if ( (int)v39 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                WppDbgPrint("FindOnePropertyInXML() failed: %!hresult!");
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  16,
                  (unsigned int)WPP_35f0385197fd35cdb48f774109abba17_Traceguids,
                  (unsigned int)"NPSDS",
                  (char)v39);
              }
              if ( v41 )
                ((void (__fastcall *)(struct IUnknown *))v41->lpVtbl->Release)(v41);
              if ( v2 )
                ((void (__fastcall *)(struct IUnknown *))v2->lpVtbl->Release)(v2);
              if ( v29 )
                ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
              _bstr_t::_Free((_bstr_t *)&v40);
              if ( v38 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
              if ( v17 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
              if ( v3 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
              return 2147549183LL;
            }
            v34 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v43);
            v35 = *(struct IUnknown **)MSXML2::IXMLDOMNodeList::nextNode(v34);
            v39 = v41;
            if ( v41 != v35 )
            {
              v41 = v35;
              _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v41);
              if ( v39 )
                ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->Release)(v39);
            }
            if ( v61 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
          }
          v36 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v44);
          v37 = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v36);
          if ( v5 != *v37 )
          {
            v65 = v5;
            v5 = *v37;
            v42 = *v37;
            _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v42);
            if ( v65 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
          }
          if ( v50 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
          if ( v41 )
            ((void (__fastcall *)(struct IUnknown *))v41->lpVtbl->Release)(v41);
          if ( v2 )
            ((void (__fastcall *)(struct IUnknown *))v2->lpVtbl->Release)(v2);
          v2 = 0;
          if ( v29 )
            ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
          _bstr_t::_Free((_bstr_t *)&v40);
          if ( v38 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
        while ( v5 );
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        return 0;
      }
      else
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        return 2147549183LL;
      }
    }
    else
    {
      if ( v3 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      return 2147549183LL;
    }
  }
  else
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18004f2cc  mov     [rsp+arg_8], rdx
0x18004f2d1  mov     [rsp+arg_0], rcx
0x18004f2d6  push    rbx
0x18004f2d7  push    rsi
0x18004f2d8  push    rdi
0x18004f2d9  push    r12
0x18004f2db  push    r13
0x18004f2dd  push    r14
0x18004f2df  push    r15
0x18004f2e1  sub     rsp, 120h
0x18004f2e8  xor     r12d, r12d
0x18004f2eb  mov     ebx, r12d
0x18004f2ee  mov     [rsp+158h+var_F0], rbx
0x18004f2f3  mov     edi, r12d
0x18004f2f6  mov     [rsp+158h+var_F8], r12
0x18004f2fb  mov     r14d, r12d
0x18004f2fe  mov     [rsp+158h+var_108], r12
0x18004f303  mov     rcx, rdx
0x18004f306  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004f30b  lea     rdx, [rsp+158h+var_E8]
0x18004f310  mov     rcx, rax; struct IUnknown *
0x18004f313  call    ?GetdocumentElement@IXMLDOMDocument@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMDocument::GetdocumentElement(void)
0x18004f318  nop
0x18004f319  mov     rcx, rax
0x18004f31c  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004f321  mov     rsi, rax
0x18004f324  lea     rdx, ?m_identifiersQuery@CIASMigrationHelper@@1QBGB; "/Root/SDO_NAP_Schema_Identifiers"
0x18004f32b  lea     rcx, [rsp+158h+arg_10]; this
0x18004f333  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004f338  mov     r8, rax
0x18004f33b  lea     rdx, [rsp+158h+arg_18]
0x18004f343  mov     rcx, rsi; struct IUnknown *
0x18004f346  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004f34b  mov     rsi, [rax]
0x18004f34e  mov     r15d, r12d
0x18004f351  test    rsi, rsi
0x18004f354  jz      short loc_18004F36B
0x18004f356  mov     rbx, rsi
0x18004f359  mov     [rsp+158h+var_F0], rbx
0x18004f35e  lea     rcx, [rsp+158h+var_F0]
0x18004f363  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004f368  mov     r15, rsi
0x18004f36b  mov     rcx, [rsp+158h+arg_18]
0x18004f373  test    rcx, rcx
0x18004f376  jz      short loc_18004F385
0x18004f378  mov     rax, [rcx]
0x18004f37b  mov     rax, [rax+10h]
0x18004f37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f384  nop
0x18004f385  lea     rcx, [rsp+158h+var_E8]
0x18004f38a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004f38f  test    r15, r15
0x18004f392  jnz     short loc_18004F3B3
0x18004f394  test    rbx, rbx
0x18004f397  jz      short loc_18004F3A9
0x18004f399  mov     rax, [rbx]
0x18004f39c  mov     rcx, rbx
0x18004f39f  mov     rax, [rax+10h]
0x18004f3a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f3a8  nop
0x18004f3a9  mov     eax, 8000FFFFh
0x18004f3ae  jmp     loc_180050028
0x18004f3b3  lea     rcx, [rsp+158h+var_F0]
0x18004f3b8  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004f3bd  lea     rdx, [rsp+158h+arg_10]
0x18004f3c5  mov     rcx, rax; struct IUnknown *
0x18004f3c8  call    ?GetchildNodes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNode::GetchildNodes(void)
0x18004f3cd  nop
0x18004f3ce  cmp     [rax], r12
0x18004f3d1  jz      short loc_18004F3E6
0x18004f3d3  mov     rdi, [rax]
0x18004f3d6  mov     [rsp+158h+var_F8], rdi
0x18004f3db  lea     rcx, [rsp+158h+var_F8]
0x18004f3e0  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004f3e5  nop
0x18004f3e6  mov     rcx, [rsp+158h+arg_10]
0x18004f3ee  test    rcx, rcx
0x18004f3f1  jz      short loc_18004F400
0x18004f3f3  mov     rax, [rcx]
0x18004f3f6  mov     rax, [rax+10h]
0x18004f3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f3ff  nop
0x18004f400  test    rdi, rdi
0x18004f403  jnz     short loc_18004F424
0x18004f405  test    rbx, rbx
0x18004f408  jz      short loc_18004F41A
0x18004f40a  mov     rax, [rbx]
0x18004f40d  mov     rcx, rbx
0x18004f410  mov     rax, [rax+10h]
0x18004f414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f419  nop
0x18004f41a  mov     eax, 8000FFFFh
0x18004f41f  jmp     loc_180050028
0x18004f424  lea     rcx, [rsp+158h+var_F8]
0x18004f429  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004f42e  lea     rdx, [rsp+158h+arg_10]
0x18004f436  mov     rcx, rax; struct IUnknown *
0x18004f439  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x18004f43e  nop
0x18004f43f  cmp     [rax], r12
0x18004f442  jz      short loc_18004F457
0x18004f444  mov     r14, [rax]
0x18004f447  mov     [rsp+158h+var_108], r14
0x18004f44c  lea     rcx, [rsp+158h+var_108]
0x18004f451  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004f456  nop
0x18004f457  mov     rcx, [rsp+158h+arg_10]
0x18004f45f  test    rcx, rcx
0x18004f462  jz      short loc_18004F471
0x18004f464  mov     rax, [rcx]
0x18004f467  mov     rax, [rax+10h]
0x18004f46b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f470  nop
0x18004f471  test    r14, r14
0x18004f474  jnz     short loc_18004F4AE
0x18004f476  mov     rax, [rdi]
0x18004f479  mov     rcx, rdi
0x18004f47c  mov     rax, [rax+10h]
0x18004f480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f485  nop
0x18004f486  test    rbx, rbx
0x18004f489  jz      short loc_18004F49B
0x18004f48b  mov     rax, [rbx]
0x18004f48e  mov     rcx, rbx
0x18004f491  mov     rax, [rax+10h]
0x18004f495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f49a  nop
0x18004f49b  mov     eax, 8000FFFFh
0x18004f4a0  jmp     loc_180050028
0x18004f4a5  test    r14, r14
0x18004f4a8  jz      loc_18004FFAE
0x18004f4ae  mov     rsi, r12
0x18004f4b1  mov     [rsp+158h+var_E0], r12
0x18004f4b6  mov     r13, r12
0x18004f4b9  mov     [rsp+158h+var_D8], r12
0x18004f4c1  mov     [rsp+158h+var_128], r12
0x18004f4c6  mov     [rsp+158h+var_118], r12
0x18004f4cb  lea     rcx, [rsp+158h+var_108]
0x18004f4d0  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004f4d5  mov     r15, rax
0x18004f4d8  lea     rdx, ?m_migPathQuery@CIASMigrationHelper@@1QBGB; "./Path"
0x18004f4df  lea     rcx, [rsp+158h+var_B8]; this
0x18004f4e7  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004f4ec  mov     r8, rax
0x18004f4ef  lea     rdx, [rsp+158h+var_B0]
0x18004f4f7  mov     rcx, r15; struct IUnknown *
0x18004f4fa  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004f4ff  mov     r15, [rax]
0x18004f502  test    r15, r15
0x18004f505  jz      short loc_18004F51B
0x18004f507  mov     rsi, r15
0x18004f50a  mov     [rsp+158h+var_E0], r15
0x18004f50f  lea     rcx, [rsp+158h+var_E0]
0x18004f514  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004f519  jmp     short loc_18004F51E
0x18004f51b  mov     r15, r12
0x18004f51e  mov     rcx, [rsp+158h+var_B0]
0x18004f526  test    rcx, rcx
0x18004f529  jz      short loc_18004F538
0x18004f52b  mov     rax, [rcx]
0x18004f52e  mov     rax, [rax+10h]
0x18004f532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f537  nop
0x18004f538  test    r15, r15
0x18004f53b  jnz     short loc_18004F5B8
0x18004f53d  lea     rcx, [rsp+158h+var_118]; this
0x18004f542  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004f547  nop
0x18004f548  mov     rcx, [rsp+158h+var_128]
0x18004f54d  test    rcx, rcx
0x18004f550  jz      short loc_18004F55F
0x18004f552  mov     rax, [rcx]
0x18004f555  mov     rax, [rax+10h]
0x18004f559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f55e  nop
0x18004f55f  test    rsi, rsi
0x18004f562  jz      short loc_18004F574
0x18004f564  mov     rax, [rsi]
0x18004f567  mov     rcx, rsi
0x18004f56a  mov     rax, [rax+10h]
0x18004f56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f573  nop
0x18004f574  mov     rax, [r14]
0x18004f577  mov     rcx, r14
0x18004f57a  mov     rax, [rax+10h]
0x18004f57e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f583  nop
0x18004f584  test    rdi, rdi
0x18004f587  jz      short loc_18004F599
0x18004f589  mov     rax, [rdi]
0x18004f58c  mov     rcx, rdi
0x18004f58f  mov     rax, [rax+10h]
0x18004f593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f598  nop
0x18004f599  test    rbx, rbx
0x18004f59c  jz      short loc_18004F5AE
0x18004f59e  mov     rax, [rbx]
0x18004f5a1  mov     rcx, rbx
0x18004f5a4  mov     rax, [rax+10h]
0x18004f5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5ad  nop
0x18004f5ae  mov     eax, 8000FFFFh
0x18004f5b3  jmp     loc_180050028
0x18004f5b8  lea     rdx, [rsp+158h+var_118]
0x18004f5bd  lea     rcx, [rsp+158h+var_E0]
0x18004f5c2  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004f5c7  mov     r15d, eax
0x18004f5ca  test    eax, eax
0x18004f5cc  jns     short loc_18004F647
0x18004f5ce  lea     rcx, [rsp+158h+var_118]; this
0x18004f5d3  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004f5d8  nop
0x18004f5d9  mov     rcx, [rsp+158h+var_128]
0x18004f5de  test    rcx, rcx
0x18004f5e1  jz      short loc_18004F5F0
0x18004f5e3  mov     rax, [rcx]
0x18004f5e6  mov     rax, [rax+10h]
0x18004f5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5ef  nop
0x18004f5f0  test    rsi, rsi
0x18004f5f3  jz      short loc_18004F605
0x18004f5f5  mov     rax, [rsi]
0x18004f5f8  mov     rcx, rsi
0x18004f5fb  mov     rax, [rax+10h]
0x18004f5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f604  nop
0x18004f605  mov     rax, [r14]
0x18004f608  mov     rcx, r14
0x18004f60b  mov     rax, [rax+10h]
0x18004f60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f614  nop
0x18004f615  test    rdi, rdi
0x18004f618  jz      short loc_18004F62A
0x18004f61a  mov     rax, [rdi]
0x18004f61d  mov     rcx, rdi
0x18004f620  mov     rax, [rax+10h]
0x18004f624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f629  nop
0x18004f62a  test    rbx, rbx
0x18004f62d  jz      short loc_18004F63F
0x18004f62f  mov     rax, [rbx]
0x18004f632  mov     rcx, rbx
0x18004f635  mov     rax, [rax+10h]
0x18004f639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f63e  nop
0x18004f63f  mov     eax, r15d
0x18004f642  jmp     loc_180050028
0x18004f647  mov     rcx, [rsp+158h+arg_0]
0x18004f64f  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004f654  mov     rcx, [rsp+158h+var_118]
0x18004f659  mov     [rsp+158h+var_E8], rcx
0x18004f65e  test    rcx, rcx
0x18004f661  jz      short loc_18004F667
0x18004f663  lock inc dword ptr [rcx+10h]
0x18004f667  lea     r8, [rsp+158h+var_E8]
0x18004f66c  lea     rdx, [rsp+158h+var_A8]
0x18004f674  mov     rcx, rax; struct IUnknown *
0x18004f677  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004f67c  mov     rax, [rax]
0x18004f67f  mov     r15, [rsp+158h+var_128]
0x18004f684  cmp     r15, rax
0x18004f687  jz      short loc_18004F6AD
0x18004f689  mov     [rsp+158h+var_128], rax
0x18004f68e  lea     rcx, [rsp+158h+var_128]
0x18004f693  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004f698  test    r15, r15
0x18004f69b  jz      short loc_18004F6AD
0x18004f69d  mov     rax, [r15]
0x18004f6a0  mov     rcx, r15
0x18004f6a3  mov     rax, [rax+10h]
0x18004f6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6ac  nop
0x18004f6ad  mov     rcx, [rsp+158h+var_A8]
0x18004f6b5  test    rcx, rcx
0x18004f6b8  jz      short loc_18004F6C7
0x18004f6ba  mov     rax, [rcx]
0x18004f6bd  mov     rax, [rax+10h]
0x18004f6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6c6  nop
0x18004f6c7  cmp     [rsp+158h+var_128], r12
0x18004f6cc  jnz     short loc_18004F749
0x18004f6ce  lea     rcx, [rsp+158h+var_118]; this
0x18004f6d3  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004f6d8  nop
0x18004f6d9  mov     rcx, [rsp+158h+var_128]
0x18004f6de  test    rcx, rcx
0x18004f6e1  jz      short loc_18004F6F0
0x18004f6e3  mov     rax, [rcx]
0x18004f6e6  mov     rax, [rax+10h]
0x18004f6ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6ef  nop
0x18004f6f0  test    rsi, rsi
0x18004f6f3  jz      short loc_18004F705
0x18004f6f5  mov     rax, [rsi]
0x18004f6f8  mov     rcx, rsi
0x18004f6fb  mov     rax, [rax+10h]
0x18004f6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f704  nop
0x18004f705  mov     rax, [r14]
0x18004f708  mov     rcx, r14
  ... truncated ...
```
