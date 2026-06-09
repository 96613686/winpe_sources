# mlib::XmlDOM::LoadManyFilesIntoOneDocument(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>> const &,IXMLDOMNode * *)

- ea: `0x18002d0c0`
- end: `0x18002d31f`
- name: `?LoadManyFilesIntoOneDocument@XmlDOM@mlib@@SA_NAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEBV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@PEAPEAUIXMLDOMNode@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f070`

## callees

- `0x180001a34`
- `0x180003548`
- `0x18000782c`
- `0x18000c480`
- `0x18002cc4c`
- `0x18002d0c0`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002d110`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d2ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d110`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d2ee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d1a7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d1a7`

## string_xrefs

- `0x18002d175`: `base\winsat\mlib\mxmldom.cpp`
- `0x18002d1dd`: `base\winsat\mlib\mxmldom.cpp`
- `0x18002d2d5`: `base\winsat\mlib\mxmldom.cpp`
- `0x18002d1b4`: `cannot create an IXMLDOMDocument2 document`
- `0x18002d210`: `cannot create a root XML document element`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall mlib::XmlDOM::LoadManyFilesIntoOneDocument(__int64 a1, __int64 *a2, _QWORD *a3)
{
  OLECHAR *v6; // rcx
  OLECHAR *v8; // rbx
  char v9; // di
  HRESULT v10; // r8d
  int v11; // eax
  int v12; // eax
  int v13; // eax
  BSTR bstrString[2]; // [rsp+40h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp+40h] BYREF
  __int64 v16; // [rsp+98h] [rbp+48h] BYREF

  bstrString[1] = (BSTR)-2LL;
  ppv = 0;
  v16 = 0;
  bstrString[0] = 0;
  *a3 = 0;
  if ( !mlib::XmlDOM::Init() )
    goto LABEL_2;
  ATL::CComBSTR::operator=(bstrString, *(const OLECHAR **)(*(_QWORD *)a1 + 24LL));
  v8 = bstrString[0];
  if ( !bstrString[0] )
  {
    mlib::XmlDOM::ReportCOMError_w(
      (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
      510,
      -2147024882,
      0,
      (__int64)qword_18004E508,
      0,
      (__int64)L"cannot allocate memory for a string");
LABEL_2:
    v6 = 0;
LABEL_3:
    SysFreeString(v6);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
    return 0;
  }
  v9 = 1;
  v10 = CoCreateInstance(&mlib::XmlDOM::clsIDDocument, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv);
  if ( v10 < 0 )
  {
    mlib::XmlDOM::ReportCOMError_w(
      (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
      532,
      v10,
      0,
      (__int64)qword_18004E508,
      0,
      (__int64)L"cannot create an IXMLDOMDocument2 document");
LABEL_8:
    v6 = v8;
    goto LABEL_3;
  }
  v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 376LL))(ppv, v8, &v16);
  if ( v11 < 0 )
  {
    mlib::XmlDOM::ReportCOMError_w(
      (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
      543,
      v11,
      (_DWORD)ppv,
      (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
      0,
      (__int64)L"cannot create a root XML document element");
    goto LABEL_8;
  }
  v12 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 368LL))(ppv, v16);
  if ( v12 < 0 )
  {
    mlib::XmlDOM::ReportCOMError_w(
      (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
      554,
      v12,
      (_DWORD)ppv,
      (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
      0,
      (__int64)L"cannot set the new element as the DOM document root");
    goto LABEL_8;
  }
  if ( !mlib::XmlDOM::AppendFilesToElementNode(a2, v16) )
    goto LABEL_8;
  v13 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, _QWORD *))ppv)(ppv, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60, a3);
  if ( v13 < 0 )
  {
    mlib::XmlDOM::ReportCOMError_w(
      (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
      571,
      v13,
      (_DWORD)ppv,
      (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
      0,
      (__int64)L"cannot get root DOM node");
    *a3 = 0;
    v9 = 0;
  }
  SysFreeString(v8);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return v9;
}

```

## disassembly

