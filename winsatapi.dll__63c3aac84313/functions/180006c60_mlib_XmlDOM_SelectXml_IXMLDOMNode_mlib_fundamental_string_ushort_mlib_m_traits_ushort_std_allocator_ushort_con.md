# mlib::XmlDOM::SelectXml(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180006c60`
- end: `0x1800071bd`
- name: `?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z`
- size: `1373`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001a70`
- `0x180006970`
- `0x180009d50`
- `0x18001f070`
- `0x18002b49c`

## callees

- `0x180001a34`
- `0x180006c60`
- `0x18000782c`
- `0x18000c480`
- `0x180013fa3`
- `0x1800171e0`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180006cca`
- `OLEAUT32!__imp_SysAllocString` at `0x180006cca`
- `OLEAUT32!__imp_SysFreeString` at `0x180006cc1`
- `OLEAUT32!__imp_SysFreeString` at `0x180006d81`
- `OLEAUT32!__imp_SysFreeString` at `0x180006d8b`
- `OLEAUT32!__imp_SysFreeString` at `0x180006d95`
- `OLEAUT32!__imp_SysFreeString` at `0x180006de2`
- `OLEAUT32!__imp_SysFreeString` at `0x180006dec`
- `OLEAUT32!__imp_SysFreeString` at `0x180006df6`
- `OLEAUT32!__imp_SysFreeString` at `0x180006f0c`
- `OLEAUT32!__imp_SysFreeString` at `0x180006f15`
- `OLEAUT32!__imp_SysFreeString` at `0x180006f1e`
- `OLEAUT32!__imp_SysFreeString` at `0x180006ff2`
- `OLEAUT32!__imp_SysFreeString` at `0x180006ffb`
- `OLEAUT32!__imp_SysFreeString` at `0x180007005`
- `OLEAUT32!__imp_SysFreeString` at `0x180007065`
- `OLEAUT32!__imp_SysFreeString` at `0x18000706f`
- `OLEAUT32!__imp_SysFreeString` at `0x180007079`
- `OLEAUT32!__imp_SysFreeString` at `0x180007112`
- `OLEAUT32!__imp_SysFreeString` at `0x18000711c`
- `OLEAUT32!__imp_SysFreeString` at `0x180007126`
- `OLEAUT32!__imp_SysFreeString` at `0x180006cc1`
- `OLEAUT32!__imp_SysFreeString` at `0x180006d81`
- `OLEAUT32!__imp_SysFreeString` at `0x180006d8b`
- `OLEAUT32!__imp_SysFreeString` at `0x180006d95`
- `OLEAUT32!__imp_SysFreeString` at `0x180006de2`
- `OLEAUT32!__imp_SysFreeString` at `0x180006dec`
- `OLEAUT32!__imp_SysFreeString` at `0x180006df6`
- `OLEAUT32!__imp_SysFreeString` at `0x180006f0c`
- `OLEAUT32!__imp_SysFreeString` at `0x180006f15`
- `OLEAUT32!__imp_SysFreeString` at `0x180006f1e`
- `OLEAUT32!__imp_SysFreeString` at `0x180006ff2`
- `OLEAUT32!__imp_SysFreeString` at `0x180006ffb`
- `OLEAUT32!__imp_SysFreeString` at `0x180007005`
- `OLEAUT32!__imp_SysFreeString` at `0x180007065`
- `OLEAUT32!__imp_SysFreeString` at `0x18000706f`
- `OLEAUT32!__imp_SysFreeString` at `0x180007079`
- `OLEAUT32!__imp_SysFreeString` at `0x180007112`
- `OLEAUT32!__imp_SysFreeString` at `0x18000711c`
- `OLEAUT32!__imp_SysFreeString` at `0x180007126`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180006f96`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180006f96`

## string_xrefs

