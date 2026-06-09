# CIASMigrationHelper::ConvertIasXMLToCurrentVersion(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)

- ea: `0x18004c16c`
- end: `0x18004c553`
- name: `?ConvertIasXMLToCurrentVersion@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@00@Z`
- size: `999`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800477a4`

## callees

- `0x1800241bb`
- `0x180024cac`
- `0x18002d08c`
- `0x180047604`
- `0x18004c16c`
- `0x18004cf60`
- `0x18004d1ec`
- `0x18004dea0`
- `0x180050044`
- `0x180052588`
- `0x180055030`
- `0x180058010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18004c384`
- `msvcrt!swprintf_s` at `0x18004c384`

## pseudocode

```c
// Hidden C++ exception states: #wind=21 #try_helpers=1
__int64 __fastcall CIASMigrationHelper::ConvertIasXMLToCurrentVersion(__int64 *a1, __int64 *a2, __int64 *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rsi
  struct IUnknown *v8; // rax
  __int64 *v9; // rax
  struct IUnknown *v10; // r14
  _bstr_t *v11; // rax
  __int64 *v12; // rax
  int DWordValueFromNode; // r14d
  struct IUnknown *v15; // rax
  __int64 *v16; // rax
  struct IUnknown *v17; // r14
  _bstr_t *v18; // rax
  __int64 *v19; // rax
  int v20; // r14d
  unsigned int v21; // r15d
  struct IUnknown *v22; // rax
  __int64 *v23; // rax
  struct IUnknown *v24; // r14
  _bstr_t *v25; // rax
  __int64 *v26; // rax
  int v27; // r14d
  int v28; // [rsp+20h] [rbp-8D8h] BYREF
  unsigned int v29; // [rsp+24h] [rbp-8D4h] BYREF
  __int64 v30; // [rsp+28h] [rbp-8D0h] BYREF
  __int64 v31; // [rsp+30h] [rbp-8C8h] BYREF
  __int64 v32; // [rsp+38h] [rbp-8C0h] BYREF
  __int64 v33; // [rsp+40h] [rbp-8B8h] BYREF
  __int64 v34; // [rsp+48h] [rbp-8B0h] BYREF
  __int64 v35; // [rsp+50h] [rbp-8A8h] BYREF
  __int64 *v36[9]; // [rsp+58h] [rbp-8A0h] BYREF
  wchar_t Buffer[1032]; // [rsp+A0h] [rbp-858h] BYREF

  v36[0] = a3;
  v5 = 0;
  v34 = 0;
  v6 = 0;
  v33 = 0;
  v29 = 0;
  v28 = 0;
  v7 = 0;
  v32 = 0;
  v36[2] = 0;
  v36[3] = 0;
  v8 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
  v9 = (__int64 *)MSXML2::IXMLDOMDocument::GetdocumentElement(v8);
  v10 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(v9);
  v11 = _bstr_t::_bstr_t((_bstr_t *)&v35, L"/Root/Children/Version");
  v12 = MSXML2::IXMLDOMNode::selectSingleNode(v10, &v30, v11);
  if ( *v12 )
  {
    v5 = *v12;
    v34 = *v12;
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v34);
  }
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
  if ( !v5 )
    return 2147549183LL;
  DWordValueFromNode = CIASMigrationHelper::GetDWordValueFromNode(&v34, &v29);
  if ( DWordValueFromNode >= 0 )
  {
    v15 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a2);
    v16 = (__int64 *)MSXML2::IXMLDOMDocument::GetdocumentElement(v15);
    v17 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(v16);
    v18 = _bstr_t::_bstr_t((_bstr_t *)&v31, L"/Root/Children/Version");
    v19 = MSXML2::IXMLDOMNode::selectSingleNode(v17, &v30, v18);
    if ( *v19 )
    {
      v6 = *v19;
      v33 = *v19;
      _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v33);
    }
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
    if ( v6 )
    {
      v20 = CIASMigrationHelper::GetDWordValueFromNode(&v33, &v28);
      if ( v20 >= 0 )
      {
        memset_0(Buffer, 0, 0x802u);
        v21 = v29;
        swprintf_s(Buffer, 0x401u, L"/Root/SDO_Schema_Migration/Migration_Actions[@SourceVersion='%d']", v29);
        v22 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(v36[0]);
        v23 = (__int64 *)MSXML2::IXMLDOMDocument::GetdocumentElement(v22);
        v24 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(v23);
        v25 = _bstr_t::_bstr_t((_bstr_t *)v36, Buffer);
        v26 = MSXML2::IXMLDOMNode::selectSingleNode(v24, &v31, v25);
        if ( *v26 )
        {
          v7 = *v26;
          v32 = *v26;
          _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v32);
        }
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
        if ( v7 )
        {
          v27 = CIASMigrationHelper::PerformMigrationActions(a1, a2, &v32);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          if ( v27 >= 0 )
            return 0;
          else
            return (unsigned int)v27;
        }
        else if ( v21 == v28 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          return 0;
        }
        else
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          return 2147549183LL;
        }
      }
      else
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        return (unsigned int)v20;
      }
    }
    else
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      return 2147549183LL;
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    return (unsigned int)DWordValueFromNode;
  }
}

