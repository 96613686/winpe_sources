# mlib::XmlDOM::SelectXml(IXMLDOMDocument2 *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x140055d78`
- end: `0x140056080`
- name: `?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMDocument2@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z`
- size: `776`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002de00`
- `0x14002e2ac`
- `0x14005412c`

## callees

- `0x14000712c`
- `0x140053e14`
- `0x1400557f4`
- `0x140055d78`
- `0x14011a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140055e1e`
- `OLEAUT32!__imp_SysFreeString` at `0x140055e27`
- `OLEAUT32!__imp_SysFreeString` at `0x140055e30`
- `OLEAUT32!__imp_SysFreeString` at `0x140055ea0`
- `OLEAUT32!__imp_SysFreeString` at `0x140055f0e`
- `OLEAUT32!__imp_SysFreeString` at `0x140055f18`
- `OLEAUT32!__imp_SysFreeString` at `0x14005604a`
- `OLEAUT32!__imp_SysFreeString` at `0x140056054`
- `OLEAUT32!__imp_SysFreeString` at `0x140056061`
- `OLEAUT32!__imp_SysFreeString` at `0x140055e1e`
- `OLEAUT32!__imp_SysFreeString` at `0x140055e27`
- `OLEAUT32!__imp_SysFreeString` at `0x140055e30`
- `OLEAUT32!__imp_SysFreeString` at `0x140055ea0`
- `OLEAUT32!__imp_SysFreeString` at `0x140055f0e`
- `OLEAUT32!__imp_SysFreeString` at `0x140055f18`
- `OLEAUT32!__imp_SysFreeString` at `0x14005604a`
- `OLEAUT32!__imp_SysFreeString` at `0x140056054`
- `OLEAUT32!__imp_SysFreeString` at `0x140056061`

## string_xrefs

- `0x140055e04`: `base\winsat\mlib\mxmldom.cpp`
- `0x140055e85`: `base\winsat\mlib\mxmldom.cpp`
- `0x140055ef3`: `base\winsat\mlib\mxmldom.cpp`
- `0x140055f91`: `base\winsat\mlib\mxmldom.cpp`
- `0x140055ff8`: `base\winsat\mlib\mxmldom.cpp`
- `0x140055fcc`: `cannot get the root node for an XML documentt`
- `0x140056027`: `cannot select the nodes for an XPATH expression`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall mlib::XmlDOM::SelectXml(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, __int64 a5)
{
  unsigned int v8; // ebx
  OLECHAR *v10; // rbx
  unsigned int v11; // r14d
  OLECHAR *v12; // rcx
  OLECHAR *v13; // rdi
  OLECHAR *v14; // rcx
  int v15; // eax
  unsigned int v16; // eax
  int v17; // eax
  int v18; // r15d
  BSTR bstrString; // [rsp+40h] [rbp-30h] BYREF
  BSTR v20; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v21[4]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+98h] [rbp+28h] BYREF
  BSTR v23; // [rsp+A8h] [rbp+38h] BYREF

  v23 = 0;
  bstrString = 0;
  v20 = 0;
  v22 = 0;
  *a4 = 0;
  ATL::CComBSTR::operator=(&v23, *(const OLECHAR **)(*(_QWORD *)a2 + 24LL));
  if ( !v23 )
  {
    v8 = mlib::XmlDOM::ReportCOMError_w(
           (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
           915,
           -2147024882,
           0,
           (__int64)qword_1401C3B08,
           a5,
           (__int64)L"cannot allocate memory for a string");
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v22);
    SysFreeString(0);
    SysFreeString(0);
    SysFreeString(0);
    return v8;
  }
  ATL::CComBSTR::operator=(&bstrString, L"SelectionNamespaces");
  v10 = bstrString;
  if ( bstrString )
  {
    ATL::CComBSTR::operator=(&v20, *(const OLECHAR **)(*(_QWORD *)a3 + 24LL));
    v13 = v20;
    if ( v20 )
    {
      v21[0] = 8;
      v21[1] = v20;
      v21[2] = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD *))(*(_QWORD *)a1 + 640LL))(a1, v10, v21);
      if ( v15 >= 0 )
      {
        v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 360LL))(a1, &v22);
        if ( v17 >= 0 )
        {
          v18 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD *))(*(_QWORD *)v22 + 288LL))(v22, v23, a4);
          if ( v18 >= 0 )
          {
            ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v22);
            SysFreeString(v13);
            SysFreeString(v10);
            v11 = v18;
            goto LABEL_18;
          }
          v16 = mlib::XmlDOM::ReportCOMError_w(
                  (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                  950,
                  v18,
                  a1,
                  (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                  a5,
                  (__int64)L"cannot select the nodes for an XPATH expression");
        }
        else
        {
          v16 = mlib::XmlDOM::ReportCOMError_w(
                  (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                  942,
                  v17,
                  a1,
                  (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                  a5,
                  (__int64)L"cannot get the root node for an XML documentt");
        }
      }
      else
      {
        v16 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                936,
                v15,
                a1,
                (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                a5,
                (__int64)L"cannot set the %s document propert",
                v10);
      }
      v11 = v16;
      ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v22);
      v14 = v13;
    }
    else
    {
      v11 = mlib::XmlDOM::ReportCOMError_w(
              (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
              927,
              -2147024882,
              0,
              (__int64)qword_1401C3B08,
              a5,
              (__int64)L"cannot allocate memory for a string");
      ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v22);
      v14 = 0;
    }
    SysFreeString(v14);
    v12 = v10;
  }
  else
  {
    v11 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            921,
            -2147024882,
            0,
            (__int64)qword_1401C3B08,
            a5,
            (__int64)L"cannot allocate memory for a string");
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v22);
    SysFreeString(0);
    v12 = 0;
  }
  SysFreeString(v12);
LABEL_18:
  SysFreeString(v23);
  return v11;
}

```