```asm
0x18002d0c0  mov     rax, rsp
0x18002d0c3  push    rbp
0x18002d0c4  push    rsi
0x18002d0c5  push    rdi
0x18002d0c6  push    r12
0x18002d0c8  push    r14
0x18002d0ca  mov     rbp, rsp
0x18002d0cd  sub     rsp, 50h
0x18002d0d1  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x18002d0d9  mov     [rax+8], rbx
0x18002d0dd  mov     rsi, r8
0x18002d0e0  mov     r14, rdx
0x18002d0e3  mov     rbx, rcx
0x18002d0e6  mov     [rbp+arg_10], 0
0x18002d0ee  mov     [rbp+arg_18], 0
0x18002d0f6  mov     [rbp+bstrString], 0
0x18002d0fe  mov     qword ptr [r8], 0
0x18002d105  call    ?Init@XmlDOM@mlib@@CA_NXZ; mlib::XmlDOM::Init(void)
0x18002d10a  test    al, al
0x18002d10c  jnz     short loc_18002D131
0x18002d10e  xor     ecx, ecx; bstrString
0x18002d110  call    cs:__imp_SysFreeString
0x18002d116  nop
0x18002d117  lea     rcx, [rbp+arg_18]
0x18002d11b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d120  nop
0x18002d121  lea     rcx, [rbp+arg_10]
0x18002d125  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d12a  xor     al, al
0x18002d12c  jmp     loc_18002D30B
0x18002d131  mov     rdx, [rbx]
0x18002d134  mov     rdx, [rdx+18h]
0x18002d138  lea     rcx, [rbp+bstrString]
0x18002d13c  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18002d141  mov     rbx, [rbp+bstrString]
0x18002d145  test    rbx, rbx
0x18002d148  jnz     short loc_18002D183
0x18002d14a  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x18002d151  mov     [rsp+50h+var_20], rax
0x18002d156  mov     [rsp+50h+var_28], rbx
0x18002d15b  lea     rax, qword_18004E508
0x18002d162  mov     [rsp+50h+ppv], rax
0x18002d167  xor     r9d, r9d
0x18002d16a  mov     edx, 1FEh
0x18002d16f  mov     r8d, 8007000Eh
0x18002d175  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18002d17c  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18002d181  jmp     short loc_18002D10E
0x18002d183  lea     rax, [rbp+arg_10]
0x18002d187  mov     [rsp+50h+ppv], rax; ppv
0x18002d18c  lea     r12, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x18002d193  mov     r9, r12; riid
0x18002d196  mov     edi, 1
0x18002d19b  mov     r8d, edi; dwClsContext
0x18002d19e  xor     edx, edx; pUnkOuter
0x18002d1a0  lea     rcx, ?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A; rclsid
0x18002d1a7  call    cs:__imp_CoCreateInstance
0x18002d1ad  mov     r8d, eax
0x18002d1b0  test    eax, eax
0x18002d1b2  jns     short loc_18002D1F2
0x18002d1b4  lea     rax, aCannotCreateAn; "cannot create an IXMLDOMDocument2 docum"...
0x18002d1bb  mov     [rsp+50h+var_20], rax
0x18002d1c0  mov     [rsp+50h+var_28], 0
0x18002d1c9  lea     rax, qword_18004E508
0x18002d1d0  mov     [rsp+50h+ppv], rax
0x18002d1d5  xor     r9d, r9d
0x18002d1d8  mov     edx, 214h
0x18002d1dd  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18002d1e4  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18002d1e9  nop
0x18002d1ea  mov     rcx, rbx
0x18002d1ed  jmp     loc_18002D110
0x18002d1f2  mov     rcx, [rbp+arg_10]
0x18002d1f6  mov     rax, [rcx]
0x18002d1f9  lea     r8, [rbp+arg_18]
0x18002d1fd  mov     rdx, rbx
0x18002d200  mov     rax, [rax+178h]
0x18002d207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d20c  test    eax, eax
0x18002d20e  jns     short loc_18002D238
0x18002d210  lea     rcx, aCannotCreateAR; "cannot create a root XML document eleme"...
0x18002d217  mov     [rsp+50h+var_20], rcx
0x18002d21c  mov     [rsp+50h+var_28], 0
0x18002d225  mov     [rsp+50h+ppv], r12
0x18002d22a  mov     r9, [rbp+arg_10]
0x18002d22e  mov     r8d, eax
0x18002d231  mov     edx, 21Fh
0x18002d236  jmp     short loc_18002D1DD
0x18002d238  mov     rcx, [rbp+arg_10]
0x18002d23c  mov     rax, [rcx]
0x18002d23f  mov     rdx, [rbp+arg_18]
0x18002d243  mov     rax, [rax+170h]
0x18002d24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d24f  test    eax, eax
0x18002d251  jns     short loc_18002D27E
0x18002d253  lea     rcx, aCannotSetTheNe; "cannot set the new element as the DOM d"...
0x18002d25a  mov     [rsp+50h+var_20], rcx
0x18002d25f  mov     [rsp+50h+var_28], 0
0x18002d268  mov     [rsp+50h+ppv], r12
0x18002d26d  mov     r9, [rbp+arg_10]
0x18002d271  mov     r8d, eax
0x18002d274  mov     edx, 22Ah
0x18002d279  jmp     loc_18002D1DD
0x18002d27e  mov     rdx, [rbp+arg_18]
0x18002d282  mov     rcx, r14
0x18002d285  call    ?AppendFilesToElementNode@XmlDOM@mlib@@SA_NAEBV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@PEAUIXMLDOMNode@@@Z; mlib::XmlDOM::AppendFilesToElementNode(std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> const &,IXMLDOMNode *)
0x18002d28a  test    al, al
0x18002d28c  jz      loc_18002D1EA
0x18002d292  mov     rcx, [rbp+arg_10]
0x18002d296  mov     rax, [rcx]
0x18002d299  mov     r8, rsi
0x18002d29c  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x18002d2a3  mov     rax, [rax]
0x18002d2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2ab  test    eax, eax
0x18002d2ad  jns     short loc_18002D2EB
0x18002d2af  lea     rcx, aCannotGetRootD; "cannot get root DOM node"
0x18002d2b6  mov     [rsp+50h+var_20], rcx
0x18002d2bb  mov     [rsp+50h+var_28], 0
0x18002d2c4  mov     [rsp+50h+ppv], r12
0x18002d2c9  mov     r9, [rbp+arg_10]
0x18002d2cd  mov     r8d, eax
0x18002d2d0  mov     edx, 23Bh
0x18002d2d5  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18002d2dc  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18002d2e1  mov     qword ptr [rsi], 0
0x18002d2e8  xor     dil, dil
0x18002d2eb  mov     rcx, rbx; bstrString
0x18002d2ee  call    cs:__imp_SysFreeString
0x18002d2f4  nop
0x18002d2f5  lea     rcx, [rbp+arg_18]
0x18002d2f9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d2fe  nop
0x18002d2ff  lea     rcx, [rbp+arg_10]
0x18002d303  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d308  mov     al, dil
0x18002d30b  mov     rbx, [rsp+50h+arg_0]
0x18002d313  add     rsp, 50h
0x18002d317  pop     r14
0x18002d319  pop     r12
0x18002d31b  pop     rdi
0x18002d31c  pop     rsi
0x18002d31d  pop     rbp
0x18002d31e  retn
```
