# CSpResult::GetAlternateXML(ushort * *)

- ea: `0x180127b64`
- end: `0x180128186`
- name: `?GetAlternateXML@CSpResult@@AEAAJPEAPEAG@Z`
- size: `1570`
- prototype: `__int64 __fastcall(CSpResult *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180128aa0`

## callees

- `0x18000a590`
- `0x18000bec4`
- `0x18000cdb0`
- `0x18001ae00`
- `0x180126754`
- `0x180127b64`
- `0x18028b010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180127c43`
- `OLEAUT32!__imp_SysFreeString` at `0x180127d30`
- `OLEAUT32!__imp_SysFreeString` at `0x180127dd5`
- `OLEAUT32!__imp_SysFreeString` at `0x180127e86`
- `OLEAUT32!__imp_SysFreeString` at `0x180127fbe`
- `OLEAUT32!__imp_SysFreeString` at `0x18012814e`
- `OLEAUT32!__imp_SysFreeString` at `0x180127c43`
- `OLEAUT32!__imp_SysFreeString` at `0x180127d30`
- `OLEAUT32!__imp_SysFreeString` at `0x180127dd5`
- `OLEAUT32!__imp_SysFreeString` at `0x180127e86`
- `OLEAUT32!__imp_SysFreeString` at `0x180127fbe`
- `OLEAUT32!__imp_SysFreeString` at `0x18012814e`
- `OLEAUT32!__imp_VariantInit` at `0x180127f26`
- `OLEAUT32!__imp_VariantInit` at `0x180127f26`
- `OLEAUT32!__imp_VariantClear` at `0x180127dca`
- `OLEAUT32!__imp_VariantClear` at `0x180127fb2`
- `OLEAUT32!__imp_VariantClear` at `0x180127dca`
- `OLEAUT32!__imp_VariantClear` at `0x180127fb2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180127bb3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180127cbb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180127bb3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180127cbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CSpResult::GetAlternateXML(CSpResult *this, unsigned __int16 **a2)
{
  unsigned __int16 **v2; // r13
  HRESULT v4; // ebx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, _QWORD, unsigned __int16 **); // rbx
  _QWORD *v7; // rax
  unsigned int v8; // r12d
  _QWORD *v9; // r15
  unsigned int v10; // r14d
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, _QWORD, __int64 *); // rbx
  _QWORD *v13; // rax
  __int64 v14; // rax
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, _QWORD, unsigned __int16 **); // rbx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  int i; // edi
  int j; // edi
  unsigned __int16 *v21; // rax
  LPVOID ppv; // [rsp+30h] [rbp-89h] BYREF
  BSTR v24; // [rsp+38h] [rbp-81h] BYREF
  __int64 v25; // [rsp+40h] [rbp-79h] BYREF
  __int64 v26; // [rsp+48h] [rbp-71h] BYREF
  LPVOID v27; // [rsp+50h] [rbp-69h] BYREF
  __int64 v28; // [rsp+58h] [rbp-61h] BYREF
  __int64 v29; // [rsp+60h] [rbp-59h] BYREF
  __int64 v30; // [rsp+68h] [rbp-51h] BYREF
  __int64 v31; // [rsp+70h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int16 *v33; // [rsp+80h] [rbp-39h] BYREF
  __int64 v34; // [rsp+88h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-29h] BYREF
  BSTR v36; // [rsp+A8h] [rbp-11h] BYREF
  BSTR v37[2]; // [rsp+B0h] [rbp-9h] BYREF
  VARIANTARG v38[3]; // [rsp+C0h] [rbp+7h] BYREF
  unsigned __int16 *v40; // [rsp+130h] [rbp+77h] BYREF
  BSTR v41; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = a2;
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, &ppv);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
    if ( v4 >= 0 )
    {
      v41 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, BSTR *, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 13) + 8LL) + 56LL))(
             *((_QWORD *)this + 13) + 8LL,
             &v41,
             0);
      if ( v4 >= 0 )
      {
        LOWORD(v40) = 0;
        v5 = ppv;
        v6 = *(__int64 (__fastcall **)(LPVOID, _QWORD, unsigned __int16 **))(*(_QWORD *)ppv + 520LL);
        v7 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v41);
        v4 = v6(v5, *v7, &v40);
        SysFreeString(bstrString);
        if ( v4 >= 0 && !(_WORD)v40 )
          v4 = -2147467259;
      }
      SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v41);
    }
  }
  v31 = 0;
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 104LL))(ppv, &v31);
    if ( v4 >= 0 )
    {
      if ( v31 )
      {
        v27 = 0;
        v4 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, &v27);
        v8 = *((_DWORD *)this + 46);
        v9 = (_QWORD *)*((_QWORD *)this + 21);
        v10 = 1;
        if ( v4 >= 0 )
        {
          do
          {
            if ( v10 > v8 )
              break;
            v26 = 0;
            v30 = 0;
            v11 = ppv;
            v12 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 376LL);
            v13 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v36, L"alternate");
            v4 = v12(v11, *v13, &v26);
            SysFreeString(v36);
            if ( v4 >= 0 )
            {
              v4 = ATL::CComPtrBase<IXMLDOMElement>::QueryInterface<IXMLDOMNode>(&v26, &v30);
              if ( v4 >= 0 )
              {
                v4 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v31 + 168LL))(v31, v30, 0);
                if ( v4 >= 0 )
                {
                  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"Rank");
                  pvarg.vt = 3;
                  pvarg.lVal = v10;
                  v38[0] = pvarg;
                  v4 = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v26 + 360LL))(
                         v26,
                         bstrString,
                         v38);
                  VariantClear(&pvarg);
                  SysFreeString(bstrString);
                  if ( v4 >= 0 )
                  {
                    v14 = v9[2];
                    v9 = (_QWORD *)*v9;
                    v34 = 0;
                    v4 = (****(__int64 (__fastcall *****)(_QWORD, GUID *, __int64 *))(v14 + 72))(
                           **(_QWORD **)(v14 + 72),
                           &GUID_f264da52_e457_4696_b856_a737b717af79,
                           &v34);
                    if ( v4 >= 0 )
                      v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v27 + 504LL))(v27, 0);
                    v33 = 0;
                    if ( v4 >= 0 )
                    {
                      v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, _QWORD))(*(_QWORD *)v34 + 56LL))(
                             v34,
                             &v33,
                             0);
                      if ( v4 >= 0 )
                      {
                        LOWORD(v40) = 0;
                        v15 = v27;
                        v16 = *(__int64 (__fastcall **)(LPVOID, _QWORD, unsigned __int16 **))(*(_QWORD *)v27 + 520LL);
                        v17 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v37, v33);
                        v4 = v16(v15, *v17, &v40);
                        SysFreeString(v37[0]);
                        if ( v4 >= 0 && !(_WORD)v40 )
                          v4 = -2147467259;
                      }
                    }
                    v25 = 0;
                    if ( v4 >= 0 )
                    {
                      v4 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v27 + 104LL))(v27, &v25);
                      if ( v4 >= 0 && !v25 )
                        v4 = -2147418113;
                    }
                    v18 = 0;
                    v29 = 0;
                    if ( v4 >= 0 )
                    {
                      v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 136LL))(v25, &v29);
                      v18 = v29;
                    }
                    LODWORD(v41) = 0;
                    if ( v4 >= 0 )
                      v4 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v18 + 88LL))(v18, &v41);
                    for ( i = 0; v4 >= 0 && i < (int)v41; ++i )
                    {
                      v40 = 0;
                      v24 = 0;
                      VariantInit(&pvarg);
                      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 **))(*(_QWORD *)v29 + 80LL))(
                             v29,
                             (unsigned int)i,
                             &v40);
                      if ( v4 >= 0 )
                      {
                        v4 = (*(__int64 (__fastcall **)(unsigned __int16 *, BSTR *))(*(_QWORD *)v40 + 56LL))(v40, &v24);
                        if ( v4 >= 0 )
                        {
                          v4 = (*(__int64 (__fastcall **)(unsigned __int16 *, VARIANTARG *))(*(_QWORD *)v40 + 64LL))(
                                 v40,
                                 &pvarg);
                          if ( v4 >= 0 )
                          {
                            v38[0] = pvarg;
                            v4 = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v26 + 360LL))(
                                   v26,
                                   v24,
                                   v38);
                          }
                        }
                      }
                      VariantClear(&pvarg);
                      SysFreeString(v24);
                      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v40);
                    }
                    v28 = 0;
                    if ( v4 >= 0 )
                    {
                      v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 96LL))(v25, &v28);
                      if ( v4 >= 0 )
                        v4 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v28 + 64LL))(v28, &v41);
                    }
                    for ( j = 0; v4 >= 0 && j < (int)v41; ++j )
                    {
                      v24 = 0;
                      v40 = 0;
                      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v28 + 56LL))(
                             v28,
                             (unsigned int)j,
                             &v24);
                      if ( v4 >= 0 )
                      {
                        v4 = (*(__int64 (__fastcall **)(BSTR, __int64, unsigned __int16 **))(*(_QWORD *)v24 + 192LL))(
                               v24,
                               0xFFFFFFFFLL,
                               &v40);
                        if ( v4 >= 0 )
                          v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD))(*(_QWORD *)v30 + 168LL))(
                                 v30,
                                 v40,
                                 0);
                      }
                      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v40);
                      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v24);
                    }
                    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v28);
                    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v29);
                    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v25);
                    SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v33);
                    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v34);
                  }
                }
              }
            }
            ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v30);
            ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v26);
            ++v10;
          }
          while ( v4 >= 0 );
          v2 = a2;
        }
        ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v27);
        if ( v4 >= 0 )
        {
          v41 = 0;
          v4 = (*(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)ppv + 272LL))(ppv, &v41);
          v40 = 0;
          CSpDynamicString::operator=(&v40, v41);
          v21 = v40;
          v40 = 0;
          *v2 = v21;
          SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v40);
          SysFreeString(v41);
        }
      }
      else
      {
        v4 = -2147418113;
      }
    }
  }
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v31);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180127b64  mov     [rsp-8+arg_0], rbx
0x180127b69  mov     [rsp-8+arg_8], rdx
0x180127b6e  push    rbp
0x180127b6f  push    rsi
0x180127b70  push    rdi
0x180127b71  push    r12
0x180127b73  push    r13
0x180127b75  push    r14
0x180127b77  push    r15
0x180127b79  lea     rbp, [rsp-27h]
0x180127b7e  sub     rsp, 0E0h
0x180127b85  mov     r13, rdx
0x180127b88  mov     rsi, rcx
0x180127b8b  xor     edi, edi
0x180127b8d  mov     [rsp+110h+var_E0], rdi
0x180127b92  lea     rax, [rsp+110h+var_E0]
0x180127b97  mov     [rsp+110h+ppv], rax; ppv
0x180127b9c  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x180127ba3  lea     r14d, [rdi+17h]
0x180127ba7  mov     r8d, r14d; dwClsContext
0x180127baa  xor     edx, edx; pUnkOuter
0x180127bac  lea     rcx, CLSID_DOMDocument60; rclsid
0x180127bb3  call    cs:__imp_CoCreateInstance
0x180127bb9  mov     ebx, eax
0x180127bbb  mov     r15d, 80004005h
0x180127bc1  test    eax, eax
0x180127bc3  js      loc_180127C60
0x180127bc9  mov     rcx, [rsp+110h+var_E0]
0x180127bce  mov     rax, [rcx]
0x180127bd1  xor     edx, edx
0x180127bd3  mov     rax, [rax+1F8h]
0x180127bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127bdf  mov     ebx, eax
0x180127be1  test    eax, eax
0x180127be3  js      short loc_180127C60
0x180127be5  mov     [rbp+57h+arg_18], rdi
0x180127be9  mov     rcx, [rsi+68h]
0x180127bed  add     rcx, 8
0x180127bf1  mov     rax, [rcx]
0x180127bf4  xor     r8d, r8d
0x180127bf7  lea     rdx, [rbp+57h+arg_18]
0x180127bfb  mov     rax, [rax+38h]
0x180127bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127c04  mov     ebx, eax
0x180127c06  test    eax, eax
0x180127c08  js      short loc_180127C57
0x180127c0a  mov     word ptr [rbp+57h+arg_10], di
0x180127c0e  mov     rdi, [rsp+110h+var_E0]
0x180127c13  mov     rax, [rdi]
0x180127c16  mov     rbx, [rax+208h]
0x180127c1d  mov     rdx, [rbp+57h+arg_18]; unsigned __int16 *
0x180127c21  lea     rcx, [rbp+57h+bstrString]; this
0x180127c25  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180127c2a  nop
0x180127c2b  lea     r8, [rbp+57h+arg_10]
0x180127c2f  mov     rdx, [rax]
0x180127c32  mov     rcx, rdi
0x180127c35  mov     rax, rbx
0x180127c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127c3d  mov     ebx, eax
0x180127c3f  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180127c43  call    cs:__imp_SysFreeString
0x180127c49  xor     edi, edi
0x180127c4b  test    ebx, ebx
0x180127c4d  js      short loc_180127C57
0x180127c4f  cmp     word ptr [rbp+57h+arg_10], di
0x180127c53  cmovz   ebx, r15d
0x180127c57  lea     rcx, [rbp+57h+arg_18]; this
0x180127c5b  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x180127c60  mov     [rbp+57h+var_A0], rdi
0x180127c64  test    ebx, ebx
0x180127c66  js      loc_180128155
0x180127c6c  mov     rcx, [rsp+110h+var_E0]
0x180127c71  mov     rax, [rcx]
0x180127c74  lea     rdx, [rbp+57h+var_A0]
0x180127c78  mov     rax, [rax+68h]
0x180127c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127c81  mov     ebx, eax
0x180127c83  test    eax, eax
0x180127c85  js      loc_180128155
0x180127c8b  cmp     [rbp+57h+var_A0], rdi
0x180127c8f  jnz     short loc_180127C9B
0x180127c91  mov     ebx, 8000FFFFh
0x180127c96  jmp     loc_180128155
0x180127c9b  mov     [rbp+57h+var_C0], rdi
0x180127c9f  lea     rax, [rbp+57h+var_C0]
0x180127ca3  mov     [rsp+110h+ppv], rax; ppv
0x180127ca8  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x180127caf  mov     r8d, r14d; dwClsContext
0x180127cb2  xor     edx, edx; pUnkOuter
0x180127cb4  lea     rcx, CLSID_DOMDocument60; rclsid
0x180127cbb  call    cs:__imp_CoCreateInstance
0x180127cc1  mov     ebx, eax
0x180127cc3  mov     r12d, [rsi+0B8h]
0x180127cca  mov     r15, [rsi+0A8h]
0x180127cd1  mov     r14d, 1
0x180127cd7  test    eax, eax
0x180127cd9  js      loc_1801280F8
0x180127cdf  mov     esi, 8000FFFFh
0x180127ce4  xor     r13d, r13d
0x180127ce7  cmp     r14d, r12d
0x180127cea  ja      loc_1801280F2
0x180127cf0  mov     [rbp+57h+var_C8], r13
0x180127cf4  mov     [rbp+57h+var_A8], r13
0x180127cf8  mov     rdi, [rsp+110h+var_E0]
0x180127cfd  mov     rax, [rdi]
0x180127d00  mov     rbx, [rax+178h]
0x180127d07  lea     rdx, aAlternate; "alternate"
0x180127d0e  lea     rcx, [rbp+57h+var_68]; this
0x180127d12  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180127d17  nop
0x180127d18  lea     r8, [rbp+57h+var_C8]
0x180127d1c  mov     rdx, [rax]
0x180127d1f  mov     rcx, rdi
0x180127d22  mov     rax, rbx
0x180127d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127d2a  mov     ebx, eax
0x180127d2c  mov     rcx, [rbp+57h+var_68]; bstrString
0x180127d30  call    cs:__imp_SysFreeString
0x180127d36  test    ebx, ebx
0x180127d38  js      loc_1801280D4
0x180127d3e  lea     rdx, [rbp+57h+var_A8]
0x180127d42  lea     rcx, [rbp+57h+var_C8]
0x180127d46  call    ??$QueryInterface@UIXMLDOMNode@@@?$CComPtrBase@UIXMLDOMElement@@@ATL@@QEBAJPEAPEAUIXMLDOMNode@@@Z; ATL::CComPtrBase<IXMLDOMElement>::QueryInterface<IXMLDOMNode>(IXMLDOMNode * *)
0x180127d4b  mov     ebx, eax
0x180127d4d  test    eax, eax
0x180127d4f  js      loc_1801280D4
0x180127d55  mov     rcx, [rbp+57h+var_A0]
0x180127d59  mov     rax, [rcx]
0x180127d5c  xor     r8d, r8d
0x180127d5f  mov     rdx, [rbp+57h+var_A8]
0x180127d63  mov     rax, [rax+0A8h]
0x180127d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127d6f  mov     ebx, eax
0x180127d71  test    eax, eax
0x180127d73  js      loc_1801280D4
0x180127d79  lea     rdx, aRank; "Rank"
0x180127d80  lea     rcx, [rbp+57h+bstrString]; this
0x180127d84  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180127d89  nop
0x180127d8a  mov     eax, 3
0x180127d8f  mov     word ptr [rbp+57h+pvarg], ax
0x180127d93  mov     dword ptr [rbp+57h+pvarg+8], r14d
0x180127d97  mov     rcx, [rbp+57h+var_C8]
0x180127d9b  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180127d9f  movaps  [rbp+57h+var_50], xmm0
0x180127da3  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180127da8  movsd   [rbp+57h+var_40], xmm1
0x180127dad  mov     rax, [rcx]
0x180127db0  lea     r8, [rbp+57h+var_50]
0x180127db4  mov     rdx, [rbp+57h+bstrString]
0x180127db8  mov     rax, [rax+168h]
0x180127dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127dc4  mov     ebx, eax
0x180127dc6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180127dca  call    cs:__imp_VariantClear
0x180127dd0  nop
0x180127dd1  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180127dd5  call    cs:__imp_SysFreeString
0x180127ddb  test    ebx, ebx
0x180127ddd  js      loc_1801280D4
0x180127de3  mov     rax, [r15+10h]
0x180127de7  mov     r15, [r15]
0x180127dea  mov     [rbp+57h+var_88], r13
0x180127dee  mov     rax, [rax+48h]
0x180127df2  mov     rcx, [rax]
0x180127df5  mov     rax, [rcx]
0x180127df8  lea     r8, [rbp+57h+var_88]
0x180127dfc  lea     rdx, _GUID_f264da52_e457_4696_b856_a737b717af79
0x180127e03  mov     rax, [rax]
0x180127e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127e0b  mov     ebx, eax
0x180127e0d  test    eax, eax
0x180127e0f  js      short loc_180127E28
0x180127e11  mov     rcx, [rbp+57h+var_C0]
0x180127e15  mov     rax, [rcx]
0x180127e18  xor     edx, edx
0x180127e1a  mov     rax, [rax+1F8h]
0x180127e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127e26  mov     ebx, eax
0x180127e28  mov     [rbp+57h+var_90], r13
0x180127e2c  test    ebx, ebx
0x180127e2e  js      short loc_180127E9D
0x180127e30  mov     rcx, [rbp+57h+var_88]
0x180127e34  mov     rax, [rcx]
0x180127e37  xor     r8d, r8d
0x180127e3a  lea     rdx, [rbp+57h+var_90]
0x180127e3e  mov     rax, [rax+38h]
0x180127e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127e47  mov     ebx, eax
0x180127e49  test    eax, eax
0x180127e4b  js      short loc_180127E9D
0x180127e4d  mov     word ptr [rbp+57h+arg_10], r13w
0x180127e52  mov     rdi, [rbp+57h+var_C0]
0x180127e56  mov     rax, [rdi]
0x180127e59  mov     rbx, [rax+208h]
0x180127e60  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x180127e64  lea     rcx, [rbp+57h+var_60]; this
0x180127e68  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180127e6d  nop
0x180127e6e  lea     r8, [rbp+57h+arg_10]
0x180127e72  mov     rdx, [rax]
0x180127e75  mov     rcx, rdi
0x180127e78  mov     rax, rbx
0x180127e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127e80  mov     ebx, eax
0x180127e82  mov     rcx, [rbp+57h+var_60]; bstrString
0x180127e86  call    cs:__imp_SysFreeString
0x180127e8c  test    ebx, ebx
0x180127e8e  js      short loc_180127E9D
0x180127e90  cmp     word ptr [rbp+57h+arg_10], r13w
0x180127e95  mov     eax, 80004005h
0x180127e9a  cmovz   ebx, eax
0x180127e9d  mov     [rbp+57h+var_D0], r13
0x180127ea1  test    ebx, ebx
0x180127ea3  js      short loc_180127EC6
0x180127ea5  mov     rcx, [rbp+57h+var_C0]
0x180127ea9  mov     rax, [rcx]
0x180127eac  lea     rdx, [rbp+57h+var_D0]
0x180127eb0  mov     rax, [rax+68h]
0x180127eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127eb9  mov     ebx, eax
0x180127ebb  test    eax, eax
0x180127ebd  js      short loc_180127EC6
0x180127ebf  cmp     [rbp+57h+var_D0], r13
0x180127ec3  cmovz   ebx, esi
0x180127ec6  mov     rcx, r13
0x180127ec9  mov     [rbp+57h+var_B0], rcx
0x180127ecd  test    ebx, ebx
0x180127ecf  js      short loc_180127EEE
0x180127ed1  mov     rcx, [rbp+57h+var_D0]
0x180127ed5  mov     rax, [rcx]
0x180127ed8  lea     rdx, [rbp+57h+var_B0]
0x180127edc  mov     rax, [rax+88h]
0x180127ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127ee8  mov     ebx, eax
0x180127eea  mov     rcx, [rbp+57h+var_B0]
0x180127eee  mov     dword ptr [rbp+57h+arg_18], r13d
0x180127ef2  test    ebx, ebx
0x180127ef4  js      short loc_180127F08
0x180127ef6  mov     rax, [rcx]
0x180127ef9  lea     rdx, [rbp+57h+arg_18]
0x180127efd  mov     rax, [rax+58h]
0x180127f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127f06  mov     ebx, eax
0x180127f08  mov     edi, r13d
0x180127f0b  jmp     loc_180127FD0
0x180127f10  cmp     edi, dword ptr [rbp+57h+arg_18]
0x180127f13  jge     loc_180127FD8
0x180127f19  mov     [rbp+57h+arg_10], r13
0x180127f1d  mov     [rsp+110h+var_D8], r13
0x180127f22  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180127f26  call    cs:__imp_VariantInit
0x180127f2c  nop
0x180127f2d  mov     rcx, [rbp+57h+var_B0]
0x180127f31  mov     rax, [rcx]
0x180127f34  lea     r8, [rbp+57h+arg_10]
0x180127f38  mov     edx, edi
0x180127f3a  mov     rax, [rax+50h]
0x180127f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127f43  mov     ebx, eax
0x180127f45  test    eax, eax
0x180127f47  js      short loc_180127FAE
0x180127f49  mov     rcx, [rbp+57h+arg_10]
0x180127f4d  mov     rax, [rcx]
0x180127f50  lea     rdx, [rsp+110h+var_D8]
0x180127f55  mov     rax, [rax+38h]
0x180127f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127f5e  mov     ebx, eax
0x180127f60  test    eax, eax
0x180127f62  js      short loc_180127FAE
0x180127f64  mov     rcx, [rbp+57h+arg_10]
0x180127f68  mov     rax, [rcx]
0x180127f6b  lea     rdx, [rbp+57h+pvarg]
0x180127f6f  mov     rax, [rax+40h]
0x180127f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127f78  mov     ebx, eax
0x180127f7a  test    eax, eax
0x180127f7c  js      short loc_180127FAE
0x180127f7e  mov     rcx, [rbp+57h+var_C8]
0x180127f82  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180127f86  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180127f8b  movaps  [rbp+57h+var_50], xmm0
0x180127f8f  movsd   [rbp+57h+var_40], xmm1
0x180127f94  mov     rax, [rcx]
0x180127f97  lea     r8, [rbp+57h+var_50]
0x180127f9b  mov     rdx, [rsp+110h+var_D8]
0x180127fa0  mov     rax, [rax+168h]
0x180127fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127fac  mov     ebx, eax
0x180127fae  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180127fb2  call    cs:__imp_VariantClear
0x180127fb8  nop
0x180127fb9  mov     rcx, [rsp+110h+var_D8]; bstrString
0x180127fbe  call    cs:__imp_SysFreeString
0x180127fc4  nop
0x180127fc5  lea     rcx, [rbp+57h+arg_10]
0x180127fc9  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x180127fce  inc     edi
0x180127fd0  test    ebx, ebx
  ... truncated ...
```
