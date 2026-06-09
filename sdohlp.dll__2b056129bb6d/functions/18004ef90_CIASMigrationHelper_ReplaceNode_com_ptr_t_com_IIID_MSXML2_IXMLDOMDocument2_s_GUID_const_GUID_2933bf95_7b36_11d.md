# CIASMigrationHelper::ReplaceNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)

- ea: `0x18004ef90`
- end: `0x18004f2c5`
- name: `?ReplaceNode@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `821`
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
- `0x18004ef90`
- `0x180050044`
- `0x1800521d4`
- `0x180052588`
- `0x180058010`

## string_xrefs

- `0x18004efd7`: `./Path`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CIASMigrationHelper::ReplaceNode(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rsi
  __int64 v7; // r14
  struct IUnknown *v8; // r15
  __int64 *v9; // rax
  __int64 v10; // r12
  __int64 v11; // r15
  bool v12; // zf
  int StringValueFromNode; // r12d
  struct IUnknown *v15; // rax
  __int64 v16; // r15
  __int64 *v17; // rax
  struct IUnknown *v18; // rax
  __int64 *v19; // rax
  struct IUnknown *v20; // rax
  __int64 *v21; // rax
  struct IUnknown *v22; // rax
  __int64 v23; // r15
  __int64 v24; // [rsp+20h] [rbp-40h] BYREF
  __int64 v25; // [rsp+28h] [rbp-38h] BYREF
  __int64 v26; // [rsp+30h] [rbp-30h] BYREF
  __int64 v27; // [rsp+38h] [rbp-28h] BYREF
  __int64 v28; // [rsp+40h] [rbp-20h] BYREF
  __int64 v29; // [rsp+48h] [rbp-18h]
  __int64 v31; // [rsp+B8h] [rbp+58h] BYREF

  v4 = 0;
  v24 = 0;
  v5 = 0;
  v25 = 0;
  v6 = 0;
  v28 = 0;
  v7 = 0;
  v26 = 0;
  v31 = 0;
  v8 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  _bstr_t::_bstr_t((_bstr_t *)&v27, L"./Path");
  v9 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v8);
  v10 = *v9;
  if ( *v9 )
  {
    v4 = *v9;
    v24 = *v9;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v24);
    v11 = v10;
  }
  else
  {
    v11 = 0;
  }
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( !v10 )
  {
    _bstr_t::_Free((_bstr_t *)&v31);
    v12 = v11 == 0;
LABEL_39:
    if ( !v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return 2147549183LL;
  }
  StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v24, &v31);
  if ( StringValueFromNode < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v31);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return (unsigned int)StringValueFromNode;
  }
  v15 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
  v16 = v31;
  v27 = v31;
  if ( v31 )
    _InterlockedIncrement((volatile signed __int32 *)(v31 + 16));
  v17 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v15);
  if ( *v17 )
  {
    v5 = *v17;
    v25 = *v17;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v25);
  }
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( !v5 )
  {
    _bstr_t::_Free((_bstr_t *)&v31);
LABEL_38:
    v12 = v4 == 0;
    goto LABEL_39;
  }
  v18 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a2);
  v27 = v16;
  if ( v16 )
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 16));
  v19 = (__int64 *)MSXML2::IXMLDOMNode::selectSingleNode(v18);
  if ( *v19 )
  {
    v6 = *v19;
    v28 = *v19;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v28);
  }
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( !v6 )
  {
    _bstr_t::_Free((_bstr_t *)&v31);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    goto LABEL_38;
  }
  v20 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v25);
  v21 = (__int64 *)MSXML2::IXMLDOMNode::GetparentNode(v20);
  if ( *v21 )
  {
    v7 = *v21;
    v26 = *v21;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v26);
  }
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( !v7 )
  {
    _bstr_t::_Free((_bstr_t *)&v31);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    goto LABEL_38;
  }
  v22 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v26);
  v23 = *(_QWORD *)MSXML2::IXMLDOMNode::replaceChild(v22);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  _bstr_t::_Free((_bstr_t *)&v31);
  if ( !v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    goto LABEL_38;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x18004ef90  mov     [rsp-38h+arg_0], rbx
0x18004ef95  mov     [rsp-38h+arg_8], rdx
0x18004ef9a  push    rbp
0x18004ef9b  push    rsi
0x18004ef9c  push    rdi
0x18004ef9d  push    r12
0x18004ef9f  push    r13
0x18004efa1  push    r14
0x18004efa3  push    r15
0x18004efa5  mov     rbp, rsp
0x18004efa8  sub     rsp, 60h
0x18004efac  mov     r13, rcx
0x18004efaf  xor     ebx, ebx
0x18004efb1  mov     [rbp+var_40], rbx
0x18004efb5  xor     edi, edi
0x18004efb7  mov     [rbp+var_38], rdi
0x18004efbb  xor     esi, esi
0x18004efbd  mov     [rbp+var_20], rsi
0x18004efc1  xor     r14d, r14d
0x18004efc4  mov     [rbp+var_30], r14
0x18004efc8  mov     [rbp+arg_18], r14
0x18004efcc  mov     rcx, r8
0x18004efcf  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004efd4  mov     r15, rax
0x18004efd7  lea     rdx, ?m_migPathQuery@CIASMigrationHelper@@1QBGB; "./Path"
0x18004efde  lea     rcx, [rbp+var_28]; this
0x18004efe2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004efe7  mov     r8, rax
0x18004efea  lea     rdx, [rbp+var_18]
0x18004efee  mov     rcx, r15; struct IUnknown *
0x18004eff1  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004eff6  mov     r12, [rax]
0x18004eff9  test    r12, r12
0x18004effc  jz      short loc_18004F013
0x18004effe  mov     rbx, r12
0x18004f001  mov     [rbp+var_40], rbx
0x18004f005  lea     rcx, [rbp+var_40]
0x18004f009  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004f00e  mov     r15, r12
0x18004f011  jmp     short loc_18004F016
0x18004f013  xor     r15d, r15d
0x18004f016  mov     rcx, [rbp+var_18]
0x18004f01a  test    rcx, rcx
0x18004f01d  jz      short loc_18004F02C
0x18004f01f  mov     rax, [rcx]
0x18004f022  mov     rax, [rax+10h]
0x18004f026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f02b  nop
0x18004f02c  test    r12, r12
0x18004f02f  jnz     short loc_18004F043
0x18004f031  lea     rcx, [rbp+arg_18]; this
0x18004f035  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004f03a  nop
0x18004f03b  test    r15, r15
0x18004f03e  jmp     loc_18004F24D
0x18004f043  lea     rdx, [rbp+arg_18]
0x18004f047  lea     rcx, [rbp+var_40]
0x18004f04b  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004f050  mov     r12d, eax
0x18004f053  test    eax, eax
0x18004f055  jns     short loc_18004F07E
0x18004f057  lea     rcx, [rbp+arg_18]; this
0x18004f05b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004f060  nop
0x18004f061  test    r15, r15
0x18004f064  jz      short loc_18004F076
0x18004f066  mov     rax, [rbx]
0x18004f069  mov     rcx, rbx
0x18004f06c  mov     rax, [rax+10h]
0x18004f070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f075  nop
0x18004f076  mov     eax, r12d
0x18004f079  jmp     loc_18004F2AD
0x18004f07e  mov     rcx, r13
0x18004f081  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004f086  mov     r15, [rbp+arg_18]
0x18004f08a  mov     [rbp+var_28], r15
0x18004f08e  xor     r12d, r12d
0x18004f091  test    r15, r15
0x18004f094  jz      short loc_18004F09B
0x18004f096  lock inc dword ptr [r15+10h]
0x18004f09b  lea     r8, [rbp+var_28]
0x18004f09f  lea     rdx, [rbp+var_18]
0x18004f0a3  mov     rcx, rax; struct IUnknown *
0x18004f0a6  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004f0ab  nop
0x18004f0ac  cmp     [rax], r12
0x18004f0af  jz      short loc_18004F0C2
0x18004f0b1  mov     rdi, [rax]
0x18004f0b4  mov     [rbp+var_38], rdi
0x18004f0b8  lea     rcx, [rbp+var_38]
0x18004f0bc  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004f0c1  nop
0x18004f0c2  mov     rcx, [rbp+var_18]
0x18004f0c6  test    rcx, rcx
0x18004f0c9  jz      short loc_18004F0D8
0x18004f0cb  mov     rax, [rcx]
0x18004f0ce  mov     rax, [rax+10h]
0x18004f0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f0d7  nop
0x18004f0d8  test    rdi, rdi
0x18004f0db  jnz     short loc_18004F0EC
0x18004f0dd  lea     rcx, [rbp+arg_18]; this
0x18004f0e1  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004f0e6  nop
0x18004f0e7  jmp     loc_18004F24A
0x18004f0ec  mov     rcx, [rbp+arg_8]
0x18004f0f0  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004f0f5  mov     [rbp+var_28], r15
0x18004f0f9  test    r15, r15
0x18004f0fc  jz      short loc_18004F103
0x18004f0fe  lock inc dword ptr [r15+10h]
0x18004f103  lea     r8, [rbp+var_28]
0x18004f107  lea     rdx, [rbp+var_18]
0x18004f10b  mov     rcx, rax; struct IUnknown *
0x18004f10e  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004f113  nop
0x18004f114  cmp     [rax], r12
0x18004f117  jz      short loc_18004F12A
0x18004f119  mov     rsi, [rax]
0x18004f11c  mov     [rbp+var_20], rsi
0x18004f120  lea     rcx, [rbp+var_20]
0x18004f124  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004f129  nop
0x18004f12a  mov     rcx, [rbp+var_18]
0x18004f12e  test    rcx, rcx
0x18004f131  jz      short loc_18004F140
0x18004f133  mov     rax, [rcx]
0x18004f136  mov     rax, [rax+10h]
0x18004f13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f13f  nop
0x18004f140  test    rsi, rsi
0x18004f143  jnz     short loc_18004F164
0x18004f145  lea     rcx, [rbp+arg_18]; this
0x18004f149  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004f14e  nop
0x18004f14f  mov     rax, [rdi]
0x18004f152  mov     rcx, rdi
0x18004f155  mov     rax, [rax+10h]
0x18004f159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f15e  nop
0x18004f15f  jmp     loc_18004F24A
0x18004f164  lea     rcx, [rbp+var_38]
0x18004f168  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004f16d  lea     rdx, [rbp+var_18]
0x18004f171  mov     rcx, rax; struct IUnknown *
0x18004f174  call    ?GetparentNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNode::GetparentNode(void)
0x18004f179  nop
0x18004f17a  cmp     [rax], r12
0x18004f17d  jz      short loc_18004F190
0x18004f17f  mov     r14, [rax]
0x18004f182  mov     [rbp+var_30], r14
0x18004f186  lea     rcx, [rbp+var_30]
0x18004f18a  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004f18f  nop
0x18004f190  mov     rcx, [rbp+var_18]
0x18004f194  test    rcx, rcx
0x18004f197  jz      short loc_18004F1A6
0x18004f199  mov     rax, [rcx]
0x18004f19c  mov     rax, [rax+10h]
0x18004f1a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1a5  nop
0x18004f1a6  test    r14, r14
0x18004f1a9  jnz     short loc_18004F1D7
0x18004f1ab  lea     rcx, [rbp+arg_18]; this
0x18004f1af  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004f1b4  nop
0x18004f1b5  mov     rax, [rsi]
0x18004f1b8  mov     rcx, rsi
0x18004f1bb  mov     rax, [rax+10h]
0x18004f1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1c4  nop
0x18004f1c5  mov     rax, [rdi]
0x18004f1c8  mov     rcx, rdi
0x18004f1cb  mov     rax, [rax+10h]
0x18004f1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1d4  nop
0x18004f1d5  jmp     short loc_18004F24A
0x18004f1d7  lea     rcx, [rbp+var_30]
0x18004f1db  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004f1e0  mov     r9, rdi
0x18004f1e3  mov     r8, rsi
0x18004f1e6  lea     rdx, [rbp+var_18]
0x18004f1ea  mov     rcx, rax; struct IUnknown *
0x18004f1ed  call    ?replaceChild@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEAU12@0@Z; MSXML2::IXMLDOMNode::replaceChild(MSXML2::IXMLDOMNode *,MSXML2::IXMLDOMNode *)
0x18004f1f2  mov     r15, [rax]
0x18004f1f5  mov     rcx, [rbp+var_18]
0x18004f1f9  test    rcx, rcx
0x18004f1fc  jz      short loc_18004F20B
0x18004f1fe  mov     rax, [rcx]
0x18004f201  mov     rax, [rax+10h]
0x18004f205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f20a  nop
0x18004f20b  lea     rcx, [rbp+arg_18]; this
0x18004f20f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004f214  nop
0x18004f215  test    r15, r15
0x18004f218  jnz     short loc_18004F266
0x18004f21a  mov     rax, [r14]
0x18004f21d  mov     rcx, r14
0x18004f220  mov     rax, [rax+10h]
0x18004f224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f229  nop
0x18004f22a  mov     rax, [rsi]
0x18004f22d  mov     rcx, rsi
0x18004f230  mov     rax, [rax+10h]
0x18004f234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f239  nop
0x18004f23a  mov     rax, [rdi]
0x18004f23d  mov     rcx, rdi
0x18004f240  mov     rax, [rax+10h]
0x18004f244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f249  nop
0x18004f24a  test    rbx, rbx
0x18004f24d  jz      short loc_18004F25F
0x18004f24f  mov     rax, [rbx]
0x18004f252  mov     rcx, rbx
0x18004f255  mov     rax, [rax+10h]
0x18004f259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f25e  nop
0x18004f25f  mov     eax, 8000FFFFh
0x18004f264  jmp     short loc_18004F2AD
0x18004f266  mov     rax, [r14]
0x18004f269  mov     rcx, r14
0x18004f26c  mov     rax, [rax+10h]
0x18004f270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f275  nop
0x18004f276  mov     rax, [rsi]
0x18004f279  mov     rcx, rsi
0x18004f27c  mov     rax, [rax+10h]
0x18004f280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f285  nop
0x18004f286  mov     rax, [rdi]
0x18004f289  mov     rcx, rdi
0x18004f28c  mov     rax, [rax+10h]
0x18004f290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f295  nop
0x18004f296  test    rbx, rbx
0x18004f299  jz      short loc_18004F2AB
0x18004f29b  mov     rax, [rbx]
0x18004f29e  mov     rcx, rbx
0x18004f2a1  mov     rax, [rax+10h]
0x18004f2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2aa  nop
0x18004f2ab  xor     eax, eax
0x18004f2ad  mov     rbx, [rsp+60h+arg_0]
0x18004f2b5  add     rsp, 60h
0x18004f2b9  pop     r15
0x18004f2bb  pop     r14
0x18004f2bd  pop     r13
0x18004f2bf  pop     r12
0x18004f2c1  pop     rdi
0x18004f2c2  pop     rsi
0x18004f2c3  pop     rbp
0x18004f2c4  retn
```
