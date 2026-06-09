# CIasMigErrorHelper::AddError(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,ulong,_bstr_t &,_bstr_t &)

- ea: `0x180052d80`
- end: `0x180053050`
- name: `?AddError@CIasMigErrorHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@1KAEAV_bstr_t@@2@Z`
- size: `720`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b6d0`
- `0x18004c610`

## callees

- `0x18002d08c`
- `0x18002efa0`
- `0x180047604`
- `0x18004cf60`
- `0x18004d11c`
- `0x180052588`
- `0x180052d80`
- `0x1800534b0`
- `0x180053bd0`
- `0x180054194`
- `0x180058010`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CIasMigErrorHelper::AddError(
        __int64 a1,
        __int64 *a2,
        __int64 *a3,
        int a4,
        LPCWCH **a5,
        const WCHAR ***a6)
{
  int MessageResource; // ebx
  unsigned int v11; // r15d
  struct IUnknown *v12; // rbx
  _bstr_t *v13; // rax
  __int64 v14; // rbx
  int DWordValueFromNode; // edi
  struct IUnknown *v16; // rax
  struct IUnknown *v17; // rdi
  __int64 v18; // rsi
  int StringValueFromNode; // r14d
  const struct ErrorSectionTableItem near *const *i; // rax
  __int64 v21; // rcx
  __int64 v22; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v23; // [rsp+38h] [rbp-38h] BYREF
  __int64 v24; // [rsp+40h] [rbp-30h] BYREF
  __int64 v25; // [rsp+48h] [rbp-28h] BYREF
  __int64 v26; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v27[8]; // [rsp+58h] [rbp-18h] BYREF
  struct IUnknown *v28; // [rsp+60h] [rbp-10h]

  v23 = 0;
  v24 = 0;
  MessageResource = CIasMigErrorHelper::GetMessageResource(a1, a5, a6, &v23, (__int64)&v24);
  if ( MessageResource < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v24);
    return (unsigned int)MessageResource;
  }
  v11 = 0;
  LODWORD(v22) = 0;
  v12 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a2);
  v13 = _bstr_t::_bstr_t((_bstr_t *)v27, L"./TabTitleResource");
  MSXML2::IXMLDOMNode::selectSingleNode(v12, &v26, v13);
  v14 = v26;
  if ( v26 )
  {
    DWordValueFromNode = CIASMigrationHelper::GetDWordValueFromNode(&v26, &v22);
    if ( DWordValueFromNode < 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      _bstr_t::_Free((_bstr_t *)&v24);
      return (unsigned int)DWordValueFromNode;
    }
    v11 = v22;
  }
  v16 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a3);
  MSXML2::IXMLDOMNode::Getattributes(v16);
  v17 = v28;
  if ( !v28 )
    goto LABEL_27;
  _bstr_t::_bstr_t((_bstr_t *)v27, L"name");
  MSXML2::IXMLDOMNamedNodeMap::getNamedItem(v17);
  v18 = v22;
  if ( !v22 )
  {
    ((void (__fastcall *)(struct IUnknown *))v17->lpVtbl->Release)(v17);
LABEL_27:
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    _bstr_t::_Free((_bstr_t *)&v24);
    return 2147549183LL;
  }
  v25 = 0;
  StringValueFromNode = CIASMigrationHelper::GetStringValueFromNode(&v22, (__int64)&v25);
  if ( StringValueFromNode < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v25);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    ((void (__fastcall *)(struct IUnknown *))v17->lpVtbl->Release)(v17);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_13:
    _bstr_t::_Free((_bstr_t *)&v24);
    return (unsigned int)StringValueFromNode;
  }
  for ( i = &CIasMigErrorHelper::m_errorSectionTable; ; i += 2 )
  {
    if ( !*(_DWORD *)i )
      goto LABEL_26;
    if ( a4 == *(_DWORD *)i )
      break;
  }
  v21 = *((_QWORD *)i + 1);
  if ( !v21 )
  {
LABEL_26:
    _bstr_t::_Free((_bstr_t *)&v25);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    ((void (__fastcall *)(struct IUnknown *))v17->lpVtbl->Release)(v17);
    goto LABEL_27;
  }
  StringValueFromNode = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *, __int64 *))(*(_QWORD *)v21 + 8LL))(
                          v21,
                          v11,
                          v23,
                          &v24,
                          &v25);
  if ( StringValueFromNode < 0 )
  {
    _bstr_t::_Free((_bstr_t *)&v25);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    ((void (__fastcall *)(struct IUnknown *))v17->lpVtbl->Release)(v17);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    goto LABEL_13;
  }
  _bstr_t::_Free((_bstr_t *)&v25);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  ((void (__fastcall *)(struct IUnknown *))v17->lpVtbl->Release)(v17);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  _bstr_t::_Free((_bstr_t *)&v24);
  return 0;
}

```

## disassembly

