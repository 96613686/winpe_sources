# CIASMigrationHelper::AddRequiredProperties(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)

- ea: `0x18004a3b0`
- end: `0x18004b255`
- name: `?AddRequiredProperties@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `3749`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180024cac`
- `0x18002d08c`
- `0x18002efa0`
- `0x180047604`
- `0x18004a0c8`
- `0x18004a3b0`
- `0x18004cef4`
- `0x18004d11c`
- `0x18004d190`
- `0x18004d1ec`
- `0x180050044`
- `0x180051e7c`
- `0x1800524fc`
- `0x180052588`
- `0x180058010`

## string_xrefs

- `0x18004a884`: `./ReplaceChildrenNode`
- `0x18004a426`: `./Path`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall CIASMigrationHelper::AddRequiredProperties(__int64 a1, __int64 a2, __int64 a3)
{
  struct IUnknown *v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // r15
  __int64 v6; // r13
  __int64 v7; // r14
  __int64 v8; // r12
  __int64 v9; // rdi
  struct IUnknown *v10; // rax
  __int64 *v12; // rax
  __int64 *v13; // rax
  __int64 *v14; // rax
  __int64 *v15; // rax
  struct IUnknown *v16; // rax
  __int64 v17; // rax
  struct IUnknown *v18; // rax
  __int64 *v19; // rax
  struct IUnknown *v20; // rax
  __int64 *Node; // rax
  struct IUnknown *v22; // rdi
  __int64 v23; // r12
  struct IUnknown *v24; // r14
  struct IUnknown *v25; // rax
  struct IUnknown *v26; // rax
  __int64 *v27; // rax
  struct IUnknown *v28; // rax
  struct IUnknown **v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r9
  __int64 v32; // r8
  struct IUnknown *v33; // rax
  struct IUnknown **v34; // rax
  __int64 v35; // rcx
  __int64 v36; // r9
  __int64 v37; // r8
  int v38; // r14d
  struct IUnknown *v39; // rax
  __int64 *v40; // rax
  __int64 v41; // r14
  struct IUnknown *v42; // [rsp+38h] [rbp-89h] BYREF
  __int64 *v43; // [rsp+40h] [rbp-81h] BYREF
  __int64 *v44; // [rsp+48h] [rbp-79h] BYREF
  __int64 *v45; // [rsp+50h] [rbp-71h] BYREF
  __int64 v46; // [rsp+58h] [rbp-69h] BYREF
  struct IUnknown *v47; // [rsp+60h] [rbp-61h] BYREF
  struct IUnknown *v48; // [rsp+68h] [rbp-59h]
  __int64 v49; // [rsp+70h] [rbp-51h] BYREF
  __int64 v50; // [rsp+78h] [rbp-49h] BYREF
  __int64 v51; // [rsp+80h] [rbp-41h] BYREF
  __int64 v52; // [rsp+88h] [rbp-39h] BYREF
  struct IUnknown *v53; // [rsp+90h] [rbp-31h] BYREF
  __int64 v54; // [rsp+98h] [rbp-29h]
  struct IUnknown *v55; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v56; // [rsp+A8h] [rbp-19h] BYREF
  __int64 v57; // [rsp+B0h] [rbp-11h] BYREF
  __int64 v58; // [rsp+B8h] [rbp-9h] BYREF
  char v59[8]; // [rsp+C0h] [rbp-1h] BYREF
  __int64 v60; // [rsp+C8h] [rbp+7h]
  __int64 v61; // [rsp+D0h] [rbp+Fh]
  __int64 v62; // [rsp+D8h] [rbp+17h]
  __int64 v63; // [rsp+E0h] [rbp+1Fh]
  int v66; // [rsp+140h] [rbp+7Fh] BYREF

  v3 = 0;
  v55 = 0;
  v46 = 0;
  v4 = 0;
  v56 = 0;
  v45 = 0;
  v5 = 0;
  v57 = 0;
  v44 = 0;
  v6 = 0;
  v58 = 0;
  v43 = 0;
  v7 = 0;
  v52 = 0;
  v66 = 0;
  v8 = 0;
  v51 = 0;
  v9 = 0;
  v50 = 0;
  v42 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&v47, L"./Path");
  v10 = *(struct IUnknown **)MSXML2::IXMLDOMNode::selectSingleNode(v42);
  v42 = 0;
  if ( v10 )
  {
    v3 = v10;
    v55 = v10;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v55);
    v42 = v3;
  }
  if ( v53 )
    ((void (__fastcall *)(struct IUnknown *))v53->lpVtbl->Release)(v53);
  if ( !v42 )
  {
    _bstr_t::_Free((_bstr_t *)&v43);
    _bstr_t::_Free((_bstr_t *)&v44);
    _bstr_t::_Free((_bstr_t *)&v45);
    _bstr_t::_Free((_bstr_t *)&v46);
    return 2147549183LL;
  }
  LODWORD(v48) = CIASMigrationHelper::GetStringValueFromNode(&v55, &v46);
  if ( (int)v48 < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v43);
    _bstr_t::_Free((_bstr_t *)&v44);
    _bstr_t::_Free((_bstr_t *)&v45);
    _bstr_t::_Free((_bstr_t *)&v46);
    ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
    return (unsigned int)v48;
  }
  v47 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&v42, L"./Name");
  v12 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v47);
  if ( *v12 )
  {
    v4 = *v12;
    v56 = *v12;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v56);
  }
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  if ( !v4 )
  {
    _bstr_t::_Free((_bstr_t *)&v43);
    _bstr_t::_Free((_bstr_t *)&v44);
    _bstr_t::_Free((_bstr_t *)&v45);
    _bstr_t::_Free((_bstr_t *)&v46);
    ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
    return 2147549183LL;
  }
  LODWORD(v48) = CIASMigrationHelper::GetStringValueFromNode(&v56, &v45);
  if ( (int)v48 < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v43);
    _bstr_t::_Free((_bstr_t *)&v44);
    _bstr_t::_Free((_bstr_t *)&v45);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    _bstr_t::_Free((_bstr_t *)&v46);
    ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
    return (unsigned int)v48;
  }
  v47 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&v42, L"./Type");
  v13 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v47);
  if ( *v13 )
  {
    v5 = *v13;
    v57 = *v13;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v57);
  }
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  if ( !v5 )
  {
    _bstr_t::_Free((_bstr_t *)&v43);
    _bstr_t::_Free((_bstr_t *)&v44);
    _bstr_t::_Free((_bstr_t *)&v45);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    _bstr_t::_Free((_bstr_t *)&v46);
    ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
    return 2147549183LL;
  }
  LODWORD(v48) = CIASMigrationHelper::GetStringValueFromNode(&v57, &v44);
  if ( (int)v48 < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v43);
    _bstr_t::_Free((_bstr_t *)&v44);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v45);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    _bstr_t::_Free((_bstr_t *)&v46);
    ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
    return (unsigned int)v48;
  }
  v47 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&v42, L"./Value");
  v14 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v47);
  if ( *v14 )
  {
    v6 = *v14;
    v58 = *v14;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v58);
  }
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  if ( !v6 )
  {
    _bstr_t::_Free((_bstr_t *)&v43);
    _bstr_t::_Free((_bstr_t *)&v44);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v45);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    _bstr_t::_Free((_bstr_t *)&v46);
    ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
    return 2147549183LL;
  }
  LODWORD(v48) = CIASMigrationHelper::GetStringValueFromNode(&v58, &v43);
  if ( (int)v48 < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v43);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    _bstr_t::_Free((_bstr_t *)&v44);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v45);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    _bstr_t::_Free((_bstr_t *)&v46);
    ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
    return (unsigned int)v48;
  }
  v47 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&v42, L"./ReplaceChildrenNode");
  v15 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v47);
  if ( *v15 )
  {
    v7 = *v15;
    v52 = *v15;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v52);
  }
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  if ( !v7 )
  {
    _bstr_t::_Free((_bstr_t *)&v43);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    _bstr_t::_Free((_bstr_t *)&v44);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v45);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    _bstr_t::_Free((_bstr_t *)&v46);
    ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
    return 2147549183LL;
  }
  LODWORD(v48) = CIASMigrationHelper::GetBOOLValueFromNode(&v52, &v66);
  if ( (int)v48 < 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    _bstr_t::_Free((_bstr_t *)&v43);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    _bstr_t::_Free((_bstr_t *)&v44);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v45);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    _bstr_t::_Free((_bstr_t *)&v46);
    ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
    return (unsigned int)v48;
  }
  v16 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
  v17 = MSXML2::IXMLDOMDocument::GetdocumentElement(v16);
  v18 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(v17);
  v42 = (struct IUnknown *)v46;
  if ( v46 )
    _InterlockedIncrement((volatile signed __int32 *)(v46 + 16));
  v19 = (__int64 *)MSXML2::IXMLDOMNode::selectNodes(v18);
  if ( *v19 )
  {
    v8 = *v19;
    v51 = *v19;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v51);
  }
  if ( v47 )
    ((void (__fastcall *)(struct IUnknown *))v47->lpVtbl->Release)(v47);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
  if ( !v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    _bstr_t::_Free((_bstr_t *)&v43);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    _bstr_t::_Free((_bstr_t *)&v44);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v45);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    _bstr_t::_Free((_bstr_t *)&v46);
    ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
    return 2147549183LL;
  }
  v20 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v51);
  Node = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v20);
  if ( *Node )
  {
    v9 = *Node;
    v50 = *Node;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v50);
  }
  if ( v42 )
    ((void (__fastcall *)(struct IUnknown *))v42->lpVtbl->Release)(v42);
  while ( v9 )
  {
    if ( v66 )
    {
      v22 = 0;
      v42 = 0;
      v23 = 0;
      v49 = 0;
      v24 = 0;
      v53 = 0;
      v47 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v50);
      _bstr_t::_bstr_t((_bstr_t *)v59, L"./Children");
      v25 = *(struct IUnknown **)MSXML2::IXMLDOMNode::selectSingleNode(v47);
      v47 = v25;
      if ( v25 )
      {
        v22 = v25;
        v42 = v25;
        _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v42);
        v48 = v22;
      }
      else
      {
        v47 = 0;
        v48 = 0;
      }
      if ( v60 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      if ( !v47 )
      {
        if ( v48 )
          ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
        goto LABEL_120;
      }
      v26 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v42);
      v27 = (__int64 *)MSXML2::IXMLDOMNode::GetchildNodes(v26);
      if ( *v27 )
      {
        v23 = *v27;
        v49 = *v27;
        _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v49);
      }
      if ( v61 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      if ( !v23 )
      {
        if ( v48 )
          ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
        goto LABEL_120;
      }
      v28 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v49);
      v29 = (struct IUnknown **)MSXML2::IXMLDOMNodeList::nextNode(v28);
      if ( *v29 )
      {
        v24 = *v29;
        v53 = *v29;
        _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v53);
      }
      if ( v62 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      if ( !v24 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        if ( v48 )
          ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
LABEL_120:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
        _bstr_t::_Free((_bstr_t *)&v43);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        _bstr_t::_Free((_bstr_t *)&v44);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        _bstr_t::_Free((_bstr_t *)&v45);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        _bstr_t::_Free((_bstr_t *)&v46);
        ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
        return 2147549183LL;
      }
      while ( v24 )
      {
        if ( v43 )
          v30 = *v43;
        else
          v30 = 0;
        if ( v44 )
          v31 = *v44;
        else
          v31 = 0;
        if ( v45 )
          v32 = *v45;
        else
          v32 = 0;
        LODWORD(v48) = CIASMigrationHelper::AddPropertiesToANode(a1, &v53, v32, v31, v30);
        if ( (int)v48 < 0 )
        {
          ((void (__fastcall *)(struct IUnknown *))v24->lpVtbl->Release)(v24);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          if ( v22 )
            ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
          _bstr_t::_Free((_bstr_t *)&v43);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          _bstr_t::_Free((_bstr_t *)&v44);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          _bstr_t::_Free((_bstr_t *)&v45);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
          _bstr_t::_Free((_bstr_t *)&v46);
          ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
          return (unsigned int)v48;
        }
        v33 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v49);
        v34 = (struct IUnknown **)MSXML2::IXMLDOMNodeList::nextNode(v33);
        if ( v24 != *v34 )
        {
          v47 = v24;
          v24 = *v34;
          v53 = *v34;
          _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v53);
          if ( v47 )
            ((void (__fastcall *)(struct IUnknown *))v47->lpVtbl->Release)(v47);
        }
        if ( v63 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      if ( v22 )
        ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
      v9 = v50;
    }
    else
    {
      if ( v43 )
        v35 = *v43;
      else
        v35 = 0;
      if ( v44 )
        v36 = *v44;
      else
        v36 = 0;
      if ( v45 )
        v37 = *v45;
      else
        v37 = 0;
      v38 = CIASMigrationHelper::AddPropertiesToANode(a1, &v50, v37, v36, v35);
      if ( v38 < 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
        _bstr_t::_Free((_bstr_t *)&v43);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        _bstr_t::_Free((_bstr_t *)&v44);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        _bstr_t::_Free((_bstr_t *)&v45);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        _bstr_t::_Free((_bstr_t *)&v46);
        ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
        return (unsigned int)v38;
      }
    }
    v39 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v51);
    v40 = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v39);
    if ( v9 != *v40 )
    {
      v41 = v9;
      v9 = *v40;
      v50 = *v40;
      _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v50);
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    if ( v54 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  _bstr_t::_Free((_bstr_t *)&v43);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  _bstr_t::_Free((_bstr_t *)&v44);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  _bstr_t::_Free((_bstr_t *)&v45);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  _bstr_t::_Free((_bstr_t *)&v46);
  ((void (__fastcall *)(struct IUnknown *))v3->lpVtbl->Release)(v3);
  return 0;
}