- `0x180006d6f`: `base\winsat\mlib\mxmldom.cpp`
- `0x180006efc`: `base\winsat\mlib\mxmldom.cpp`
- `0x180006fe2`: `base\winsat\mlib\mxmldom.cpp`
- `0x180007055`: `base\winsat\mlib\mxmldom.cpp`
- `0x1800070c7`: `base\winsat\mlib\mxmldom.cpp`
- `0x180007100`: `base\winsat\mlib\mxmldom.cpp`
- `0x180006d43`: `cannot select nodes in an XML document`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall mlib::XmlDOM::SelectXml(__int64 a1, __int64 a2, _QWORD **a3, _QWORD *a4, __int64 a5)
{
  OLECHAR *v8; // rdi
  OLECHAR *v9; // rsi
  const OLECHAR *v10; // rbx
  OLECHAR *v11; // rbx
  __int64 v12; // rax
  const WCHAR *i; // r14
  int v14; // eax
  unsigned int v15; // r14d
  unsigned __int64 v17; // r14
  unsigned __int64 *v18; // rax
  unsigned __int64 cchCount2; // r15
  int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // ebx
  const WCHAR *v23; // r8
  int v24; // eax
  unsigned int v25; // edi
  unsigned int v26; // esi
  int v27; // eax
  int v28; // eax
  __int64 v29; // [rsp+40h] [rbp-61h] BYREF
  __int64 v30; // [rsp+48h] [rbp-59h] BYREF
  char pExceptionObject; // [rsp+50h] [rbp-51h] BYREF
  __int64 v32; // [rsp+58h] [rbp-49h]
  BSTR bstrString; // [rsp+60h] [rbp-41h] BYREF
  BSTR v34; // [rsp+68h] [rbp-39h] BYREF
  _QWORD v35[4]; // [rsp+70h] [rbp-31h] BYREF
  _QWORD **v36; // [rsp+90h] [rbp-11h]
  __int64 v37; // [rsp+98h] [rbp-9h]
  OLECHAR *v38; // [rsp+A0h] [rbp-1h]

  v37 = -2;
  v36 = a3;
  v32 = a5;
  v30 = 0;
  v29 = 0;
  v8 = 0;
  bstrString = 0;
  v9 = 0;
  v34 = 0;
  *a4 = 0;
  v10 = *(const OLECHAR **)(*(_QWORD *)a2 + 24LL);
  if ( !v10 )
  {
    v22 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            824,
            -2147024882,
            0,
            (__int64)qword_18004E508,
            a5,
            (__int64)L"cannot allocate memory for a string");
    SysFreeString(0);
    SysFreeString(0);
    SysFreeString(0);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    return v22;
  }
  SysFreeString(0);
  v11 = SysAllocString(v10);
  v38 = v11;
  if ( !v11 )
    ATL::AtlThrowImpl(-2147024882);
  v12 = 0x10000;
  for ( i = &String2; ; ++i )
  {
    if ( !v12 )
      throw (mlib::CStringTooBig *)&pExceptionObject;
    if ( !*i )
      break;
    --v12;
  }
  v17 = i - &String2;
  v18 = *a3;
  cchCount2 = **a3;
  if ( cchCount2 )
  {
    if ( !v17 )
      goto LABEL_21;
    v23 = (const WCHAR *)v18[3];
    v24 = cchCount2 >= v17
        ? CompareStringW(0x400u, 0x1000u, v23, v17, &String2, v17)
        : CompareStringW(0x400u, 0x1000u, v23, cchCount2, &String2, cchCount2);
    if ( v24 != 2 || cchCount2 != v17 )
      goto LABEL_21;
  }
  else if ( v17 )
  {
LABEL_21:
    ATL::CComBSTR::operator=(&bstrString, L"SelectionNamespaces");
    v8 = bstrString;
    if ( !bstrString )
    {
      v25 = mlib::XmlDOM::ReportCOMError_w(
              (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
              832,
              -2147024882,
              0,
              (__int64)qword_18004E508,
              v32,
              (__int64)L"cannot allocate memory for a string");
      SysFreeString(0);
      SysFreeString(0);
      SysFreeString(v11);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
      return v25;
    }
    ATL::CComBSTR::operator=(&v34, (const OLECHAR *)(*v36)[3]);
    v9 = v34;
    if ( !v34 )
    {
      v26 = mlib::XmlDOM::ReportCOMError_w(
              (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
              838,
              -2147024882,
              0,
              (__int64)qword_18004E508,
              v32,
              (__int64)L"cannot allocate memory for a string");
      SysFreeString(0);
      SysFreeString(v8);
      SysFreeString(v11);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
      return v26;
    }
    v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 184LL))(a1, &v30);
    if ( v20 < 0 )
    {
      v21 = mlib::XmlDOM::ReportCOMError_w(
              (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
              844,
              v20,
              a1,
              (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
              v32,
              (__int64)L"cannot get owner document");
LABEL_41:
      v15 = v21;
      SysFreeString(v9);
      SysFreeString(v8);
      SysFreeString(v11);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
      return v15;
    }
    if ( v30 )
    {
      v27 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v30)(
              v30,
              &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
              &v29);
      if ( v27 < 0 )
      {
        v21 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                853,
                v27,
                v30,
                (__int64)&GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
                v32,
                (__int64)L"cannot get a document node");
        goto LABEL_41;
      }
      v35[0] = 8;
      v35[1] = v9;
      v35[2] = 0;
      v28 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD *))(*(_QWORD *)v29 + 640LL))(v29, v8, v35);
      if ( v28 < 0 )
      {
        v21 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                862,
                v28,
                v29,
                (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                v32,
                (__int64)L"cannot set the %s document propert",
                v8);
        goto LABEL_41;
      }
    }
  }
  v14 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD *))(*(_QWORD *)a1 + 288LL))(a1, v11, a4);
  if ( v14 < 0 )
  {
    *a4 = 0;
    v15 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            871,
            v14,
            a1,
            (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
            v32,
            (__int64)L"cannot select nodes in an XML document");
    SysFreeString(v9);
    SysFreeString(v8);
    SysFreeString(v11);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    return v15;
  }
  SysFreeString(v9);
  SysFreeString(v8);
  SysFreeString(v11);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  return 0;
}

