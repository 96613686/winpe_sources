# CIASMigrationHelper::FindOnePropertyInXML(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,int,ulong)

- ea: `0x18004c8d0`
- end: `0x18004cdeb`
- name: `?FindOnePropertyInXML@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@1HK@Z`
- size: `1307`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004f2cc`

## callees

- `0x18002cd00`
- `0x18002d08c`
- `0x18002efa0`
- `0x180042a80`
- `0x180047604`
- `0x180049164`
- `0x18004c8d0`
- `0x18004d11c`
- `0x18004d190`
- `0x180050044`
- `0x180051e7c`
- `0x180052588`
- `0x180058010`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CIASMigrationHelper::FindOnePropertyInXML(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 *a4,
        int a5,
        int a6)
{
  __int64 *v6; // rsi
  __int64 v7; // r14
  __int64 v8; // r12
  struct IUnknown *v9; // rbx
  __int64 v10; // rdi
  char v12; // r13
  const struct IasIdentifyFunction near *const *i; // r15
  __int64 v14; // rbx
  __int64 v15; // rsi
  struct IUnknown *v16; // r14
  __int64 *v17; // rax
  __int64 v18; // r14
  __int64 v19; // r12
  struct IUnknown *v20; // rax
  __int64 *v21; // rax
  struct IUnknown *v22; // rax
  __int64 *Node; // rax
  __int64 v24; // r14
  int v25; // r14d
  struct IUnknown *v26; // rax
  __int64 *v27; // rax
  __int64 v28; // r14
  __int64 v29; // [rsp+48h] [rbp-59h] BYREF
  __int64 v30; // [rsp+50h] [rbp-51h] BYREF
  __int64 v31; // [rsp+58h] [rbp-49h] BYREF
  __int64 v32; // [rsp+60h] [rbp-41h] BYREF
  __int64 v33; // [rsp+68h] [rbp-39h] BYREF
  __int64 v34; // [rsp+70h] [rbp-31h]
  _BYTE v35[8]; // [rsp+78h] [rbp-29h] BYREF
  _BYTE v36[8]; // [rsp+80h] [rbp-21h] BYREF
  __int64 v37; // [rsp+88h] [rbp-19h]
  __int64 v38; // [rsp+90h] [rbp-11h]
  __int64 v39; // [rsp+98h] [rbp-9h]

  v6 = a4;
  v7 = a2;
  v8 = a1;
  v30 = 0;
  v9 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a4);
  _bstr_t::_bstr_t((_bstr_t *)v35, L"./Handler");
  MSXML2::IXMLDOMNode::selectSingleNode(v9);
  v10 = v33;
  if ( !v33 )
    goto LABEL_2;
  if ( (int)CIASMigrationHelper::GetStringValueFromNode(&v33, &v30) < 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
LABEL_2:
    _bstr_t::_Free((_bstr_t *)&v30);
    return 2147549183LL;
  }
  v12 = 0;
  for ( i = &CIASMigrationHelper::m_identifyFunctionTable; ; i += 3 )
  {
    if ( !*((_QWORD *)i + 1) || v12 )
      goto LABEL_68;
    if ( (unsigned __int8)_bstr_t::operator==(&v30, i) )
      break;
LABEL_40:
    ;
  }
  v12 = 1;
  if ( a5 )
  {
    v14 = 0;
    v32 = 0;
    v15 = 0;
    v31 = 0;
    v29 = 0;
    v16 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
    _bstr_t::_bstr_t((_bstr_t *)v36, L"./Children");
    v17 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v16);
    v18 = *v17;
    if ( *v17 )
    {
      v14 = *v17;
      v32 = *v17;
      _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v32);
      v19 = v18;
    }
    else
    {
      v19 = 0;
    }
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( !v18 )
    {
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v25 = -2147418113;
      goto LABEL_69;
    }
    v20 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v32);
    v21 = (__int64 *)MSXML2::IXMLDOMNode::GetchildNodes(v20);
    if ( *v21 )
    {
      v15 = *v21;
      v31 = *v21;
      _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v31);
    }
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( !v15 )
    {
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      goto LABEL_68;
    }
    v22 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v31);
    Node = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v22);
    v24 = v29;
    if ( v29 != *Node )
    {
      v29 = *Node;
      _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v29);
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    if ( !v29 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_68:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v25 = 0;
      goto LABEL_69;
    }
    while ( v29 )
    {
      v25 = (*((__int64 (__fastcall **)(__int64, __int64, __int64 *, __int64 *, _QWORD, int))i + 1))(
              a1,
              a2,
              &v29,
              a4,
              *((_QWORD *)i + 2),
              a6);
      if ( v25 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("handler failed: %!hresult!");
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            (unsigned int)WPP_35f0385197fd35cdb48f774109abba17_Traceguids,
            (unsigned int)"NPSDS",
            v25);
        }
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        goto LABEL_49;
      }
      v26 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v31);
      v27 = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v26);
      v28 = v29;
      if ( v29 != *v27 )
      {
        v29 = *v27;
        _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v29);
        if ( v28 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v6 = a4;
    v8 = a1;
    goto LABEL_39;
  }
  v25 = (*((__int64 (__fastcall **)(__int64, __int64, __int64 *, __int64 *, _QWORD, int))i + 1))(
          v8,
          v7,
          a3,
          v6,
          *((_QWORD *)i + 2),
          a6);
  if ( v25 >= 0 )
  {
LABEL_39:
    v7 = a2;
    goto LABEL_40;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("handler failed: %!hresult!");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)WPP_35f0385197fd35cdb48f774109abba17_Traceguids,
      (unsigned int)"NPSDS",
      v25);
  }
LABEL_49:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
LABEL_69:
  _bstr_t::_Free((_bstr_t *)&v30);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x18004c8d0  mov     rax, rsp
0x18004c8d3  mov     [rax+20h], r9
0x18004c8d7  mov     [rax+18h], r8
0x18004c8db  mov     [rax+10h], rdx
0x18004c8df  mov     [rax+8], rcx
0x18004c8e3  push    rbp
0x18004c8e4  push    rbx
0x18004c8e5  push    rsi
0x18004c8e6  push    rdi
0x18004c8e7  push    r12
0x18004c8e9  push    r13
0x18004c8eb  push    r14
0x18004c8ed  push    r15
0x18004c8ef  lea     rbp, [rax-4Fh]
0x18004c8f3  sub     rsp, 0A8h
0x18004c8fa  mov     rsi, r9
0x18004c8fd  mov     r14, rdx
0x18004c900  mov     r12, rcx
0x18004c903  mov     [rbp+47h+var_98], 0
0x18004c90b  mov     rcx, r9
0x18004c90e  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004c913  mov     rbx, rax
0x18004c916  lea     rdx, ?m_migActionHandlerQuery@CIASMigrationHelper@@1QBGB; "./Handler"
0x18004c91d  lea     rcx, [rbp+47h+var_70]; this
0x18004c921  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004c926  mov     r8, rax
0x18004c929  lea     rdx, [rbp+47h+var_80]
0x18004c92d  mov     rcx, rbx; struct IUnknown *
0x18004c930  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004c935  nop
0x18004c936  mov     rdi, [rbp+47h+var_80]
0x18004c93a  test    rdi, rdi
0x18004c93d  jnz     short loc_18004C952
0x18004c93f  lea     rcx, [rbp+47h+var_98]; this
0x18004c943  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004c948  mov     eax, 8000FFFFh
0x18004c94d  jmp     loc_18004CDD7
0x18004c952  lea     rdx, [rbp+47h+var_98]
0x18004c956  lea     rcx, [rbp+47h+var_80]
0x18004c95a  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004c95f  test    eax, eax
0x18004c961  jns     short loc_18004C975
0x18004c963  mov     rax, [rdi]
0x18004c966  mov     rcx, rdi
0x18004c969  mov     rax, [rax+10h]
0x18004c96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c972  nop
0x18004c973  jmp     short loc_18004C93F
0x18004c975  xor     r13b, r13b
0x18004c978  lea     r15, ?m_identifyFunctionTable@CIASMigrationHelper@@1QBUIasIdentifyFunction@@B; IasIdentifyFunction const near * const CIASMigrationHelper::m_identifyFunctionTable
0x18004c97f  cmp     qword ptr [r15+8], 0
0x18004c984  jz      loc_18004CDB8
0x18004c98a  test    r13b, r13b
0x18004c98d  jnz     loc_18004CDB8
0x18004c993  mov     rdx, r15
0x18004c996  lea     rcx, [rbp+47h+var_98]
0x18004c99a  call    ??8_bstr_t@@QEBA_NAEBV0@@Z; _bstr_t::operator==(_bstr_t const &)
0x18004c99f  test    al, al
0x18004c9a1  jz      loc_18004CBE2
0x18004c9a7  mov     r13b, 1
0x18004c9aa  cmp     [rbp+47h+arg_20], 0
0x18004c9ae  jz      loc_18004CBAD
0x18004c9b4  xor     ebx, ebx
0x18004c9b6  mov     [rbp+47h+var_88], rbx
0x18004c9ba  xor     esi, esi
0x18004c9bc  mov     [rbp+47h+var_90], rsi
0x18004c9c0  mov     [rbp+47h+var_A0], rsi
0x18004c9c4  mov     rcx, [rbp+47h+arg_10]
0x18004c9c8  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004c9cd  mov     r14, rax
0x18004c9d0  lea     rdx, ?m_migChildrenQuery@CIASMigrationHelper@@1QBGB; "./Children"
0x18004c9d7  lea     rcx, [rbp+47h+var_68]; this
0x18004c9db  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004c9e0  mov     r8, rax
0x18004c9e3  lea     rdx, [rbp+47h+var_60]
0x18004c9e7  mov     rcx, r14; struct IUnknown *
0x18004c9ea  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004c9ef  mov     r14, [rax]
0x18004c9f2  test    r14, r14
0x18004c9f5  jz      short loc_18004CA0C
0x18004c9f7  mov     rbx, r14
0x18004c9fa  mov     [rbp+47h+var_88], rbx
0x18004c9fe  lea     rcx, [rbp+47h+var_88]
0x18004ca02  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004ca07  mov     r12, r14
0x18004ca0a  jmp     short loc_18004CA0F
0x18004ca0c  xor     r12d, r12d
0x18004ca0f  mov     rcx, [rbp+47h+var_60]
0x18004ca13  test    rcx, rcx
0x18004ca16  jz      short loc_18004CA25
0x18004ca18  mov     rax, [rcx]
0x18004ca1b  mov     rax, [rax+10h]
0x18004ca1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca24  nop
0x18004ca25  test    r14, r14
0x18004ca28  jz      loc_18004CD0C
0x18004ca2e  lea     rcx, [rbp+47h+var_88]
0x18004ca32  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004ca37  lea     rdx, [rbp+47h+var_58]
0x18004ca3b  mov     rcx, rax; struct IUnknown *
0x18004ca3e  call    ?GetchildNodes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNode::GetchildNodes(void)
0x18004ca43  nop
0x18004ca44  cmp     qword ptr [rax], 0
0x18004ca48  jz      short loc_18004CA5B
0x18004ca4a  mov     rsi, [rax]
0x18004ca4d  mov     [rbp+47h+var_90], rsi
0x18004ca51  lea     rcx, [rbp+47h+var_90]
0x18004ca55  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004ca5a  nop
0x18004ca5b  mov     rcx, [rbp+47h+var_58]
0x18004ca5f  test    rcx, rcx
0x18004ca62  jz      short loc_18004CA71
0x18004ca64  mov     rax, [rcx]
0x18004ca67  mov     rax, [rax+10h]
0x18004ca6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca70  nop
0x18004ca71  test    rsi, rsi
0x18004ca74  jz      loc_18004CCCC
0x18004ca7a  lea     rcx, [rbp+47h+var_90]
0x18004ca7e  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004ca83  lea     rdx, [rbp+47h+var_50]
0x18004ca87  mov     rcx, rax; struct IUnknown *
0x18004ca8a  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x18004ca8f  mov     rcx, [rax]
0x18004ca92  mov     r14, [rbp+47h+var_A0]
0x18004ca96  cmp     r14, rcx
0x18004ca99  jz      short loc_18004CABD
0x18004ca9b  mov     [rbp+47h+var_A0], rcx
0x18004ca9f  lea     rcx, [rbp+47h+var_A0]
0x18004caa3  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004caa8  test    r14, r14
0x18004caab  jz      short loc_18004CABD
0x18004caad  mov     rax, [r14]
0x18004cab0  mov     rcx, r14
0x18004cab3  mov     rax, [rax+10h]
0x18004cab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cabc  nop
0x18004cabd  mov     rcx, [rbp+47h+var_50]
0x18004cac1  test    rcx, rcx
0x18004cac4  jz      short loc_18004CAD3
0x18004cac6  mov     rax, [rcx]
0x18004cac9  mov     rax, [rax+10h]
0x18004cacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cad2  nop
0x18004cad3  cmp     [rbp+47h+var_A0], 0
0x18004cad8  jz      loc_18004CC92
0x18004cade  mov     r12, [rbp+47h+arg_18]
0x18004cae2  cmp     [rbp+47h+var_A0], 0
0x18004cae7  jz      loc_18004CB7E
0x18004caed  mov     eax, [rbp+47h+arg_28]
0x18004caf0  mov     [rsp+28h], eax
0x18004caf4  mov     rcx, [r15+10h]
0x18004caf8  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x18004cafd  mov     r9, r12
0x18004cb00  lea     r8, [rbp+47h+var_A0]
0x18004cb04  mov     rdx, [rbp+47h+arg_8]
0x18004cb08  mov     rcx, [rbp+47h+arg_0]
0x18004cb0c  mov     rax, [r15+8]
0x18004cb10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb15  mov     r14d, eax
0x18004cb18  test    eax, eax
0x18004cb1a  js      loc_18004CBEB
0x18004cb20  lea     rcx, [rbp+47h+var_90]
0x18004cb24  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004cb29  lea     rdx, [rbp+47h+var_78]
0x18004cb2d  mov     rcx, rax; struct IUnknown *
0x18004cb30  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x18004cb35  mov     rcx, [rax]
0x18004cb38  mov     r14, [rbp+47h+var_A0]
0x18004cb3c  cmp     r14, rcx
0x18004cb3f  jz      short loc_18004CB63
0x18004cb41  mov     [rbp+47h+var_A0], rcx
0x18004cb45  lea     rcx, [rbp+47h+var_A0]
0x18004cb49  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004cb4e  test    r14, r14
0x18004cb51  jz      short loc_18004CB63
0x18004cb53  mov     rax, [r14]
0x18004cb56  mov     rcx, r14
0x18004cb59  mov     rax, [rax+10h]
0x18004cb5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb62  nop
0x18004cb63  mov     rcx, [rbp+47h+var_78]
0x18004cb67  test    rcx, rcx
0x18004cb6a  jz      short loc_18004CB79
0x18004cb6c  mov     rax, [rcx]
0x18004cb6f  mov     rax, [rax+10h]
0x18004cb73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb78  nop
0x18004cb79  jmp     loc_18004CAE2
0x18004cb7e  mov     rax, [rsi]
0x18004cb81  mov     rcx, rsi
0x18004cb84  mov     rax, [rax+10h]
0x18004cb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb8d  nop
0x18004cb8e  test    rbx, rbx
0x18004cb91  jz      short loc_18004CBA3
0x18004cb93  mov     rax, [rbx]
0x18004cb96  mov     rcx, rbx
0x18004cb99  mov     rax, [rax+10h]
0x18004cb9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cba2  nop
0x18004cba3  mov     rsi, [rbp+47h+arg_18]
0x18004cba7  mov     r12, [rbp+47h+arg_0]
0x18004cbab  jmp     short loc_18004CBDE
0x18004cbad  mov     eax, [rbp+47h+arg_28]
0x18004cbb0  mov     [rsp+28h], eax
0x18004cbb4  mov     rcx, [r15+10h]
0x18004cbb8  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x18004cbbd  mov     r9, rsi
0x18004cbc0  mov     r8, [rbp+47h+arg_10]
0x18004cbc4  mov     rdx, r14
0x18004cbc7  mov     rcx, r12
0x18004cbca  mov     rax, [r15+8]
0x18004cbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbd3  mov     r14d, eax
0x18004cbd6  test    eax, eax
0x18004cbd8  js      loc_18004CD4F
0x18004cbde  mov     r14, [rbp+47h+arg_8]
0x18004cbe2  add     r15, 18h
0x18004cbe6  jmp     loc_18004C97F
0x18004cbeb  lea     rcx, WPP_GLOBAL_Control
0x18004cbf2  mov     rax, cs:WPP_GLOBAL_Control
0x18004cbf9  cmp     rax, rcx
0x18004cbfc  jz      short loc_18004CC42
0x18004cbfe  cmp     byte ptr [rax+19h], 2
0x18004cc02  jb      short loc_18004CC42
0x18004cc04  test    byte ptr [rax+1Ch], 10h
0x18004cc08  jz      short loc_18004CC42
0x18004cc0a  mov     edx, r14d
0x18004cc0d  lea     rcx, aHandlerFailedH; "handler failed: %!hresult!"
0x18004cc14  call    WppDbgPrint
0x18004cc19  mov     edx, 11h
0x18004cc1e  mov     [rsp+0E0h+var_C0], r14d
0x18004cc23  lea     r9, aNpsds; "NPSDS"
0x18004cc2a  lea     r8, WPP_35f0385197fd35cdb48f774109abba17_Traceguids
0x18004cc31  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cc38  mov     rcx, [rcx+10h]
0x18004cc3c  call    WPP_SF_sd
0x18004cc41  nop
0x18004cc42  mov     rcx, [rbp+47h+var_A0]
0x18004cc46  test    rcx, rcx
0x18004cc49  jz      short loc_18004CC58
0x18004cc4b  mov     rax, [rcx]
0x18004cc4e  mov     rax, [rax+10h]
0x18004cc52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc57  nop
0x18004cc58  mov     rax, [rsi]
0x18004cc5b  mov     rcx, rsi
0x18004cc5e  mov     rax, [rax+10h]
0x18004cc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc67  nop
0x18004cc68  test    rbx, rbx
0x18004cc6b  jz      short loc_18004CC7D
0x18004cc6d  mov     rax, [rbx]
0x18004cc70  mov     rcx, rbx
0x18004cc73  mov     rax, [rax+10h]
0x18004cc77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc7c  nop
0x18004cc7d  mov     rax, [rdi]
0x18004cc80  mov     rcx, rdi
0x18004cc83  mov     rax, [rax+10h]
0x18004cc87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc8c  nop
0x18004cc8d  jmp     loc_18004CDCB
0x18004cc92  mov     rax, [rsi]
0x18004cc95  mov     rcx, rsi
0x18004cc98  mov     rax, [rax+10h]
0x18004cc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cca1  nop
0x18004cca2  test    rbx, rbx
0x18004cca5  jz      short loc_18004CCB7
0x18004cca7  mov     rax, [rbx]
0x18004ccaa  mov     rcx, rbx
0x18004ccad  mov     rax, [rax+10h]
0x18004ccb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ccb6  nop
0x18004ccb7  mov     rax, [rdi]
0x18004ccba  mov     rcx, rdi
0x18004ccbd  mov     rax, [rax+10h]
0x18004ccc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ccc6  nop
0x18004ccc7  jmp     loc_18004CDC8
0x18004cccc  mov     rcx, [rbp+47h+var_A0]
0x18004ccd0  test    rcx, rcx
0x18004ccd3  jz      short loc_18004CCE2
0x18004ccd5  mov     rax, [rcx]
0x18004ccd8  mov     rax, [rax+10h]
0x18004ccdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cce1  nop
0x18004cce2  test    rbx, rbx
0x18004cce5  jz      short loc_18004CCF7
0x18004cce7  mov     rax, [rbx]
0x18004ccea  mov     rcx, rbx
0x18004cced  mov     rax, [rax+10h]
0x18004ccf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ccf6  nop
0x18004ccf7  mov     rax, [rdi]
0x18004ccfa  mov     rcx, rdi
0x18004ccfd  mov     rax, [rax+10h]
0x18004cd01  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
