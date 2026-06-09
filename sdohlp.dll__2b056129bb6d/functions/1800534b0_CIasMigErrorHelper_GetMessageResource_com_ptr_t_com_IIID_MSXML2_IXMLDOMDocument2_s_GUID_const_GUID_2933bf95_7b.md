# CIasMigErrorHelper::GetMessageResource(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &,_bstr_t &,ulong &,_bstr_t &)

- ea: `0x1800534b0`
- end: `0x180053bca`
- name: `?GetMessageResource@CIasMigErrorHelper@@CAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@1AEAK1@Z`
- size: `1818`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052d80`

## callees

- `0x1800241bb`
- `0x180024cac`
- `0x18002d08c`
- `0x18002efa0`
- `0x18002f08c`
- `0x180041148`
- `0x180042a80`
- `0x180047604`
- `0x18004cf60`
- `0x18004d11c`
- `0x18004d1ec`
- `0x180050044`
- `0x180051e7c`
- `0x1800524fc`
- `0x180052588`
- `0x1800534b0`
- `0x180054ce0`
- `0x180055030`
- `0x180058010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180053558`
- `msvcrt!swprintf_s` at `0x180053558`
- `KERNEL32!lstrcmpW` at `0x180053792`
- `KERNEL32!lstrcmpW` at `0x180053792`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CIasMigErrorHelper::GetMessageResource(
        __int64 a1,
        LPCWCH **a2,
        const WCHAR ***a3,
        _DWORD *a4,
        __int64 a5)
{
  LPCWCH **v6; // r13
  LPCWCH *v8; // rbx
  char *v9; // rax
  struct IUnknown *v10; // rax
  __int64 v11; // rax
  struct IUnknown *v12; // rbx
  __int64 v13; // rsi
  __int64 v14; // r14
  __int64 v15; // rdi
  struct IUnknown *v16; // rbx
  __int64 v17; // r15
  struct IUnknown *v19; // rax
  __int64 v20; // rbx
  struct IUnknown *v21; // r12
  __int64 *v22; // rax
  struct IUnknown *v23; // r12
  __int64 *v24; // rax
  struct IUnknown *v25; // r12
  __int64 v26; // r12
  int StringValueFromNode; // r13d
  const WCHAR *v28; // rdx
  const WCHAR *v29; // rcx
  struct IUnknown *v30; // rax
  __int64 *Node; // rax
  __int64 v32; // r13
  struct IUnknown *v33; // r13
  __int64 *v34; // rax
  struct IUnknown *v35; // r13
  __int64 *v36; // rax
  int DWordValueFromNode; // r12d
  LPCWCH *v38; // rax
  __int64 v39; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v40; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v41; // [rsp+40h] [rbp-C0h] BYREF
  const WCHAR **v42; // [rsp+48h] [rbp-B8h] BYREF
  LPCWCH **v43; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h] BYREF
  const WCHAR ***v47; // [rsp+70h] [rbp-90h]
  __int64 v48; // [rsp+78h] [rbp-88h] BYREF
  char v49[8]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD *v50; // [rsp+88h] [rbp-78h]
  __int64 v51; // [rsp+90h] [rbp-70h]
  wchar_t Buffer[1024]; // [rsp+A0h] [rbp-60h] BYREF

  v50 = a4;
  v47 = a3;
  v6 = a2;
  v43 = a2;
  v51 = a5;
  memset_0(Buffer, 0, sizeof(Buffer));
  v8 = *v6;
  if ( !*v6 )
  {
LABEL_6:
    v9 = 0;
    goto LABEL_7;
  }
  v9 = (char *)v8[1];
  if ( !v9 )
  {
    v9 = _com_util::ConvertBSTRToString(*v8);
    v8[1] = (LPCWCH)v9;
    if ( !v9 )
    {
      if ( *v8 )
        _com_issue_error(-2147024882);
      goto LABEL_6;
    }
  }
LABEL_7:
  swprintf_s(Buffer, 0x400u, L"/Root/User_Message_Dictionary/Property_Message[@name='%S']", v9);
  v10 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
  v11 = MSXML2::IXMLDOMDocument::GetdocumentElement(v10);
  v12 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(v11);
  _bstr_t::_bstr_t((_bstr_t *)&v39, Buffer);
  MSXML2::IXMLDOMNode::selectSingleNode(v12);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
  v13 = v48;
  if ( v48 )
  {
    v14 = 0;
    v44 = 0;
    v15 = 0;
    v45 = 0;
    v16 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v48);
    _bstr_t::_bstr_t((_bstr_t *)&v39, L"./Value_Message");
    MSXML2::IXMLDOMNode::selectNodes(v16);
    v17 = v46;
    if ( v46 )
    {
      v19 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v46);
      MSXML2::IXMLDOMNodeList::nextNode(v19);
      v20 = v41;
      if ( v41 )
      {
        while ( 1 )
        {
          v25 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v41);
          _bstr_t::_bstr_t((_bstr_t *)v49, L"./Value");
          MSXML2::IXMLDOMNode::selectSingleNode(v25);
          v26 = v39;
          if ( !v39 )
            break;
          v42 = 0;
          StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v39, &v42);
          if ( StringValueFromNode < 0 )
          {
            _bstr_t::_Free((_bstr_t *)&v42);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            return (unsigned int)StringValueFromNode;
          }
          if ( *v47 )
            v28 = **v47;
          else
            v28 = 0;
          if ( v42 )
            v29 = *v42;
          else
            v29 = 0;
          if ( !lstrcmpW(v29, v28) )
          {
            v33 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v41);
            _bstr_t::_bstr_t((_bstr_t *)&v40, L"./Message");
            v34 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v33);
            if ( *v34 )
            {
              v14 = *v34;
              v44 = *v34;
              _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v44);
            }
            if ( v47 )
              ((void (__fastcall *)(const WCHAR ***))(*v47)[2])(v47);
            v35 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v41);
            _bstr_t::_bstr_t((_bstr_t *)&v40, L"./Parameter");
            v36 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v35);
            if ( *v36 )
            {
              v15 = *v36;
              v45 = *v36;
              _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v45);
            }
            if ( v47 )
              ((void (__fastcall *)(const WCHAR ***))(*v47)[2])(v47);
            _bstr_t::_Free((_bstr_t *)&v42);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
LABEL_47:
            v6 = v43;
            goto LABEL_48;
          }
          v30 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v46);
          Node = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v30);
          if ( v20 != *Node )
          {
            v32 = v20;
            v20 = *Node;
            v41 = *Node;
            _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v41);
            if ( v32 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
          }
          if ( v40 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
          _bstr_t::_Free((_bstr_t *)&v42);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          if ( !v20 )
            goto LABEL_47;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        return 2147549183LL;
      }
      v21 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v48);
      _bstr_t::_bstr_t((_bstr_t *)&v43, L"./Message");
      v22 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v21);
      if ( *v22 )
      {
        v14 = *v22;
        v44 = *v22;
        _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v44);
      }
      if ( v39 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      v23 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v48);
      _bstr_t::_bstr_t((_bstr_t *)&v43, L"./Parameter");
      v24 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v23);
      if ( *v24 )
      {
        v15 = *v24;
        v45 = *v24;
        _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v45);
      }
      if ( v39 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
LABEL_48:
      if ( v14 )
      {
        DWordValueFromNode = CIASMigrationHelper::GetDWordValueFromNode(&v44, v50);
        if ( DWordValueFromNode >= 0 )
        {
          if ( !v15
            || (DWordValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v45, v51), DWordValueFromNode >= 0) )
          {
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            if ( v15 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            return 0;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WppDbgPrint("GetStringValueFromNode() failed for %S: %!hresult!");
            v38 = *v6;
            if ( *v6 )
              v38 = (LPCWCH *)*v38;
            WPP_SF_sSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              (unsigned int)WPP_a172f93e3a9532ef0a391bb7dc34d5ba_Traceguids,
              (unsigned int)"NPSDS",
              (__int64)v38,
              DWordValueFromNode);
          }
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        else
        {
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          if ( v15 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        return (unsigned int)DWordValueFromNode;
      }
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    return 2147549183LL;
  }
  *a4 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800534b0  push    rbp
0x1800534b2  push    rbx
0x1800534b3  push    rsi
0x1800534b4  push    rdi
0x1800534b5  push    r12
0x1800534b7  push    r13
0x1800534b9  push    r14
0x1800534bb  push    r15
0x1800534bd  lea     rbp, [rsp-7B8h]
0x1800534c5  sub     rsp, 8B8h
0x1800534cc  mov     rax, cs:__security_cookie
0x1800534d3  xor     rax, rsp
0x1800534d6  mov     [rbp+7F0h+var_50], rax
0x1800534dd  mov     r12, r9
0x1800534e0  mov     [rbp+7F0h+var_868], r9
0x1800534e4  mov     [rsp+8F0h+var_880], r8
0x1800534e9  mov     r13, rdx
0x1800534ec  mov     [rsp+8F0h+var_8A0], rdx
0x1800534f1  mov     rdi, rcx
0x1800534f4  mov     rax, [rbp+7F0h+arg_20]
0x1800534fb  mov     [rbp+7F0h+var_860], rax
0x1800534ff  xor     edx, edx; Val
0x180053501  mov     r8d, 800h; Size
0x180053507  lea     rcx, [rbp+7F0h+Buffer]; void *
0x18005350b  call    memset_0
0x180053510  mov     rbx, [r13+0]
0x180053514  test    rbx, rbx
0x180053517  jz      short loc_180053543
0x180053519  mov     rax, [rbx+8]
0x18005351d  test    rax, rax
0x180053520  jnz     short loc_180053545
0x180053522  mov     rcx, [rbx]; lpWideCharStr
0x180053525  call    ?ConvertBSTRToString@_com_util@@YAPEADPEAG@Z; _com_util::ConvertBSTRToString(ushort *)
0x18005352a  mov     [rbx+8], rax
0x18005352e  test    rax, rax
0x180053531  jnz     short loc_180053545
0x180053533  cmp     [rbx], rax
0x180053536  jz      short loc_180053543
0x180053538  mov     ecx, 8007000Eh; int
0x18005353d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180053543  xor     eax, eax
0x180053545  mov     r9, rax
0x180053548  lea     r8, ?m_msgDictionaryQuery@CIASMigrationHelper@@1QBGB; "/Root/User_Message_Dictionary/Property_"...
0x18005354f  mov     edx, 400h; BufferCount
0x180053554  lea     rcx, [rbp+7F0h+Buffer]; Buffer
0x180053558  call    cs:__imp_swprintf_s
0x18005355e  mov     rcx, rdi
0x180053561  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180053566  lea     rdx, [rsp+8F0h+var_888]
0x18005356b  mov     rcx, rax; struct IUnknown *
0x18005356e  call    ?GetdocumentElement@IXMLDOMDocument@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMDocument::GetdocumentElement(void)
0x180053573  nop
0x180053574  mov     rcx, rax
0x180053577  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18005357c  mov     rbx, rax
0x18005357f  lea     rdx, [rbp+7F0h+Buffer]; unsigned __int16 *
0x180053583  lea     rcx, [rsp+8F0h+var_8C0]; this
0x180053588  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18005358d  mov     r8, rax
0x180053590  lea     rdx, [rsp+8F0h+var_878]
0x180053595  mov     rcx, rbx; struct IUnknown *
0x180053598  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18005359d  nop
0x18005359e  lea     rcx, [rsp+8F0h+var_888]
0x1800535a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800535a8  mov     rsi, [rsp+8F0h+var_878]
0x1800535ad  test    rsi, rsi
0x1800535b0  jnz     short loc_1800535BB
0x1800535b2  mov     [r12], esi
0x1800535b6  jmp     loc_180053BA5
0x1800535bb  xor     r14d, r14d
0x1800535be  mov     [rsp+8F0h+var_898], r14
0x1800535c3  xor     edi, edi
0x1800535c5  mov     [rsp+8F0h+var_890], rdi
0x1800535ca  lea     rcx, [rsp+8F0h+var_878]
0x1800535cf  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x1800535d4  mov     rbx, rax
0x1800535d7  lea     rdx, ?m_valMessageQuery@CIASMigrationHelper@@1QBGB; "./Value_Message"
0x1800535de  lea     rcx, [rsp+8F0h+var_8C0]; this
0x1800535e3  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800535e8  mov     r8, rax
0x1800535eb  lea     rdx, [rsp+8F0h+var_888]
0x1800535f0  mov     rcx, rbx; struct IUnknown *
0x1800535f3  call    ?selectNodes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectNodes(_bstr_t)
0x1800535f8  nop
0x1800535f9  mov     r15, [rsp+8F0h+var_888]
0x1800535fe  test    r15, r15
0x180053601  jnz     short loc_18005361D
0x180053603  mov     rax, [rsi]
0x180053606  mov     rcx, rsi
0x180053609  mov     rax, [rax+10h]
0x18005360d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053612  nop
0x180053613  mov     eax, 8000FFFFh
0x180053618  jmp     loc_180053BA7
0x18005361d  lea     rcx, [rsp+8F0h+var_888]
0x180053622  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180053627  lea     rdx, [rsp+8F0h+var_8B0]
0x18005362c  mov     rcx, rax; struct IUnknown *
0x18005362f  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x180053634  nop
0x180053635  mov     rbx, [rsp+8F0h+var_8B0]
0x18005363a  test    rbx, rbx
0x18005363d  jnz     loc_18005370E
0x180053643  lea     rcx, [rsp+8F0h+var_878]
0x180053648  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18005364d  mov     r12, rax
0x180053650  lea     rdx, ?m_messageQuery@CIASMigrationHelper@@1QBGB; "./Message"
0x180053657  lea     rcx, [rsp+8F0h+var_8A0]; this
0x18005365c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180053661  mov     r8, rax
0x180053664  lea     rdx, [rsp+8F0h+var_8C0]
0x180053669  mov     rcx, r12; struct IUnknown *
0x18005366c  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x180053671  nop
0x180053672  cmp     [rax], rbx
0x180053675  jz      short loc_18005368A
0x180053677  mov     r14, [rax]
0x18005367a  mov     [rsp+8F0h+var_898], r14
0x18005367f  lea     rcx, [rsp+8F0h+var_898]
0x180053684  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x180053689  nop
0x18005368a  mov     rcx, [rsp+8F0h+var_8C0]
0x18005368f  test    rcx, rcx
0x180053692  jz      short loc_1800536A1
0x180053694  mov     rax, [rcx]
0x180053697  mov     rax, [rax+10h]
0x18005369b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536a0  nop
0x1800536a1  lea     rcx, [rsp+8F0h+var_878]
0x1800536a6  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x1800536ab  mov     r12, rax
0x1800536ae  lea     rdx, ?m_parameterQuery@CIASMigrationHelper@@1QBGB; "./Parameter"
0x1800536b5  lea     rcx, [rsp+8F0h+var_8A0]; this
0x1800536ba  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800536bf  mov     r8, rax
0x1800536c2  lea     rdx, [rsp+8F0h+var_8C0]
0x1800536c7  mov     rcx, r12; struct IUnknown *
0x1800536ca  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x1800536cf  nop
0x1800536d0  cmp     qword ptr [rax], 0
0x1800536d4  jz      short loc_1800536E9
0x1800536d6  mov     rdi, [rax]
0x1800536d9  mov     [rsp+8F0h+var_890], rdi
0x1800536de  lea     rcx, [rsp+8F0h+var_890]
0x1800536e3  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x1800536e8  nop
0x1800536e9  mov     rcx, [rsp+8F0h+var_8C0]
0x1800536ee  test    rcx, rcx
0x1800536f1  jz      short loc_180053700
0x1800536f3  mov     rax, [rcx]
0x1800536f6  mov     rax, [rax+10h]
0x1800536fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536ff  nop
0x180053700  jmp     loc_1800538FF
0x180053705  test    rbx, rbx
0x180053708  jz      loc_1800538FA
0x18005370e  lea     rcx, [rsp+8F0h+var_8B0]
0x180053713  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180053718  mov     r12, rax
0x18005371b  lea     rdx, ?m_propValueQuery@CIASMigrationHelper@@1QBGB; "./Value"
0x180053722  lea     rcx, [rbp+7F0h+var_870]; this
0x180053726  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18005372b  mov     r8, rax
0x18005372e  lea     rdx, [rsp+8F0h+var_8C0]
0x180053733  mov     rcx, r12; struct IUnknown *
0x180053736  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18005373b  nop
0x18005373c  mov     r12, [rsp+8F0h+var_8C0]
0x180053741  test    r12, r12
0x180053744  jz      loc_1800539AB
0x18005374a  mov     [rsp+8F0h+var_8A8], 0
0x180053753  lea     rdx, [rsp+8F0h+var_8A8]
0x180053758  lea     rcx, [rsp+8F0h+var_8C0]
0x18005375d  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x180053762  mov     r13d, eax
0x180053765  test    eax, eax
0x180053767  js      loc_180053957
0x18005376d  mov     rax, [rsp+8F0h+var_880]
0x180053772  mov     rax, [rax]
0x180053775  test    rax, rax
0x180053778  jz      short loc_18005377F
0x18005377a  mov     rdx, [rax]
0x18005377d  jmp     short loc_180053781
0x18005377f  xor     edx, edx; lpString2
0x180053781  mov     rax, [rsp+8F0h+var_8A8]
0x180053786  test    rax, rax
0x180053789  jz      short loc_180053790
0x18005378b  mov     rcx, [rax]
0x18005378e  jmp     short loc_180053792
0x180053790  xor     ecx, ecx; lpString1
0x180053792  call    cs:__imp_lstrcmpW
0x180053798  test    eax, eax
0x18005379a  jz      loc_180053820
0x1800537a0  lea     rcx, [rsp+8F0h+var_888]
0x1800537a5  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x1800537aa  lea     rdx, [rsp+8F0h+var_8B8]
0x1800537af  mov     rcx, rax; struct IUnknown *
0x1800537b2  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x1800537b7  nop
0x1800537b8  cmp     rbx, [rax]
0x1800537bb  jz      short loc_1800537E8
0x1800537bd  mov     r13, rbx
0x1800537c0  mov     rbx, [rax]
0x1800537c3  mov     [rsp+8F0h+var_8B0], rbx
0x1800537c8  lea     rcx, [rsp+8F0h+var_8B0]
0x1800537cd  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x1800537d2  test    r13, r13
0x1800537d5  jz      short loc_1800537E8
0x1800537d7  mov     rax, [r13+0]
0x1800537db  mov     rcx, r13
0x1800537de  mov     rax, [rax+10h]
0x1800537e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537e7  nop
0x1800537e8  mov     rcx, [rsp+8F0h+var_8B8]
0x1800537ed  test    rcx, rcx
0x1800537f0  jz      short loc_1800537FF
0x1800537f2  mov     rax, [rcx]
0x1800537f5  mov     rax, [rax+10h]
0x1800537f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537fe  nop
0x1800537ff  lea     rcx, [rsp+8F0h+var_8A8]; this
0x180053804  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180053809  nop
0x18005380a  mov     rax, [r12]
0x18005380e  mov     rcx, r12
0x180053811  mov     rax, [rax+10h]
0x180053815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005381a  nop
0x18005381b  jmp     loc_180053705
0x180053820  lea     rcx, [rsp+8F0h+var_8B0]
0x180053825  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18005382a  mov     r13, rax
0x18005382d  lea     rdx, ?m_messageQuery@CIASMigrationHelper@@1QBGB; "./Message"
0x180053834  lea     rcx, [rsp+8F0h+var_8B8]; this
0x180053839  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18005383e  mov     r8, rax
0x180053841  lea     rdx, [rsp+8F0h+var_880]
0x180053846  mov     rcx, r13; struct IUnknown *
0x180053849  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18005384e  nop
0x18005384f  cmp     qword ptr [rax], 0
0x180053853  jz      short loc_180053868
0x180053855  mov     r14, [rax]
0x180053858  mov     [rsp+8F0h+var_898], r14
0x18005385d  lea     rcx, [rsp+8F0h+var_898]
0x180053862  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x180053867  nop
0x180053868  mov     rcx, [rsp+8F0h+var_880]
0x18005386d  test    rcx, rcx
0x180053870  jz      short loc_18005387F
0x180053872  mov     rax, [rcx]
0x180053875  mov     rax, [rax+10h]
0x180053879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005387e  nop
0x18005387f  lea     rcx, [rsp+8F0h+var_8B0]
0x180053884  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180053889  mov     r13, rax
0x18005388c  lea     rdx, ?m_parameterQuery@CIASMigrationHelper@@1QBGB; "./Parameter"
0x180053893  lea     rcx, [rsp+8F0h+var_8B8]; this
0x180053898  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18005389d  mov     r8, rax
0x1800538a0  lea     rdx, [rsp+8F0h+var_880]
0x1800538a5  mov     rcx, r13; struct IUnknown *
0x1800538a8  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x1800538ad  nop
0x1800538ae  cmp     qword ptr [rax], 0
0x1800538b2  jz      short loc_1800538C7
0x1800538b4  mov     rdi, [rax]
0x1800538b7  mov     [rsp+8F0h+var_890], rdi
0x1800538bc  lea     rcx, [rsp+8F0h+var_890]
0x1800538c1  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x1800538c6  nop
0x1800538c7  mov     rcx, [rsp+8F0h+var_880]
0x1800538cc  test    rcx, rcx
0x1800538cf  jz      short loc_1800538DE
0x1800538d1  mov     rax, [rcx]
0x1800538d4  mov     rax, [rax+10h]
0x1800538d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538dd  nop
0x1800538de  lea     rcx, [rsp+8F0h+var_8A8]; this
0x1800538e3  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800538e8  nop
0x1800538e9  mov     rax, [r12]
0x1800538ed  mov     rcx, r12
0x1800538f0  mov     rax, [rax+10h]
0x1800538f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538f9  nop
0x1800538fa  mov     r13, [rsp+8F0h+var_8A0]
0x1800538ff  test    r14, r14
0x180053902  jnz     loc_1800539E0
0x180053908  test    rbx, rbx
0x18005390b  jz      short loc_18005391D
0x18005390d  mov     rax, [rbx]
0x180053910  mov     rcx, rbx
0x180053913  mov     rax, [rax+10h]
0x180053917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005391c  nop
0x18005391d  mov     rax, [r15]
0x180053920  mov     rcx, r15
  ... truncated ...
```
