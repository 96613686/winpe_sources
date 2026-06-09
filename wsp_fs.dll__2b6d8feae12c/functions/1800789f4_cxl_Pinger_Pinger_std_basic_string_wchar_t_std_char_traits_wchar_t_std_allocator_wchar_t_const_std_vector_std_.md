# cxl::Pinger::Pinger(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,cxl::ResourceTraceManager &,uint,uint,FlushDnsCache::Enum,ThrowIfHostNotFound::Enum)

- ea: `0x1800789f4`
- end: `0x180078c38`
- name: `??0Pinger@cxl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@AEAVResourceTraceManager@1@IIW4Enum@FlushDnsCache@@W46ThrowIfHostNotFound@@@Z`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x180064310`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000d218`
- `0x18000d250`
- `0x18000d298`
- `0x18000d2bc`
- `0x18000d33c`
- `0x18000dd74`
- `0x180010750`
- `0x180012028`
- `0x180019374`
- `0x180053330`
- `0x1800781d8`
- `0x18007820c`
- `0x180078560`
- `0x1800789f4`

## import_xrefs

- `IPHLPAPI!Icmp6CreateFile` at `0x180078ad6`
- `IPHLPAPI!Icmp6CreateFile` at `0x180078ad6`
- `IPHLPAPI!IcmpCreateFile` at `0x180078acc`
- `IPHLPAPI!IcmpCreateFile` at `0x180078acc`
- `DNSAPI!DnsFlushResolverCacheEntry_W` at `0x180078c0b`
- `DNSAPI!DnsFlushResolverCacheEntry_W` at `0x180078c0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall cxl::Pinger::Pinger(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  bool v11; // cl
  bool v12; // al
  void *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v23[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v24[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+C0h] [rbp-40h] BYREF

  v21[2] = a1;
  LODWORD(v19) = 20000;
  v20 = 5000;
  std::wstring::wstring(a1);
  std::vector<std::wstring>::vector<std::wstring>(a1 + 32, a3);
  *(_WORD *)(a1 + 56) = 257;
  *(_DWORD *)(a1 + 60) = v20;
  *(_DWORD *)(a1 + 64) = v19;
  v8 = std::wstring::wstring(v23, L"\"]");
  v9 = std::wstring::wstring(v24, L"[cxl::Pinger-\"");
  v10 = std::operator+<wchar_t>(v22, v9, a2);
  std::operator+<wchar_t>(a1 + 72, v10, v8);
  std::wstring::_Tidy_deallocate(v22);
  std::wstring::_Tidy_deallocate(v24);
  std::wstring::_Tidy_deallocate(v23);
  *(_QWORD *)(a1 + 104) = a4;
  *(_QWORD *)(a1 + 112) = IcmpCreateFile();
  *(_QWORD *)(a1 + 120) = Icmp6CreateFile();
  std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(a1 + 136);
  v11 = (unsigned __int64)(*(_QWORD *)(a1 + 112) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL;
  *(_BYTE *)(a1 + 128) = v11;
  v12 = (unsigned __int64)(*(_QWORD *)(a1 + 120) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL;
  *(_BYTE *)(a1 + 129) = v12;
  if ( !v11 && !v12 )
  {
    std::wstring::wstring(v24, L" Neither IPv4 or IPv6 stacks are supported.");
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 72);
    v14 = std::wstring::_Insert<wchar_t>(v13);
    std::wstring::wstring(v23, v14);
    v15 = std::wstring::wstring(v22, L"internal error");
    LODWORD(v21[0]) = 1359;
    cxl::Error<std::wstring>(pExceptionObject, v21, v15, v23);
    throw (cxl::ExceptionWithArg<std::wstring> *)pExceptionObject;
  }
  if ( v20 > (unsigned int)v19 )
  {
    std::wstring::wstring(v22);
    cxl::StringWriter::StringWriter(v23, v22);
    cxl::TextWriter::Write<char,std::wstring,unsigned int,unsigned int>(
      (struct cxl::TextWriter *)v23,
      v16,
      a1 + 72,
      (__int64)&v20,
      (__int64)&v19);
    v21[0] = 87;
    cxl::Exception::Exception(pExceptionObject, v21, v22);
    throw (cxl::Exception *)pExceptionObject;
  }
  v17 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  DnsFlushResolverCacheEntry_W(v17);
  return a1;
}

```

