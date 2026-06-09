# CIASMigrationHelper::LoadXMLFromFile(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,ushort const *)

- ea: `0x18004d4c8`
- end: `0x18004d8f7`
- name: `?LoadXMLFromFile@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEBG@Z`
- size: `1071`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047628`
- `0x1800477a4`
- `0x180047a60`

## callees

- `0x18002cd74`
- `0x18002efa0`
- `0x18002f240`
- `0x180042a80`
- `0x1800475b8`
- `0x180047604`
- `0x180048a2c`
- `0x180048acc`
- `0x180048e7c`
- `0x1800491a0`
- `0x18004c55c`
- `0x18004d24c`
- `0x18004d370`
- `0x18004d3d0`
- `0x18004d434`
- `0x18004d4c8`
- `0x18004e16c`
- `0x180050044`
- `0x180051d9c`
- `0x180058010`

## string_xrefs

- `0x18004d569`: `CIASMigrationHelper::LoadXMLFromFile(), failed load xml from %S `

## pseudocode

```c
// Hidden C++ exception states: #wind=36 #try_helpers=1
int __fastcall CIASMigrationHelper::LoadXMLFromFile(LPVOID *a1, const unsigned __int16 *a2, IUnknown *a3)
{
  __int64 v5; // rbx
  int result; // eax
  struct IUnknown *v7; // rax
  __int16 v8; // dx
  struct IUnknown *v9; // r14
  struct IUnknown *v10; // rax
  __int64 *v11; // rax
  _bstr_t *v12; // rdi
  _bstr_t *v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdi
  _bstr_t *v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdi
  _bstr_t *v23; // rax
  __int64 v24; // rdi
  struct IUnknown *v25; // rax
  _bstr_t *v26; // rax
  __int64 v27; // rdi
  _bstr_t *v28; // rax
  __int64 v29; // rcx
  __int64 *v30; // [rsp+30h] [rbp-C8h] BYREF
  __int16 v31; // [rsp+38h] [rbp-C0h] BYREF
  int v32; // [rsp+40h] [rbp-B8h]
  _BYTE v33[8]; // [rsp+50h] [rbp-A8h] BYREF
  _BYTE v34[8]; // [rsp+58h] [rbp-A0h] BYREF
  _BYTE v35[8]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v36[8]; // [rsp+68h] [rbp-90h] BYREF
  _BYTE v37[8]; // [rsp+70h] [rbp-88h] BYREF
  _BYTE v38[8]; // [rsp+78h] [rbp-80h] BYREF
  _BYTE v39[8]; // [rsp+80h] [rbp-78h] BYREF
  _BYTE v40[8]; // [rsp+88h] [rbp-70h] BYREF
  _BYTE v41[8]; // [rsp+90h] [rbp-68h] BYREF
  _BYTE v42[8]; // [rsp+98h] [rbp-60h] BYREF
  _BYTE v43[8]; // [rsp+A0h] [rbp-58h] BYREF
  _BYTE v44[8]; // [rsp+A8h] [rbp-50h] BYREF
  _BYTE v45[8]; // [rsp+B0h] [rbp-48h] BYREF
  _BYTE v46[64]; // [rsp+B8h] [rbp-40h] BYREF
  __int64 v47; // [rsp+110h] [rbp+18h]
  int v48; // [rsp+110h] [rbp+18h]
  __int64 v49; // [rsp+118h] [rbp+20h] BYREF

  v5 = 0;
  v49 = 0;
  result = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance(
             a1,
             (__int64)a2,
             a3,
             0x17u);
  if ( result >= 0 )
  {
    v7 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
    MSXML2::IXMLDOMDocument::Putasync(v7, v8);
    v9 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
    _variant_t::_variant_t((_variant_t *)&v31, a2);
    LOWORD(v9) = MSXML2::IXMLDOMDocument::load(v9, (const struct _variant_t *)&v31);
    _variant_t::~_variant_t((_variant_t *)&v31);
    if ( (_WORD)v9 == 0xFFFF )
    {
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("CIASMigrationHelper::LoadXMLFromFile(), failed load xml from %S ");
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_35f0385197fd35cdb48f774109abba17_Traceguids,
          (unsigned int)"NPSDS",
          (__int64)a2);
      }
      v10 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
      v11 = (__int64 *)MSXML2::IXMLDOMDocument::GetparseError(v10);
      if ( *v11 )
      {
        v5 = *v11;
        v49 = *v11;
        _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v49);
      }
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      v12 = _bstr_t::_bstr_t((_bstr_t *)v46, "\n=====================");
      v13 = _bstr_t::_bstr_t((_bstr_t *)v45, "\nReason: ");
      v14 = _bstr_t::operator+(v12, v44, v13);
      v15 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v49);
      v16 = MSXML2::IXMLDOMParseError::Getreason(v15, v43);
      v17 = _bstr_t::operator+(v14, v42, v16);
      v18 = _bstr_t::_bstr_t((_bstr_t *)v41, "\nSource: ");
      v19 = _bstr_t::operator+(v17, v40, v18);
      v20 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v49);
      v21 = MSXML2::IXMLDOMParseError::GetsrcText(v20, v39);
      v22 = _bstr_t::operator+(v19, v38, v21);
      v23 = _bstr_t::_bstr_t((_bstr_t *)v37, "\nLine: ");
      v24 = _bstr_t::operator+(v22, v36, v23);
      v25 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v49);
      v48 = MSXML2::IXMLDOMParseError::Getline(v25);
      v31 = 3;
      v32 = v48;
      v26 = _bstr_t::_bstr_t((_bstr_t *)v35, (const struct _variant_t *)&v31);
      v27 = _bstr_t::operator+(v24, v34, v26);
      v28 = _bstr_t::_bstr_t((_bstr_t *)v33, "\n");
      _bstr_t::operator+(v27, &v30, v28);
      _bstr_t::_Free((_bstr_t *)v33);
      _bstr_t::_Free((_bstr_t *)v34);
      _bstr_t::_Free((_bstr_t *)v35);
      _variant_t::~_variant_t((_variant_t *)&v31);
      _bstr_t::_Free((_bstr_t *)v36);
      _bstr_t::_Free((_bstr_t *)v37);
      _bstr_t::_Free((_bstr_t *)v38);
      _bstr_t::_Free((_bstr_t *)v39);
      _bstr_t::_Free((_bstr_t *)v40);
      _bstr_t::_Free((_bstr_t *)v41);
      _bstr_t::_Free((_bstr_t *)v42);
      _bstr_t::_Free((_bstr_t *)v43);
      _bstr_t::_Free((_bstr_t *)v44);
      _bstr_t::_Free((_bstr_t *)v45);
      _bstr_t::_Free((_bstr_t *)v46);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("%S");
        if ( v30 )
          v29 = *v30;
        else
          v29 = 0;
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_35f0385197fd35cdb48f774109abba17_Traceguids,
          (unsigned int)"NPSDS",
          v29);
      }
      _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator=(a1);
      _bstr_t::_Free((_bstr_t *)&v30);
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      return -2147418113;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004d4c8  mov     rax, rsp
0x18004d4cb  mov     [rax+8], rbx
0x18004d4cf  push    rsi
0x18004d4d0  push    rdi
0x18004d4d1  push    r14
0x18004d4d3  sub     rsp, 0E0h
0x18004d4da  mov     rdi, rdx
0x18004d4dd  mov     rsi, rcx
0x18004d4e0  xor     ebx, ebx
0x18004d4e2  mov     [rax+20h], rbx
0x18004d4e6  lea     r9d, [rbx+17h]
0x18004d4ea  call    ?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance(_GUID const &,IUnknown *,ulong)
0x18004d4ef  test    eax, eax
0x18004d4f1  jns     short loc_18004D4F8
0x18004d4f3  jmp     loc_18004D8E3
0x18004d4f8  mov     rcx, rsi
0x18004d4fb  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004d500  mov     rcx, rax; this
0x18004d503  call    ?Putasync@IXMLDOMDocument@MSXML2@@QEAAXF@Z; MSXML2::IXMLDOMDocument::Putasync(short)
0x18004d508  mov     rcx, rsi
0x18004d50b  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004d510  mov     r14, rax
0x18004d513  mov     rdx, rdi; unsigned __int16 *
0x18004d516  lea     rcx, [rsp+0F8h+var_C0]; this
0x18004d51b  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18004d520  nop
0x18004d521  lea     rdx, [rsp+0F8h+var_C0]; struct _variant_t *
0x18004d526  mov     rcx, r14; this
0x18004d529  call    ?load@IXMLDOMDocument@MSXML2@@QEAAFAEBV_variant_t@@@Z; MSXML2::IXMLDOMDocument::load(_variant_t const &)
0x18004d52e  movzx   r14d, ax
0x18004d532  lea     rcx, [rsp+0F8h+var_C0]; this
0x18004d537  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004d53c  cmp     r14w, 0FFFFh
0x18004d541  jz      loc_18004D8BE
0x18004d547  lea     r14, WPP_GLOBAL_Control
0x18004d54e  mov     rax, cs:WPP_GLOBAL_Control
0x18004d555  cmp     rax, r14
0x18004d558  jz      short loc_18004D59D
0x18004d55a  cmp     byte ptr [rax+19h], 2
0x18004d55e  jb      short loc_18004D59D
0x18004d560  test    byte ptr [rax+1Ch], 10h
0x18004d564  jz      short loc_18004D59D
0x18004d566  mov     rdx, rdi
0x18004d569  lea     rcx, aCiasmigrationh; "CIASMigrationHelper::LoadXMLFromFile(),"...
0x18004d570  call    WppDbgPrint
0x18004d575  mov     edx, 0Ah
0x18004d57a  mov     [rsp+0F8h+var_D8], rdi
0x18004d57f  lea     r9, aNpsds; "NPSDS"
0x18004d586  lea     r8, WPP_35f0385197fd35cdb48f774109abba17_Traceguids
0x18004d58d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d594  mov     rcx, [rcx+10h]
0x18004d598  call    WPP_SF_sS
0x18004d59d  mov     rcx, rsi
0x18004d5a0  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004d5a5  lea     rdx, [rsp+0F8h+arg_10]
0x18004d5ad  mov     rcx, rax; struct IUnknown *
0x18004d5b0  call    ?GetparseError@IXMLDOMDocument@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMParseError@MSXML2@@$1?_GUID_3efaa426_272f_11d2_836f_0000f87a7782@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMDocument::GetparseError(void)
0x18004d5b5  nop
0x18004d5b6  cmp     qword ptr [rax], 0
0x18004d5ba  jz      short loc_18004D5D5
0x18004d5bc  mov     rbx, [rax]
0x18004d5bf  mov     [rsp+0F8h+arg_18], rbx
0x18004d5c7  lea     rcx, [rsp+0F8h+arg_18]
0x18004d5cf  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004d5d4  nop
0x18004d5d5  mov     rcx, [rsp+0F8h+arg_10]
0x18004d5dd  test    rcx, rcx
0x18004d5e0  jz      short loc_18004D5EF
0x18004d5e2  mov     rax, [rcx]
0x18004d5e5  mov     rax, [rax+10h]
0x18004d5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d5ee  nop
0x18004d5ef  lea     rdx, asc_180066E88; "\n====================="
0x18004d5f6  lea     rcx, [rsp+0F8h+var_40]; this
0x18004d5fe  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18004d603  mov     rdi, rax
0x18004d606  lea     rdx, aReason; "\nReason: "
0x18004d60d  lea     rcx, [rsp+0F8h+var_48]; this
0x18004d615  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18004d61a  nop
0x18004d61b  mov     r8, rax
0x18004d61e  lea     rdx, [rsp+0F8h+var_50]
0x18004d626  mov     rcx, rdi
0x18004d629  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004d62e  mov     rdi, rax
0x18004d631  lea     rcx, [rsp+0F8h+arg_18]
0x18004d639  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004d63e  lea     rdx, [rsp+0F8h+var_58]
0x18004d646  mov     rcx, rax
0x18004d649  call    ?Getreason@IXMLDOMParseError@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMParseError::Getreason(void)
0x18004d64e  nop
0x18004d64f  mov     r8, rax
0x18004d652  lea     rdx, [rsp+0F8h+var_60]
0x18004d65a  mov     rcx, rdi
0x18004d65d  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004d662  mov     rdi, rax
0x18004d665  lea     rdx, aSource; "\nSource: "
0x18004d66c  lea     rcx, [rsp+0F8h+var_68]; this
0x18004d674  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18004d679  nop
0x18004d67a  mov     r8, rax
0x18004d67d  lea     rdx, [rsp+0F8h+var_70]
0x18004d685  mov     rcx, rdi
0x18004d688  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004d68d  mov     rdi, rax
0x18004d690  lea     rcx, [rsp+0F8h+arg_18]
0x18004d698  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004d69d  lea     rdx, [rsp+0F8h+var_78]
0x18004d6a5  mov     rcx, rax
0x18004d6a8  call    ?GetsrcText@IXMLDOMParseError@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMParseError::GetsrcText(void)
0x18004d6ad  nop
0x18004d6ae  mov     r8, rax
0x18004d6b1  lea     rdx, [rsp+0F8h+var_80]
0x18004d6b6  mov     rcx, rdi
0x18004d6b9  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004d6be  mov     rdi, rax
0x18004d6c1  lea     rdx, aLine; "\nLine: "
0x18004d6c8  lea     rcx, [rsp+0F8h+var_88]; this
0x18004d6cd  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18004d6d2  nop
0x18004d6d3  mov     r8, rax
0x18004d6d6  lea     rdx, [rsp+0F8h+var_90]
0x18004d6db  mov     rcx, rdi
0x18004d6de  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004d6e3  mov     rdi, rax
0x18004d6e6  lea     rcx, [rsp+0F8h+arg_18]
0x18004d6ee  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004d6f3  mov     rcx, rax; this
0x18004d6f6  call    ?Getline@IXMLDOMParseError@MSXML2@@QEAAJXZ; MSXML2::IXMLDOMParseError::Getline(void)
0x18004d6fb  mov     dword ptr [rsp+0F8h+arg_10], eax
0x18004d702  mov     ecx, 3
0x18004d707  mov     [rsp+0F8h+var_C0], cx
0x18004d70c  mov     word ptr [rsp+0F8h+var_B8], ax
0x18004d711  movzx   eax, word ptr [rsp+0F8h+arg_10+2]
0x18004d719  mov     word ptr [rsp+0F8h+var_B8+2], ax
0x18004d71e  lea     rdx, [rsp+0F8h+var_C0]; struct _variant_t *
0x18004d723  lea     rcx, [rsp+0F8h+var_98]; this
0x18004d728  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x18004d72d  nop
0x18004d72e  mov     r8, rax
0x18004d731  lea     rdx, [rsp+0F8h+var_A0]
0x18004d736  mov     rcx, rdi
0x18004d739  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004d73e  mov     rdi, rax
0x18004d741  lea     rdx, asc_180066EC8; "\n"
0x18004d748  lea     rcx, [rsp+0F8h+var_A8]; this
0x18004d74d  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18004d752  nop
0x18004d753  mov     r8, rax
0x18004d756  lea     rdx, [rsp+0F8h+var_C8]
0x18004d75b  mov     rcx, rdi
0x18004d75e  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004d763  nop
0x18004d764  lea     rcx, [rsp+0F8h+var_A8]; this
0x18004d769  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d76e  nop
0x18004d76f  lea     rcx, [rsp+0F8h+var_A0]; this
0x18004d774  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d779  nop
0x18004d77a  lea     rcx, [rsp+0F8h+var_98]; this
0x18004d77f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d784  nop
0x18004d785  lea     rcx, [rsp+0F8h+var_C0]; this
0x18004d78a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004d78f  nop
0x18004d790  lea     rcx, [rsp+0F8h+var_90]; this
0x18004d795  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d79a  nop
0x18004d79b  lea     rcx, [rsp+0F8h+var_88]; this
0x18004d7a0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d7a5  nop
0x18004d7a6  lea     rcx, [rsp+0F8h+var_80]; this
0x18004d7ab  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d7b0  nop
0x18004d7b1  lea     rcx, [rsp+0F8h+var_78]; this
0x18004d7b9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d7be  nop
0x18004d7bf  lea     rcx, [rsp+0F8h+var_70]; this
0x18004d7c7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d7cc  nop
0x18004d7cd  lea     rcx, [rsp+0F8h+var_68]; this
0x18004d7d5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d7da  nop
0x18004d7db  lea     rcx, [rsp+0F8h+var_60]; this
0x18004d7e3  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d7e8  nop
0x18004d7e9  lea     rcx, [rsp+0F8h+var_58]; this
0x18004d7f1  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d7f6  nop
0x18004d7f7  lea     rcx, [rsp+0F8h+var_50]; this
0x18004d7ff  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d804  nop
0x18004d805  lea     rcx, [rsp+0F8h+var_48]; this
0x18004d80d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d812  nop
0x18004d813  lea     rcx, [rsp+0F8h+var_40]; this
0x18004d81b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d820  mov     rax, cs:WPP_GLOBAL_Control
0x18004d827  cmp     rax, r14
0x18004d82a  jz      short loc_18004D88E
0x18004d82c  cmp     byte ptr [rax+19h], 2
0x18004d830  jb      short loc_18004D88E
0x18004d832  test    byte ptr [rax+1Ch], 10h
0x18004d836  jz      short loc_18004D88E
0x18004d838  mov     rax, [rsp+0F8h+var_C8]
0x18004d83d  test    rax, rax
0x18004d840  jz      short loc_18004D847
0x18004d842  mov     rdx, [rax]
0x18004d845  jmp     short loc_18004D849
0x18004d847  xor     edx, edx
0x18004d849  lea     rcx, aS_0; "%S"
0x18004d850  call    WppDbgPrint
0x18004d855  mov     rax, [rsp+0F8h+var_C8]
0x18004d85a  test    rax, rax
0x18004d85d  jz      short loc_18004D864
0x18004d85f  mov     rcx, [rax]
0x18004d862  jmp     short loc_18004D866
0x18004d864  xor     ecx, ecx
0x18004d866  mov     edx, 0Bh
0x18004d86b  mov     [rsp+0F8h+var_D8], rcx
0x18004d870  lea     r9, aNpsds; "NPSDS"
0x18004d877  lea     r8, WPP_35f0385197fd35cdb48f774109abba17_Traceguids
0x18004d87e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d885  mov     rcx, [rcx+10h]
0x18004d889  call    WPP_SF_sS
0x18004d88e  mov     rcx, rsi
0x18004d891  call    ??4?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAAAEAV0@H@Z; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator=(int)
0x18004d896  nop
0x18004d897  lea     rcx, [rsp+0F8h+var_C8]; this
0x18004d89c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004d8a1  nop
0x18004d8a2  test    rbx, rbx
0x18004d8a5  jz      short loc_18004D8B7
0x18004d8a7  mov     rax, [rbx]
0x18004d8aa  mov     rcx, rbx
0x18004d8ad  mov     rax, [rax+10h]
0x18004d8b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8b6  nop
0x18004d8b7  mov     eax, 8000FFFFh
0x18004d8bc  jmp     short loc_18004D8E3
0x18004d8be  xor     eax, eax
0x18004d8c0  jmp     short loc_18004D8E3
0x18004d8c2  mov     rcx, [rsp+0F8h+arg_18]
0x18004d8ca  test    rcx, rcx
0x18004d8cd  jz      short loc_18004D8DC
0x18004d8cf  mov     rax, [rcx]
0x18004d8d2  mov     rax, [rax+10h]
0x18004d8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8db  nop
0x18004d8dc  mov     eax, dword ptr [rsp+0F8h+arg_10]
0x18004d8e3  mov     rbx, [rsp+0F8h+arg_0]
0x18004d8eb  add     rsp, 0E0h
0x18004d8f2  pop     r14
0x18004d8f4  pop     rdi
0x18004d8f5  pop     rsi
0x18004d8f6  retn
```
