# CIASMigrationHelper::AddNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)

- ea: `0x180049500`
- end: `0x18004a0bf`
- name: `?AddNode@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `3007`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180024cac`
- `0x18002d08c`
- `0x18002efa0`
- `0x18002f240`
- `0x180041148`
- `0x180047604`
- `0x1800481d0`
- `0x180048b24`
- `0x180049500`
- `0x18004d11c`
- `0x180050044`
- `0x180050e80`
- `0x1800510f8`
- `0x180052588`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180049b78`
- `OLEAUT32!__imp_VariantInit` at `0x180049b78`
- `OLEAUT32!__imp_VariantClear` at `0x180049c4b`
- `OLEAUT32!__imp_VariantClear` at `0x180049d23`
- `OLEAUT32!__imp_VariantClear` at `0x180049e76`
- `OLEAUT32!__imp_VariantClear` at `0x180049f5a`
- `OLEAUT32!__imp_VariantClear` at `0x180049c4b`
- `OLEAUT32!__imp_VariantClear` at `0x180049d23`
- `OLEAUT32!__imp_VariantClear` at `0x180049e76`
- `OLEAUT32!__imp_VariantClear` at `0x180049f5a`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180049df7`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180049df7`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180049e03`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180049e03`

## string_xrefs

- `0x18004956d`: `./Path`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall CIASMigrationHelper::AddNode(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r13
  __int64 v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // r14
  __int64 v7; // r15
  __int64 v8; // r12
  struct IUnknown *v9; // rdi
  __int64 *v10; // rax
  __int64 v11; // rdi
  bool v12; // zf
  int StringValueFromNode; // edi
  struct IUnknown *v15; // rdi
  __int64 *v16; // rax
  struct IUnknown *v17; // rdi
  __int64 *v18; // rax
  struct IUnknown *v19; // rdi
  __int64 *v20; // rax
  struct IUnknown *v21; // rax
  __int64 *v22; // rax
  struct IUnknown *v23; // rdi
  struct IUnknown *v24; // rax
  __int64 v25; // r13
  struct IUnknown *v26; // rax
  __int64 Node; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  CHAR *v30; // rax
  UINT v31; // eax
  BSTR v32; // rax
  struct IUnknown *v33; // rax
  __int64 v34; // r13
  CHAR **v35; // [rsp+38h] [rbp-D0h] BYREF
  __int64 *v36; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+58h] [rbp-B0h] BYREF
  struct IUnknown *v40; // [rsp+60h] [rbp-A8h] BYREF
  __int64 *v41; // [rsp+68h] [rbp-A0h]
  __int64 v42; // [rsp+70h] [rbp-98h] BYREF
  __int64 v43; // [rsp+78h] [rbp-90h] BYREF
  __int64 v44; // [rsp+80h] [rbp-88h] BYREF
  __int64 v45; // [rsp+88h] [rbp-80h] BYREF
  __int64 v46; // [rsp+90h] [rbp-78h] BYREF
  __int64 v47; // [rsp+98h] [rbp-70h] BYREF
  struct IUnknown *v48; // [rsp+A0h] [rbp-68h] BYREF
  __int64 **v49; // [rsp+A8h] [rbp-60h]
  VARIANTARG pvarg; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-40h]
  __int128 v52; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v53; // [rsp+E0h] [rbp-28h]
  VARIANTARG pvargDest; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v55; // [rsp+108h] [rbp+0h] BYREF
  __int64 v56; // [rsp+118h] [rbp+10h]
  LPCSTR psz; // [rsp+180h] [rbp+78h] BYREF

  v3 = 0;
  v4 = 0;
  v43 = 0;
  v38 = 0;
  v5 = 0;
  v44 = 0;
  v37 = 0;
  v6 = 0;
  v45 = 0;
  v36 = 0;
  v7 = 0;
  v46 = 0;
  v35 = 0;
  v8 = 0;
  v42 = 0;
  v9 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&psz, L"./Path");
  v10 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v9);
  v11 = *v10;
  if ( *v10 )
  {
    v4 = *v10;
    v43 = *v10;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v43);
    v3 = v11;
  }
  else
  {
    v11 = 0;
  }
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( !v11 )
  {
    _bstr_t::_Free((_bstr_t *)&v35);
    _bstr_t::_Free((_bstr_t *)&v36);
    _bstr_t::_Free((_bstr_t *)&v37);
    _bstr_t::_Free((_bstr_t *)&v38);
    v12 = v3 == 0;
LABEL_93:
    if ( !v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return 2147549183LL;
  }
  StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v43, &v38);
  if ( StringValueFromNode < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v35);
    _bstr_t::_Free((_bstr_t *)&v36);
    _bstr_t::_Free((_bstr_t *)&v37);
    _bstr_t::_Free((_bstr_t *)&v38);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return (unsigned int)StringValueFromNode;
  }
  v15 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&psz, L"./Name");
  v16 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v15);
  if ( *v16 )
  {
    v5 = *v16;
    v44 = *v16;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v44);
  }
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( !v5 )
  {
    _bstr_t::_Free((_bstr_t *)&v35);
    _bstr_t::_Free((_bstr_t *)&v36);
    _bstr_t::_Free((_bstr_t *)&v37);
    _bstr_t::_Free((_bstr_t *)&v38);
LABEL_92:
    v12 = v4 == 0;
    goto LABEL_93;
  }
  StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v44, &v37);
  if ( StringValueFromNode < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v35);
    _bstr_t::_Free((_bstr_t *)&v36);
    _bstr_t::_Free((_bstr_t *)&v37);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v38);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return (unsigned int)StringValueFromNode;
  }
  v17 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&psz, L"./Type");
  v18 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v17);
  if ( *v18 )
  {
    v6 = *v18;
    v45 = *v18;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v45);
  }
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( !v6 )
  {
    _bstr_t::_Free((_bstr_t *)&v35);
    _bstr_t::_Free((_bstr_t *)&v36);
    _bstr_t::_Free((_bstr_t *)&v37);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v38);
    goto LABEL_92;
  }
  StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v45, &v36);
  if ( StringValueFromNode < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v35);
    _bstr_t::_Free((_bstr_t *)&v36);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    _bstr_t::_Free((_bstr_t *)&v37);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v38);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return (unsigned int)StringValueFromNode;
  }
  v19 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&psz, L"./Value");
  v20 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v19);
  if ( *v20 )
  {
    v7 = *v20;
    v46 = *v20;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v46);
  }
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( !v7 )
  {
    _bstr_t::_Free((_bstr_t *)&v35);
    _bstr_t::_Free((_bstr_t *)&v36);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    _bstr_t::_Free((_bstr_t *)&v37);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v38);
    goto LABEL_92;
  }
  StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v46, &v35);
  if ( StringValueFromNode < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v35);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    _bstr_t::_Free((_bstr_t *)&v36);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    _bstr_t::_Free((_bstr_t *)&v37);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v38);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return (unsigned int)StringValueFromNode;
  }
  v21 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
  psz = (LPCSTR)v38;
  if ( v38 )
    _InterlockedIncrement((volatile signed __int32 *)(v38 + 16));
  v22 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v21);
  if ( *v22 )
  {
    v8 = *v22;
    v42 = *v22;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v42);
  }
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( !v8 )
  {
    _bstr_t::_Free((_bstr_t *)&v35);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    _bstr_t::_Free((_bstr_t *)&v36);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    _bstr_t::_Free((_bstr_t *)&v37);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v38);
    goto LABEL_92;
  }
  v23 = 0;
  v48 = 0;
  v24 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v42);
  v25 = v37;
  psz = (LPCSTR)v37;
  if ( v37 )
    _InterlockedIncrement((volatile signed __int32 *)(v37 + 16));
  v26 = *(struct IUnknown **)MSXML2::IXMLDOMNode::selectSingleNode(v24);
  v40 = 0;
  if ( v26 )
  {
    v23 = v26;
    v48 = v26;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v48);
    v40 = v23;
  }
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  if ( !v40 )
  {
    VariantInit(&pvarg);
    pvarg.vt = 3;
    pvarg.lVal = 1;
    v40 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
    v41 = &v47;
    psz = (LPCSTR)_bstr_t::_bstr_t((_bstr_t *)&v47, &dword_180066E34);
    v49 = (__int64 **)&v39;
    v39 = v25;
    if ( v25 )
      _InterlockedIncrement((volatile signed __int32 *)(v25 + 16));
    _variant_t::_variant_t(&pvargDest, &pvarg);
    Node = MSXML2::IXMLDOMDocument::createNode(v40, (_bstr_t *)psz);
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>(
      &v40,
      Node);
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    _variant_t::~_variant_t((_variant_t *)&pvargDest);
    if ( !v40 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
      VariantClear(&pvarg);
      if ( v23 )
        ((void (__fastcall *)(struct IUnknown *))v23->lpVtbl->Release)(v23);
      goto LABEL_91;
    }
    v28 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v40);
    if ( v36 )
      v29 = *v36;
    else
      v29 = 0;
    LODWORD(psz) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 264LL))(v28, v29);
    if ( (int)psz >= 0 )
    {
      v49 = (__int64 **)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v40);
      v41 = *v49;
      if ( v35 )
        v30 = *v35;
      else
        v30 = 0;
      psz = v30;
      v31 = SysStringByteLen((BSTR)v30);
      v32 = SysAllocStringByteLen(psz, v31);
      if ( !v32 )
        _com_issue_error(-2147024882);
      LOWORD(v52) = 8;
      *((_QWORD *)&v52 + 1) = v32;
      v55 = v52;
      v56 = v53;
      LODWORD(psz) = ((__int64 (__fastcall *)(__int64 **, __int128 *))v41[31])(v49, &v55);
      _variant_t::~_variant_t((_variant_t *)&v52);
      if ( (int)psz >= 0 )
      {
        v33 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v42);
        v34 = *(_QWORD *)MSXML2::IXMLDOMNode::appendChild(v33);
        if ( psz )
          (*(void (__fastcall **)(LPCSTR))(*(_QWORD *)psz + 16LL))(psz);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
        VariantClear(&pvarg);
        if ( v34 )
        {
          if ( v23 )
            ((void (__fastcall *)(struct IUnknown *))v23->lpVtbl->Release)(v23);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          _bstr_t::_Free((_bstr_t *)&v35);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          _bstr_t::_Free((_bstr_t *)&v36);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          _bstr_t::_Free((_bstr_t *)&v37);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          _bstr_t::_Free((_bstr_t *)&v38);
          goto LABEL_99;
        }
        if ( v23 )
          ((void (__fastcall *)(struct IUnknown *))v23->lpVtbl->Release)(v23);
LABEL_91:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        _bstr_t::_Free((_bstr_t *)&v35);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        _bstr_t::_Free((_bstr_t *)&v36);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        _bstr_t::_Free((_bstr_t *)&v37);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        _bstr_t::_Free((_bstr_t *)&v38);
        goto LABEL_92;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
      VariantClear(&pvarg);
      if ( v23 )
        ((void (__fastcall *)(struct IUnknown *))v23->lpVtbl->Release)(v23);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      _bstr_t::_Free((_bstr_t *)&v35);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      _bstr_t::_Free((_bstr_t *)&v36);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      _bstr_t::_Free((_bstr_t *)&v37);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      _bstr_t::_Free((_bstr_t *)&v38);
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    else
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
      VariantClear(&pvarg);
      if ( v23 )
        ((void (__fastcall *)(struct IUnknown *))v23->lpVtbl->Release)(v23);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      _bstr_t::_Free((_bstr_t *)&v35);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      _bstr_t::_Free((_bstr_t *)&v36);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      _bstr_t::_Free((_bstr_t *)&v37);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      _bstr_t::_Free((_bstr_t *)&v38);
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return (unsigned int)psz;
  }
  ((void (__fastcall *)(struct IUnknown *))v23->lpVtbl->Release)(v23);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  _bstr_t::_Free((_bstr_t *)&v35);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  _bstr_t::_Free((_bstr_t *)&v36);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  _bstr_t::_Free((_bstr_t *)&v37);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  _bstr_t::_Free((_bstr_t *)&v38);
LABEL_99:
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x180049500  mov     rax, rsp
0x180049503  mov     [rax+10h], rbx
0x180049507  mov     [rax+18h], r8
0x18004950b  mov     [rax+8], rcx
0x18004950f  push    rbp
0x180049510  push    rsi
0x180049511  push    rdi
0x180049512  push    r12
0x180049514  push    r13
0x180049516  push    r14
0x180049518  push    r15
0x18004951a  lea     rbp, [rax-58h]
0x18004951e  sub     rsp, 120h
0x180049525  mov     rcx, r8
0x180049528  xor     r13d, r13d
0x18004952b  mov     ebx, r13d
0x18004952e  mov     [rsp+150h+var_E0], rbx
0x180049533  mov     [rsp+150h+var_108], r13
0x180049538  mov     esi, r13d
0x18004953b  mov     [rsp+150h+var_D8], r13
0x180049540  mov     [rsp+150h+var_110], r13
0x180049545  mov     r14d, r13d
0x180049548  mov     [rbp+50h+var_D0], r13
0x18004954c  mov     [rsp+150h+var_118], r13
0x180049551  mov     r15d, r13d
0x180049554  mov     [rbp+50h+var_C8], r13
0x180049558  mov     [rsp+150h+var_120], r13
0x18004955d  mov     r12d, r13d
0x180049560  mov     [rsp+150h+var_E8], r13
0x180049565  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004956a  mov     rdi, rax
0x18004956d  lea     rdx, ?m_migPathQuery@CIASMigrationHelper@@1QBGB; "./Path"
0x180049574  lea     rcx, [rbp+50h+psz]; this
0x180049578  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004957d  mov     r8, rax
0x180049580  lea     rdx, [rsp+150h+var_100]
0x180049585  mov     rcx, rdi; struct IUnknown *
0x180049588  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004958d  mov     rdi, [rax]
0x180049590  test    rdi, rdi
0x180049593  jz      short loc_1800495AC
0x180049595  mov     rbx, rdi
0x180049598  mov     [rsp+150h+var_E0], rbx
0x18004959d  lea     rcx, [rsp+150h+var_E0]
0x1800495a2  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x1800495a7  mov     r13, rdi
0x1800495aa  jmp     short loc_1800495AF
0x1800495ac  mov     rdi, r13
0x1800495af  mov     rcx, [rsp+150h+var_100]
0x1800495b4  test    rcx, rcx
0x1800495b7  jz      short loc_1800495C6
0x1800495b9  mov     rax, [rcx]
0x1800495bc  mov     rax, [rax+10h]
0x1800495c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800495c5  nop
0x1800495c6  test    rdi, rdi
0x1800495c9  jnz     short loc_1800495FF
0x1800495cb  lea     rcx, [rsp+150h+var_120]; this
0x1800495d0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800495d5  nop
0x1800495d6  lea     rcx, [rsp+150h+var_118]; this
0x1800495db  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800495e0  nop
0x1800495e1  lea     rcx, [rsp+150h+var_110]; this
0x1800495e6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800495eb  nop
0x1800495ec  lea     rcx, [rsp+150h+var_108]; this
0x1800495f1  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800495f6  nop
0x1800495f7  test    r13, r13
0x1800495fa  jmp     loc_180049FEF
0x1800495ff  lea     rdx, [rsp+150h+var_108]
0x180049604  lea     rcx, [rsp+150h+var_E0]
0x180049609  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004960e  mov     edi, eax
0x180049610  test    eax, eax
0x180049612  jns     short loc_18004965C
0x180049614  lea     rcx, [rsp+150h+var_120]; this
0x180049619  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004961e  nop
0x18004961f  lea     rcx, [rsp+150h+var_118]; this
0x180049624  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180049629  nop
0x18004962a  lea     rcx, [rsp+150h+var_110]; this
0x18004962f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180049634  nop
0x180049635  lea     rcx, [rsp+150h+var_108]; this
0x18004963a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004963f  nop
0x180049640  test    r13, r13
0x180049643  jz      short loc_180049655
0x180049645  mov     rax, [rbx]
0x180049648  mov     rcx, rbx
0x18004964b  mov     rax, [rax+10h]
0x18004964f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049654  nop
0x180049655  mov     eax, edi
0x180049657  jmp     loc_18004A0A4
0x18004965c  mov     r13, [rbp+50h+arg_10]
0x180049660  mov     rcx, r13
0x180049663  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180049668  mov     rdi, rax
0x18004966b  lea     rdx, ?m_migNameQuery@CIASMigrationHelper@@1QBGB; "./Name"
0x180049672  lea     rcx, [rbp+50h+psz]; this
0x180049676  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004967b  mov     r8, rax
0x18004967e  lea     rdx, [rsp+150h+var_100]
0x180049683  mov     rcx, rdi; struct IUnknown *
0x180049686  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004968b  nop
0x18004968c  cmp     qword ptr [rax], 0
0x180049690  jz      short loc_1800496A5
0x180049692  mov     rsi, [rax]
0x180049695  mov     [rsp+150h+var_D8], rsi
0x18004969a  lea     rcx, [rsp+150h+var_D8]
0x18004969f  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x1800496a4  nop
0x1800496a5  mov     rcx, [rsp+150h+var_100]
0x1800496aa  test    rcx, rcx
0x1800496ad  jz      short loc_1800496BC
0x1800496af  mov     rax, [rcx]
0x1800496b2  mov     rax, [rax+10h]
0x1800496b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800496bb  nop
0x1800496bc  test    rsi, rsi
0x1800496bf  jnz     short loc_1800496F2
0x1800496c1  lea     rcx, [rsp+150h+var_120]; this
0x1800496c6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800496cb  nop
0x1800496cc  lea     rcx, [rsp+150h+var_118]; this
0x1800496d1  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800496d6  nop
0x1800496d7  lea     rcx, [rsp+150h+var_110]; this
0x1800496dc  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800496e1  nop
0x1800496e2  lea     rcx, [rsp+150h+var_108]; this
0x1800496e7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800496ec  nop
0x1800496ed  jmp     loc_180049FEC
0x1800496f2  lea     rdx, [rsp+150h+var_110]
0x1800496f7  lea     rcx, [rsp+150h+var_D8]
0x1800496fc  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x180049701  mov     edi, eax
0x180049703  test    eax, eax
0x180049705  jns     short loc_18004975D
0x180049707  lea     rcx, [rsp+150h+var_120]; this
0x18004970c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180049711  nop
0x180049712  lea     rcx, [rsp+150h+var_118]; this
0x180049717  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004971c  nop
0x18004971d  lea     rcx, [rsp+150h+var_110]; this
0x180049722  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180049727  nop
0x180049728  mov     rax, [rsi]
0x18004972b  mov     rcx, rsi
0x18004972e  mov     rax, [rax+10h]
0x180049732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049737  nop
0x180049738  lea     rcx, [rsp+150h+var_108]; this
0x18004973d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180049742  nop
0x180049743  test    rbx, rbx
0x180049746  jz      short loc_180049758
0x180049748  mov     rax, [rbx]
0x18004974b  mov     rcx, rbx
0x18004974e  mov     rax, [rax+10h]
0x180049752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049757  nop
0x180049758  jmp     loc_180049655
0x18004975d  mov     rcx, r13
0x180049760  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180049765  mov     rdi, rax
0x180049768  lea     rdx, ?m_migTypeQuery@CIASMigrationHelper@@1QBGB; "./Type"
0x18004976f  lea     rcx, [rbp+50h+psz]; this
0x180049773  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180049778  mov     r8, rax
0x18004977b  lea     rdx, [rsp+150h+var_100]
0x180049780  mov     rcx, rdi; struct IUnknown *
0x180049783  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x180049788  nop
0x180049789  cmp     qword ptr [rax], 0
0x18004978d  jz      short loc_1800497A0
0x18004978f  mov     r14, [rax]
0x180049792  mov     [rbp+50h+var_D0], r14
0x180049796  lea     rcx, [rbp+50h+var_D0]
0x18004979a  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004979f  nop
0x1800497a0  mov     rcx, [rsp+150h+var_100]
0x1800497a5  test    rcx, rcx
0x1800497a8  jz      short loc_1800497B7
0x1800497aa  mov     rax, [rcx]
0x1800497ad  mov     rax, [rax+10h]
0x1800497b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497b6  nop
0x1800497b7  test    r14, r14
0x1800497ba  jnz     short loc_1800497FD
0x1800497bc  lea     rcx, [rsp+150h+var_120]; this
0x1800497c1  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800497c6  nop
0x1800497c7  lea     rcx, [rsp+150h+var_118]; this
0x1800497cc  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800497d1  nop
0x1800497d2  lea     rcx, [rsp+150h+var_110]; this
0x1800497d7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800497dc  nop
0x1800497dd  mov     rax, [rsi]
0x1800497e0  mov     rcx, rsi
0x1800497e3  mov     rax, [rax+10h]
0x1800497e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497ec  nop
0x1800497ed  lea     rcx, [rsp+150h+var_108]; this
0x1800497f2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800497f7  nop
0x1800497f8  jmp     loc_180049FEC
0x1800497fd  lea     rdx, [rsp+150h+var_118]
0x180049802  lea     rcx, [rbp+50h+var_D0]
0x180049806  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004980b  mov     edi, eax
0x18004980d  test    eax, eax
0x18004980f  jns     short loc_180049877
0x180049811  lea     rcx, [rsp+150h+var_120]; this
0x180049816  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004981b  nop
0x18004981c  lea     rcx, [rsp+150h+var_118]; this
0x180049821  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180049826  nop
0x180049827  mov     rax, [r14]
0x18004982a  mov     rcx, r14
0x18004982d  mov     rax, [rax+10h]
0x180049831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049836  nop
0x180049837  lea     rcx, [rsp+150h+var_110]; this
0x18004983c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180049841  nop
0x180049842  mov     rax, [rsi]
0x180049845  mov     rcx, rsi
0x180049848  mov     rax, [rax+10h]
0x18004984c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049851  nop
0x180049852  lea     rcx, [rsp+150h+var_108]; this
0x180049857  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004985c  nop
0x18004985d  test    rbx, rbx
0x180049860  jz      short loc_180049872
0x180049862  mov     rax, [rbx]
0x180049865  mov     rcx, rbx
0x180049868  mov     rax, [rax+10h]
0x18004986c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049871  nop
0x180049872  jmp     loc_180049655
0x180049877  mov     rcx, r13
0x18004987a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004987f  mov     rdi, rax
0x180049882  lea     rdx, ?m_migValueQuery@CIASMigrationHelper@@1QBGB; "./Value"
0x180049889  lea     rcx, [rbp+50h+psz]; this
0x18004988d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180049892  mov     r8, rax
0x180049895  lea     rdx, [rsp+150h+var_100]
0x18004989a  mov     rcx, rdi; struct IUnknown *
0x18004989d  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x1800498a2  nop
0x1800498a3  cmp     qword ptr [rax], 0
0x1800498a7  jz      short loc_1800498BA
0x1800498a9  mov     r15, [rax]
0x1800498ac  mov     [rbp+50h+var_C8], r15
0x1800498b0  lea     rcx, [rbp+50h+var_C8]
0x1800498b4  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x1800498b9  nop
0x1800498ba  mov     rcx, [rsp+150h+var_100]
0x1800498bf  test    rcx, rcx
0x1800498c2  jz      short loc_1800498D1
0x1800498c4  mov     rax, [rcx]
0x1800498c7  mov     rax, [rax+10h]
0x1800498cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498d0  nop
0x1800498d1  test    r15, r15
0x1800498d4  jnz     short loc_180049927
0x1800498d6  lea     rcx, [rsp+150h+var_120]; this
0x1800498db  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800498e0  nop
0x1800498e1  lea     rcx, [rsp+150h+var_118]; this
0x1800498e6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800498eb  nop
0x1800498ec  mov     rax, [r14]
0x1800498ef  mov     rcx, r14
0x1800498f2  mov     rax, [rax+10h]
0x1800498f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498fb  nop
0x1800498fc  lea     rcx, [rsp+150h+var_110]; this
0x180049901  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180049906  nop
0x180049907  mov     rax, [rsi]
0x18004990a  mov     rcx, rsi
0x18004990d  mov     rax, [rax+10h]
0x180049911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049916  nop
0x180049917  lea     rcx, [rsp+150h+var_108]; this
0x18004991c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180049921  nop
  ... truncated ...
```
