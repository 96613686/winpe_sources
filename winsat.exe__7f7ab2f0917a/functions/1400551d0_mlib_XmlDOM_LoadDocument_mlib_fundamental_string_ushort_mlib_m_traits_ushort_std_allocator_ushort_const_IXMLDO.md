# mlib::XmlDOM::LoadDocument(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMDocument2 * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,bool)

- ea: `0x1400551d0`
- end: `0x1400553ca`
- name: `?LoadDocument@XmlDOM@mlib@@SAJAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEAPEAUIXMLDOMDocument2@@PEAV32@_N@Z`
- size: `506`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000e440`
- `0x14001eb1c`
- `0x140033bf4`
- `0x1400342b4`

## callees

- `0x140002f80`
- `0x140002ff0`
- `0x14000712c`
- `0x140053e14`
- `0x140055054`
- `0x1400551d0`
- `0x1400557f4`
- `0x14011a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14005539f`
- `OLEAUT32!__imp_SysFreeString` at `0x14005539f`
- `ole32!CoCreateInstance` at `0x140055282`
- `ole32!CoCreateInstance` at `0x140055282`

## string_xrefs

- `0x1400552e6`: `base\winsat\mlib\mxmldom.cpp`
- `0x14005533b`: `base\winsat\mlib\mxmldom.cpp`
- `0x14005528c`: `cannot create an IXMLDOMDocument2 document`
- `0x140055321`: `cannot load XML data from a string`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall mlib::XmlDOM::LoadDocument(__int64 a1, char *a2, __int64 a3)
{
  int v6; // edi
  HRESULT v7; // eax
  int v8; // eax
  BSTR v9; // rbx
  OLECHAR *v10; // rcx
  int v11; // eax
  int v12; // r8d
  int v13; // edx
  int v14; // eax
  LPVOID v15; // rax
  BSTR bstrString; // [rsp+40h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+38h] BYREF
  __int16 v19; // [rsp+98h] [rbp+48h] BYREF

  ppv = 0;
  v19 = 0;
  bstrString = 0;
  if ( dword_1401CBCB8 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_1401CBCB8);
    if ( dword_1401CBCB8 == -1 )
    {
      byte_1401CBCC4 = *a2;
      Init_thread_footer(&dword_1401CBCB8);
    }
  }
  *(_QWORD *)a2 = 0;
  if ( mlib::XmlDOM::Init() )
  {
    v7 = CoCreateInstance(&mlib::XmlDOM::clsIDDocument, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv);
    if ( v7 < 0 )
    {
      v8 = mlib::XmlDOM::ReportCOMError_w(
             (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
             399,
             v7,
             0,
             (__int64)qword_1401C3B08,
             a3,
             (__int64)L"cannot create an IXMLDOMDocument2 document");
LABEL_10:
      v6 = v8;
      goto LABEL_11;
    }
    ATL::CComBSTR::operator=(&bstrString, *(const OLECHAR **)(*(_QWORD *)a1 + 24LL));
    v9 = bstrString;
    if ( !bstrString )
    {
      v8 = mlib::XmlDOM::ReportCOMError_w(
             (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
             405,
             -2147024882,
             0,
             (__int64)qword_1401C3B08,
             a3,
             (__int64)L"cannot allocate memory for a string");
      goto LABEL_10;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, bstrString, &v19);
    if ( v11 >= 0 )
    {
      if ( v19 )
      {
        v6 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 576LL))(ppv, 0xFFFFFFFFLL);
        if ( v6 >= 0 )
        {
          v15 = ppv;
          ppv = 0;
          *(_QWORD *)a2 = v15;
          goto LABEL_21;
        }
        v14 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                427,
                v6,
                (_DWORD)ppv,
                (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                a3,
                (__int64)L"cannot set the 'preserve white space' flag");
LABEL_15:
        v6 = v14;
LABEL_21:
        v10 = v9;
        goto LABEL_22;
      }
      v13 = 416;
      v12 = -2147467259;
    }
    else
    {
      v12 = v11;
      v13 = 411;
    }
    v14 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            v13,
            v12,
            (_DWORD)ppv,
            (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
            a3,
            (__int64)L"cannot load XML data from a string");
    goto LABEL_15;
  }
  v6 = -2147467259;
LABEL_11:
  v10 = 0;
LABEL_22:
  SysFreeString(v10);
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>((__int64 *)&ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400551d0  mov     [rsp-28h+arg_0], rbx
0x1400551d5  mov     [rsp-28h+arg_10], rsi
0x1400551da  mov     byte ptr [rsp-28h+arg_18], r9b
0x1400551df  push    rbp
0x1400551e0  push    rdi
0x1400551e1  push    r12
0x1400551e3  push    r14
0x1400551e5  push    r15
0x1400551e7  mov     rbp, rsp
0x1400551ea  sub     rsp, 50h
0x1400551ee  mov     r14, r8
0x1400551f1  mov     rsi, rdx
0x1400551f4  mov     rbx, rcx
0x1400551f7  xor     r15d, r15d
0x1400551fa  mov     [rbp+arg_8], r15
0x1400551fe  mov     [rbp+arg_18], r15w
0x140055203  mov     [rbp+bstrString], r15
0x140055207  mov     ecx, 4
0x14005520c  mov     rax, gs:58h
0x140055215  mov     rax, [rax]
0x140055218  mov     eax, [rcx+rax]
0x14005521b  cmp     cs:dword_1401CBCB8, eax
0x140055221  jle     short loc_14005524C
0x140055223  lea     rcx, dword_1401CBCB8
0x14005522a  call    _Init_thread_header
0x14005522f  cmp     cs:dword_1401CBCB8, 0FFFFFFFFh
0x140055236  jnz     short loc_14005524C
0x140055238  mov     al, [rsi]
0x14005523a  mov     cs:byte_1401CBCC4, al
0x140055240  lea     rcx, dword_1401CBCB8
0x140055247  call    _Init_thread_footer
0x14005524c  mov     [rsi], r15
0x14005524f  call    ?Init@XmlDOM@mlib@@CA_NXZ; mlib::XmlDOM::Init(void)
0x140055254  test    al, al
0x140055256  jnz     short loc_140055262
0x140055258  mov     edi, 80004005h
0x14005525d  jmp     loc_1400552F4
0x140055262  lea     rax, [rbp+arg_8]
0x140055266  mov     [rsp+50h+ppv], rax; ppv
0x14005526b  lea     r12, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x140055272  mov     r9, r12; riid
0x140055275  xor     edx, edx; pUnkOuter
0x140055277  lea     r8d, [rdx+1]; dwClsContext
0x14005527b  lea     rcx, ?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A; rclsid
0x140055282  call    cs:__imp_CoCreateInstance
0x140055288  test    eax, eax
0x14005528a  jns     short loc_1400552A2
0x14005528c  lea     rcx, aCannotCreateAn; "cannot create an IXMLDOMDocument2 docum"...
0x140055293  mov     [rsp+50h+var_20], rcx
0x140055298  mov     r8d, eax
0x14005529b  mov     edx, 18Fh
0x1400552a0  jmp     short loc_1400552D2
0x1400552a2  mov     rdx, [rbx]
0x1400552a5  mov     rdx, [rdx+18h]
0x1400552a9  lea     rcx, [rbp+bstrString]
0x1400552ad  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1400552b2  mov     rbx, [rbp+bstrString]
0x1400552b6  test    rbx, rbx
0x1400552b9  jnz     short loc_1400552FB
0x1400552bb  lea     rax, aCannotAllocate_0; "cannot allocate memory for a string"
0x1400552c2  mov     [rsp+50h+var_20], rax
0x1400552c7  mov     edx, 195h
0x1400552cc  mov     r8d, 8007000Eh
0x1400552d2  mov     [rsp+50h+var_28], r14
0x1400552d7  lea     rcx, qword_1401C3B08
0x1400552de  mov     [rsp+50h+ppv], rcx
0x1400552e3  xor     r9d, r9d
0x1400552e6  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x1400552ed  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x1400552f2  mov     edi, eax
0x1400552f4  xor     ecx, ecx
0x1400552f6  jmp     loc_14005539F
0x1400552fb  mov     rcx, [rbp+arg_8]
0x1400552ff  mov     rax, [rcx]
0x140055302  lea     r8, [rbp+arg_18]
0x140055306  mov     rdx, rbx
0x140055309  mov     rax, [rax+208h]
0x140055310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055315  test    eax, eax
0x140055317  jns     short loc_14005534B
0x140055319  mov     r8d, eax
0x14005531c  mov     edx, 19Bh
0x140055321  lea     rcx, aCannotLoadXmlD; "cannot load XML data from a string"
0x140055328  mov     [rsp+50h+var_20], rcx
0x14005532d  mov     [rsp+50h+var_28], r14
0x140055332  mov     [rsp+50h+ppv], r12
0x140055337  mov     r9, [rbp+arg_8]
0x14005533b  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x140055342  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x140055347  mov     edi, eax
0x140055349  jmp     short loc_14005539C
0x14005534b  cmp     [rbp+arg_18], r15w
0x140055350  jnz     short loc_14005535F
0x140055352  mov     edx, 1A0h
0x140055357  mov     r8d, 80004005h
0x14005535d  jmp     short loc_140055321
0x14005535f  mov     rcx, [rbp+arg_8]
0x140055363  mov     rax, [rcx]
0x140055366  or      edx, 0FFFFFFFFh
0x140055369  mov     rax, [rax+240h]
0x140055370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055375  mov     edi, eax
0x140055377  test    eax, eax
0x140055379  jns     short loc_140055391
0x14005537b  lea     rax, aCannotSetThePr; "cannot set the 'preserve white space' f"...
0x140055382  mov     [rsp+50h+var_20], rax
0x140055387  mov     r8d, edi
0x14005538a  mov     edx, 1ABh
0x14005538f  jmp     short loc_14005532D
0x140055391  mov     rax, [rbp+arg_8]
0x140055395  mov     [rbp+arg_8], r15
0x140055399  mov     [rsi], rax
0x14005539c  mov     rcx, rbx; bstrString
0x14005539f  call    cs:__imp_SysFreeString
0x1400553a5  nop
0x1400553a6  lea     rcx, [rbp+arg_8]
0x1400553aa  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x1400553af  mov     eax, edi
0x1400553b1  lea     r11, [rsp+50h+var_s0]
0x1400553b6  mov     rbx, [r11+30h]
0x1400553ba  mov     rsi, [r11+40h]
0x1400553be  mov     rsp, r11
0x1400553c1  pop     r15
0x1400553c3  pop     r14
0x1400553c5  pop     r12
0x1400553c7  pop     rdi
0x1400553c8  pop     rbp
0x1400553c9  retn
```