```

## disassembly

```asm
0x18004c16c  push    rbx
0x18004c16e  push    rsi
0x18004c16f  push    rdi
0x18004c170  push    r12
0x18004c172  push    r13
0x18004c174  push    r14
0x18004c176  push    r15
0x18004c178  sub     rsp, 8C0h
0x18004c17f  mov     rax, cs:__security_cookie
0x18004c186  xor     rax, rsp
0x18004c189  mov     [rsp+8F8h+var_48], rax
0x18004c191  mov     [rsp+8F8h+var_8A0], r8
0x18004c196  mov     r13, rdx
0x18004c199  mov     r12, rcx
0x18004c19c  xor     ebx, ebx
0x18004c19e  mov     [rsp+8F8h+var_8B0], rbx
0x18004c1a3  xor     edi, edi
0x18004c1a5  mov     [rsp+8F8h+var_8B8], rdi
0x18004c1aa  mov     [rsp+8F8h+var_8D4], edi
0x18004c1ae  mov     [rsp+8F8h+var_8D8], edi
0x18004c1b2  xor     esi, esi
0x18004c1b4  mov     [rsp+8F8h+var_8C0], rsi
0x18004c1b9  mov     [rsp+8F8h+var_890], rsi
0x18004c1be  mov     [rsp+8F8h+var_888], rsi
0x18004c1c3  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004c1c8  lea     rdx, [rsp+8F8h+var_8C8]
0x18004c1cd  mov     rcx, rax; struct IUnknown *
0x18004c1d0  call    ?GetdocumentElement@IXMLDOMDocument@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMDocument::GetdocumentElement(void)
0x18004c1d5  nop
0x18004c1d6  mov     rcx, rax
0x18004c1d9  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004c1de  mov     r14, rax
0x18004c1e1  lea     rdx, ?m_versionQuery@CIASMigrationHelper@@1QBGB; "/Root/Children/Version"
0x18004c1e8  lea     rcx, [rsp+8F8h+var_8A8]; this
0x18004c1ed  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004c1f2  mov     r8, rax
0x18004c1f5  lea     rdx, [rsp+8F8h+var_8D0]
0x18004c1fa  mov     rcx, r14; struct IUnknown *
0x18004c1fd  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004c202  nop
0x18004c203  cmp     [rax], rsi
0x18004c206  jz      short loc_18004C21B
0x18004c208  mov     rbx, [rax]
0x18004c20b  mov     [rsp+8F8h+var_8B0], rbx
0x18004c210  lea     rcx, [rsp+8F8h+var_8B0]
0x18004c215  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004c21a  nop
0x18004c21b  mov     rcx, [rsp+8F8h+var_8D0]
0x18004c220  test    rcx, rcx
0x18004c223  jz      short loc_18004C232
0x18004c225  mov     rax, [rcx]
0x18004c228  mov     rax, [rax+10h]
0x18004c22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c231  nop
0x18004c232  lea     rcx, [rsp+8F8h+var_8C8]
0x18004c237  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c23c  test    rbx, rbx
0x18004c23f  jnz     short loc_18004C24B
0x18004c241  mov     eax, 8000FFFFh
0x18004c246  jmp     loc_18004C530
0x18004c24b  lea     rdx, [rsp+8F8h+var_8D4]
0x18004c250  lea     rcx, [rsp+8F8h+var_8B0]
0x18004c255  call    ?GetDWordValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAK@Z; CIASMigrationHelper::GetDWordValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,ulong &)
0x18004c25a  mov     r14d, eax
0x18004c25d  test    eax, eax
0x18004c25f  jns     short loc_18004C279
0x18004c261  mov     rax, [rbx]
0x18004c264  mov     rcx, rbx
0x18004c267  mov     rax, [rax+10h]
0x18004c26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c270  nop
0x18004c271  mov     eax, r14d
0x18004c274  jmp     loc_18004C530
0x18004c279  mov     rcx, r13
0x18004c27c  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004c281  lea     rdx, [rsp+8F8h+var_8A8]
0x18004c286  mov     rcx, rax; struct IUnknown *
0x18004c289  call    ?GetdocumentElement@IXMLDOMDocument@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMDocument::GetdocumentElement(void)
0x18004c28e  nop
0x18004c28f  mov     rcx, rax
0x18004c292  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004c297  mov     r14, rax
0x18004c29a  lea     rdx, ?m_versionQuery@CIASMigrationHelper@@1QBGB; "/Root/Children/Version"
0x18004c2a1  lea     rcx, [rsp+8F8h+var_8C8]; this
0x18004c2a6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004c2ab  mov     r8, rax
0x18004c2ae  lea     rdx, [rsp+8F8h+var_8D0]
0x18004c2b3  mov     rcx, r14; struct IUnknown *
0x18004c2b6  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004c2bb  nop
0x18004c2bc  cmp     qword ptr [rax], 0
0x18004c2c0  jz      short loc_18004C2D5
0x18004c2c2  mov     rdi, [rax]
0x18004c2c5  mov     [rsp+8F8h+var_8B8], rdi
0x18004c2ca  lea     rcx, [rsp+8F8h+var_8B8]
0x18004c2cf  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004c2d4  nop
0x18004c2d5  mov     rcx, [rsp+8F8h+var_8D0]
0x18004c2da  test    rcx, rcx
0x18004c2dd  jz      short loc_18004C2EC
0x18004c2df  mov     rax, [rcx]
0x18004c2e2  mov     rax, [rax+10h]
0x18004c2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2eb  nop
0x18004c2ec  lea     rcx, [rsp+8F8h+var_8A8]
0x18004c2f1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c2f6  test    rdi, rdi
0x18004c2f9  jnz     short loc_18004C315
0x18004c2fb  mov     rax, [rbx]
0x18004c2fe  mov     rcx, rbx
0x18004c301  mov     rax, [rax+10h]
0x18004c305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c30a  nop
0x18004c30b  mov     eax, 8000FFFFh
0x18004c310  jmp     loc_18004C530
0x18004c315  lea     rdx, [rsp+8F8h+var_8D8]
0x18004c31a  lea     rcx, [rsp+8F8h+var_8B8]
0x18004c31f  call    ?GetDWordValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAK@Z; CIASMigrationHelper::GetDWordValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,ulong &)
0x18004c324  mov     r14d, eax
0x18004c327  test    eax, eax
0x18004c329  jns     short loc_18004C353
0x18004c32b  mov     rax, [rdi]
0x18004c32e  mov     rcx, rdi
0x18004c331  mov     rax, [rax+10h]
0x18004c335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c33a  nop
0x18004c33b  mov     rax, [rbx]
0x18004c33e  mov     rcx, rbx
0x18004c341  mov     rax, [rax+10h]
0x18004c345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c34a  nop
0x18004c34b  mov     eax, r14d
0x18004c34e  jmp     loc_18004C530
0x18004c353  xor     edx, edx; Val
0x18004c355  mov     r8d, 802h; Size
0x18004c35b  lea     rcx, [rsp+8F8h+Buffer]; void *
0x18004c363  call    memset_0
0x18004c368  mov     r15d, [rsp+8F8h+var_8D4]
0x18004c36d  mov     r9d, r15d
0x18004c370  lea     r8, ?m_migrationQuery@CIASMigrationHelper@@1QBGB; "/Root/SDO_Schema_Migration/Migration_Ac"...
0x18004c377  mov     edx, 401h; BufferCount
0x18004c37c  lea     rcx, [rsp+8F8h+Buffer]; Buffer
0x18004c384  call    cs:__imp_swprintf_s
0x18004c38a  mov     rcx, [rsp+8F8h+var_8A0]
0x18004c38f  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004c394  lea     rdx, [rsp+8F8h+var_8D0]
0x18004c399  mov     rcx, rax; struct IUnknown *
0x18004c39c  call    ?GetdocumentElement@IXMLDOMDocument@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMDocument::GetdocumentElement(void)
0x18004c3a1  nop
0x18004c3a2  mov     rcx, rax
0x18004c3a5  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004c3aa  mov     r14, rax
0x18004c3ad  lea     rdx, [rsp+8F8h+Buffer]; unsigned __int16 *
0x18004c3b5  lea     rcx, [rsp+8F8h+var_8A0]; this
0x18004c3ba  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004c3bf  mov     r8, rax
0x18004c3c2  lea     rdx, [rsp+8F8h+var_8C8]
0x18004c3c7  mov     rcx, r14; struct IUnknown *
0x18004c3ca  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004c3cf  nop
0x18004c3d0  cmp     qword ptr [rax], 0
0x18004c3d4  jz      short loc_18004C3E9
0x18004c3d6  mov     rsi, [rax]
0x18004c3d9  mov     [rsp+8F8h+var_8C0], rsi
0x18004c3de  lea     rcx, [rsp+8F8h+var_8C0]
0x18004c3e3  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004c3e8  nop
0x18004c3e9  mov     rcx, [rsp+8F8h+var_8C8]
0x18004c3ee  test    rcx, rcx
0x18004c3f1  jz      short loc_18004C400
0x18004c3f3  mov     rax, [rcx]
0x18004c3f6  mov     rax, [rax+10h]
0x18004c3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c3ff  nop
0x18004c400  lea     rcx, [rsp+8F8h+var_8D0]
0x18004c405  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c40a  test    rsi, rsi
0x18004c40d  jnz     short loc_18004C467
0x18004c40f  cmp     r15d, [rsp+8F8h+var_8D8]
0x18004c414  jnz     short loc_18004C43D
0x18004c416  mov     rax, [rdi]
0x18004c419  mov     rcx, rdi
0x18004c41c  mov     rax, [rax+10h]
0x18004c420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c425  nop
0x18004c426  mov     rax, [rbx]
0x18004c429  mov     rcx, rbx
0x18004c42c  mov     rax, [rax+10h]
0x18004c430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c435  nop
0x18004c436  xor     eax, eax
0x18004c438  jmp     loc_18004C530
0x18004c43d  mov     rax, [rdi]
0x18004c440  mov     rcx, rdi
0x18004c443  mov     rax, [rax+10h]
0x18004c447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c44c  nop
0x18004c44d  mov     rax, [rbx]
0x18004c450  mov     rcx, rbx
0x18004c453  mov     rax, [rax+10h]
0x18004c457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c45c  nop
0x18004c45d  mov     eax, 8000FFFFh
0x18004c462  jmp     loc_18004C530
0x18004c467  lea     r8, [rsp+8F8h+var_8C0]
0x18004c46c  mov     rdx, r13
0x18004c46f  mov     rcx, r12
0x18004c472  call    ?PerformMigrationActions@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; CIASMigrationHelper::PerformMigrationActions(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &)
0x18004c477  mov     r14d, eax
0x18004c47a  test    eax, eax
0x18004c47c  jns     short loc_18004C4B3
0x18004c47e  mov     rax, [rsi]
0x18004c481  mov     rcx, rsi
0x18004c484  mov     rax, [rax+10h]
0x18004c488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c48d  nop
0x18004c48e  mov     rax, [rdi]
0x18004c491  mov     rcx, rdi
0x18004c494  mov     rax, [rax+10h]
0x18004c498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c49d  nop
0x18004c49e  mov     rax, [rbx]
0x18004c4a1  mov     rcx, rbx
0x18004c4a4  mov     rax, [rax+10h]
0x18004c4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c4ad  nop
0x18004c4ae  mov     eax, r14d
0x18004c4b1  jmp     short loc_18004C530
0x18004c4b3  mov     rax, [rsi]
0x18004c4b6  mov     rcx, rsi
0x18004c4b9  mov     rax, [rax+10h]
0x18004c4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c4c2  nop
0x18004c4c3  mov     rax, [rdi]
0x18004c4c6  mov     rcx, rdi
0x18004c4c9  mov     rax, [rax+10h]
0x18004c4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c4d2  nop
0x18004c4d3  mov     rax, [rbx]
0x18004c4d6  mov     rcx, rbx
0x18004c4d9  mov     rax, [rax+10h]
0x18004c4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c4e2  nop
0x18004c4e3  xor     eax, eax
0x18004c4e5  jmp     short loc_18004C530
0x18004c4e7  mov     rcx, [rsp+8F8h+var_8C0]
0x18004c4ec  test    rcx, rcx
0x18004c4ef  jz      short loc_18004C4FE
0x18004c4f1  mov     rax, [rcx]
0x18004c4f4  mov     rax, [rax+10h]
0x18004c4f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c4fd  nop
0x18004c4fe  mov     rcx, [rsp+8F8h+var_8B8]
0x18004c503  test    rcx, rcx
0x18004c506  jz      short loc_18004C515
0x18004c508  mov     rax, [rcx]
0x18004c50b  mov     rax, [rax+10h]
0x18004c50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c514  nop
0x18004c515  mov     rcx, [rsp+8F8h+var_8B0]
0x18004c51a  test    rcx, rcx
0x18004c51d  jz      short loc_18004C52C
0x18004c51f  mov     rax, [rcx]
0x18004c522  mov     rax, [rax+10h]
0x18004c526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c52b  nop
0x18004c52c  mov     eax, [rsp+8F8h+var_8D8]
0x18004c530  mov     rcx, [rsp+8F8h+var_48]
0x18004c538  xor     rcx, rsp; StackCookie
0x18004c53b  call    __security_check_cookie
0x18004c540  add     rsp, 8C0h
0x18004c547  pop     r15
0x18004c549  pop     r14
0x18004c54b  pop     r13
0x18004c54d  pop     r12
0x18004c54f  pop     rdi
0x18004c550  pop     rsi
0x18004c551  pop     rbx
0x18004c552  retn
```