## disassembly

```asm
0x1800789f4  mov     [rsp-8+arg_18], rbx
0x1800789f9  push    rbp
0x1800789fa  push    rsi
0x1800789fb  push    rdi
0x1800789fc  push    r14
0x1800789fe  push    r15
0x180078a00  lea     rbp, [rsp-60h]
0x180078a05  sub     rsp, 160h
0x180078a0c  mov     rax, cs:__security_cookie
0x180078a13  xor     rax, rsp
0x180078a16  mov     [rbp+80h+var_30], rax
0x180078a1a  mov     rdi, r9
0x180078a1d  mov     rbx, r8
0x180078a20  mov     r15, rdx
0x180078a23  mov     rsi, rcx
0x180078a26  mov     [rsp+180h+var_130], rcx
0x180078a2b  mov     dword ptr [rsp+180h+var_150], 4E20h
0x180078a33  mov     [rsp+180h+var_148], 1388h
0x180078a3b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180078a40  nop
0x180078a41  lea     rcx, [rsi+20h]
0x180078a45  mov     rdx, rbx
0x180078a48  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180078a4d  nop
0x180078a4e  mov     word ptr [rsi+38h], 101h
0x180078a54  mov     eax, [rsp+180h+var_148]
0x180078a58  mov     [rsi+3Ch], eax
0x180078a5b  mov     eax, dword ptr [rsp+180h+var_150]
0x180078a5f  mov     [rsi+40h], eax
0x180078a62  lea     rdx, asc_180135850; "\"]"
0x180078a69  lea     rcx, [rbp+80h+var_100]
0x180078a6d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180078a72  mov     rbx, rax
0x180078a75  lea     rdx, aCxlPinger; "[cxl::Pinger-\""
0x180078a7c  lea     rcx, [rbp+80h+var_E0]
0x180078a80  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180078a85  nop
0x180078a86  mov     r8, r15
0x180078a89  mov     rdx, rax
0x180078a8c  lea     rcx, [rsp+180h+var_120]
0x180078a91  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x180078a96  nop
0x180078a97  lea     r14, [rsi+48h]
0x180078a9b  mov     r8, rbx
0x180078a9e  mov     rdx, rax
0x180078aa1  mov     rcx, r14
0x180078aa4  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x180078aa9  nop
0x180078aaa  lea     rcx, [rsp+180h+var_120]
0x180078aaf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078ab4  nop
0x180078ab5  lea     rcx, [rbp+80h+var_E0]
0x180078ab9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078abe  nop
0x180078abf  lea     rcx, [rbp+80h+var_100]
0x180078ac3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078ac8  mov     [rsi+68h], rdi
0x180078acc  call    cs:__imp_IcmpCreateFile
0x180078ad2  mov     [rsi+70h], rax
0x180078ad6  call    cs:__imp_Icmp6CreateFile
0x180078adc  mov     [rsi+78h], rax
0x180078ae0  lea     rcx, [rsi+88h]
0x180078ae7  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x180078aec  nop
0x180078aed  mov     rax, [rsi+70h]
0x180078af1  dec     rax
0x180078af4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180078af8  setbe   cl
0x180078afb  mov     [rsi+80h], cl
0x180078b01  mov     rax, [rsi+78h]
0x180078b05  dec     rax
0x180078b08  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180078b0c  setbe   al
0x180078b0f  mov     [rsi+81h], al
0x180078b15  test    cl, cl
0x180078b17  jnz     short loc_180078B94
0x180078b19  test    al, al
0x180078b1b  jnz     short loc_180078B94
0x180078b1d  lea     rdx, aNeitherIpv4OrI; " Neither IPv4 or IPv6 stacks are suppor"...
0x180078b24  lea     rcx, [rbp+80h+var_E0]
0x180078b28  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180078b2d  mov     rdx, rax
0x180078b30  mov     rcx, r14
0x180078b33  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180078b38  mov     r8, rax
0x180078b3b  mov     r9, [r14+10h]
0x180078b3f  mov     rcx, rdx; Src
0x180078b42  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z; std::wstring::_Insert<wchar_t>(unsigned __int64,wchar_t const * const,unsigned __int64)
0x180078b47  mov     rdx, rax
0x180078b4a  lea     rcx, [rbp+80h+var_100]
0x180078b4e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180078b53  nop
0x180078b54  lea     rdx, aInternalError; "internal error"
0x180078b5b  lea     rcx, [rsp+180h+var_120]
0x180078b60  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180078b65  nop
0x180078b66  mov     dword ptr [rsp+180h+var_140], 54Fh
0x180078b6e  lea     r9, [rbp+80h+var_100]
0x180078b72  mov     r8, rax
0x180078b75  lea     rdx, [rsp+180h+var_140]
0x180078b7a  lea     rcx, [rbp+80h+pExceptionObject]
0x180078b7e  call    ??$Error@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@YA?AV?$ExceptionWithArg@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@AEBW4Enum@ErrorCode@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; cxl::Error<std::wstring>(cxl::ErrorCode::Enum const &,std::wstring const &,std::wstring const &)
0x180078b83  lea     rdx, _TI3?AV?$ExceptionWithArg@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@; pThrowInfo
0x180078b8a  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180078b8e  call    _CxxThrowException_0
0x180078b94  mov     eax, dword ptr [rsp+180h+var_150]
0x180078b98  cmp     [rsp+180h+var_148], eax
0x180078b9c  jbe     short loc_180078C00
0x180078b9e  lea     rcx, [rsp+180h+var_120]
0x180078ba3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180078ba8  nop
0x180078ba9  lea     rdx, [rsp+180h+var_120]
0x180078bae  lea     rcx, [rbp+80h+var_100]
0x180078bb2  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180078bb7  nop
0x180078bb8  lea     rax, [rsp+180h+var_150]
0x180078bbd  mov     [rsp+180h+var_160], rax; __int64
0x180078bc2  lea     r9, [rsp+180h+var_148]
0x180078bc7  mov     r8, r14
0x180078bca  lea     rcx, [rbp+80h+var_100]; struct cxl::TextWriter *
0x180078bce  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@II@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBI2@Z; cxl::TextWriter::Write<char,std::wstring,uint,uint>(char const *,std::wstring const &,uint const &,uint const &)
0x180078bd3  mov     [rsp+180h+var_140], 57h ; 'W'
0x180078bdc  lea     r8, [rsp+180h+var_120]
0x180078be1  lea     rdx, [rsp+180h+var_140]
0x180078be6  lea     rcx, [rbp+80h+pExceptionObject]
0x180078bea  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180078bef  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180078bf6  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180078bfa  call    _CxxThrowException_0
0x180078c00  mov     rcx, r15
0x180078c03  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180078c08  mov     rcx, rax
0x180078c0b  call    cs:__imp_DnsFlushResolverCacheEntry_W
0x180078c11  nop
0x180078c12  mov     rax, rsi
0x180078c15  mov     rcx, [rbp+80h+var_30]
0x180078c19  xor     rcx, rsp; StackCookie
0x180078c1c  call    __security_check_cookie
0x180078c21  mov     rbx, [rsp+180h+arg_18]
0x180078c29  add     rsp, 160h
0x180078c30  pop     r15
0x180078c32  pop     r14
0x180078c34  pop     rdi
0x180078c35  pop     rsi
0x180078c36  pop     rbp
0x180078c37  retn
```
