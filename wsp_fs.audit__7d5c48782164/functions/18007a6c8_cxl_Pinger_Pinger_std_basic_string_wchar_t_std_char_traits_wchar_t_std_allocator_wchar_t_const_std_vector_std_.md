# cxl::Pinger::Pinger(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,cxl::ResourceTraceManager &,uint,uint,FlushDnsCache::Enum,ThrowIfHostNotFound::Enum)

- ea: `0x18007a6c8`
- end: `0x18007a91f`
- name: `??0Pinger@cxl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@AEAVResourceTraceManager@1@IIW4Enum@FlushDnsCache@@W46ThrowIfHostNotFound@@@Z`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x1800655d4`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000d580`
- `0x18000d5b8`
- `0x18000d600`
- `0x18000d624`
- `0x18000d6a4`
- `0x18000e14c`
- `0x180010bb4`
- `0x1800124ac`
- `0x180019d88`
- `0x180054354`
- `0x180079e9c`
- `0x180079ed0`
- `0x18007a220`
- `0x18007a6c8`

## import_xrefs

- `IPHLPAPI!Icmp6CreateFile` at `0x18007a7b0`
- `IPHLPAPI!Icmp6CreateFile` at `0x18007a7b0`
- `IPHLPAPI!IcmpCreateFile` at `0x18007a7a0`
- `IPHLPAPI!IcmpCreateFile` at `0x18007a7a0`
- `DNSAPI!DnsFlushResolverCacheEntry_W` at `0x18007a8eb`
- `DNSAPI!DnsFlushResolverCacheEntry_W` at `0x18007a8eb`

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
  __int64 v16; // rax
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v19; // [rsp+38h] [rbp-C8h]
  _QWORD v20[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+C0h] [rbp-40h] BYREF

  v20[2] = a1;
  LODWORD(v18) = 20000;
  v19 = 5000;
  std::wstring::wstring();
  std::vector<std::wstring>::vector<std::wstring>(a1 + 32, a3);
  *(_WORD *)(a1 + 56) = 257;
  *(_DWORD *)(a1 + 60) = v19;
  *(_DWORD *)(a1 + 64) = v18;
  v8 = std::wstring::wstring(v22, L"\"]");
  v9 = std::wstring::wstring(v23, L"[cxl::Pinger-\"");
  v10 = std::operator+<wchar_t>(v21, v9, a2);
  std::operator+<wchar_t>(a1 + 72, v10, v8);
  std::wstring::_Tidy_deallocate(v21);
  std::wstring::_Tidy_deallocate(v23);
  std::wstring::_Tidy_deallocate(v22);
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
    std::wstring::wstring(v23, L" Neither IPv4 or IPv6 stacks are supported.");
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 72);
    v14 = std::wstring::_Insert<wchar_t>(v13);
    std::wstring::wstring(v22, v14);
    v15 = std::wstring::wstring(v21, L"internal error");
    LODWORD(v20[0]) = 1359;
    cxl::Error<std::wstring>(pExceptionObject, v20, v15, v22);
    throw (cxl::ExceptionWithArg<std::wstring> *)pExceptionObject;
  }
  if ( v19 > (unsigned int)v18 )
  {
    std::wstring::wstring(v21);
    cxl::StringWriter::StringWriter(v22, v21);
    cxl::TextWriter::Write<char,std::wstring,unsigned int,unsigned int>((struct cxl::TextWriter *)v22, (__int64)&v18);
    v20[0] = 87;
    cxl::Exception::Exception(pExceptionObject, v20, v21);
    throw (cxl::Exception *)pExceptionObject;
  }
  v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  DnsFlushResolverCacheEntry_W(v16);
  return a1;
}