```

## disassembly

```asm
0x18004a3b0  mov     rax, rsp
0x18004a3b3  mov     [rax+10h], rbx
0x18004a3b7  mov     [rax+18h], r8
0x18004a3bb  mov     [rax+8], rcx
0x18004a3bf  push    rbp
0x18004a3c0  push    rsi
0x18004a3c1  push    rdi
0x18004a3c2  push    r12
0x18004a3c4  push    r13
0x18004a3c6  push    r14
0x18004a3c8  push    r15
0x18004a3ca  lea     rbp, [rax-5Fh]
0x18004a3ce  sub     rsp, 0E0h
0x18004a3d5  xor     ecx, ecx
0x18004a3d7  mov     ebx, ecx
0x18004a3d9  mov     [rbp+57h+var_78], rcx
0x18004a3dd  mov     [rbp+57h+var_C0], rcx
0x18004a3e1  mov     esi, ecx
0x18004a3e3  mov     [rbp+57h+var_70], rcx
0x18004a3e7  mov     [rbp+57h+var_C8], rcx
0x18004a3eb  mov     r15d, ecx
0x18004a3ee  mov     [rbp+57h+var_68], rcx
0x18004a3f2  mov     [rbp+57h+var_D0], rcx
0x18004a3f6  mov     r13d, ecx
0x18004a3f9  mov     [rbp+57h+var_60], rcx
0x18004a3fd  mov     [rsp+110h+var_D8], rcx
0x18004a402  mov     r14d, ecx
0x18004a405  mov     [rbp+57h+var_90], rcx
0x18004a409  mov     [rbp+57h+arg_18], ecx
0x18004a40c  mov     r12d, ecx
0x18004a40f  mov     [rbp+57h+var_98], rcx
0x18004a413  mov     edi, ecx
0x18004a415  mov     [rbp+57h+var_A0], rcx
0x18004a419  mov     rcx, r8
0x18004a41c  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004a421  mov     [rsp+110h+var_E0], rax
0x18004a426  lea     rdx, ?m_migPathQuery@CIASMigrationHelper@@1QBGB; "./Path"
0x18004a42d  lea     rcx, [rbp+57h+var_B8]; this
0x18004a431  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004a436  mov     r8, rax
0x18004a439  lea     rdx, [rbp+57h+var_88]
0x18004a43d  mov     rcx, [rsp+110h+var_E0]; struct IUnknown *
0x18004a442  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004a447  mov     rax, [rax]
0x18004a44a  mov     [rsp+110h+var_E0], rdi
0x18004a44f  test    rax, rax
0x18004a452  jz      short loc_18004A46C
0x18004a454  mov     rbx, rax
0x18004a457  mov     [rbp+57h+var_78], rax
0x18004a45b  lea     rcx, [rbp+57h+var_78]
0x18004a45f  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004a464  mov     rax, rbx
0x18004a467  mov     [rsp+110h+var_E0], rbx
0x18004a46c  mov     rcx, [rbp+57h+var_88]
0x18004a470  test    rcx, rcx
0x18004a473  jz      short loc_18004A482
0x18004a475  mov     rax, [rcx]
0x18004a478  mov     rax, [rax+10h]
0x18004a47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a481  nop
0x18004a482  cmp     [rsp+110h+var_E0], 0
0x18004a488  jnz     short loc_18004A4BD
0x18004a48a  lea     rcx, [rsp+110h+var_D8]; this
0x18004a48f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a494  nop
0x18004a495  lea     rcx, [rbp+57h+var_D0]; this
0x18004a499  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a49e  nop
0x18004a49f  lea     rcx, [rbp+57h+var_C8]; this
0x18004a4a3  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a4a8  nop
0x18004a4a9  lea     rcx, [rbp+57h+var_C0]; this
0x18004a4ad  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a4b2  nop
0x18004a4b3  mov     eax, 8000FFFFh
0x18004a4b8  jmp     loc_18004B23A
0x18004a4bd  lea     rdx, [rbp+57h+var_C0]
0x18004a4c1  lea     rcx, [rbp+57h+var_78]
0x18004a4c5  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004a4ca  mov     dword ptr [rbp+57h+var_B0], eax
0x18004a4cd  test    eax, eax
0x18004a4cf  jns     short loc_18004A512
0x18004a4d1  lea     rcx, [rsp+110h+var_D8]; this
0x18004a4d6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a4db  nop
0x18004a4dc  lea     rcx, [rbp+57h+var_D0]; this
0x18004a4e0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a4e5  nop
0x18004a4e6  lea     rcx, [rbp+57h+var_C8]; this
0x18004a4ea  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a4ef  nop
0x18004a4f0  lea     rcx, [rbp+57h+var_C0]; this
0x18004a4f4  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a4f9  nop
0x18004a4fa  mov     rax, [rbx]
0x18004a4fd  mov     rcx, rbx
0x18004a500  mov     rax, [rax+10h]
0x18004a504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a509  nop
0x18004a50a  mov     eax, dword ptr [rbp+57h+var_B0]
0x18004a50d  jmp     loc_18004B23A
0x18004a512  mov     rcx, [rbp+57h+arg_10]
0x18004a516  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004a51b  mov     [rbp+57h+var_B8], rax
0x18004a51f  lea     rdx, ?m_migNameQuery@CIASMigrationHelper@@1QBGB; "./Name"
0x18004a526  lea     rcx, [rsp+110h+var_E0]; this
0x18004a52b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004a530  mov     r8, rax
0x18004a533  lea     rdx, [rbp+57h+var_A8]
0x18004a537  mov     rcx, [rbp+57h+var_B8]; struct IUnknown *
0x18004a53b  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004a540  nop
0x18004a541  cmp     qword ptr [rax], 0
0x18004a545  jz      short loc_18004A558
0x18004a547  mov     rsi, [rax]
0x18004a54a  mov     [rbp+57h+var_70], rsi
0x18004a54e  lea     rcx, [rbp+57h+var_70]
0x18004a552  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004a557  nop
0x18004a558  mov     rcx, [rbp+57h+var_A8]
0x18004a55c  test    rcx, rcx
0x18004a55f  jz      short loc_18004A56E
0x18004a561  mov     rax, [rcx]
0x18004a564  mov     rax, [rax+10h]
0x18004a568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a56d  nop
0x18004a56e  test    rsi, rsi
0x18004a571  jnz     short loc_18004A5B1
0x18004a573  lea     rcx, [rsp+110h+var_D8]; this
0x18004a578  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a57d  nop
0x18004a57e  lea     rcx, [rbp+57h+var_D0]; this
0x18004a582  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a587  nop
0x18004a588  lea     rcx, [rbp+57h+var_C8]; this
0x18004a58c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a591  nop
0x18004a592  lea     rcx, [rbp+57h+var_C0]; this
0x18004a596  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a59b  nop
0x18004a59c  mov     rax, [rbx]
0x18004a59f  mov     rcx, rbx
0x18004a5a2  mov     rax, [rax+10h]
0x18004a5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5ab  nop
0x18004a5ac  jmp     loc_18004A4B3
0x18004a5b1  lea     rdx, [rbp+57h+var_C8]
0x18004a5b5  lea     rcx, [rbp+57h+var_70]
0x18004a5b9  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004a5be  mov     dword ptr [rbp+57h+var_B0], eax
0x18004a5c1  test    eax, eax
0x18004a5c3  jns     short loc_18004A613
0x18004a5c5  lea     rcx, [rsp+110h+var_D8]; this
0x18004a5ca  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a5cf  nop
0x18004a5d0  lea     rcx, [rbp+57h+var_D0]; this
0x18004a5d4  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a5d9  nop
0x18004a5da  lea     rcx, [rbp+57h+var_C8]; this
0x18004a5de  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a5e3  nop
0x18004a5e4  mov     rax, [rsi]
0x18004a5e7  mov     rcx, rsi
0x18004a5ea  mov     rax, [rax+10h]
0x18004a5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5f3  nop
0x18004a5f4  lea     rcx, [rbp+57h+var_C0]; this
0x18004a5f8  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a5fd  nop
0x18004a5fe  mov     rax, [rbx]
0x18004a601  mov     rcx, rbx
0x18004a604  mov     rax, [rax+10h]
0x18004a608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a60d  nop
0x18004a60e  jmp     loc_18004A50A
0x18004a613  mov     rcx, [rbp+57h+arg_10]
0x18004a617  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004a61c  mov     [rbp+57h+var_B8], rax
0x18004a620  lea     rdx, ?m_migTypeQuery@CIASMigrationHelper@@1QBGB; "./Type"
0x18004a627  lea     rcx, [rsp+110h+var_E0]; this
0x18004a62c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004a631  mov     r8, rax
0x18004a634  lea     rdx, [rbp+57h+var_A8]
0x18004a638  mov     rcx, [rbp+57h+var_B8]; struct IUnknown *
0x18004a63c  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004a641  nop
0x18004a642  cmp     qword ptr [rax], 0
0x18004a646  jz      short loc_18004A659
0x18004a648  mov     r15, [rax]
0x18004a64b  mov     [rbp+57h+var_68], r15
0x18004a64f  lea     rcx, [rbp+57h+var_68]
0x18004a653  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004a658  nop
0x18004a659  mov     rcx, [rbp+57h+var_A8]
0x18004a65d  test    rcx, rcx
0x18004a660  jz      short loc_18004A66F
0x18004a662  mov     rax, [rcx]
0x18004a665  mov     rax, [rax+10h]
0x18004a669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a66e  nop
0x18004a66f  test    r15, r15
0x18004a672  jnz     short loc_18004A6C2
0x18004a674  lea     rcx, [rsp+110h+var_D8]; this
0x18004a679  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a67e  nop
0x18004a67f  lea     rcx, [rbp+57h+var_D0]; this
0x18004a683  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a688  nop
0x18004a689  lea     rcx, [rbp+57h+var_C8]; this
0x18004a68d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a692  nop
0x18004a693  mov     rax, [rsi]
0x18004a696  mov     rcx, rsi
0x18004a699  mov     rax, [rax+10h]
0x18004a69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6a2  nop
0x18004a6a3  lea     rcx, [rbp+57h+var_C0]; this
0x18004a6a7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a6ac  nop
0x18004a6ad  mov     rax, [rbx]
0x18004a6b0  mov     rcx, rbx
0x18004a6b3  mov     rax, [rax+10h]
0x18004a6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6bc  nop
0x18004a6bd  jmp     loc_18004A4B3
0x18004a6c2  lea     rdx, [rbp+57h+var_D0]
0x18004a6c6  lea     rcx, [rbp+57h+var_68]
0x18004a6ca  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004a6cf  mov     dword ptr [rbp+57h+var_B0], eax
0x18004a6d2  test    eax, eax
0x18004a6d4  jns     short loc_18004A734
0x18004a6d6  lea     rcx, [rsp+110h+var_D8]; this
0x18004a6db  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a6e0  nop
0x18004a6e1  lea     rcx, [rbp+57h+var_D0]; this
0x18004a6e5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a6ea  nop
0x18004a6eb  mov     rax, [r15]
0x18004a6ee  mov     rcx, r15
0x18004a6f1  mov     rax, [rax+10h]
0x18004a6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6fa  nop
0x18004a6fb  lea     rcx, [rbp+57h+var_C8]; this
0x18004a6ff  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a704  nop
0x18004a705  mov     rax, [rsi]
0x18004a708  mov     rcx, rsi
0x18004a70b  mov     rax, [rax+10h]
0x18004a70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a714  nop
0x18004a715  lea     rcx, [rbp+57h+var_C0]; this
0x18004a719  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a71e  nop
0x18004a71f  mov     rax, [rbx]
0x18004a722  mov     rcx, rbx
0x18004a725  mov     rax, [rax+10h]
0x18004a729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a72e  nop
0x18004a72f  jmp     loc_18004A50A
0x18004a734  mov     rcx, [rbp+57h+arg_10]
0x18004a738  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004a73d  mov     [rbp+57h+var_B8], rax
0x18004a741  lea     rdx, ?m_migValueQuery@CIASMigrationHelper@@1QBGB; "./Value"
0x18004a748  lea     rcx, [rsp+110h+var_E0]; this
0x18004a74d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004a752  mov     r8, rax
0x18004a755  lea     rdx, [rbp+57h+var_A8]
0x18004a759  mov     rcx, [rbp+57h+var_B8]; struct IUnknown *
0x18004a75d  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004a762  nop
0x18004a763  cmp     qword ptr [rax], 0
0x18004a767  jz      short loc_18004A77A
0x18004a769  mov     r13, [rax]
0x18004a76c  mov     [rbp+57h+var_60], r13
0x18004a770  lea     rcx, [rbp+57h+var_60]
0x18004a774  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004a779  nop
0x18004a77a  mov     rcx, [rbp+57h+var_A8]
0x18004a77e  test    rcx, rcx
0x18004a781  jz      short loc_18004A790
0x18004a783  mov     rax, [rcx]
0x18004a786  mov     rax, [rax+10h]
0x18004a78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a78f  nop
0x18004a790  test    r13, r13
0x18004a793  jnz     short loc_18004A7F3
0x18004a795  lea     rcx, [rsp+110h+var_D8]; this
0x18004a79a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a79f  nop
0x18004a7a0  lea     rcx, [rbp+57h+var_D0]; this
0x18004a7a4  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a7a9  nop
0x18004a7aa  mov     rax, [r15]
0x18004a7ad  mov     rcx, r15
0x18004a7b0  mov     rax, [rax+10h]
0x18004a7b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7b9  nop
0x18004a7ba  lea     rcx, [rbp+57h+var_C8]; this
0x18004a7be  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a7c3  nop
  ... truncated ...
```
