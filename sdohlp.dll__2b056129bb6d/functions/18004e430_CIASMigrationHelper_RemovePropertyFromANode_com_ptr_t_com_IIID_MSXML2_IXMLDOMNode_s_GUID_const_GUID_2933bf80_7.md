# CIASMigrationHelper::RemovePropertyFromANode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,ushort *)

- ea: `0x18004e430`
- end: `0x18004e61d`
- name: `?RemovePropertyFromANode@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEAG@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004e630`

## callees

- `0x18002d08c`
- `0x180047604`
- `0x18004e430`
- `0x180050044`
- `0x18005216c`
- `0x180052588`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18004e455`
- `OLEAUT32!__imp_VariantInit` at `0x18004e455`
- `OLEAUT32!__imp_VariantClear` at `0x18004e465`
- `OLEAUT32!__imp_VariantClear` at `0x18004e4dc`
- `OLEAUT32!__imp_VariantClear` at `0x18004e557`
- `OLEAUT32!__imp_VariantClear` at `0x18004e5b2`
- `OLEAUT32!__imp_VariantClear` at `0x18004e5ec`
- `OLEAUT32!__imp_VariantClear` at `0x18004e465`
- `OLEAUT32!__imp_VariantClear` at `0x18004e4dc`
- `OLEAUT32!__imp_VariantClear` at `0x18004e557`
- `OLEAUT32!__imp_VariantClear` at `0x18004e5b2`
- `OLEAUT32!__imp_VariantClear` at `0x18004e5ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CIASMigrationHelper::RemovePropertyFromANode(__int64 *a1, const unsigned __int16 *a2)
{
  __int64 v4; // rbx
  struct IUnknown *v6; // rdi
  _bstr_t *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rsi
  __int64 v10; // rdi
  struct IUnknown *v11; // rsi
  _bstr_t *v12; // rax
  __int64 *v13; // rax
  __int64 v14; // rsi
  __int64 v15; // r14
  struct IUnknown *v16; // rax
  __int64 v17; // rsi
  __int64 v18; // [rsp+20h] [rbp-30h] BYREF
  __int64 v19; // [rsp+28h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  __int64 v21; // [rsp+80h] [rbp+30h] BYREF
  __int64 v22; // [rsp+88h] [rbp+38h] BYREF

  v4 = 0;
  v21 = 0;
  VariantInit(&pvarg);
  if ( !a2 )
  {
    VariantClear(&pvarg);
    return 2147942487LL;
  }
  v6 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
  v7 = _bstr_t::_bstr_t((_bstr_t *)&v22, L"./Properties");
  v8 = *MSXML2::IXMLDOMNode::selectSingleNode(v6, &v18, v7);
  v9 = 0;
  if ( v8 )
  {
    v4 = v8;
    v21 = v8;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v21);
    v9 = v8;
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( !v9 )
  {
    VariantClear(&pvarg);
    return 2147549183LL;
  }
  v10 = 0;
  v22 = 0;
  v11 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v21);
  v12 = _bstr_t::_bstr_t((_bstr_t *)&v18, a2);
  v13 = MSXML2::IXMLDOMNode::selectSingleNode(v11, &v19, v12);
  v14 = *v13;
  v15 = 0;
  if ( *v13 )
  {
    v10 = *v13;
    v22 = *v13;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v22);
    v15 = v14;
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v15 )
  {
    v16 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v21);
    v17 = *(_QWORD *)MSXML2::IXMLDOMNode::removeChild(v16);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    if ( !v17 )
    {
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      VariantClear(&pvarg);
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      return 2147549183LL;
    }
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  VariantClear(&pvarg);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x18004e430  mov     [rsp-18h+arg_0], rbx
0x18004e435  mov     [rsp-18h+arg_8], rsi
0x18004e43a  push    rbp
0x18004e43b  push    rdi
0x18004e43c  push    r14
0x18004e43e  mov     rbp, rsp
0x18004e441  sub     rsp, 50h
0x18004e445  mov     r14, rdx
0x18004e448  mov     rdi, rcx
0x18004e44b  xor     ebx, ebx
0x18004e44d  mov     [rbp+arg_10], rbx
0x18004e451  lea     rcx, [rbp+pvarg]; pvarg
0x18004e455  call    cs:__imp_VariantInit
0x18004e45b  nop
0x18004e45c  test    r14, r14
0x18004e45f  jnz     short loc_18004E476
0x18004e461  lea     rcx, [rbp+pvarg]; pvarg
0x18004e465  call    cs:__imp_VariantClear
0x18004e46b  nop
0x18004e46c  mov     eax, 80070057h
0x18004e471  jmp     loc_18004E60A
0x18004e476  mov     rcx, rdi
0x18004e479  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e47e  mov     rdi, rax
0x18004e481  lea     rdx, ?m_migPropertiesQuery@CIASMigrationHelper@@1QBGB; "./Properties"
0x18004e488  lea     rcx, [rbp+arg_18]; this
0x18004e48c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004e491  mov     r8, rax
0x18004e494  lea     rdx, [rbp+var_30]
0x18004e498  mov     rcx, rdi; struct IUnknown *
0x18004e49b  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004e4a0  mov     rdi, [rax]
0x18004e4a3  xor     esi, esi
0x18004e4a5  test    rdi, rdi
0x18004e4a8  jz      short loc_18004E4BD
0x18004e4aa  mov     rbx, rdi
0x18004e4ad  mov     [rbp+arg_10], rbx
0x18004e4b1  lea     rcx, [rbp+arg_10]
0x18004e4b5  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004e4ba  mov     rsi, rdi
0x18004e4bd  mov     rcx, [rbp+var_30]
0x18004e4c1  test    rcx, rcx
0x18004e4c4  jz      short loc_18004E4D3
0x18004e4c6  mov     rax, [rcx]
0x18004e4c9  mov     rax, [rax+10h]
0x18004e4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4d2  nop
0x18004e4d3  test    rsi, rsi
0x18004e4d6  jnz     short loc_18004E4ED
0x18004e4d8  lea     rcx, [rbp+pvarg]; pvarg
0x18004e4dc  call    cs:__imp_VariantClear
0x18004e4e2  nop
0x18004e4e3  mov     eax, 8000FFFFh
0x18004e4e8  jmp     loc_18004E60A
0x18004e4ed  xor     edi, edi
0x18004e4ef  mov     [rbp+arg_18], rdi
0x18004e4f3  lea     rcx, [rbp+arg_10]
0x18004e4f7  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e4fc  mov     rsi, rax
0x18004e4ff  mov     rdx, r14; unsigned __int16 *
0x18004e502  lea     rcx, [rbp+var_30]; this
0x18004e506  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004e50b  mov     r8, rax
0x18004e50e  lea     rdx, [rbp+var_28]
0x18004e512  mov     rcx, rsi; struct IUnknown *
0x18004e515  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004e51a  mov     rsi, [rax]
0x18004e51d  xor     r14d, r14d
0x18004e520  test    rsi, rsi
0x18004e523  jz      short loc_18004E538
0x18004e525  mov     rdi, rsi
0x18004e528  mov     [rbp+arg_18], rsi
0x18004e52c  lea     rcx, [rbp+arg_18]
0x18004e530  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004e535  mov     r14, rsi
0x18004e538  mov     rcx, [rbp+var_28]
0x18004e53c  test    rcx, rcx
0x18004e53f  jz      short loc_18004E54E
0x18004e541  mov     rax, [rcx]
0x18004e544  mov     rax, [rax+10h]
0x18004e548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e54d  nop
0x18004e54e  test    r14, r14
0x18004e551  jnz     short loc_18004E563
0x18004e553  lea     rcx, [rbp+pvarg]; pvarg
0x18004e557  call    cs:__imp_VariantClear
0x18004e55d  nop
0x18004e55e  jmp     loc_18004E5F3
0x18004e563  lea     rcx, [rbp+arg_10]
0x18004e567  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004e56c  mov     r8, rdi
0x18004e56f  lea     rdx, [rbp+var_28]
0x18004e573  mov     rcx, rax; struct IUnknown *
0x18004e576  call    ?removeChild@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEAU12@@Z; MSXML2::IXMLDOMNode::removeChild(MSXML2::IXMLDOMNode *)
0x18004e57b  mov     rsi, [rax]
0x18004e57e  mov     rcx, [rbp+var_28]
0x18004e582  test    rcx, rcx
0x18004e585  jz      short loc_18004E594
0x18004e587  mov     rax, [rcx]
0x18004e58a  mov     rax, [rax+10h]
0x18004e58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e593  nop
0x18004e594  test    rsi, rsi
0x18004e597  jnz     short loc_18004E5D3
0x18004e599  test    rdi, rdi
0x18004e59c  jz      short loc_18004E5AE
0x18004e59e  mov     rax, [rdi]
0x18004e5a1  mov     rcx, rdi
0x18004e5a4  mov     rax, [rax+10h]
0x18004e5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5ad  nop
0x18004e5ae  lea     rcx, [rbp+pvarg]; pvarg
0x18004e5b2  call    cs:__imp_VariantClear
0x18004e5b8  nop
0x18004e5b9  test    rbx, rbx
0x18004e5bc  jz      short loc_18004E5CE
0x18004e5be  mov     rax, [rbx]
0x18004e5c1  mov     rcx, rbx
0x18004e5c4  mov     rax, [rax+10h]
0x18004e5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5cd  nop
0x18004e5ce  jmp     loc_18004E4E3
0x18004e5d3  test    rdi, rdi
0x18004e5d6  jz      short loc_18004E5E8
0x18004e5d8  mov     rax, [rdi]
0x18004e5db  mov     rcx, rdi
0x18004e5de  mov     rax, [rax+10h]
0x18004e5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5e7  nop
0x18004e5e8  lea     rcx, [rbp+pvarg]; pvarg
0x18004e5ec  call    cs:__imp_VariantClear
0x18004e5f2  nop
0x18004e5f3  test    rbx, rbx
0x18004e5f6  jz      short loc_18004E608
0x18004e5f8  mov     rax, [rbx]
0x18004e5fb  mov     rcx, rbx
0x18004e5fe  mov     rax, [rax+10h]
0x18004e602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e607  nop
0x18004e608  xor     eax, eax
0x18004e60a  mov     rbx, [rsp+50h+arg_0]
0x18004e60f  mov     rsi, [rsp+50h+arg_8]
0x18004e614  add     rsp, 50h
0x18004e618  pop     r14
0x18004e61a  pop     rdi
0x18004e61b  pop     rbp
0x18004e61c  retn
```
