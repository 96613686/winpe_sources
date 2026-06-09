# CIASMigrationHelper::FindAnyValue(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,long (*)(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,CompareOperator,int &,_bstr_t &),ulong)

- ea: `0x18004c610`
- end: `0x18004c8c9`
- name: `?FindAnyValue@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@1P6AJ11W4CompareOperator@@AEAHAEAV_bstr_t@@@ZK@Z`
- size: `697`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002cd00`
- `0x18002d08c`
- `0x18002efa0`
- `0x180042a80`
- `0x180047604`
- `0x180048acc`
- `0x18004c610`
- `0x18004d11c`
- `0x180050044`
- `0x180052588`
- `0x180052d80`
- `0x180058010`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CIASMigrationHelper::FindAnyValue(__int64 a1, __int64 a2, __int64 *a3, __int64 *a4, int a5, int a6)
{
  __int64 v9; // rbx
  struct IUnknown *v10; // rdi
  _bstr_t *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rsi
  int StringValueFromNode; // edi
  struct IUnknown *v16; // rdi
  _bstr_t *v17; // rax
  __int64 v18; // rdi
  struct IUnknown *v19; // rax
  __int64 v20; // rsi
  int v21; // r14d
  LPCWCH *v22; // [rsp+30h] [rbp-30h] BYREF
  __int64 v23; // [rsp+38h] [rbp-28h] BYREF
  const WCHAR **v24; // [rsp+40h] [rbp-20h] BYREF
  __int64 v25; // [rsp+48h] [rbp-18h] BYREF
  LPCWCH *v26; // [rsp+50h] [rbp-10h] BYREF
  __int64 v27; // [rsp+58h] [rbp-8h] BYREF

  v9 = 0;
  v23 = 0;
  v22 = 0;
  v10 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a4);
  v11 = _bstr_t::_bstr_t((_bstr_t *)&v26, L"./Name");
  v12 = *MSXML2::IXMLDOMNode::selectSingleNode(v10, &v25, v11);
  v13 = 0;
  if ( v12 )
  {
    v9 = v12;
    v23 = v12;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v23);
    v13 = v12;
  }
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( !v13 )
  {
    _bstr_t::_Free((_bstr_t *)&v22);
    return 2147549183LL;
  }
  StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v23, (__int64)&v22);
  if ( StringValueFromNode < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v22);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    return (unsigned int)StringValueFromNode;
  }
  v16 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  v17 = _bstr_t::_bstr_t((_bstr_t *)&v24, L"./Properties");
  MSXML2::IXMLDOMNode::selectSingleNode(v16, &v25, v17);
  v18 = v25;
  if ( !v25 )
  {
    _bstr_t::_Free((_bstr_t *)&v22);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    return 2147549183LL;
  }
  v19 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v25);
  v26 = v22;
  if ( v22 )
    _InterlockedIncrement((volatile signed __int32 *)v22 + 4);
  MSXML2::IXMLDOMNode::selectSingleNode(v19, &v27, (_bstr_t *)&v26);
  v20 = v27;
  if ( !v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    _bstr_t::_Free((_bstr_t *)&v22);
LABEL_27:
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    return 0;
  }
  _bstr_t::_bstr_t((_bstr_t *)&v24, qword_180063E98);
  v21 = CIasMigErrorHelper::AddError(a2, a4, a3, a6, &v22, &v24);
  if ( v21 >= 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v24);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    _bstr_t::_Free((_bstr_t *)&v22);
    goto LABEL_27;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("AddError() failed: %!hresult!");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_35f0385197fd35cdb48f774109abba17_Traceguids,
      (unsigned int)"NPSDS",
      v21);
  }
  _bstr_t::_Free((_bstr_t *)&v24);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  _bstr_t::_Free((_bstr_t *)&v22);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18004c610  push    rbp
0x18004c612  push    rbx
0x18004c613  push    rsi
0x18004c614  push    rdi
0x18004c615  push    r12
0x18004c617  push    r14
0x18004c619  push    r15
0x18004c61b  mov     rbp, rsp
0x18004c61e  sub     rsp, 60h
0x18004c622  mov     r15, r9
0x18004c625  mov     r14, r8
0x18004c628  mov     r12, rdx
0x18004c62b  xor     ebx, ebx
0x18004c62d  mov     [rbp+var_28], rbx
0x18004c631  mov     [rbp+var_30], rbx
0x18004c635  mov     rcx, r9
0x18004c638  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004c63d  mov     rdi, rax
0x18004c640  lea     rdx, ?m_migNameQuery@CIASMigrationHelper@@1QBGB; "./Name"
0x18004c647  lea     rcx, [rbp+var_10]; this
0x18004c64b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004c650  mov     r8, rax
0x18004c653  lea     rdx, [rbp+var_18]
0x18004c657  mov     rcx, rdi; struct IUnknown *
0x18004c65a  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004c65f  mov     rdi, [rax]
0x18004c662  xor     esi, esi
0x18004c664  test    rdi, rdi
0x18004c667  jz      short loc_18004C67C
0x18004c669  mov     rbx, rdi
0x18004c66c  mov     [rbp+var_28], rbx
0x18004c670  lea     rcx, [rbp+var_28]
0x18004c674  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004c679  mov     rsi, rdi
0x18004c67c  mov     rcx, [rbp+var_18]
0x18004c680  test    rcx, rcx
0x18004c683  jz      short loc_18004C692
0x18004c685  mov     rax, [rcx]
0x18004c688  mov     rax, [rax+10h]
0x18004c68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c691  nop
0x18004c692  test    rsi, rsi
0x18004c695  jnz     short loc_18004C6AB
0x18004c697  lea     rcx, [rbp+var_30]; this
0x18004c69b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004c6a0  nop
0x18004c6a1  mov     eax, 8000FFFFh
0x18004c6a6  jmp     loc_18004C8BA
0x18004c6ab  lea     rdx, [rbp+var_30]
0x18004c6af  lea     rcx, [rbp+var_28]
0x18004c6b3  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x18004c6b8  mov     edi, eax
0x18004c6ba  test    eax, eax
0x18004c6bc  jns     short loc_18004C6DF
0x18004c6be  lea     rcx, [rbp+var_30]; this
0x18004c6c2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004c6c7  nop
0x18004c6c8  mov     rcx, [rbx]
0x18004c6cb  mov     rax, [rcx+10h]
0x18004c6cf  mov     rcx, rbx
0x18004c6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c6d7  nop
0x18004c6d8  mov     eax, edi
0x18004c6da  jmp     loc_18004C8BA
0x18004c6df  mov     rcx, r14
0x18004c6e2  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004c6e7  mov     rdi, rax
0x18004c6ea  lea     rdx, ?m_migPropertiesQuery@CIASMigrationHelper@@1QBGB; "./Properties"
0x18004c6f1  lea     rcx, [rbp+var_20]; this
0x18004c6f5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004c6fa  mov     r8, rax
0x18004c6fd  lea     rdx, [rbp+var_18]
0x18004c701  mov     rcx, rdi; struct IUnknown *
0x18004c704  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004c709  nop
0x18004c70a  mov     rdi, [rbp+var_18]
0x18004c70e  test    rdi, rdi
0x18004c711  jnz     short loc_18004C737
0x18004c713  lea     rcx, [rbp+var_30]; this
0x18004c717  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004c71c  nop
0x18004c71d  test    rbx, rbx
0x18004c720  jz      short loc_18004C732
0x18004c722  mov     rax, [rbx]
0x18004c725  mov     rcx, rbx
0x18004c728  mov     rax, [rax+10h]
0x18004c72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c731  nop
0x18004c732  jmp     loc_18004C6A1
0x18004c737  lea     rcx, [rbp+var_18]
0x18004c73b  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004c740  mov     rcx, [rbp+var_30]
0x18004c744  mov     [rbp+var_10], rcx
0x18004c748  test    rcx, rcx
0x18004c74b  jz      short loc_18004C751
0x18004c74d  lock inc dword ptr [rcx+10h]
0x18004c751  lea     r8, [rbp+var_10]
0x18004c755  lea     rdx, [rbp+var_8]
0x18004c759  mov     rcx, rax; struct IUnknown *
0x18004c75c  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004c761  nop
0x18004c762  mov     rsi, [rbp+var_8]
0x18004c766  test    rsi, rsi
0x18004c769  jnz     short loc_18004C78A
0x18004c76b  mov     rax, [rdi]
0x18004c76e  mov     rcx, rdi
0x18004c771  mov     rax, [rax+10h]
0x18004c775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c77a  nop
0x18004c77b  lea     rcx, [rbp+var_30]; this
0x18004c77f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004c784  nop
0x18004c785  jmp     loc_18004C8A3
0x18004c78a  lea     rdx, qword_180063E98; char *
0x18004c791  lea     rcx, [rbp+var_20]; this
0x18004c795  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18004c79a  nop
0x18004c79b  lea     rax, [rbp+var_20]
0x18004c79f  mov     [rsp+60h+var_38], rax
0x18004c7a4  lea     rax, [rbp+var_30]
0x18004c7a8  mov     [rsp+60h+var_40], rax
0x18004c7ad  mov     r9d, [rbp+arg_28]
0x18004c7b1  mov     r8, r14
0x18004c7b4  mov     rdx, r15
0x18004c7b7  mov     rcx, r12
0x18004c7ba  call    ?AddError@CIasMigErrorHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@1KAEAV_bstr_t@@2@Z; CIasMigErrorHelper::AddError(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,ulong,_bstr_t &,_bstr_t &)
0x18004c7bf  mov     r14d, eax
0x18004c7c2  test    eax, eax
0x18004c7c4  jns     loc_18004C86F
0x18004c7ca  lea     rax, WPP_GLOBAL_Control
0x18004c7d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c7d8  cmp     rcx, rax
0x18004c7db  jz      short loc_18004C821
0x18004c7dd  cmp     byte ptr [rcx+19h], 2
0x18004c7e1  jb      short loc_18004C821
0x18004c7e3  test    byte ptr [rcx+1Ch], 10h
0x18004c7e7  jz      short loc_18004C821
0x18004c7e9  mov     edx, r14d
0x18004c7ec  lea     rcx, aAdderrorFailed; "AddError() failed: %!hresult!"
0x18004c7f3  call    WppDbgPrint
0x18004c7f8  mov     edx, 16h
0x18004c7fd  mov     dword ptr [rsp+60h+var_40], r14d
0x18004c802  lea     r9, aNpsds; "NPSDS"
0x18004c809  lea     r8, WPP_35f0385197fd35cdb48f774109abba17_Traceguids
0x18004c810  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c817  mov     rcx, [rcx+10h]
0x18004c81b  call    WPP_SF_sd
0x18004c820  nop
0x18004c821  lea     rcx, [rbp+var_20]; this
0x18004c825  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004c82a  nop
0x18004c82b  mov     rax, [rsi]
0x18004c82e  mov     rcx, rsi
0x18004c831  mov     rax, [rax+10h]
0x18004c835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c83a  nop
0x18004c83b  mov     rax, [rdi]
0x18004c83e  mov     rcx, rdi
0x18004c841  mov     rax, [rax+10h]
0x18004c845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c84a  nop
0x18004c84b  lea     rcx, [rbp+var_30]; this
0x18004c84f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004c854  nop
0x18004c855  test    rbx, rbx
0x18004c858  jz      short loc_18004C86A
0x18004c85a  mov     rax, [rbx]
0x18004c85d  mov     rcx, rbx
0x18004c860  mov     rax, [rax+10h]
0x18004c864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c869  nop
0x18004c86a  mov     eax, r14d
0x18004c86d  jmp     short loc_18004C8BA
0x18004c86f  lea     rcx, [rbp+var_20]; this
0x18004c873  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004c878  nop
0x18004c879  mov     rax, [rsi]
0x18004c87c  mov     rcx, rsi
0x18004c87f  mov     rax, [rax+10h]
0x18004c883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c888  nop
0x18004c889  mov     rax, [rdi]
0x18004c88c  mov     rcx, rdi
0x18004c88f  mov     rax, [rax+10h]
0x18004c893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c898  nop
0x18004c899  lea     rcx, [rbp+var_30]; this
0x18004c89d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004c8a2  nop
0x18004c8a3  test    rbx, rbx
0x18004c8a6  jz      short loc_18004C8B8
0x18004c8a8  mov     rax, [rbx]
0x18004c8ab  mov     rcx, rbx
0x18004c8ae  mov     rax, [rax+10h]
0x18004c8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c8b7  nop
0x18004c8b8  xor     eax, eax
0x18004c8ba  add     rsp, 60h
0x18004c8be  pop     r15
0x18004c8c0  pop     r14
0x18004c8c2  pop     r12
0x18004c8c4  pop     rdi
0x18004c8c5  pop     rsi
0x18004c8c6  pop     rbx
0x18004c8c7  pop     rbp
0x18004c8c8  retn
```
