# CIASMigrationHelper::RemoveRequiredProperties(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)

- ea: `0x18004e630`
- end: `0x18004ef80`
- name: `?RemoveRequiredProperties@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `2384`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180024cac`
- `0x18002d08c`
- `0x18002efa0`
- `0x180047604`
- `0x18004cef4`
- `0x18004d11c`
- `0x18004d190`
- `0x18004d1ec`
- `0x18004e430`
- `0x18004e630`
- `0x180050044`
- `0x180051e7c`
- `0x1800524fc`
- `0x180052588`
- `0x180058010`

## string_xrefs

- `0x18004e822`: `./ReplaceChildrenNode`
- `0x18004e692`: `./Path`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall CIASMigrationHelper::RemoveRequiredProperties(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  __int64 v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // r13
  __int64 v7; // rdi
  __int64 v8; // r12
  struct IUnknown *v9; // r14
  __int64 *v10; // rax
  __int64 v11; // r14
  bool v12; // zf
  int StringValueFromNode; // r14d
  struct IUnknown *v15; // r14
  __int64 *v16; // rax
  struct IUnknown *v17; // r14
  __int64 *v18; // rax
  struct IUnknown *v19; // rax
  __int64 v20; // rax
  struct IUnknown *v21; // rax
  __int64 *v22; // rax
  struct IUnknown *v23; // rax
  __int64 *Node; // rax
  struct IUnknown *v25; // rdi
  __int64 v26; // r15
  struct IUnknown *v27; // r14
  struct IUnknown *v28; // rax
  struct IUnknown *v29; // rax
  __int64 *v30; // rax
  struct IUnknown *v31; // rax
  struct IUnknown **v32; // rax
  __int64 v33; // rdx
  struct IUnknown *v34; // rax
  struct IUnknown **v35; // rax
  __int64 v36; // rdx
  int v37; // edi
  struct IUnknown *v38; // rax
  __int64 *v39; // rax
  __int64 v40; // rdi
  __int64 *v41; // [rsp+28h] [rbp-69h] BYREF
  __int64 v42; // [rsp+30h] [rbp-61h] BYREF
  struct IUnknown *v43; // [rsp+38h] [rbp-59h]
  struct IUnknown *v44; // [rsp+40h] [rbp-51h] BYREF
  __int64 v45; // [rsp+48h] [rbp-49h] BYREF
  struct IUnknown *v46; // [rsp+50h] [rbp-41h]
  __int64 v47; // [rsp+58h] [rbp-39h] BYREF
  __int64 v48; // [rsp+60h] [rbp-31h] BYREF
  struct IUnknown *v49; // [rsp+68h] [rbp-29h] BYREF
  __int64 v50; // [rsp+70h] [rbp-21h]
  __int64 v51; // [rsp+78h] [rbp-19h] BYREF
  __int64 v52; // [rsp+80h] [rbp-11h] BYREF
  __int64 v53; // [rsp+88h] [rbp-9h] BYREF
  char v54[8]; // [rsp+90h] [rbp-1h] BYREF
  __int64 v55; // [rsp+98h] [rbp+7h]
  __int64 v56; // [rsp+A0h] [rbp+Fh]
  __int64 v57; // [rsp+A8h] [rbp+17h]
  __int64 v58; // [rsp+B0h] [rbp+1Fh]
  int v61; // [rsp+110h] [rbp+7Fh] BYREF

  v3 = 0;
  v4 = 0;
  v51 = 0;
  v42 = 0;
  v5 = 0;
  v52 = 0;
  v41 = 0;
  v6 = 0;
  v53 = 0;
  v61 = 0;
  v7 = 0;
  v45 = 0;
  v8 = 0;
  v47 = 0;
  v9 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&v44, L"./Path");
  v10 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v9);
  v11 = *v10;
  if ( *v10 )
  {
    v4 = *v10;
    v51 = *v10;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v51);
    v3 = v11;
  }
  else
  {
    v11 = 0;
  }
  if ( v43 )
    ((void (__fastcall *)(struct IUnknown *))v43->lpVtbl->Release)(v43);
  if ( !v11 )
    goto LABEL_7;
  StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v51, &v42);
  if ( StringValueFromNode < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v41);
    _bstr_t::_Free((_bstr_t *)&v42);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return (unsigned int)StringValueFromNode;
  }
  v15 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&v44, L"./Name");
  v16 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v15);
  if ( *v16 )
  {
    v5 = *v16;
    v52 = *v16;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v52);
  }
  if ( v43 )
    ((void (__fastcall *)(struct IUnknown *))v43->lpVtbl->Release)(v43);
  if ( !v5 )
  {
LABEL_7:
    _bstr_t::_Free((_bstr_t *)&v41);
    _bstr_t::_Free((_bstr_t *)&v42);
    goto LABEL_8;
  }
  StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v52, &v41);
  if ( StringValueFromNode < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v41);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v42);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return (unsigned int)StringValueFromNode;
  }
  v17 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&v44, L"./ReplaceChildrenNode");
  v18 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v17);
  if ( *v18 )
  {
    v6 = *v18;
    v53 = *v18;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v53);
  }
  if ( v43 )
    ((void (__fastcall *)(struct IUnknown *))v43->lpVtbl->Release)(v43);
  if ( v6 )
  {
    StringValueFromNode = CIASMigrationHelper::GetBOOLValueFromNode(&v53, &v61);
    if ( StringValueFromNode < 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      _bstr_t::_Free((_bstr_t *)&v41);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      _bstr_t::_Free((_bstr_t *)&v42);
      if ( v3 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      return (unsigned int)StringValueFromNode;
    }
    v19 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
    v20 = MSXML2::IXMLDOMDocument::GetdocumentElement(v19);
    v21 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(v20);
    v44 = (struct IUnknown *)v42;
    if ( v42 )
      _InterlockedIncrement((volatile signed __int32 *)(v42 + 16));
    v22 = (__int64 *)MSXML2::IXMLDOMNode::selectNodes(v21);
    if ( *v22 )
    {
      v7 = *v22;
      v45 = *v22;
      _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v45);
    }
    if ( v43 )
      ((void (__fastcall *)(struct IUnknown *))v43->lpVtbl->Release)(v43);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    if ( v7 )
    {
      v23 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v45);
      Node = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v23);
      if ( *Node )
      {
        v8 = *Node;
        v47 = *Node;
        _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v47);
      }
      if ( v44 )
        ((void (__fastcall *)(struct IUnknown *))v44->lpVtbl->Release)(v44);
      while ( 1 )
      {
        if ( !v8 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          _bstr_t::_Free((_bstr_t *)&v41);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          _bstr_t::_Free((_bstr_t *)&v42);
LABEL_106:
          if ( v4 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
          return 0;
        }
        if ( v61 )
        {
          v25 = 0;
          v44 = 0;
          v26 = 0;
          v48 = 0;
          v27 = 0;
          v49 = 0;
          v43 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v47);
          _bstr_t::_bstr_t((_bstr_t *)v54, L"./Children");
          v28 = *(struct IUnknown **)MSXML2::IXMLDOMNode::selectSingleNode(v43);
          v43 = v28;
          if ( v28 )
          {
            v25 = v28;
            v44 = v28;
            _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v44);
            v46 = v25;
          }
          else
          {
            v43 = 0;
            v46 = 0;
          }
          if ( v55 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
          if ( !v43 )
          {
            if ( v46 )
              ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
            goto LABEL_98;
          }
          v29 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v44);
          v30 = (__int64 *)MSXML2::IXMLDOMNode::GetchildNodes(v29);
          if ( *v30 )
          {
            v26 = *v30;
            v48 = *v30;
            _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v48);
          }
          if ( v56 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
          if ( !v26 )
          {
            if ( v46 )
              ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
LABEL_98:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
            _bstr_t::_Free((_bstr_t *)&v41);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            _bstr_t::_Free((_bstr_t *)&v42);
            v12 = v4 == 0;
            goto LABEL_99;
          }
          v31 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v48);
          v32 = (struct IUnknown **)MSXML2::IXMLDOMNodeList::nextNode(v31);
          if ( *v32 )
          {
            v27 = *v32;
            v49 = *v32;
            _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v49);
          }
          if ( v57 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
          if ( !v27 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
            if ( v46 )
              ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
            _bstr_t::_Free((_bstr_t *)&v41);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            _bstr_t::_Free((_bstr_t *)&v42);
            goto LABEL_106;
          }
          while ( v27 )
          {
            if ( v41 )
              v33 = *v41;
            else
              v33 = 0;
            LODWORD(v46) = CIASMigrationHelper::RemovePropertyFromANode(&v49, v33);
            if ( (int)v46 < 0 )
            {
              ((void (__fastcall *)(struct IUnknown *))v27->lpVtbl->Release)(v27);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              if ( v25 )
                ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
              _bstr_t::_Free((_bstr_t *)&v41);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
              _bstr_t::_Free((_bstr_t *)&v42);
              if ( v4 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
              return (unsigned int)v46;
            }
            v34 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v48);
            v35 = (struct IUnknown **)MSXML2::IXMLDOMNodeList::nextNode(v34);
            if ( v27 != *v35 )
            {
              v43 = v27;
              v27 = *v35;
              v49 = *v35;
              _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v49);
              if ( v43 )
                ((void (__fastcall *)(struct IUnknown *))v43->lpVtbl->Release)(v43);
            }
            if ( v58 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v25 )
            ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
        }
        else
        {
          if ( v41 )
            v36 = *v41;
          else
            v36 = 0;
          v37 = CIASMigrationHelper::RemovePropertyFromANode(&v47, v36);
          if ( v37 < 0 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
            _bstr_t::_Free((_bstr_t *)&v41);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            _bstr_t::_Free((_bstr_t *)&v42);
            if ( v4 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
            return (unsigned int)v37;
          }
        }
        v38 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v45);
        v39 = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v38);
        if ( v8 != *v39 )
        {
          v40 = v8;
          v8 = *v39;
          v47 = *v39;
          _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v47);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        }
        if ( v50 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    _bstr_t::_Free((_bstr_t *)&v41);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v42);
  }
  else
  {
    _bstr_t::_Free((_bstr_t *)&v41);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    _bstr_t::_Free((_bstr_t *)&v42);
  }
