# mlib::XmlDOM::AppendFilesToElementNode(std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>> const &,IXMLDOMNode *)

- ea: `0x18002cc4c`
- end: `0x18002cd64`
- name: `?AppendFilesToElementNode@XmlDOM@mlib@@SA_NAEBV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@PEAUIXMLDOMNode@@@Z`
- size: `280`
- prototype: `char __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d0c0`

## callees

- `0x180001a34`
- `0x18000782c`
- `0x18002cc4c`
- `0x18002cfdc`
- `0x180031010`

## string_xrefs

- `0x18002ccec`: `base\winsat\mlib\mxmldom.cpp`
- `0x18002cd37`: `base\winsat\mlib\mxmldom.cpp`
- `0x18002cd06`: `cannot load XML data from file '%s'`
- `0x18002ccc3`: `cannot append data to a XML node`

## pseudocode

```c
char __fastcall mlib::XmlDOM::AppendFilesToElementNode(__int64 *a1, __int64 a2)
{
  __int64 i; // rbx
  int v5; // r8d
  __int64 v7; // [rsp+60h] [rbp+8h] BYREF

  for ( i = *a1; i != a1[1]; i += 8 )
  {
    v7 = 0;
    if ( (int)mlib::XmlDOM::LoadDocumentFromFile(i, &v7) < 0 )
    {
      mlib::XmlDOM::ReportCOMError_w(
        (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
        457,
        -2147467259,
        v7,
        (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
        0,
        (__int64)L"cannot load XML data from file '%s'",
        *(_QWORD *)(*(_QWORD *)i + 24LL),
        -2);
      goto LABEL_8;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a2 + 168LL))(a2, v7, 0);
    if ( v5 < 0 )
    {
      mlib::XmlDOM::ReportCOMError_w(
        (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
        466,
        v5,
        a2,
        (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
        0,
        (__int64)L"cannot append data to a XML node");
LABEL_8:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
      return 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  }
  return 1;
}

```

## disassembly

```asm
0x18002cc4c  push    rdi
0x18002cc4e  sub     rsp, 50h
0x18002cc52  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002cc5b  mov     [rsp+58h+arg_8], rbx
0x18002cc60  mov     [rsp+58h+arg_10], rsi
0x18002cc65  mov     rsi, rdx
0x18002cc68  mov     rdi, rcx
0x18002cc6b  mov     rbx, [rcx]
0x18002cc6e  cmp     rbx, [rdi+8]
0x18002cc72  jz      loc_18002CD52
0x18002cc78  mov     [rsp+58h+arg_0], 0
0x18002cc81  lea     rdx, [rsp+58h+arg_0]
0x18002cc86  mov     rcx, rbx
0x18002cc89  call    ?LoadDocumentFromFile@XmlDOM@mlib@@SAJAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEAPEAUIXMLDOMNode@@PEAV32@_N@Z; mlib::XmlDOM::LoadDocumentFromFile(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNode * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,bool)
0x18002cc8e  test    eax, eax
0x18002cc90  js      short loc_18002CCFA
0x18002cc92  mov     rax, [rsi]
0x18002cc95  xor     r8d, r8d
0x18002cc98  mov     rdx, [rsp+58h+arg_0]
0x18002cc9d  mov     rcx, rsi
0x18002cca0  mov     rax, [rax+0A8h]
0x18002cca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccac  mov     r8d, eax
0x18002ccaf  test    eax, eax
0x18002ccb1  js      short loc_18002CCC3
0x18002ccb3  lea     rcx, [rsp+58h+arg_0]
0x18002ccb8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ccbd  add     rbx, 8
0x18002ccc1  jmp     short loc_18002CC6E
0x18002ccc3  lea     rax, aCannotAppendDa; "cannot append data to a XML node"
0x18002ccca  mov     [rsp+58h+var_28], rax
0x18002cccf  mov     [rsp+58h+var_30], 0
0x18002ccd8  lea     rax, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x18002ccdf  mov     [rsp+58h+var_38], rax
0x18002cce4  mov     r9, rsi
0x18002cce7  mov     edx, 1D2h
0x18002ccec  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18002ccf3  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18002ccf8  jmp     short loc_18002CD44
0x18002ccfa  mov     rax, [rbx]
0x18002ccfd  mov     rcx, [rax+18h]
0x18002cd01  mov     [rsp+58h+var_20], rcx
0x18002cd06  lea     rax, aCannotLoadXmlD; "cannot load XML data from file '%s'"
0x18002cd0d  mov     [rsp+58h+var_28], rax
0x18002cd12  mov     [rsp+58h+var_30], 0
0x18002cd1b  lea     rax, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x18002cd22  mov     [rsp+58h+var_38], rax
0x18002cd27  mov     r9, [rsp+58h+arg_0]
0x18002cd2c  mov     edx, 1C9h
0x18002cd31  mov     r8d, 80004005h
0x18002cd37  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18002cd3e  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x18002cd43  nop
0x18002cd44  lea     rcx, [rsp+58h+arg_0]
0x18002cd49  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002cd4e  xor     al, al
0x18002cd50  jmp     short loc_18002CD54
0x18002cd52  mov     al, 1
0x18002cd54  mov     rbx, [rsp+58h+arg_8]
0x18002cd59  mov     rsi, [rsp+58h+arg_10]
0x18002cd5e  add     rsp, 50h
0x18002cd62  pop     rdi
0x18002cd63  retn
```
