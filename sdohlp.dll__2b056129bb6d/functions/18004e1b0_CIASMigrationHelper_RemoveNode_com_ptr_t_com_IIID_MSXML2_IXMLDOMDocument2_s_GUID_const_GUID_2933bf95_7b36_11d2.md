# CIASMigrationHelper::RemoveNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)

- ea: `0x18004e1b0`
- end: `0x18004e428`
- name: `?RemoveNode@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `632`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002d08c`
- `0x18002efa0`
- `0x180047604`
- `0x18004d11c`
- `0x18004d314`
- `0x18004e1b0`
- `0x180050044`
- `0x18005216c`
- `0x180052588`
- `0x180058010`

## string_xrefs

- `0x18004e1ed`: `./Path`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CIASMigrationHelper::RemoveNode(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rsi
  struct IUnknown *v7; // r14
  __int64 *v8; // rax
  __int64 v9; // r14
  __int64 v10; // r15
  int StringValueFromNode; // r14d
  struct IUnknown *v13; // rax
  __int64 *v14; // rax
  struct IUnknown *v15; // rax
  __int64 *v16; // rax
  struct IUnknown *v17; // rax
  __int64 v18; // r14
  __int64 v19; // [rsp+20h] [rbp-30h] BYREF
  __int64 v20; // [rsp+28h] [rbp-28h] BYREF
  __int64 v21; // [rsp+30h] [rbp-20h] BYREF
  __int64 v22; // [rsp+38h] [rbp-18h] BYREF
  __int64 v23; // [rsp+40h] [rbp-10h]
  __int64 v24; // [rsp+98h] [rbp+48h] BYREF

  v4 = 0;
  v19 = 0;
  v5 = 0;
  v20 = 0;
  v6 = 0;
  v21 = 0;
  v24 = 0;
  v7 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&v22, L"./Path");
  v8 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v7);
  v9 = *v8;
  v10 = 0;
  if ( *v8 )
  {
    v4 = *v8;
    v19 = *v8;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v19);
    v10 = v9;
  }
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( !v10 )
  {
    _bstr_t::_Free((_bstr_t *)&v24);
    return 2147549183LL;
  }
  StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v19, &v24);
  if ( StringValueFromNode < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v24);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return (unsigned int)StringValueFromNode;
  }
  v13 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
  v22 = v24;
  if ( v24 )
    _InterlockedIncrement((volatile signed __int32 *)(v24 + 16));
  v14 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v13);
  if ( *v14 )
  {
    v5 = *v14;
    v20 = *v14;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v20);
  }
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v5 )
  {
    v15 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v20);
    v16 = (__int64 *)MSXML2::IXMLDOMNode::GetparentNode(v15);
    if ( *v16 )
    {
      v6 = *v16;
      v21 = *v16;
      _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v21);
    }
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v6 )
    {
      v17 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v21);
      v18 = *(_QWORD *)MSXML2::IXMLDOMNode::removeChild(v17);
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      _bstr_t::_Free((_bstr_t *)&v24);
      if ( v18 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        goto LABEL_32;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    else
    {
      _bstr_t::_Free((_bstr_t *)&v24);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return 2147549183LL;
  }
  _bstr_t::_Free((_bstr_t *)&v24);
LABEL_32:
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x18004e1b0  mov     [rsp-28h+arg_0], rbx
0x18004e1b5  mov     [rsp-28h+arg_8], rsi
0x18004e1ba  push    rbp
0x18004e1bb  push    rdi
0x18004e1bc  push    r12
0x18004e1be  push    r14
0x18004e1c0  push    r15
0x18004e1c2  mov     rbp, rsp
0x18004e1c5  sub     rsp, 50h
0x18004e1c9  mov     r12, rcx
0x18004e1cc  xor     ebx, ebx
0x18004e1ce  mov     [rbp+var_30], rbx
0x18004e1d2  xor     edi, edi
0x18004e1d4  mov     [rbp+var_28], rdi
0x18004e1d8  xor     esi, esi
0x18004e1da  mov     [rbp+var_20], rsi
0x18004e1de  mov     [rbp+arg_18], rsi
0x18004e1e2  mov     rcx, r8
0x18004e1e5  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e1ea  mov     r14, rax
0x18004e1ed  lea     rdx, ?m_migPathQuery@CIASMigrationHelper@@1QBGB; "./Path"
0x18004e1f4  lea     rcx, [rbp+var_18]; this
0x18004e1f8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004e1fd  mov     r8, rax
0x18004e200  lea     rdx, [rbp+var_10]
0x18004e204  mov     rcx, r14; struct IUnknown *
0x18004e207  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004e20c  mov     r14, [rax]
0x18004e20f  xor     r15d, r15d
0x18004e212  test    r14, r14
0x18004e215  jz      short loc_18004E22A
0x18004e217  mov     rbx, r14
0x18004e21a  mov     [rbp+var_30], rbx
0x18004e21e  lea     rcx, [rbp+var_30]
0x18004e222  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004e227  mov     r15, r14
0x18004e22a  mov     rcx, [rbp+var_10]
0x18004e22e  test    rcx, rcx
0x18004e231  jz      short loc_18004E240
0x18004e233  mov     rax, [rcx]
0x18004e236  mov     rax, [rax+10h]
0x18004e23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e23f  nop
0x18004e240  test    r15, r15
0x18004e243  jnz     short loc_18004E259
0x18004e245  lea     rcx, [rbp+arg_18]; this
0x18004e249  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e24e  nop
0x18004e24f  mov     eax, 8000FFFFh
0x18004e254  jmp     loc_18004E40F
0x18004e259  lea     rdx, [rbp+arg_18]
0x18004e25d  lea     rcx, [rbp+var_30]
0x18004e261  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004e266  mov     r14d, eax
0x18004e269  test    eax, eax
0x18004e26b  jns     short loc_18004E28F
0x18004e26d  lea     rcx, [rbp+arg_18]; this
0x18004e271  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e276  nop
0x18004e277  mov     rax, [rbx]
0x18004e27a  mov     rcx, rbx
0x18004e27d  mov     rax, [rax+10h]
0x18004e281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e286  nop
0x18004e287  mov     eax, r14d
0x18004e28a  jmp     loc_18004E40F
0x18004e28f  mov     rcx, r12
0x18004e292  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e297  mov     rcx, [rbp+arg_18]
0x18004e29b  mov     [rbp+var_18], rcx
0x18004e29f  test    rcx, rcx
0x18004e2a2  jz      short loc_18004E2A8
0x18004e2a4  lock inc dword ptr [rcx+10h]
0x18004e2a8  lea     r8, [rbp+var_18]
0x18004e2ac  lea     rdx, [rbp+var_10]
0x18004e2b0  mov     rcx, rax; struct IUnknown *
0x18004e2b3  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004e2b8  nop
0x18004e2b9  cmp     qword ptr [rax], 0
0x18004e2bd  jz      short loc_18004E2D0
0x18004e2bf  mov     rdi, [rax]
0x18004e2c2  mov     [rbp+var_28], rdi
0x18004e2c6  lea     rcx, [rbp+var_28]
0x18004e2ca  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004e2cf  nop
0x18004e2d0  mov     rcx, [rbp+var_10]
0x18004e2d4  test    rcx, rcx
0x18004e2d7  jz      short loc_18004E2E6
0x18004e2d9  mov     rax, [rcx]
0x18004e2dc  mov     rax, [rax+10h]
0x18004e2e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2e5  nop
0x18004e2e6  test    rdi, rdi
0x18004e2e9  jnz     short loc_18004E2FA
0x18004e2eb  lea     rcx, [rbp+arg_18]; this
0x18004e2ef  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e2f4  nop
0x18004e2f5  jmp     loc_18004E3F8
0x18004e2fa  lea     rcx, [rbp+var_28]
0x18004e2fe  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e303  lea     rdx, [rbp+var_10]
0x18004e307  mov     rcx, rax; struct IUnknown *
0x18004e30a  call    ?GetparentNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNode::GetparentNode(void)
0x18004e30f  nop
0x18004e310  cmp     qword ptr [rax], 0
0x18004e314  jz      short loc_18004E327
0x18004e316  mov     rsi, [rax]
0x18004e319  mov     [rbp+var_20], rsi
0x18004e31d  lea     rcx, [rbp+var_20]
0x18004e321  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004e326  nop
0x18004e327  mov     rcx, [rbp+var_10]
0x18004e32b  test    rcx, rcx
0x18004e32e  jz      short loc_18004E33D
0x18004e330  mov     rax, [rcx]
0x18004e333  mov     rax, [rax+10h]
0x18004e337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e33c  nop
0x18004e33d  test    rsi, rsi
0x18004e340  jnz     short loc_18004E35E
0x18004e342  lea     rcx, [rbp+arg_18]; this
0x18004e346  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e34b  nop
0x18004e34c  mov     rax, [rdi]
0x18004e34f  mov     rcx, rdi
0x18004e352  mov     rax, [rax+10h]
0x18004e356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e35b  nop
0x18004e35c  jmp     short loc_18004E3BE
0x18004e35e  lea     rcx, [rbp+var_20]
0x18004e362  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e367  mov     r8, rdi
0x18004e36a  lea     rdx, [rbp+var_10]
0x18004e36e  mov     rcx, rax; struct IUnknown *
0x18004e371  call    ?removeChild@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEAU12@@Z; MSXML2::IXMLDOMNode::removeChild(MSXML2::IXMLDOMNode *)
0x18004e376  mov     r14, [rax]
0x18004e379  mov     rcx, [rbp+var_10]
0x18004e37d  test    rcx, rcx
0x18004e380  jz      short loc_18004E38F
0x18004e382  mov     rax, [rcx]
0x18004e385  mov     rax, [rax+10h]
0x18004e389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e38e  nop
0x18004e38f  lea     rcx, [rbp+arg_18]; this
0x18004e393  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004e398  nop
0x18004e399  test    r14, r14
0x18004e39c  jnz     short loc_18004E3D8
0x18004e39e  mov     rax, [rsi]
0x18004e3a1  mov     rcx, rsi
0x18004e3a4  mov     rax, [rax+10h]
0x18004e3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3ad  nop
0x18004e3ae  mov     rax, [rdi]
0x18004e3b1  mov     rcx, rdi
0x18004e3b4  mov     rax, [rax+10h]
0x18004e3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3bd  nop
0x18004e3be  test    rbx, rbx
0x18004e3c1  jz      short loc_18004E3D3
0x18004e3c3  mov     rax, [rbx]
0x18004e3c6  mov     rcx, rbx
0x18004e3c9  mov     rax, [rax+10h]
0x18004e3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3d2  nop
0x18004e3d3  jmp     loc_18004E24F
0x18004e3d8  mov     rax, [rsi]
0x18004e3db  mov     rcx, rsi
0x18004e3de  mov     rax, [rax+10h]
0x18004e3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3e7  nop
0x18004e3e8  mov     rax, [rdi]
0x18004e3eb  mov     rcx, rdi
0x18004e3ee  mov     rax, [rax+10h]
0x18004e3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3f7  nop
0x18004e3f8  test    rbx, rbx
0x18004e3fb  jz      short loc_18004E40D
0x18004e3fd  mov     rax, [rbx]
0x18004e400  mov     rcx, rbx
0x18004e403  mov     rax, [rax+10h]
0x18004e407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e40c  nop
0x18004e40d  xor     eax, eax
0x18004e40f  lea     r11, [rsp+50h+var_s0]
0x18004e414  mov     rbx, [r11+30h]
0x18004e418  mov     rsi, [r11+38h]
0x18004e41c  mov     rsp, r11
0x18004e41f  pop     r15
0x18004e421  pop     r14
0x18004e423  pop     r12
0x18004e425  pop     rdi
0x18004e426  pop     rbp
0x18004e427  retn
```