```asm
0x180052d80  push    rbp
0x180052d82  push    rbx
0x180052d83  push    rsi
0x180052d84  push    rdi
0x180052d85  push    r12
0x180052d87  push    r14
0x180052d89  push    r15
0x180052d8b  mov     rbp, rsp
0x180052d8e  sub     rsp, 70h
0x180052d92  mov     r12d, r9d
0x180052d95  mov     rsi, r8
0x180052d98  mov     rdi, rdx
0x180052d9b  mov     [rbp+var_38], 0
0x180052da2  mov     [rbp+var_30], 0
0x180052daa  lea     rax, [rbp+var_30]
0x180052dae  mov     [rsp+70h+var_50], rax
0x180052db3  lea     r9, [rbp+var_38]
0x180052db7  mov     r8, [rbp+arg_28]
0x180052dbb  mov     rdx, [rbp+arg_20]
0x180052dbf  call    ?GetMessageResource@CIasMigErrorHelper@@CAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@1AEAK1@Z; CIasMigErrorHelper::GetMessageResource(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &,_bstr_t &,ulong &,_bstr_t &)
0x180052dc4  mov     ebx, eax
0x180052dc6  test    eax, eax
0x180052dc8  jns     short loc_180052DDA
0x180052dca  lea     rcx, [rbp+var_30]; this
0x180052dce  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180052dd3  mov     eax, ebx
0x180052dd5  jmp     loc_180053041
0x180052dda  xor     r15d, r15d
0x180052ddd  mov     dword ptr [rbp+var_40], r15d
0x180052de1  mov     rcx, rdi
0x180052de4  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180052de9  mov     rbx, rax
0x180052dec  lea     rdx, ?m_tabTitleQuery@CIASMigrationHelper@@1QBGB; "./TabTitleResource"
0x180052df3  lea     rcx, [rbp+var_18]; this
0x180052df7  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180052dfc  mov     r8, rax
0x180052dff  lea     rdx, [rbp+var_20]
0x180052e03  mov     rcx, rbx; struct IUnknown *
0x180052e06  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x180052e0b  nop
0x180052e0c  mov     rbx, [rbp+var_20]
0x180052e10  test    rbx, rbx
0x180052e13  jz      short loc_180052E4C
0x180052e15  lea     rdx, [rbp+var_40]
0x180052e19  lea     rcx, [rbp+var_20]
0x180052e1d  call    ?GetDWordValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAK@Z; CIASMigrationHelper::GetDWordValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,ulong &)
0x180052e22  mov     edi, eax
0x180052e24  test    eax, eax
0x180052e26  jns     short loc_180052E48
0x180052e28  mov     rcx, [rbx]
0x180052e2b  mov     rax, [rcx+10h]
0x180052e2f  mov     rcx, rbx
0x180052e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e37  nop
0x180052e38  lea     rcx, [rbp+var_30]; this
0x180052e3c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180052e41  mov     eax, edi
0x180052e43  jmp     loc_180053041
0x180052e48  mov     r15d, dword ptr [rbp+var_40]
0x180052e4c  mov     rcx, rsi
0x180052e4f  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180052e54  lea     rdx, [rbp+var_10]
0x180052e58  mov     rcx, rax; struct IUnknown *
0x180052e5b  call    ?Getattributes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNamedNodeMap@MSXML2@@$1?_GUID_2933bf83_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNode::Getattributes(void)
0x180052e60  nop
0x180052e61  mov     rdi, [rbp+var_10]
0x180052e65  test    rdi, rdi
0x180052e68  jnz     short loc_180052E6F
0x180052e6a  jmp     loc_18005301E
0x180052e6f  lea     rdx, ?m_policyNameQuery@CIASMigrationHelper@@1QBGB; "name"
0x180052e76  lea     rcx, [rbp+var_18]; this
0x180052e7a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180052e7f  mov     r8, rax
0x180052e82  lea     rdx, [rbp+var_40]
0x180052e86  mov     rcx, rdi; struct IUnknown *
0x180052e89  call    ?getNamedItem@IXMLDOMNamedNodeMap@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNamedNodeMap::getNamedItem(_bstr_t)
0x180052e8e  nop
0x180052e8f  mov     rsi, [rbp+var_40]
0x180052e93  test    rsi, rsi
0x180052e96  jnz     short loc_180052EAD
0x180052e98  mov     rax, [rdi]
0x180052e9b  mov     rcx, rdi
0x180052e9e  mov     rax, [rax+10h]
0x180052ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ea7  nop
0x180052ea8  jmp     loc_18005301E
0x180052ead  mov     [rbp+var_28], 0
0x180052eb5  lea     rdx, [rbp+var_28]
0x180052eb9  lea     rcx, [rbp+var_40]
0x180052ebd  call    ?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z; CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)
0x180052ec2  mov     r14d, eax
0x180052ec5  test    eax, eax
0x180052ec7  jns     short loc_180052F19
0x180052ec9  lea     rcx, [rbp+var_28]; this
0x180052ecd  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180052ed2  nop
0x180052ed3  mov     rcx, [rsi]
0x180052ed6  mov     rax, [rcx+10h]
0x180052eda  mov     rcx, rsi
0x180052edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ee2  nop
0x180052ee3  mov     rax, [rdi]
0x180052ee6  mov     rcx, rdi
0x180052ee9  mov     rax, [rax+10h]
0x180052eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ef2  nop
0x180052ef3  test    rbx, rbx
0x180052ef6  jz      short loc_180052F08
0x180052ef8  mov     rax, [rbx]
0x180052efb  mov     rcx, rbx
0x180052efe  mov     rax, [rax+10h]
0x180052f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f07  nop
0x180052f08  lea     rcx, [rbp+var_30]; this
0x180052f0c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180052f11  mov     eax, r14d
0x180052f14  jmp     loc_180053041
0x180052f19  lea     rax, ?m_errorSectionTable@CIasMigErrorHelper@@0QBUErrorSectionTableItem@@B; ErrorSectionTableItem const near * const CIasMigErrorHelper::m_errorSectionTable
0x180052f20  cmp     dword ptr [rax], 0
0x180052f23  jz      loc_180052FF4
0x180052f29  cmp     r12d, [rax]
0x180052f2c  jz      short loc_180052F34
0x180052f2e  add     rax, 10h
0x180052f32  jmp     short loc_180052F20
0x180052f34  mov     rcx, [rax+8]
0x180052f38  test    rcx, rcx
0x180052f3b  jz      loc_180052FF4
0x180052f41  mov     rax, [rcx]
0x180052f44  lea     rdx, [rbp+var_28]
0x180052f48  mov     [rsp+70h+var_50], rdx
0x180052f4d  lea     r9, [rbp+var_30]
0x180052f51  mov     r8d, [rbp+var_38]
0x180052f55  mov     edx, r15d
0x180052f58  mov     rax, [rax+8]
0x180052f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f61  mov     r14d, eax
0x180052f64  lea     rcx, [rbp+var_28]; this
0x180052f68  test    eax, eax
0x180052f6a  jns     short loc_180052FAC
0x180052f6c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180052f71  nop
0x180052f72  mov     rcx, [rsi]
0x180052f75  mov     rax, [rcx+10h]
0x180052f79  mov     rcx, rsi
0x180052f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f81  nop
0x180052f82  mov     rax, [rdi]
0x180052f85  mov     rcx, rdi
0x180052f88  mov     rax, [rax+10h]
0x180052f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f91  nop
0x180052f92  test    rbx, rbx
0x180052f95  jz      short loc_180052FA7
0x180052f97  mov     rax, [rbx]
0x180052f9a  mov     rcx, rbx
0x180052f9d  mov     rax, [rax+10h]
0x180052fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052fa6  nop
0x180052fa7  jmp     loc_180052F08
0x180052fac  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180052fb1  nop
0x180052fb2  mov     rax, [rsi]
0x180052fb5  mov     rcx, rsi
0x180052fb8  mov     rax, [rax+10h]
0x180052fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052fc1  nop
0x180052fc2  mov     rax, [rdi]
0x180052fc5  mov     rcx, rdi
0x180052fc8  mov     rax, [rax+10h]
0x180052fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052fd1  nop
0x180052fd2  test    rbx, rbx
0x180052fd5  jz      short loc_180052FE7
0x180052fd7  mov     rax, [rbx]
0x180052fda  mov     rcx, rbx
0x180052fdd  mov     rax, [rax+10h]
0x180052fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052fe6  nop
0x180052fe7  lea     rcx, [rbp+var_30]; this
0x180052feb  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180052ff0  xor     eax, eax
0x180052ff2  jmp     short loc_180053041
0x180052ff4  lea     rcx, [rbp+var_28]; this
0x180052ff8  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180052ffd  nop
0x180052ffe  mov     rax, [rsi]
0x180053001  mov     rcx, rsi
0x180053004  mov     rax, [rax+10h]
0x180053008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005300d  nop
0x18005300e  mov     rax, [rdi]
0x180053011  mov     rcx, rdi
0x180053014  mov     rax, [rax+10h]
0x180053018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005301d  nop
0x18005301e  test    rbx, rbx
0x180053021  jz      short loc_180053033
0x180053023  mov     rax, [rbx]
0x180053026  mov     rcx, rbx
0x180053029  mov     rax, [rax+10h]
0x18005302d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053032  nop
0x180053033  lea     rcx, [rbp+var_30]; this
0x180053037  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18005303c  mov     eax, 8000FFFFh
0x180053041  add     rsp, 70h
0x180053045  pop     r15
0x180053047  pop     r14
0x180053049  pop     r12
0x18005304b  pop     rdi
0x18005304c  pop     rsi
0x18005304d  pop     rbx
0x18005304e  pop     rbp
0x18005304f  retn
```
