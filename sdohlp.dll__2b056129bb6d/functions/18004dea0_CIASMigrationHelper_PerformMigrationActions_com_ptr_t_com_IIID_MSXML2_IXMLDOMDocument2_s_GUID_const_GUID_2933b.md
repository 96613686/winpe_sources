# CIASMigrationHelper::PerformMigrationActions(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)

- ea: `0x18004dea0`
- end: `0x18004e166`
- name: `?PerformMigrationActions@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `710`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004c16c`

## callees

- `0x18002d08c`
- `0x18002efa0`
- `0x180047604`
- `0x180049164`
- `0x18004d11c`
- `0x18004d190`
- `0x18004dea0`
- `0x180050044`
- `0x180051e7c`
- `0x180052588`
- `0x180058010`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CIASMigrationHelper::PerformMigrationActions(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rbx
  struct IUnknown *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rsi
  struct IUnknown *v10; // rax
  __int64 *Node; // rax
  __int64 v12; // rdi
  struct IUnknown *v13; // rdi
  _bstr_t *v14; // rax
  __int64 v15; // rdi
  const struct IasFunctionTableItem near *const *i; // rsi
  struct IUnknown *v17; // rax
  __int64 *v18; // rax
  __int64 v19; // rsi
  __int64 v20; // [rsp+20h] [rbp-38h] BYREF
  __int64 v21; // [rsp+28h] [rbp-30h] BYREF
  __int64 v22; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v23[8]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v24; // [rsp+40h] [rbp-18h]
  __int64 v25; // [rsp+A8h] [rbp+50h] BYREF

  v5 = 0;
  v21 = 0;
  v25 = 0;
  v6 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  v7 = *(_QWORD *)MSXML2::IXMLDOMNode::GetchildNodes(v6);
  v8 = 0;
  if ( v7 )
  {
    v5 = v7;
    v21 = v7;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v21);
    v8 = v7;
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v8 )
  {
    v10 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v21);
    Node = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v10);
    v12 = v25;
    if ( v25 != *Node )
    {
      v25 = *Node;
      _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v25);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v25 )
    {
      while ( 1 )
      {
        v20 = 0;
        v13 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v25);
        v14 = _bstr_t::_bstr_t((_bstr_t *)v23, L"./Handler");
        MSXML2::IXMLDOMNode::selectSingleNode(v13, &v22, v14);
        v15 = v22;
        if ( !v22 )
          break;
        if ( (int)CIASMigrationHelper::GetStringValueFromNode(&v22, (__int64)&v20) < 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          _bstr_t::_Free((_bstr_t *)&v20);
          if ( v25 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          goto LABEL_38;
        }
        for ( i = &CIASMigrationHelper::m_migActionFunctionTable; *((_QWORD *)i + 1); i += 2 )
        {
          if ( (unsigned __int8)_bstr_t::operator==(&v20, i) )
          {
            if ( (*((int (__fastcall **)(__int64, __int64, __int64 *))i + 1))(a1, a2, &v25) < 0 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
              _bstr_t::_Free((_bstr_t *)&v20);
              if ( v25 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
              goto LABEL_38;
            }
            break;
          }
        }
        v17 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v21);
        v18 = (__int64 *)MSXML2::IXMLDOMNodeList::nextNode(v17);
        v19 = v25;
        if ( v25 != *v18 )
        {
          v25 = *v18;
          _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v25);
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        _bstr_t::_Free((_bstr_t *)&v20);
        if ( !v25 )
        {
          if ( v5 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          return 0;
        }
      }
      _bstr_t::_Free((_bstr_t *)&v20);
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
LABEL_38:
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  else if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18004dea0  push    rbp
0x18004dea2  push    rbx
0x18004dea3  push    rsi
0x18004dea4  push    rdi
0x18004dea5  push    r14
0x18004dea7  push    r15
0x18004dea9  mov     rbp, rsp
0x18004deac  sub     rsp, 58h
0x18004deb0  mov     r14, rdx
0x18004deb3  mov     r15, rcx
0x18004deb6  xor     ebx, ebx
0x18004deb8  mov     [rbp+var_30], rbx
0x18004debc  mov     [rbp+arg_18], rbx
0x18004dec0  mov     rcx, r8
0x18004dec3  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004dec8  lea     rdx, [rbp+var_28]
0x18004decc  mov     rcx, rax; struct IUnknown *
0x18004decf  call    ?GetchildNodes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNode::GetchildNodes(void)
0x18004ded4  mov     rdi, [rax]
0x18004ded7  xor     esi, esi
0x18004ded9  test    rdi, rdi
0x18004dedc  jz      short loc_18004DEF1
0x18004dede  mov     rbx, rdi
0x18004dee1  mov     [rbp+var_30], rbx
0x18004dee5  lea     rcx, [rbp+var_30]
0x18004dee9  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004deee  mov     rsi, rdi
0x18004def1  mov     rcx, [rbp+var_28]
0x18004def5  test    rcx, rcx
0x18004def8  jz      short loc_18004DF07
0x18004defa  mov     rax, [rcx]
0x18004defd  mov     rax, [rax+10h]
0x18004df01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df06  nop
0x18004df07  test    rsi, rsi
0x18004df0a  jnz     short loc_18004DF2C
0x18004df0c  mov     rcx, [rbp+arg_18]
0x18004df10  test    rcx, rcx
0x18004df13  jz      short loc_18004DF22
0x18004df15  mov     rax, [rcx]
0x18004df18  mov     rax, [rax+10h]
0x18004df1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df21  nop
0x18004df22  mov     eax, 8000FFFFh
0x18004df27  jmp     loc_18004E159
0x18004df2c  lea     rcx, [rbp+var_30]
0x18004df30  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004df35  lea     rdx, [rbp+var_28]
0x18004df39  mov     rcx, rax; struct IUnknown *
0x18004df3c  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x18004df41  mov     rcx, [rax]
0x18004df44  mov     rdi, [rbp+arg_18]
0x18004df48  cmp     rdi, rcx
0x18004df4b  jz      short loc_18004DF6F
0x18004df4d  mov     [rbp+arg_18], rcx
0x18004df51  lea     rcx, [rbp+arg_18]
0x18004df55  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004df5a  test    rdi, rdi
0x18004df5d  jz      short loc_18004DF6F
0x18004df5f  mov     rax, [rdi]
0x18004df62  mov     rcx, rdi
0x18004df65  mov     rax, [rax+10h]
0x18004df69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df6e  nop
0x18004df6f  mov     rcx, [rbp+var_28]
0x18004df73  test    rcx, rcx
0x18004df76  jz      short loc_18004DF85
0x18004df78  mov     rax, [rcx]
0x18004df7b  mov     rax, [rax+10h]
0x18004df7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df84  nop
0x18004df85  cmp     [rbp+arg_18], 0
0x18004df8a  jnz     short loc_18004DF9C
0x18004df8c  jmp     loc_18004E128
0x18004df91  cmp     [rbp+arg_18], 0
0x18004df96  jz      loc_18004E142
0x18004df9c  mov     [rbp+var_38], 0
0x18004dfa4  lea     rcx, [rbp+arg_18]
0x18004dfa8  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004dfad  mov     rdi, rax
0x18004dfb0  lea     rdx, ?m_migActionHandlerQuery@CIASMigrationHelper@@1QBGB; "./Handler"
0x18004dfb7  lea     rcx, [rbp+var_20]; this
0x18004dfbb  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004dfc0  mov     r8, rax
0x18004dfc3  lea     rdx, [rbp+var_28]
0x18004dfc7  mov     rcx, rdi; struct IUnknown *
0x18004dfca  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004dfcf  nop
0x18004dfd0  mov     rdi, [rbp+var_28]
0x18004dfd4  test    rdi, rdi
0x18004dfd7  jz      loc_18004E108
0x18004dfdd  lea     rdx, [rbp+var_38]
0x18004dfe1  lea     rcx, [rbp+var_28]
0x18004dfe5  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004dfea  test    eax, eax
0x18004dfec  js      loc_18004E0D6
0x18004dff2  lea     rsi, ?m_migActionFunctionTable@CIASMigrationHelper@@1QBUIasFunctionTableItem@@B; IasFunctionTableItem const near * const CIASMigrationHelper::m_migActionFunctionTable
0x18004dff9  cmp     qword ptr [rsi+8], 0
0x18004dffe  jz      short loc_18004E02D
0x18004e000  mov     rdx, rsi
0x18004e003  lea     rcx, [rbp+var_38]
0x18004e007  call    ??8_bstr_t@@QEBA_NAEBV0@@Z; _bstr_t::operator==(_bstr_t const &)
0x18004e00c  test    al, al
0x18004e00e  jnz     short loc_18004E016
0x18004e010  add     rsi, 10h
0x18004e014  jmp     short loc_18004DFF9
0x18004e016  lea     r8, [rbp+arg_18]
0x18004e01a  mov     rdx, r14
0x18004e01d  mov     rcx, r15
0x18004e020  mov     rax, [rsi+8]
0x18004e024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e029  test    eax, eax
0x18004e02b  js      short loc_18004E0A4
0x18004e02d  lea     rcx, [rbp+var_30]
0x18004e031  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e036  lea     rdx, [rbp+var_18]
0x18004e03a  mov     rcx, rax; struct IUnknown *
0x18004e03d  call    ?nextNode@IXMLDOMNodeList@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNodeList::nextNode(void)
0x18004e042  mov     rcx, [rax]
0x18004e045  mov     rsi, [rbp+arg_18]
0x18004e049  cmp     rsi, rcx
0x18004e04c  jz      short loc_18004E070
0x18004e04e  mov     [rbp+arg_18], rcx
0x18004e052  lea     rcx, [rbp+arg_18]
0x18004e056  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004e05b  test    rsi, rsi
0x18004e05e  jz      short loc_18004E070
0x18004e060  mov     rax, [rsi]
0x18004e063  mov     rcx, rsi
0x18004e066  mov     rax, [rax+10h]
0x18004e06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e06f  nop
0x18004e070  mov     rcx, [rbp+var_18]
0x18004e074  test    rcx, rcx
0x18004e077  jz      short loc_18004E086
0x18004e079  mov     rax, [rcx]
0x18004e07c  mov     rax, [rax+10h]
0x18004e080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e085  nop
0x18004e086  mov     rax, [rdi]
0x18004e089  mov     rcx, rdi
0x18004e08c  mov     rax, [rax+10h]
0x18004e090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e095  nop
0x18004e096  lea     rcx, [rbp+var_38]; this
0x18004e09a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e09f  jmp     loc_18004DF91
0x18004e0a4  mov     rax, [rdi]
0x18004e0a7  mov     rcx, rdi
0x18004e0aa  mov     rax, [rax+10h]
0x18004e0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0b3  nop
0x18004e0b4  lea     rcx, [rbp+var_38]; this
0x18004e0b8  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e0bd  nop
0x18004e0be  mov     rcx, [rbp+arg_18]
0x18004e0c2  test    rcx, rcx
0x18004e0c5  jz      short loc_18004E0D4
0x18004e0c7  mov     rax, [rcx]
0x18004e0ca  mov     rax, [rax+10h]
0x18004e0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0d3  nop
0x18004e0d4  jmp     short loc_18004E128
0x18004e0d6  mov     rax, [rdi]
0x18004e0d9  mov     rcx, rdi
0x18004e0dc  mov     rax, [rax+10h]
0x18004e0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0e5  nop
0x18004e0e6  lea     rcx, [rbp+var_38]; this
0x18004e0ea  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e0ef  nop
0x18004e0f0  mov     rcx, [rbp+arg_18]
0x18004e0f4  test    rcx, rcx
0x18004e0f7  jz      short loc_18004E106
0x18004e0f9  mov     rax, [rcx]
0x18004e0fc  mov     rax, [rax+10h]
0x18004e100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e105  nop
0x18004e106  jmp     short loc_18004E128
0x18004e108  lea     rcx, [rbp+var_38]; this
0x18004e10c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e111  nop
0x18004e112  mov     rcx, [rbp+arg_18]
0x18004e116  test    rcx, rcx
0x18004e119  jz      short loc_18004E128
0x18004e11b  mov     rax, [rcx]
0x18004e11e  mov     rax, [rax+10h]
0x18004e122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e127  nop
0x18004e128  test    rbx, rbx
0x18004e12b  jz      short loc_18004E13D
0x18004e12d  mov     rax, [rbx]
0x18004e130  mov     rcx, rbx
0x18004e133  mov     rax, [rax+10h]
0x18004e137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e13c  nop
0x18004e13d  jmp     loc_18004DF22
0x18004e142  test    rbx, rbx
0x18004e145  jz      short loc_18004E157
0x18004e147  mov     rax, [rbx]
0x18004e14a  mov     rcx, rbx
0x18004e14d  mov     rax, [rax+10h]
0x18004e151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e156  nop
0x18004e157  xor     eax, eax
0x18004e159  add     rsp, 58h
0x18004e15d  pop     r15
0x18004e15f  pop     r14
0x18004e161  pop     rdi
0x18004e162  pop     rsi
0x18004e163  pop     rbx
0x18004e164  pop     rbp
0x18004e165  retn
```