```

## disassembly

```asm
0x18007a6c8  mov     [rsp-8+arg_18], rbx
0x18007a6cd  push    rbp
0x18007a6ce  push    rsi
0x18007a6cf  push    rdi
0x18007a6d0  push    r14
0x18007a6d2  push    r15
0x18007a6d4  lea     rbp, [rsp-60h]
0x18007a6d9  sub     rsp, 160h
0x18007a6e0  mov     rax, cs:__security_cookie
0x18007a6e7  xor     rax, rsp
0x18007a6ea  mov     [rbp+80h+var_30], rax
0x18007a6ee  mov     rdi, r9
0x18007a6f1  mov     rbx, r8
0x18007a6f4  mov     r15, rdx
0x18007a6f7  mov     rsi, rcx
0x18007a6fa  mov     [rsp+180h+var_130], rcx
0x18007a6ff  mov     dword ptr [rsp+180h+var_150], 4E20h
0x18007a707  mov     [rsp+180h+var_148], 1388h
0x18007a70f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18007a714  nop
0x18007a715  lea     rcx, [rsi+20h]
0x18007a719  mov     rdx, rbx
0x18007a71c  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x18007a721  nop
0x18007a722  mov     word ptr [rsi+38h], 101h
0x18007a728  mov     eax, [rsp+180h+var_148]
0x18007a72c  mov     [rsi+3Ch], eax
0x18007a72f  mov     eax, dword ptr [rsp+180h+var_150]
0x18007a733  mov     [rsi+40h], eax
0x18007a736  lea     rdx, asc_1801378B8; "\"]"
0x18007a73d  lea     rcx, [rbp+80h+var_100]
0x18007a741  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18007a746  mov     rbx, rax
0x18007a749  lea     rdx, aCxlPinger; "[cxl::Pinger-\""
0x18007a750  lea     rcx, [rbp+80h+var_E0]
0x18007a754  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18007a759  nop
0x18007a75a  mov     r8, r15
0x18007a75d  mov     rdx, rax
0x18007a760  lea     rcx, [rsp+180h+var_120]
0x18007a765  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18007a76a  nop
0x18007a76b  lea     r14, [rsi+48h]
0x18007a76f  mov     r8, rbx
0x18007a772  mov     rdx, rax
0x18007a775  mov     rcx, r14
0x18007a778  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x18007a77d  nop
0x18007a77e  lea     rcx, [rsp+180h+var_120]
0x18007a783  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a788  nop
0x18007a789  lea     rcx, [rbp+80h+var_E0]
0x18007a78d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a792  nop
0x18007a793  lea     rcx, [rbp+80h+var_100]
0x18007a797  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a79c  mov     [rsi+68h], rdi
0x18007a7a0  call    cs:__imp_IcmpCreateFile
0x18007a7a7  nop     dword ptr [rax+rax+00h]
0x18007a7ac  mov     [rsi+70h], rax
0x18007a7b0  call    cs:__imp_Icmp6CreateFile
0x18007a7b7  nop     dword ptr [rax+rax+00h]
0x18007a7bc  mov     [rsi+78h], rax
0x18007a7c0  lea     rcx, [rsi+88h]
0x18007a7c7  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x18007a7cc  nop
0x18007a7cd  mov     rax, [rsi+70h]
0x18007a7d1  dec     rax
0x18007a7d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007a7d8  setbe   cl
0x18007a7db  mov     [rsi+80h], cl
0x18007a7e1  mov     rax, [rsi+78h]
0x18007a7e5  dec     rax
0x18007a7e8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007a7ec  setbe   al
0x18007a7ef  mov     [rsi+81h], al
0x18007a7f5  test    cl, cl
0x18007a7f7  jnz     short loc_18007A874
0x18007a7f9  test    al, al
0x18007a7fb  jnz     short loc_18007A874
0x18007a7fd  lea     rdx, aNeitherIpv4OrI; " Neither IPv4 or IPv6 stacks are suppor"...
0x18007a804  lea     rcx, [rbp+80h+var_E0]
0x18007a808  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18007a80d  mov     rdx, rax
0x18007a810  mov     rcx, r14
0x18007a813  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18007a818  mov     r8, rax
0x18007a81b  mov     r9, [r14+10h]
0x18007a81f  mov     rcx, rdx; Src
0x18007a822  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z; std::wstring::_Insert<wchar_t>(unsigned __int64,wchar_t const * const,unsigned __int64)
0x18007a827  mov     rdx, rax
0x18007a82a  lea     rcx, [rbp+80h+var_100]
0x18007a82e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18007a833  nop
0x18007a834  lea     rdx, aInternalError; "internal error"
0x18007a83b  lea     rcx, [rsp+180h+var_120]
0x18007a840  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18007a845  nop
0x18007a846  mov     dword ptr [rsp+180h+var_140], 54Fh
0x18007a84e  lea     r9, [rbp+80h+var_100]
0x18007a852  mov     r8, rax
0x18007a855  lea     rdx, [rsp+180h+var_140]
0x18007a85a  lea     rcx, [rbp+80h+pExceptionObject]
0x18007a85e  call    ??$Error@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@YA?AV?$ExceptionWithArg@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@AEBW4Enum@ErrorCode@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; cxl::Error<std::wstring>(cxl::ErrorCode::Enum const &,std::wstring const &,std::wstring const &)
0x18007a863  lea     rdx, _TI3?AV?$ExceptionWithArg@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@; pThrowInfo
0x18007a86a  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x18007a86e  call    _CxxThrowException_0
0x18007a874  mov     eax, dword ptr [rsp+180h+var_150]
0x18007a878  cmp     [rsp+180h+var_148], eax
0x18007a87c  jbe     short loc_18007A8E0
0x18007a87e  lea     rcx, [rsp+180h+var_120]
0x18007a883  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18007a888  nop
0x18007a889  lea     rdx, [rsp+180h+var_120]
0x18007a88e  lea     rcx, [rbp+80h+var_100]
0x18007a892  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18007a897  nop
0x18007a898  lea     rax, [rsp+180h+var_150]
0x18007a89d  mov     [rsp+180h+var_160], rax; __int64
0x18007a8a2  lea     r9, [rsp+180h+var_148]
0x18007a8a7  mov     r8, r14
0x18007a8aa  lea     rcx, [rbp+80h+var_100]; struct cxl::TextWriter *
0x18007a8ae  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@II@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBI2@Z; cxl::TextWriter::Write<char,std::wstring,uint,uint>(char const *,std::wstring const &,uint const &,uint const &)
0x18007a8b3  mov     [rsp+180h+var_140], 57h ; 'W'
0x18007a8bc  lea     r8, [rsp+180h+var_120]
0x18007a8c1  lea     rdx, [rsp+180h+var_140]
0x18007a8c6  lea     rcx, [rbp+80h+pExceptionObject]
0x18007a8ca  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18007a8cf  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18007a8d6  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x18007a8da  call    _CxxThrowException_0
0x18007a8e0  mov     rcx, r15
0x18007a8e3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18007a8e8  mov     rcx, rax
0x18007a8eb  call    cs:__imp_DnsFlushResolverCacheEntry_W
0x18007a8f2  nop     dword ptr [rax+rax+00h]
0x18007a8f7  nop
0x18007a8f8  mov     rax, rsi
0x18007a8fb  mov     rcx, [rbp+80h+var_30]
0x18007a8ff  xor     rcx, rsp; StackCookie
0x18007a902  call    __security_check_cookie
0x18007a907  mov     rbx, [rsp+180h+arg_18]
0x18007a90f  add     rsp, 160h
0x18007a916  pop     r15
0x18007a918  pop     r14
0x18007a91a  pop     rdi
0x18007a91b  pop     rsi
0x18007a91c  pop     rbp
0x18007a91d  retn
```