```

## disassembly

```asm
0x180006c60  push    rbp
0x180006c62  push    rbx
0x180006c63  push    rsi
0x180006c64  push    rdi
0x180006c65  push    r12
0x180006c67  push    r13
0x180006c69  push    r14
0x180006c6b  push    r15
0x180006c6d  lea     rbp, [rsp-17h]
0x180006c72  sub     rsp, 0B8h
0x180006c79  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x180006c81  mov     r13, r9
0x180006c84  mov     r15, r8
0x180006c87  mov     [rbp+4Fh+var_60], r8
0x180006c8b  mov     r12, rcx
0x180006c8e  mov     rcx, [rbp+4Fh+arg_20]
0x180006c92  mov     [rbp+4Fh+var_98], rcx
0x180006c96  xor     eax, eax
0x180006c98  mov     [rbp+4Fh+var_A8], rax
0x180006c9c  mov     [rbp+4Fh+var_B0], rax
0x180006ca0  mov     edi, eax
0x180006ca2  mov     [rbp+4Fh+bstrString], rax
0x180006ca6  mov     esi, eax
0x180006ca8  mov     [rbp+4Fh+var_88], rax
0x180006cac  mov     [r9], rax
0x180006caf  mov     rax, [rdx]
0x180006cb2  mov     rbx, [rax+18h]
0x180006cb6  test    rbx, rbx
0x180006cb9  jz      loc_180006ED1
0x180006cbf  xor     ecx, ecx; bstrString
0x180006cc1  call    cs:__imp_SysFreeString
0x180006cc7  mov     rcx, rbx; psz
0x180006cca  call    cs:__imp_SysAllocString
0x180006cd0  mov     rbx, rax
0x180006cd3  mov     [rbp+4Fh+var_50], rax
0x180006cd7  test    rax, rax
0x180006cda  jz      loc_180006F58
0x180006ce0  mov     eax, 10000h
0x180006ce5  lea     rcx, String2
0x180006cec  mov     r14, rcx
0x180006cef  nop
0x180006cf0  test    rax, rax
0x180006cf3  jz      short loc_180006D09
0x180006cf5  cmp     word ptr [r14], 0
0x180006cfa  jz      loc_180006E2D
0x180006d00  add     r14, 2
0x180006d04  dec     rax
0x180006d07  jmp     short loc_180006CF0
0x180006d09  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x180006d10  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180006d14  call    _CxxThrowException_0
0x180006d1a  mov     rax, [r12]
0x180006d1e  mov     r8, r13
0x180006d21  mov     rdx, rbx
0x180006d24  mov     rcx, r12
0x180006d27  mov     rax, [rax+120h]
0x180006d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d33  test    eax, eax
0x180006d35  jns     loc_180006DDF
0x180006d3b  mov     qword ptr [r13+0], 0
0x180006d43  lea     rcx, aCannotSelectNo; "cannot select nodes in an XML document"
0x180006d4a  mov     [rsp+0F0h+var_C0], rcx
0x180006d4f  mov     rcx, [rbp+4Fh+var_98]
0x180006d53  mov     qword ptr [rsp+0F0h+cchCount2], rcx
0x180006d58  lea     rcx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x180006d5f  mov     [rsp+0F0h+lpString2], rcx
0x180006d64  mov     r9, r12
0x180006d67  mov     r8d, eax
0x180006d6a  mov     edx, 367h
0x180006d6f  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180006d76  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180006d7b  mov     r14d, eax
0x180006d7e  mov     rcx, rsi; bstrString
0x180006d81  call    cs:__imp_SysFreeString
0x180006d87  nop
0x180006d88  mov     rcx, rdi; bstrString
0x180006d8b  call    cs:__imp_SysFreeString
0x180006d91  nop
0x180006d92  mov     rcx, rbx; bstrString
0x180006d95  call    cs:__imp_SysFreeString
0x180006d9b  nop
0x180006d9c  mov     rcx, [rbp+4Fh+var_B0]
0x180006da0  test    rcx, rcx
0x180006da3  jz      short loc_180006DB2
0x180006da5  mov     rax, [rcx]
0x180006da8  mov     rax, [rax+10h]
0x180006dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006db1  nop
0x180006db2  mov     rcx, [rbp+4Fh+var_A8]
0x180006db6  test    rcx, rcx
0x180006db9  jz      short loc_180006DC8
0x180006dbb  mov     rax, [rcx]
0x180006dbe  mov     rax, [rax+10h]
0x180006dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dc7  nop
0x180006dc8  mov     eax, r14d
0x180006dcb  add     rsp, 0B8h
0x180006dd2  pop     r15
0x180006dd4  pop     r14
0x180006dd6  pop     r13
0x180006dd8  pop     r12
0x180006dda  pop     rdi
0x180006ddb  pop     rsi
0x180006ddc  pop     rbx
0x180006ddd  pop     rbp
0x180006dde  retn
0x180006ddf  mov     rcx, rsi; bstrString
0x180006de2  call    cs:__imp_SysFreeString
0x180006de8  nop
0x180006de9  mov     rcx, rdi; bstrString
0x180006dec  call    cs:__imp_SysFreeString
0x180006df2  nop
0x180006df3  mov     rcx, rbx; bstrString
0x180006df6  call    cs:__imp_SysFreeString
0x180006dfc  nop
0x180006dfd  mov     rcx, [rbp+4Fh+var_B0]
0x180006e01  test    rcx, rcx
0x180006e04  jz      short loc_180006E13
0x180006e06  mov     rax, [rcx]
0x180006e09  mov     rax, [rax+10h]
0x180006e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e12  nop
0x180006e13  mov     rcx, [rbp+4Fh+var_A8]
0x180006e17  test    rcx, rcx
0x180006e1a  jz      short loc_180006E29
0x180006e1c  mov     rax, [rcx]
0x180006e1f  mov     rax, [rax+10h]
0x180006e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e28  nop
0x180006e29  xor     eax, eax
0x180006e2b  jmp     short loc_180006DCB
0x180006e2d  sub     r14, rcx
0x180006e30  sar     r14, 1
0x180006e33  mov     rax, [r15]
0x180006e36  mov     r15, [rax]
0x180006e39  test    r15, r15
0x180006e3c  jnz     loc_180006F63
0x180006e42  test    r14, r14
0x180006e45  jz      loc_180006D1A
0x180006e4b  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180006e52  lea     rcx, [rbp+4Fh+bstrString]
0x180006e56  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180006e5b  mov     rdi, [rbp+4Fh+bstrString]
0x180006e5f  test    rdi, rdi
0x180006e62  jz      loc_180006FB3
0x180006e68  mov     rdx, [rbp+4Fh+var_60]
0x180006e6c  mov     rdx, [rdx]
0x180006e6f  mov     rdx, [rdx+18h]
0x180006e73  lea     rcx, [rbp+4Fh+var_88]
0x180006e77  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180006e7c  mov     rsi, [rbp+4Fh+var_88]
0x180006e80  test    rsi, rsi
0x180006e83  jz      loc_180007026
0x180006e89  mov     rax, [r12]
0x180006e8d  lea     rdx, [rbp+4Fh+var_A8]
0x180006e91  mov     rcx, r12
0x180006e94  mov     rax, [rax+0B8h]
0x180006e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea0  test    eax, eax
0x180006ea2  jns     loc_180007145
0x180006ea8  lea     rcx, aCannotGetOwner; "cannot get owner document"
0x180006eaf  mov     [rsp+0F0h+var_C0], rcx
0x180006eb4  mov     rcx, [rbp+4Fh+var_98]
0x180006eb8  mov     qword ptr [rsp+0F0h+cchCount2], rcx
0x180006ebd  lea     rcx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x180006ec4  mov     r9, r12
0x180006ec7  mov     edx, 34Ch
0x180006ecc  jmp     loc_1800070BF
0x180006ed1  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x180006ed8  mov     [rsp+0F0h+var_C0], rax
0x180006edd  mov     qword ptr [rsp+0F0h+cchCount2], rcx
0x180006ee2  lea     rax, qword_18004E508
0x180006ee9  mov     [rsp+0F0h+lpString2], rax
0x180006eee  xor     r9d, r9d
0x180006ef1  mov     edx, 338h
0x180006ef6  mov     r8d, 8007000Eh
0x180006efc  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180006f03  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180006f08  mov     ebx, eax
0x180006f0a  xor     ecx, ecx; bstrString
0x180006f0c  call    cs:__imp_SysFreeString
0x180006f12  nop
0x180006f13  xor     ecx, ecx; bstrString
0x180006f15  call    cs:__imp_SysFreeString
0x180006f1b  nop
0x180006f1c  xor     ecx, ecx; bstrString
0x180006f1e  call    cs:__imp_SysFreeString
0x180006f24  nop
0x180006f25  mov     rcx, [rbp+4Fh+var_B0]
0x180006f29  test    rcx, rcx
0x180006f2c  jz      short loc_180006F3B
0x180006f2e  mov     rax, [rcx]
0x180006f31  mov     rax, [rax+10h]
0x180006f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f3a  nop
0x180006f3b  mov     rcx, [rbp+4Fh+var_A8]
0x180006f3f  test    rcx, rcx
0x180006f42  jz      short loc_180006F51
0x180006f44  mov     rax, [rcx]
0x180006f47  mov     rax, [rax+10h]
0x180006f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f50  nop
0x180006f51  mov     eax, ebx
0x180006f53  jmp     loc_180006DCB
0x180006f58  mov     ecx, 8007000Eh; int
0x180006f5d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006f63  test    r14, r14
0x180006f66  jz      loc_180006E4B
0x180006f6c  mov     r8, [rax+18h]; lpString1
0x180006f70  mov     edx, 1000h; dwCmpFlags
0x180006f75  cmp     r15, r14
0x180006f78  jnb     short loc_180006F84
0x180006f7a  mov     [rsp+0F0h+cchCount2], r15d
0x180006f7f  mov     r9d, r15d
0x180006f82  jmp     short loc_180006F8C
0x180006f84  mov     [rsp+0F0h+cchCount2], r14d; cchCount2
0x180006f89  mov     r9d, r14d; cchCount1
0x180006f8c  mov     [rsp+0F0h+lpString2], rcx; lpString2
0x180006f91  mov     ecx, 400h; Locale
0x180006f96  call    cs:__imp_CompareStringW
0x180006f9c  add     eax, 0FFFFFFFEh
0x180006f9f  jnz     loc_180006E4B
0x180006fa5  cmp     r15, r14
0x180006fa8  jnz     loc_180006E4B
0x180006fae  jmp     loc_180006D1A
0x180006fb3  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x180006fba  mov     [rsp+0F0h+var_C0], rax
0x180006fbf  mov     rcx, [rbp+4Fh+var_98]
0x180006fc3  mov     qword ptr [rsp+0F0h+cchCount2], rcx
0x180006fc8  lea     rax, qword_18004E508
0x180006fcf  mov     [rsp+0F0h+lpString2], rax
0x180006fd4  xor     r9d, r9d
0x180006fd7  mov     edx, 340h
0x180006fdc  mov     r8d, 8007000Eh
0x180006fe2  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180006fe9  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180006fee  mov     edi, eax
0x180006ff0  xor     ecx, ecx; bstrString
0x180006ff2  call    cs:__imp_SysFreeString
0x180006ff8  nop
0x180006ff9  xor     ecx, ecx; bstrString
0x180006ffb  call    cs:__imp_SysFreeString
0x180007001  nop
0x180007002  mov     rcx, rbx; bstrString
0x180007005  call    cs:__imp_SysFreeString
0x18000700b  nop
0x18000700c  lea     rcx, [rbp+4Fh+var_B0]
0x180007010  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007015  nop
0x180007016  lea     rcx, [rbp+4Fh+var_A8]
0x18000701a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000701f  mov     eax, edi
0x180007021  jmp     loc_180006DCB
0x180007026  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x18000702d  mov     [rsp+0F0h+var_C0], rax
0x180007032  mov     rcx, [rbp+4Fh+var_98]
0x180007036  mov     qword ptr [rsp+0F0h+cchCount2], rcx
0x18000703b  lea     rax, qword_18004E508
0x180007042  mov     [rsp+0F0h+lpString2], rax
0x180007047  xor     r9d, r9d
0x18000704a  mov     edx, 346h
0x18000704f  mov     r8d, 8007000Eh
0x180007055  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18000705c  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180007061  mov     esi, eax
0x180007063  xor     ecx, ecx; bstrString
0x180007065  call    cs:__imp_SysFreeString
0x18000706b  nop
0x18000706c  mov     rcx, rdi; bstrString
0x18000706f  call    cs:__imp_SysFreeString
0x180007075  nop
0x180007076  mov     rcx, rbx; bstrString
0x180007079  call    cs:__imp_SysFreeString
0x18000707f  nop
0x180007080  lea     rcx, [rbp+4Fh+var_B0]
0x180007084  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007089  nop
0x18000708a  lea     rcx, [rbp+4Fh+var_A8]
0x18000708e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007093  mov     eax, esi
0x180007095  jmp     loc_180006DCB
0x18000709a  lea     rcx, aCannotGetADocu; "cannot get a document node"
0x1800070a1  mov     [rsp+0F0h+var_C0], rcx
0x1800070a6  mov     rcx, [rbp+4Fh+var_98]
0x1800070aa  mov     qword ptr [rsp+0F0h+cchCount2], rcx
0x1800070af  lea     rcx, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60
0x1800070b6  mov     r9, [rbp+4Fh+var_A8]
0x1800070ba  mov     edx, 355h
0x1800070bf  mov     r8d, eax
0x1800070c2  mov     [rsp+0F0h+lpString2], rcx
0x1800070c7  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x1800070ce  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x1800070d3  jmp     short loc_18000710C
0x1800070d5  mov     [rsp+0F0h+var_B8], rdi
0x1800070da  lea     rcx, aCannotSetTheSD; "cannot set the %s document propert"
0x1800070e1  mov     [rsp+0F0h+var_C0], rcx
0x1800070e6  mov     rcx, [rbp+4Fh+var_98]
0x1800070ea  mov     qword ptr [rsp+0F0h+cchCount2], rcx
0x1800070ef  mov     [rsp+0F0h+lpString2], r14
0x1800070f4  mov     r9, [rbp+4Fh+var_B0]
  ... truncated ...
```
