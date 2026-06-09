# mlib::XmlDOM::SelectSingleNode(IXMLDOMDocument2 *,ushort const *,ushort const *,IXMLDOMNode * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x1400558e4`
- end: `0x140055be9`
- name: `?SelectSingleNode@XmlDOM@mlib@@SAJPEAUIXMLDOMDocument2@@PEBG1AEAPEAUIXMLDOMNode@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z`
- size: `773`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001f108`
- `0x14002d51c`
- `0x140035a64`
- `0x140035cd8`
- `0x140036700`
- `0x14003808c`
- `0x14004d864`

## callees

- `0x14000712c`
- `0x140053e14`
- `0x1400557f4`
- `0x1400558e4`
- `0x14011a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140055985`
- `OLEAUT32!__imp_SysFreeString` at `0x14005598e`
- `OLEAUT32!__imp_SysFreeString` at `0x140055997`
- `OLEAUT32!__imp_SysFreeString` at `0x140055a07`
- `OLEAUT32!__imp_SysFreeString` at `0x140055bb5`
- `OLEAUT32!__imp_SysFreeString` at `0x140055bbf`
- `OLEAUT32!__imp_SysFreeString` at `0x140055bca`
- `OLEAUT32!__imp_SysFreeString` at `0x140055985`
- `OLEAUT32!__imp_SysFreeString` at `0x14005598e`
- `OLEAUT32!__imp_SysFreeString` at `0x140055997`
- `OLEAUT32!__imp_SysFreeString` at `0x140055a07`
- `OLEAUT32!__imp_SysFreeString` at `0x140055bb5`
- `OLEAUT32!__imp_SysFreeString` at `0x140055bbf`
- `OLEAUT32!__imp_SysFreeString` at `0x140055bca`

## string_xrefs

- `0x14005596b`: `base\winsat\mlib\mxmldom.cpp`
- `0x1400559ec`: `base\winsat\mlib\mxmldom.cpp`
- `0x140055a5d`: `base\winsat\mlib\mxmldom.cpp`
- `0x140055aeb`: `base\winsat\mlib\mxmldom.cpp`
- `0x140055b99`: `base\winsat\mlib\mxmldom.cpp`
- `0x140055b16`: `cannot get the root node for an XML documentt`
- `0x140055b6c`: `cannot select a XML node for from an XPATH expression`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall mlib::XmlDOM::SelectSingleNode(__int64 a1, const OLECHAR *a2, __int64 a3, _QWORD *a4, __int64 a5)
{
  unsigned int v7; // ebx
  BSTR v9; // rbx
  int v10; // r14d
  OLECHAR *v11; // rcx
  BSTR v12; // rdi
  OLECHAR *v13; // rcx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  BSTR v17; // [rsp+40h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v19[4]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+A0h] [rbp+30h] BYREF
  BSTR v21; // [rsp+A8h] [rbp+38h] BYREF

  v21 = 0;
  v17 = 0;
  bstrString = 0;
  v20 = 0;
  *a4 = 0;
  ATL::CComBSTR::operator=(&v21, a2);
  if ( !v21 )
  {
    v7 = mlib::XmlDOM::ReportCOMError_w(
           (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
           1095,
           -2147024882,
           0,
           (__int64)qword_1401C3B08,
           a5,
           (__int64)L"cannot allocate memory for a string");
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v20);
    SysFreeString(0);
    SysFreeString(0);
    SysFreeString(0);
    return v7;
  }
  ATL::CComBSTR::operator=(&v17, L"SelectionNamespaces");
  v9 = v17;
  if ( v17 )
  {
    ATL::CComBSTR::operator=(&bstrString, &qword_14012B318);
    v12 = bstrString;
    if ( !bstrString )
    {
      v10 = mlib::XmlDOM::ReportCOMError_w(
              (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
              1107,
              -2147024882,
              0,
              (__int64)qword_1401C3B08,
              a5,
              (__int64)L"cannot allocate memory for a string");
      ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v20);
      v13 = 0;
LABEL_15:
      SysFreeString(v13);
      v11 = v9;
      goto LABEL_16;
    }
    v19[0] = 8;
    v19[1] = bstrString;
    v19[2] = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD *))(*(_QWORD *)a1 + 640LL))(a1, v9, v19);
    if ( v14 >= 0 )
    {
      v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 360LL))(a1, &v20);
      if ( v16 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD *))(*(_QWORD *)v20 + 296LL))(v20, v21, a4);
        if ( v10 >= 0 )
        {
LABEL_14:
          ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v20);
          v13 = v12;
          goto LABEL_15;
        }
        *a4 = 0;
        v15 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                1130,
                v10,
                v20,
                (__int64)&GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
                a5,
                (__int64)L"cannot select a XML node for from an XPATH expression");
      }
      else
      {
        v15 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                1123,
                v16,
                a1,
                (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                a5,
                (__int64)L"cannot get the root node for an XML documentt");
      }
    }
    else
    {
      v15 = mlib::XmlDOM::ReportCOMError_w(
              (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
              1116,
              v14,
              a1,
              (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
              a5,
              (__int64)L"cannot set the %s document propert",
              v9);
    }
    v10 = v15;
    goto LABEL_14;
  }
  v10 = mlib::XmlDOM::ReportCOMError_w(
          (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
          1101,
          -2147024882,
          0,
          (__int64)qword_1401C3B08,
          a5,
          (__int64)L"cannot allocate memory for a string");
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v20);
  SysFreeString(0);
  v11 = 0;
LABEL_16:
  SysFreeString(v11);
  SysFreeString(v21);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400558e4  mov     [rsp-18h+arg_0], rbx
0x1400558e9  mov     [rsp-18h+arg_8], rdi
0x1400558ee  mov     [rsp-18h+arg_10], r8
0x1400558f3  push    rbp
0x1400558f4  push    r14
0x1400558f6  push    r15
0x1400558f8  mov     rbp, rsp
0x1400558fb  sub     rsp, 70h
0x1400558ff  mov     r15, r9
0x140055902  mov     r14, rcx
0x140055905  mov     [rbp+arg_18], 0
0x14005590d  mov     [rbp+var_30], 0
0x140055915  mov     [rbp+bstrString], 0
0x14005591d  mov     [rbp+arg_10], 0
0x140055925  mov     qword ptr [r9], 0
0x14005592c  lea     rcx, [rbp+arg_18]
0x140055930  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140055935  cmp     [rbp+arg_18], 0
0x14005593a  jnz     short loc_1400559A4
0x14005593c  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x140055943  mov     [rsp+70h+var_40], rax
0x140055948  mov     rax, [rbp+arg_20]
0x14005594c  mov     [rsp+70h+var_48], rax
0x140055951  lea     rax, qword_1401C3B08
0x140055958  mov     [rsp+70h+var_50], rax
0x14005595d  xor     r9d, r9d
0x140055960  mov     edx, 447h
0x140055965  mov     r8d, 8007000Eh
0x14005596b  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140055972  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140055977  mov     ebx, eax
0x140055979  lea     rcx, [rbp+arg_10]
0x14005597d  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140055982  nop
0x140055983  xor     ecx, ecx; bstrString
0x140055985  call    cs:__imp_SysFreeString
0x14005598b  nop
0x14005598c  xor     ecx, ecx; bstrString
0x14005598e  call    cs:__imp_SysFreeString
0x140055994  nop
0x140055995  xor     ecx, ecx; bstrString
0x140055997  call    cs:__imp_SysFreeString
0x14005599d  mov     eax, ebx
0x14005599f  jmp     loc_140055BD3
0x1400559a4  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x1400559ab  lea     rcx, [rbp+var_30]
0x1400559af  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1400559b4  mov     rbx, [rbp+var_30]
0x1400559b8  test    rbx, rbx
0x1400559bb  jnz     short loc_140055A15
0x1400559bd  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x1400559c4  mov     [rsp+70h+var_40], rax
0x1400559c9  mov     rax, [rbp+arg_20]
0x1400559cd  mov     [rsp+70h+var_48], rax
0x1400559d2  lea     rax, qword_1401C3B08
0x1400559d9  mov     [rsp+70h+var_50], rax
0x1400559de  xor     r9d, r9d
0x1400559e1  mov     edx, 44Dh
0x1400559e6  mov     r8d, 8007000Eh
0x1400559ec  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x1400559f3  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x1400559f8  mov     r14d, eax
0x1400559fb  lea     rcx, [rbp+arg_10]
0x1400559ff  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140055a04  nop
0x140055a05  xor     ecx, ecx; bstrString
0x140055a07  call    cs:__imp_SysFreeString
0x140055a0d  nop
0x140055a0e  xor     ecx, ecx
0x140055a10  jmp     loc_140055BBF
0x140055a15  lea     rdx, qword_14012B318
0x140055a1c  lea     rcx, [rbp+bstrString]
0x140055a20  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140055a25  mov     rdi, [rbp+bstrString]
0x140055a29  test    rdi, rdi
0x140055a2c  jnz     short loc_140055A7D
0x140055a2e  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x140055a35  mov     [rsp+70h+var_40], rax
0x140055a3a  mov     rax, [rbp+arg_20]
0x140055a3e  mov     [rsp+70h+var_48], rax
0x140055a43  lea     rax, qword_1401C3B08
0x140055a4a  mov     [rsp+70h+var_50], rax
0x140055a4f  xor     r9d, r9d
0x140055a52  mov     edx, 453h
0x140055a57  mov     r8d, 8007000Eh
0x140055a5d  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140055a64  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140055a69  mov     r14d, eax
0x140055a6c  lea     rcx, [rbp+arg_10]
0x140055a70  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140055a75  nop
0x140055a76  xor     ecx, ecx
0x140055a78  jmp     loc_140055BB5
0x140055a7d  xorps   xmm0, xmm0
0x140055a80  xor     ecx, ecx
0x140055a82  movups  [rbp+var_20], xmm0
0x140055a86  lea     eax, [rcx+8]
0x140055a89  mov     word ptr [rbp+var_20], ax
0x140055a8d  mov     qword ptr [rbp+var_20+8], rdi
0x140055a91  movups  xmm0, [rbp+var_20]
0x140055a95  movaps  [rbp+var_20], xmm0
0x140055a99  mov     [rbp+var_10], rcx
0x140055a9d  mov     rax, [r14]
0x140055aa0  lea     r8, [rbp+var_20]
0x140055aa4  mov     rdx, rbx
0x140055aa7  mov     rcx, r14
0x140055aaa  mov     rax, [rax+280h]
0x140055ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055ab6  test    eax, eax
0x140055ab8  jns     short loc_140055AFC
0x140055aba  mov     [rsp+70h+var_38], rbx
0x140055abf  lea     rcx, aCannotSetTheSD; "cannot set the %s document propert"
0x140055ac6  mov     [rsp+70h+var_40], rcx
0x140055acb  mov     rcx, [rbp+arg_20]
0x140055acf  mov     [rsp+70h+var_48], rcx
0x140055ad4  lea     rcx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x140055adb  mov     [rsp+70h+var_50], rcx
0x140055ae0  mov     r9, r14
0x140055ae3  mov     r8d, eax
0x140055ae6  mov     edx, 45Ch
0x140055aeb  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140055af2  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140055af7  jmp     loc_140055BA5
0x140055afc  mov     rax, [r14]
0x140055aff  lea     rdx, [rbp+arg_10]
0x140055b03  mov     rcx, r14
0x140055b06  mov     rax, [rax+168h]
0x140055b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055b12  test    eax, eax
0x140055b14  jns     short loc_140055B44
0x140055b16  lea     rcx, aCannotGetTheRo; "cannot get the root node for an XML doc"...
0x140055b1d  mov     [rsp+70h+var_40], rcx
0x140055b22  mov     rcx, [rbp+arg_20]
0x140055b26  mov     [rsp+70h+var_48], rcx
0x140055b2b  lea     rcx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x140055b32  mov     [rsp+70h+var_50], rcx
0x140055b37  mov     r9, r14
0x140055b3a  mov     r8d, eax
0x140055b3d  mov     edx, 463h
0x140055b42  jmp     short loc_140055B99
0x140055b44  mov     rcx, [rbp+arg_10]
0x140055b48  mov     rax, [rcx]
0x140055b4b  mov     r8, r15
0x140055b4e  mov     rdx, [rbp+arg_18]
0x140055b52  mov     rax, [rax+128h]
0x140055b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055b5e  mov     r14d, eax
0x140055b61  test    eax, eax
0x140055b63  jns     short loc_140055BA8
0x140055b65  mov     qword ptr [r15], 0
0x140055b6c  lea     rax, aCannotSelectAX; "cannot select a XML node for from an XP"...
0x140055b73  mov     [rsp+70h+var_40], rax
0x140055b78  mov     rcx, [rbp+arg_20]
0x140055b7c  mov     [rsp+70h+var_48], rcx
0x140055b81  lea     rax, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x140055b88  mov     [rsp+70h+var_50], rax
0x140055b8d  mov     r9, [rbp+arg_10]
0x140055b91  mov     r8d, r14d
0x140055b94  mov     edx, 46Ah
0x140055b99  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140055ba0  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140055ba5  mov     r14d, eax
0x140055ba8  lea     rcx, [rbp+arg_10]
0x140055bac  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140055bb1  nop
0x140055bb2  mov     rcx, rdi; bstrString
0x140055bb5  call    cs:__imp_SysFreeString
0x140055bbb  nop
0x140055bbc  mov     rcx, rbx; bstrString
0x140055bbf  call    cs:__imp_SysFreeString
0x140055bc5  nop
0x140055bc6  mov     rcx, [rbp+arg_18]; bstrString
0x140055bca  call    cs:__imp_SysFreeString
0x140055bd0  mov     eax, r14d
0x140055bd3  lea     r11, [rsp+70h+var_s0]
0x140055bd8  mov     rbx, [r11+20h]
0x140055bdc  mov     rdi, [r11+28h]
0x140055be0  mov     rsp, r11
0x140055be3  pop     r15
0x140055be5  pop     r14
0x140055be7  pop     rbp
0x140055be8  retn
```