LABEL_8:
  v12 = v3 == 0;
LABEL_99:
  if ( !v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return 2147549183LL;
}

```

## disassembly

```asm
0x18004e630  mov     rax, rsp
0x18004e633  mov     [rax+10h], rbx
0x18004e637  mov     [rax+18h], r8
0x18004e63b  mov     [rax+8], rcx
0x18004e63f  push    rbp
0x18004e640  push    rsi
0x18004e641  push    rdi
0x18004e642  push    r12
0x18004e644  push    r13
0x18004e646  push    r14
0x18004e648  push    r15
0x18004e64a  lea     rbp, [rax-5Fh]
0x18004e64e  sub     rsp, 0B0h
0x18004e655  mov     rcx, r8
0x18004e658  xor     r15d, r15d
0x18004e65b  mov     ebx, r15d
0x18004e65e  mov     [rbp+57h+var_70], rbx
0x18004e662  mov     [rbp+57h+var_B8], r15
0x18004e666  mov     esi, r15d
0x18004e669  mov     [rbp+57h+var_68], r15
0x18004e66d  mov     [rbp+57h+var_C0], r15
0x18004e671  mov     r13d, r15d
0x18004e674  mov     [rbp+57h+var_60], r15
0x18004e678  mov     [rbp+57h+arg_18], r15d
0x18004e67c  mov     edi, r15d
0x18004e67f  mov     [rbp+57h+var_A0], r15
0x18004e683  mov     r12d, r15d
0x18004e686  mov     [rbp+57h+var_90], r15
0x18004e68a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e68f  mov     r14, rax
0x18004e692  lea     rdx, ?m_migPathQuery@CIASMigrationHelper@@1QBGB; "./Path"
0x18004e699  lea     rcx, [rbp+57h+var_A8]; this
0x18004e69d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004e6a2  mov     r8, rax
0x18004e6a5  lea     rdx, [rbp+57h+var_B0]
0x18004e6a9  mov     rcx, r14; struct IUnknown *
0x18004e6ac  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004e6b1  mov     r14, [rax]
0x18004e6b4  test    r14, r14
0x18004e6b7  jz      short loc_18004E6CE
0x18004e6b9  mov     rbx, r14
0x18004e6bc  mov     [rbp+57h+var_70], rbx
0x18004e6c0  lea     rcx, [rbp+57h+var_70]
0x18004e6c4  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004e6c9  mov     r15, r14
0x18004e6cc  jmp     short loc_18004E6D1
0x18004e6ce  mov     r14, r15
0x18004e6d1  mov     rcx, [rbp+57h+var_B0]
0x18004e6d5  test    rcx, rcx
0x18004e6d8  jz      short loc_18004E6E7
0x18004e6da  mov     rax, [rcx]
0x18004e6dd  mov     rax, [rax+10h]
0x18004e6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6e6  nop
0x18004e6e7  test    r14, r14
0x18004e6ea  jnz     short loc_18004E708
0x18004e6ec  lea     rcx, [rbp+57h+var_C0]; this
0x18004e6f0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e6f5  nop
0x18004e6f6  lea     rcx, [rbp+57h+var_B8]; this
0x18004e6fa  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e6ff  nop
0x18004e700  test    r15, r15
0x18004e703  jmp     loc_18004EE7C
0x18004e708  lea     rdx, [rbp+57h+var_B8]
0x18004e70c  lea     rcx, [rbp+57h+var_70]
0x18004e710  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004e715  mov     r14d, eax
0x18004e718  test    eax, eax
0x18004e71a  jns     short loc_18004E74D
0x18004e71c  lea     rcx, [rbp+57h+var_C0]; this
0x18004e720  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e725  nop
0x18004e726  lea     rcx, [rbp+57h+var_B8]; this
0x18004e72a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e72f  nop
0x18004e730  test    r15, r15
0x18004e733  jz      short loc_18004E745
0x18004e735  mov     rax, [rbx]
0x18004e738  mov     rcx, rbx
0x18004e73b  mov     rax, [rax+10h]
0x18004e73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e744  nop
0x18004e745  mov     eax, r14d
0x18004e748  jmp     loc_18004EF65
0x18004e74d  mov     rcx, [rbp+57h+arg_10]
0x18004e751  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e756  mov     r14, rax
0x18004e759  lea     rdx, ?m_migNameQuery@CIASMigrationHelper@@1QBGB; "./Name"
0x18004e760  lea     rcx, [rbp+57h+var_A8]; this
0x18004e764  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004e769  mov     r8, rax
0x18004e76c  lea     rdx, [rbp+57h+var_B0]
0x18004e770  mov     rcx, r14; struct IUnknown *
0x18004e773  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004e778  nop
0x18004e779  cmp     qword ptr [rax], 0
0x18004e77d  jz      short loc_18004E790
0x18004e77f  mov     rsi, [rax]
0x18004e782  mov     [rbp+57h+var_68], rsi
0x18004e786  lea     rcx, [rbp+57h+var_68]
0x18004e78a  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004e78f  nop
0x18004e790  mov     rcx, [rbp+57h+var_B0]
0x18004e794  test    rcx, rcx
0x18004e797  jz      short loc_18004E7A6
0x18004e799  mov     rax, [rcx]
0x18004e79c  mov     rax, [rax+10h]
0x18004e7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7a5  nop
0x18004e7a6  test    rsi, rsi
0x18004e7a9  jnz     short loc_18004E7C4
0x18004e7ab  lea     rcx, [rbp+57h+var_C0]; this
0x18004e7af  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e7b4  nop
0x18004e7b5  lea     rcx, [rbp+57h+var_B8]; this
0x18004e7b9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e7be  nop
0x18004e7bf  jmp     loc_18004E700
0x18004e7c4  lea     rdx, [rbp+57h+var_C0]
0x18004e7c8  lea     rcx, [rbp+57h+var_68]
0x18004e7cc  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004e7d1  mov     r14d, eax
0x18004e7d4  test    eax, eax
0x18004e7d6  jns     short loc_18004E816
0x18004e7d8  lea     rcx, [rbp+57h+var_C0]; this
0x18004e7dc  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e7e1  nop
0x18004e7e2  mov     rax, [rsi]
0x18004e7e5  mov     rcx, rsi
0x18004e7e8  mov     rax, [rax+10h]
0x18004e7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7f1  nop
0x18004e7f2  lea     rcx, [rbp+57h+var_B8]; this
0x18004e7f6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e7fb  nop
0x18004e7fc  test    r15, r15
0x18004e7ff  jz      short loc_18004E811
0x18004e801  mov     rax, [rbx]
0x18004e804  mov     rcx, rbx
0x18004e807  mov     rax, [rax+10h]
0x18004e80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e810  nop
0x18004e811  jmp     loc_18004E745
0x18004e816  mov     rcx, [rbp+57h+arg_10]
0x18004e81a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e81f  mov     r14, rax
0x18004e822  lea     rdx, ?m_migReplaceChildrenNodeQuery@CIASMigrationHelper@@1QBGB; "./ReplaceChildrenNode"
0x18004e829  lea     rcx, [rbp+57h+var_A8]; this
0x18004e82d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004e832  mov     r8, rax
0x18004e835  lea     rdx, [rbp+57h+var_B0]
0x18004e839  mov     rcx, r14; struct IUnknown *
0x18004e83c  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004e841  nop
0x18004e842  cmp     qword ptr [rax], 0
0x18004e846  jz      short loc_18004E859
0x18004e848  mov     r13, [rax]
0x18004e84b  mov     [rbp+57h+var_60], r13
0x18004e84f  lea     rcx, [rbp+57h+var_60]
0x18004e853  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004e858  nop
0x18004e859  mov     rcx, [rbp+57h+var_B0]
0x18004e85d  test    rcx, rcx
0x18004e860  jz      short loc_18004E86F
0x18004e862  mov     rax, [rcx]
0x18004e865  mov     rax, [rax+10h]
0x18004e869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e86e  nop
0x18004e86f  test    r13, r13
0x18004e872  jnz     short loc_18004E89D
0x18004e874  lea     rcx, [rbp+57h+var_C0]; this
0x18004e878  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e87d  nop
0x18004e87e  mov     rax, [rsi]
0x18004e881  mov     rcx, rsi
0x18004e884  mov     rax, [rax+10h]
0x18004e888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e88d  nop
0x18004e88e  lea     rcx, [rbp+57h+var_B8]; this
0x18004e892  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e897  nop
0x18004e898  jmp     loc_18004E700
0x18004e89d  lea     rdx, [rbp+57h+arg_18]
0x18004e8a1  lea     rcx, [rbp+57h+var_60]
0x18004e8a5  call    ?GetBOOLValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAH@Z; CIASMigrationHelper::GetBOOLValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,int &)
0x18004e8aa  mov     r14d, eax
0x18004e8ad  test    eax, eax
0x18004e8af  jns     short loc_18004E900
0x18004e8b1  mov     rax, [r13+0]
0x18004e8b5  mov     rcx, r13
0x18004e8b8  mov     rax, [rax+10h]
0x18004e8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8c1  nop
0x18004e8c2  lea     rcx, [rbp+57h+var_C0]; this
0x18004e8c6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e8cb  nop
0x18004e8cc  mov     rax, [rsi]
0x18004e8cf  mov     rcx, rsi
0x18004e8d2  mov     rax, [rax+10h]
0x18004e8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8db  nop
0x18004e8dc  lea     rcx, [rbp+57h+var_B8]; this
0x18004e8e0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e8e5  nop
0x18004e8e6  test    r15, r15
0x18004e8e9  jz      short loc_18004E8FB
0x18004e8eb  mov     rax, [rbx]
0x18004e8ee  mov     rcx, rbx
0x18004e8f1  mov     rax, [rax+10h]
0x18004e8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8fa  nop
0x18004e8fb  jmp     loc_18004E745
0x18004e900  mov     rcx, [rbp+57h+arg_0]
0x18004e904  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e909  lea     rdx, [rbp+57h+var_88]
0x18004e90d  mov     rcx, rax; struct IUnknown *
0x18004e910  call    ?GetdocumentElement@IXMLDOMDocument@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMDocument::GetdocumentElement(void)
0x18004e915  nop
0x18004e916  mov     rcx, rax
0x18004e919  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e91e  mov     rcx, [rbp+57h+var_B8]
0x18004e922  mov     [rbp+57h+var_A8], rcx
0x18004e926  test    rcx, rcx
0x18004e929  jz      short loc_18004E92F
0x18004e92b  lock inc dword ptr [rcx+10h]
0x18004e92f  lea     r8, [rbp+57h+var_A8]
0x18004e933  lea     rdx, [rbp+57h+var_B0]
0x18004e937  mov     rcx, rax; struct IUnknown *
0x18004e93a  call    ?selectNodes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectNodes(_bstr_t)
0x18004e93f  nop
0x18004e940  cmp     qword ptr [rax], 0
0x18004e944  jz      short loc_18004E957
0x18004e946  mov     rdi, [rax]
0x18004e949  mov     [rbp+57h+var_A0], rdi
0x18004e94d  lea     rcx, [rbp+57h+var_A0]
0x18004e951  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004e956  nop
0x18004e957  mov     rcx, [rbp+57h+var_B0]
0x18004e95b  test    rcx, rcx
0x18004e95e  jz      short loc_18004E96D
0x18004e960  mov     rax, [rcx]
0x18004e963  mov     rax, [rax+10h]
0x18004e967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e96c  nop
0x18004e96d  lea     rcx, [rbp+57h+var_88]
0x18004e971  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004e976  test    rdi, rdi
0x18004e979  jnz     short loc_18004E9B5
0x18004e97b  mov     rax, [r13+0]
0x18004e97f  mov     rcx, r13
0x18004e982  mov     rax, [rax+10h]
0x18004e986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e98b  nop
0x18004e98c  lea     rcx, [rbp+57h+var_C0]; this
0x18004e990  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e995  nop
0x18004e996  mov     rax, [rsi]
0x18004e999  mov     rcx, rsi
0x18004e99c  mov     rax, [rax+10h]
0x18004e9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9a5  nop
0x18004e9a6  lea     rcx, [rbp+57h+var_B8]; this
0x18004e9aa  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e9af  nop
0x18004e9b0  jmp     loc_18004E700
0x18004e9b5  lea     rcx, [rbp+57h+var_A0]
0x18004e9b9  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e9be  lea     rdx, [rbp+57h+var_A8]
0x18004e9c2  mov     rcx, rax; struct IUnknown *
0x18004e9c5  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x18004e9ca  nop
0x18004e9cb  cmp     qword ptr [rax], 0
0x18004e9cf  jz      short loc_18004E9E2
0x18004e9d1  mov     r12, [rax]
0x18004e9d4  mov     [rbp+57h+var_90], r12
0x18004e9d8  lea     rcx, [rbp+57h+var_90]
0x18004e9dc  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004e9e1  nop
0x18004e9e2  mov     rcx, [rbp+57h+var_A8]
0x18004e9e6  test    rcx, rcx
0x18004e9e9  jz      short loc_18004E9F8
0x18004e9eb  mov     rax, [rcx]
0x18004e9ee  mov     rax, [rax+10h]
0x18004e9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9f7  nop
0x18004e9f8  test    r12, r12
0x18004e9fb  jz      loc_18004EF08
0x18004ea01  cmp     [rbp+57h+arg_18], 0
0x18004ea05  jz      loc_18004EBEE
0x18004ea0b  xor     edi, edi
0x18004ea0d  mov     [rbp+57h+var_A8], rdi
0x18004ea11  xor     r15d, r15d
0x18004ea14  mov     [rbp+57h+var_88], r15
0x18004ea18  xor     r14d, r14d
0x18004ea1b  mov     [rbp+57h+var_80], r14
0x18004ea1f  lea     rcx, [rbp+57h+var_90]
0x18004ea23  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004ea28  mov     [rbp+57h+var_B0], rax
0x18004ea2c  lea     rdx, ?m_migChildrenQuery@CIASMigrationHelper@@1QBGB; "./Children"
  ... truncated ...
```