## disassembly

```asm
0x140055d78  mov     [rsp-18h+arg_0], rbx
0x140055d7d  mov     [rsp-18h+arg_10], rdi
0x140055d82  push    rbp
0x140055d83  push    r14
0x140055d85  push    r15
0x140055d87  mov     rbp, rsp
0x140055d8a  sub     rsp, 70h
0x140055d8e  mov     r15, r9
0x140055d91  mov     rdi, r8
0x140055d94  mov     r14, rcx
0x140055d97  mov     [rbp+arg_18], 0
0x140055d9f  mov     [rbp+bstrString], 0
0x140055da7  mov     [rbp+var_28], 0
0x140055daf  mov     [rbp+arg_8], 0
0x140055db7  mov     qword ptr [r9], 0
0x140055dbe  mov     rdx, [rdx]
0x140055dc1  mov     rdx, [rdx+18h]
0x140055dc5  lea     rcx, [rbp+arg_18]
0x140055dc9  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140055dce  cmp     [rbp+arg_18], 0
0x140055dd3  jnz     short loc_140055E3D
0x140055dd5  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x140055ddc  mov     [rsp+70h+var_40], rax
0x140055de1  mov     rax, [rbp+arg_20]
0x140055de5  mov     [rsp+70h+var_48], rax
0x140055dea  lea     rax, qword_1401C3B08
0x140055df1  mov     [rsp+70h+var_50], rax
0x140055df6  xor     r9d, r9d
0x140055df9  mov     edx, 393h
0x140055dfe  mov     r8d, 8007000Eh
0x140055e04  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140055e0b  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140055e10  mov     ebx, eax
0x140055e12  lea     rcx, [rbp+arg_8]
0x140055e16  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140055e1b  nop
0x140055e1c  xor     ecx, ecx; bstrString
0x140055e1e  call    cs:__imp_SysFreeString
0x140055e24  nop
0x140055e25  xor     ecx, ecx; bstrString
0x140055e27  call    cs:__imp_SysFreeString
0x140055e2d  nop
0x140055e2e  xor     ecx, ecx; bstrString
0x140055e30  call    cs:__imp_SysFreeString
0x140055e36  mov     eax, ebx
0x140055e38  jmp     loc_14005606A
0x140055e3d  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x140055e44  lea     rcx, [rbp+bstrString]
0x140055e48  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140055e4d  mov     rbx, [rbp+bstrString]
0x140055e51  test    rbx, rbx
0x140055e54  jnz     short loc_140055EAB
0x140055e56  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x140055e5d  mov     [rsp+70h+var_40], rax
0x140055e62  mov     rax, [rbp+arg_20]
0x140055e66  mov     [rsp+70h+var_48], rax
0x140055e6b  lea     rax, qword_1401C3B08
0x140055e72  mov     [rsp+70h+var_50], rax
0x140055e77  xor     r9d, r9d
0x140055e7a  mov     edx, 399h
0x140055e7f  mov     r8d, 8007000Eh
0x140055e85  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140055e8c  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140055e91  mov     r14d, eax
0x140055e94  lea     rcx, [rbp+arg_8]
0x140055e98  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140055e9d  nop
0x140055e9e  xor     ecx, ecx; bstrString
0x140055ea0  call    cs:__imp_SysFreeString
0x140055ea6  nop
0x140055ea7  xor     ecx, ecx
0x140055ea9  jmp     short loc_140055F18
0x140055eab  mov     rdx, [rdi]
0x140055eae  mov     rdx, [rdx+18h]
0x140055eb2  lea     rcx, [rbp+var_28]
0x140055eb6  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140055ebb  mov     rdi, [rbp+var_28]
0x140055ebf  test    rdi, rdi
0x140055ec2  jnz     short loc_140055F23
0x140055ec4  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x140055ecb  mov     [rsp+70h+var_40], rax
0x140055ed0  mov     rax, [rbp+arg_20]
0x140055ed4  mov     [rsp+70h+var_48], rax
0x140055ed9  lea     rax, qword_1401C3B08
0x140055ee0  mov     [rsp+70h+var_50], rax
0x140055ee5  xor     r9d, r9d
0x140055ee8  mov     edx, 39Fh
0x140055eed  mov     r8d, 8007000Eh
0x140055ef3  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140055efa  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140055eff  mov     r14d, eax
0x140055f02  lea     rcx, [rbp+arg_8]
0x140055f06  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140055f0b  nop
0x140055f0c  xor     ecx, ecx; bstrString
0x140055f0e  call    cs:__imp_SysFreeString
0x140055f14  nop
0x140055f15  mov     rcx, rbx; bstrString
0x140055f18  call    cs:__imp_SysFreeString
0x140055f1e  jmp     loc_14005605D
0x140055f23  xorps   xmm0, xmm0
0x140055f26  xor     ecx, ecx
0x140055f28  movups  [rbp+var_20], xmm0
0x140055f2c  lea     eax, [rcx+8]
0x140055f2f  mov     word ptr [rbp+var_20], ax
0x140055f33  mov     qword ptr [rbp+var_20+8], rdi
0x140055f37  movups  xmm0, [rbp+var_20]
0x140055f3b  movaps  [rbp+var_20], xmm0
0x140055f3f  mov     [rbp+var_10], rcx
0x140055f43  mov     rax, [r14]
0x140055f46  lea     r8, [rbp+var_20]
0x140055f4a  mov     rdx, rbx
0x140055f4d  mov     rcx, r14
0x140055f50  mov     rax, [rax+280h]
0x140055f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055f5c  test    eax, eax
0x140055f5e  jns     short loc_140055FB2
0x140055f60  mov     [rsp+70h+var_38], rbx
0x140055f65  lea     rcx, aCannotSetTheSD; "cannot set the %s document propert"
0x140055f6c  mov     [rsp+70h+var_40], rcx
0x140055f71  mov     rcx, [rbp+arg_20]
0x140055f75  mov     [rsp+70h+var_48], rcx
0x140055f7a  lea     rcx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x140055f81  mov     [rsp+70h+var_50], rcx
0x140055f86  mov     r9, r14
0x140055f89  mov     r8d, eax
0x140055f8c  mov     edx, 3A8h
0x140055f91  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140055f98  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140055f9d  mov     r14d, eax
0x140055fa0  lea     rcx, [rbp+arg_8]
0x140055fa4  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140055fa9  nop
0x140055faa  mov     rcx, rdi
0x140055fad  jmp     loc_140055F0E
0x140055fb2  mov     rax, [r14]
0x140055fb5  lea     rdx, [rbp+arg_8]
0x140055fb9  mov     rcx, r14
0x140055fbc  mov     rax, [rax+168h]
0x140055fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055fc8  test    eax, eax
0x140055fca  jns     short loc_140056006
0x140055fcc  lea     rcx, aCannotGetTheRo; "cannot get the root node for an XML doc"...
0x140055fd3  mov     [rsp+70h+var_40], rcx
0x140055fd8  mov     r8d, eax
0x140055fdb  mov     edx, 3AEh
0x140055fe0  mov     rcx, [rbp+arg_20]
0x140055fe4  mov     [rsp+70h+var_48], rcx
0x140055fe9  lea     rcx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x140055ff0  mov     r9, r14
0x140055ff3  mov     [rsp+70h+var_50], rcx
0x140055ff8  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140055fff  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140056004  jmp     short loc_140055F9D
0x140056006  mov     rcx, [rbp+arg_8]
0x14005600a  mov     rax, [rcx]
0x14005600d  mov     r8, r15
0x140056010  mov     rdx, [rbp+arg_18]
0x140056014  mov     rax, [rax+120h]
0x14005601b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056020  mov     r15d, eax
0x140056023  test    eax, eax
0x140056025  jns     short loc_14005603D
0x140056027  lea     rax, aCannotSelectTh; "cannot select the nodes for an XPATH ex"...
0x14005602e  mov     [rsp+70h+var_40], rax
0x140056033  mov     r8d, r15d
0x140056036  mov     edx, 3B6h
0x14005603b  jmp     short loc_140055FE0
0x14005603d  lea     rcx, [rbp+arg_8]
0x140056041  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140056046  nop
0x140056047  mov     rcx, rdi; bstrString
0x14005604a  call    cs:__imp_SysFreeString
0x140056050  nop
0x140056051  mov     rcx, rbx; bstrString
0x140056054  call    cs:__imp_SysFreeString
0x14005605a  mov     r14d, r15d
0x14005605d  mov     rcx, [rbp+arg_18]; bstrString
0x140056061  call    cs:__imp_SysFreeString
0x140056067  mov     eax, r14d
0x14005606a  lea     r11, [rsp+70h+var_s0]
0x14005606f  mov     rbx, [r11+20h]
0x140056073  mov     rdi, [r11+30h]
0x140056077  mov     rsp, r11
0x14005607a  pop     r15
0x14005607c  pop     r14
0x14005607e  pop     rbp
0x14005607f  retn
```
