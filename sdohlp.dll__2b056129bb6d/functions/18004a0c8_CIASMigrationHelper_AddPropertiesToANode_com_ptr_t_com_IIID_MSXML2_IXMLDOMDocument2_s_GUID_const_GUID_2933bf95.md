# CIASMigrationHelper::AddPropertiesToANode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,ushort *,ushort *,ushort *)

- ea: `0x18004a0c8`
- end: `0x18004a3aa`
- name: `?AddPropertiesToANode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEAG22@Z`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004a3b0`

## callees

- `0x180024cac`
- `0x18002d08c`
- `0x18002f240`
- `0x1800475b8`
- `0x180047604`
- `0x1800481d0`
- `0x180048b24`
- `0x18004a0c8`
- `0x180050044`
- `0x180050e80`
- `0x1800510f8`
- `0x180052588`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18004a0f6`
- `OLEAUT32!__imp_VariantInit` at `0x18004a0f6`
- `OLEAUT32!__imp_VariantClear` at `0x18004a1d2`
- `OLEAUT32!__imp_VariantClear` at `0x18004a21a`
- `OLEAUT32!__imp_VariantClear` at `0x18004a28b`
- `OLEAUT32!__imp_VariantClear` at `0x18004a304`
- `OLEAUT32!__imp_VariantClear` at `0x18004a353`
- `OLEAUT32!__imp_VariantClear` at `0x18004a38c`
- `OLEAUT32!__imp_VariantClear` at `0x18004a1d2`
- `OLEAUT32!__imp_VariantClear` at `0x18004a21a`
- `OLEAUT32!__imp_VariantClear` at `0x18004a28b`
- `OLEAUT32!__imp_VariantClear` at `0x18004a304`
- `OLEAUT32!__imp_VariantClear` at `0x18004a353`
- `OLEAUT32!__imp_VariantClear` at `0x18004a38c`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CIASMigrationHelper::AddPropertiesToANode(
        __int64 *a1,
        __int64 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5)
{
  __int64 v9; // rbx
  struct IUnknown *v10; // r14
  _bstr_t *v11; // rsi
  __int64 Node; // rax
  __int64 v14; // rax
  int v15; // esi
  __int64 v16; // r14
  __int64 (__fastcall *v17)(__int64, __int128 *); // rsi
  _variant_t *v18; // rax
  struct IUnknown *v19; // rsi
  _bstr_t *v20; // rax
  __int64 *v21; // rax
  struct IUnknown *v22; // rax
  __int64 v23; // rdi
  __int64 v24; // [rsp+30h] [rbp-91h] BYREF
  _BYTE *v25; // [rsp+38h] [rbp-89h] BYREF
  __int64 v26; // [rsp+40h] [rbp-81h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-79h] BYREF
  _BYTE *v28; // [rsp+60h] [rbp-61h] BYREF
  _BYTE v29[8]; // [rsp+68h] [rbp-59h] BYREF
  _BYTE v30[8]; // [rsp+70h] [rbp-51h] BYREF
  __int64 v31; // [rsp+78h] [rbp-49h]
  VARIANTARG pvargDest; // [rsp+88h] [rbp-39h] BYREF
  __int128 v33; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v34; // [rsp+B0h] [rbp-11h]
  _BYTE v35[80]; // [rsp+C0h] [rbp-1h] BYREF

  v9 = 0;
  v26 = 0;
  VariantInit(&pvarg);
  if ( a3 && a4 && a5 )
  {
    pvarg.vt = 3;
    pvarg.lVal = 1;
    v10 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
    v25 = v29;
    v11 = _bstr_t::_bstr_t((_bstr_t *)v29, &dword_180066E34);
    v28 = v30;
    _bstr_t::_bstr_t((_bstr_t *)v30, a3);
    _variant_t::_variant_t(&pvargDest, &pvarg);
    Node = MSXML2::IXMLDOMDocument::createNode(v10, v11);
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>(
      &v24,
      Node);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    _variant_t::~_variant_t((_variant_t *)&pvargDest);
    if ( !v24 )
      goto LABEL_7;
    v14 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v24);
    v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 264LL))(v14, a4);
    if ( v15 < 0
      || (v16 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v24),
          v17 = *(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v16 + 248LL),
          v18 = _variant_t::_variant_t((_variant_t *)v35, a5),
          v33 = *(_OWORD *)v18,
          v34 = *((_QWORD *)v18 + 2),
          v15 = v17(v16, &v33),
          _variant_t::~_variant_t((_variant_t *)v35),
          v15 < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
      VariantClear(&pvarg);
      return (unsigned int)v15;
    }
    else
    {
      v19 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a2);
      v20 = _bstr_t::_bstr_t((_bstr_t *)&v28, L"./Properties");
      v21 = MSXML2::IXMLDOMNode::selectSingleNode(v19, &v25, v20);
      if ( *v21 )
      {
        v9 = *v21;
        v26 = *v21;
        _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v26);
      }
      if ( v25 )
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v25 + 16LL))(v25);
      if ( !v9 )
      {
LABEL_7:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
        VariantClear(&pvarg);
        return 2147549183LL;
      }
      v22 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v26);
      v23 = *(_QWORD *)MSXML2::IXMLDOMNode::appendChild(v22);
      if ( v25 )
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v25 + 16LL))(v25);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
      VariantClear(&pvarg);
      if ( !v23 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        return 2147549183LL;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      return 0;
    }
  }
  else
  {
    VariantClear(&pvarg);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18004a0c8  push    rbp
0x18004a0ca  push    rbx
0x18004a0cb  push    rsi
0x18004a0cc  push    rdi
0x18004a0cd  push    r13
0x18004a0cf  push    r14
0x18004a0d1  push    r15
0x18004a0d3  lea     rbp, [rsp-1Fh]
0x18004a0d8  sub     rsp, 0E0h
0x18004a0df  mov     r15, r9
0x18004a0e2  mov     rdi, r8
0x18004a0e5  mov     r13, rdx
0x18004a0e8  mov     rsi, rcx
0x18004a0eb  xor     ebx, ebx
0x18004a0ed  mov     [rsp+110h+var_D0], rbx
0x18004a0f2  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18004a0f6  call    cs:__imp_VariantInit
0x18004a0fc  nop
0x18004a0fd  test    rdi, rdi
0x18004a100  jz      loc_18004A388
0x18004a106  test    r15, r15
0x18004a109  jz      loc_18004A388
0x18004a10f  cmp     [rbp+4Fh+arg_20], rbx
0x18004a113  jz      loc_18004A388
0x18004a119  lea     eax, [rbx+3]
0x18004a11c  mov     word ptr [rbp+4Fh+pvarg], ax
0x18004a120  mov     dword ptr [rbp+4Fh+pvarg+8], 1
0x18004a127  mov     rcx, rsi
0x18004a12a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004a12f  mov     r14, rax
0x18004a132  lea     rax, [rbp+4Fh+var_A8]
0x18004a136  mov     [rsp+110h+var_D8], rax
0x18004a13b  lea     rdx, dword_180066E34; unsigned __int16 *
0x18004a142  lea     rcx, [rbp+4Fh+var_A8]; this
0x18004a146  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004a14b  mov     rsi, rax
0x18004a14e  lea     rax, [rbp+4Fh+var_A0]
0x18004a152  mov     [rbp+4Fh+var_B0], rax
0x18004a156  mov     rdx, rdi; unsigned __int16 *
0x18004a159  lea     rcx, [rbp+4Fh+var_A0]; this
0x18004a15d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004a162  mov     rdi, rax
0x18004a165  lea     rdx, [rbp+4Fh+pvarg]; pvargSrc
0x18004a169  lea     rcx, [rbp+4Fh+pvargDest]; pvargDest
0x18004a16d  call    ??0_variant_t@@QEAA@AEBUtagVARIANT@@@Z; _variant_t::_variant_t(tagVARIANT const &)
0x18004a172  nop
0x18004a173  mov     [rsp+110h+var_F0], rsi; _bstr_t *
0x18004a178  mov     r9, rdi
0x18004a17b  lea     r8, [rbp+4Fh+pvargDest]
0x18004a17f  lea     rdx, [rbp+4Fh+var_98]
0x18004a183  mov     rcx, r14; struct IUnknown *
0x18004a186  call    ?createNode@IXMLDOMDocument@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEBV_variant_t@@V_bstr_t@@1@Z; MSXML2::IXMLDOMDocument::createNode(_variant_t const &,_bstr_t,_bstr_t)
0x18004a18b  nop
0x18004a18c  mov     rdx, rax
0x18004a18f  lea     rcx, [rsp+110h+var_E0]
0x18004a194  call    ??$?0V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> const &)
0x18004a199  nop
0x18004a19a  mov     rcx, [rbp+4Fh+var_98]
0x18004a19e  test    rcx, rcx
0x18004a1a1  jz      short loc_18004A1B0
0x18004a1a3  mov     rax, [rcx]
0x18004a1a6  mov     rax, [rax+10h]
0x18004a1aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1af  nop
0x18004a1b0  lea     rcx, [rbp+4Fh+pvargDest]; this
0x18004a1b4  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004a1b9  mov     rdi, [rsp+110h+var_E0]
0x18004a1be  test    rdi, rdi
0x18004a1c1  jnz     short loc_18004A1E3
0x18004a1c3  lea     rcx, [rsp+110h+var_E0]
0x18004a1c8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004a1cd  nop
0x18004a1ce  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18004a1d2  call    cs:__imp_VariantClear
0x18004a1d8  nop
0x18004a1d9  mov     eax, 8000FFFFh
0x18004a1de  jmp     loc_18004A398
0x18004a1e3  lea     rcx, [rsp+110h+var_E0]
0x18004a1e8  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004a1ed  mov     r8, rax
0x18004a1f0  mov     rcx, [rax]
0x18004a1f3  mov     rax, [rcx+108h]
0x18004a1fa  mov     rdx, r15
0x18004a1fd  mov     rcx, r8
0x18004a200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a205  mov     esi, eax
0x18004a207  test    eax, eax
0x18004a209  jns     short loc_18004A228
0x18004a20b  lea     rcx, [rsp+110h+var_E0]
0x18004a210  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004a215  nop
0x18004a216  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18004a21a  call    cs:__imp_VariantClear
0x18004a220  nop
0x18004a221  mov     eax, esi
0x18004a223  jmp     loc_18004A398
0x18004a228  lea     rcx, [rsp+110h+var_E0]
0x18004a22d  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004a232  mov     r14, rax
0x18004a235  mov     rcx, [rax]
0x18004a238  mov     rsi, [rcx+0F8h]
0x18004a23f  mov     rdx, [rbp+4Fh+arg_20]; unsigned __int16 *
0x18004a243  lea     rcx, [rbp+4Fh+var_50]; this
0x18004a247  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18004a24c  nop
0x18004a24d  movups  xmm0, xmmword ptr [rax]
0x18004a250  movaps  [rbp+4Fh+var_70], xmm0
0x18004a254  movsd   xmm1, qword ptr [rax+10h]
0x18004a259  movsd   [rbp+4Fh+var_60], xmm1
0x18004a25e  lea     rdx, [rbp+4Fh+var_70]
0x18004a262  mov     rcx, r14
0x18004a265  mov     rax, rsi
0x18004a268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a26d  mov     esi, eax
0x18004a26f  lea     rcx, [rbp+4Fh+var_50]; this
0x18004a273  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004a278  test    esi, esi
0x18004a27a  jns     short loc_18004A294
0x18004a27c  lea     rcx, [rsp+110h+var_E0]
0x18004a281  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004a286  nop
0x18004a287  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18004a28b  call    cs:__imp_VariantClear
0x18004a291  nop
0x18004a292  jmp     short loc_18004A221
0x18004a294  mov     rcx, r13
0x18004a297  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004a29c  mov     rsi, rax
0x18004a29f  lea     rdx, ?m_migPropertiesQuery@CIASMigrationHelper@@1QBGB; "./Properties"
0x18004a2a6  lea     rcx, [rbp+4Fh+var_B0]; this
0x18004a2aa  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004a2af  mov     r8, rax
0x18004a2b2  lea     rdx, [rsp+110h+var_D8]
0x18004a2b7  mov     rcx, rsi; struct IUnknown *
0x18004a2ba  call    ?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)
0x18004a2bf  nop
0x18004a2c0  cmp     qword ptr [rax], 0
0x18004a2c4  jz      short loc_18004A2D9
0x18004a2c6  mov     rbx, [rax]
0x18004a2c9  mov     [rsp+110h+var_D0], rbx
0x18004a2ce  lea     rcx, [rsp+110h+var_D0]
0x18004a2d3  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004a2d8  nop
0x18004a2d9  mov     rcx, [rsp+110h+var_D8]
0x18004a2de  test    rcx, rcx
0x18004a2e1  jz      short loc_18004A2F0
0x18004a2e3  mov     rax, [rcx]
0x18004a2e6  mov     rax, [rax+10h]
0x18004a2ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a2ef  nop
0x18004a2f0  test    rbx, rbx
0x18004a2f3  jnz     short loc_18004A310
0x18004a2f5  lea     rcx, [rsp+110h+var_E0]
0x18004a2fa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004a2ff  nop
0x18004a300  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18004a304  call    cs:__imp_VariantClear
0x18004a30a  nop
0x18004a30b  jmp     loc_18004A1D9
0x18004a310  lea     rcx, [rsp+110h+var_D0]
0x18004a315  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004a31a  mov     r8, rdi
0x18004a31d  lea     rdx, [rsp+110h+var_D8]
0x18004a322  mov     rcx, rax; struct IUnknown *
0x18004a325  call    ?appendChild@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEAU12@@Z; MSXML2::IXMLDOMNode::appendChild(MSXML2::IXMLDOMNode *)
0x18004a32a  mov     rdi, [rax]
0x18004a32d  mov     rcx, [rsp+110h+var_D8]
0x18004a332  test    rcx, rcx
0x18004a335  jz      short loc_18004A344
0x18004a337  mov     rax, [rcx]
0x18004a33a  mov     rax, [rax+10h]
0x18004a33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a343  nop
0x18004a344  lea     rcx, [rsp+110h+var_E0]
0x18004a349  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004a34e  nop
0x18004a34f  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18004a353  call    cs:__imp_VariantClear
0x18004a359  nop
0x18004a35a  test    rdi, rdi
0x18004a35d  jnz     short loc_18004A374
0x18004a35f  mov     rax, [rbx]
0x18004a362  mov     rcx, rbx
0x18004a365  mov     rax, [rax+10h]
0x18004a369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a36e  nop
0x18004a36f  jmp     loc_18004A1D9
0x18004a374  mov     rax, [rbx]
0x18004a377  mov     rcx, rbx
0x18004a37a  mov     rax, [rax+10h]
0x18004a37e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a383  nop
0x18004a384  xor     eax, eax
0x18004a386  jmp     short loc_18004A398
0x18004a388  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18004a38c  call    cs:__imp_VariantClear
0x18004a392  nop
0x18004a393  mov     eax, 80070057h
0x18004a398  add     rsp, 0E0h
0x18004a39f  pop     r15
0x18004a3a1  pop     r14
0x18004a3a3  pop     r13
0x18004a3a5  pop     rdi
0x18004a3a6  pop     rsi
0x18004a3a7  pop     rbx
0x18004a3a8  pop     rbp
0x18004a3a9  retn
```
