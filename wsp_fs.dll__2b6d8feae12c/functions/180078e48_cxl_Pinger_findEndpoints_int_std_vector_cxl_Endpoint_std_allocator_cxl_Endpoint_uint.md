# cxl::Pinger::findEndpoints(int,std::vector<cxl::Endpoint,std::allocator<cxl::Endpoint>> &,uint)

- ea: `0x180078e48`
- end: `0x180079074`
- name: `?findEndpoints@Pinger@cxl@@AEAAXHAEAV?$vector@VEndpoint@cxl@@V?$allocator@VEndpoint@cxl@@@std@@@std@@I@Z`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180078758`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d298`
- `0x18000d33c`
- `0x18000dd74`
- `0x18000e6f4`
- `0x180010b68`
- `0x180012028`
- `0x18007825c`
- `0x1800782ac`
- `0x1800783b0`
- `0x1800783dc`
- `0x180078c84`
- `0x180078e48`
- `0x18007959c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180078e9c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180078ee7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180078f12`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180078e9c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180078ee7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180078f12`
- `WS2_32!GetAddrInfoW` at `0x180078ec0`
- `WS2_32!GetAddrInfoW` at `0x180078ec0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180078f0c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180078f0c`
- `DNSAPI!DnsFlushResolverCacheEntry_W` at `0x180078ee1`
- `DNSAPI!DnsFlushResolverCacheEntry_W` at `0x180078ee1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall cxl::Pinger::findEndpoints(__int64 a1, int a2, __int64 a3)
{
  ULONGLONG v5; // rbx
  const WCHAR *v6; // rax
  INT AddrInfoW; // esi
  __int64 v8; // rax
  ULONGLONG TickCount64; // rax
  ULONGLONG v10; // rax
  struct cxl::TraceManager *v11; // rax
  char *v12; // rdx
  __int64 v13; // rdx
  PADDRINFOW i; // rbx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  PADDRINFOW ppResult; // [rsp+38h] [rbp-C8h] BYREF
  PADDRINFOW *p_ppResult; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v20[2]; // [rsp+48h] [rbp-B8h] BYREF
  ADDRINFOW pHints; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[128]; // [rsp+C0h] [rbp-40h] BYREF

  LODWORD(v17) = a2;
  ppResult = 0;
  p_ppResult = &ppResult;
  memset(&pHints, 0, sizeof(pHints));
  pHints.ai_family = a2;
  v5 = 10000 * GetTickCount64();
  do
  {
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1);
    AddrInfoW = GetAddrInfoW(v6, 0, &pHints, &ppResult);
    if ( !AddrInfoW )
    {
      for ( i = ppResult; i; i = i->ai_next )
      {
        v15 = cxl::Endpoint::Endpoint((cxl::Endpoint *)pExceptionObject, i);
        v16 = *(_QWORD *)(a3 + 8);
        if ( v16 == *(_QWORD *)(a3 + 16) )
          std::vector<cxl::Endpoint>::_Emplace_reallocate<cxl::Endpoint>(a3, v16, v15);
        else
          std::vector<cxl::Endpoint>::_Emplace_back_with_unused_capacity<cxl::Endpoint>(a3, v15);
      }
      goto LABEL_24;
    }
    if ( *(_BYTE *)(a1 + 57) )
    {
      v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1);
      DnsFlushResolverCacheEntry_W(v8);
    }
    TickCount64 = GetTickCount64();
    if ( 10000 * TickCount64 < v5 )
    {
      std::wstring::wstring(v23, L"nowTicks >= startTicks is false");
      cxl::Throw::AssertionFailed(v23);
    }
    if ( 10000 * TickCount64 - v5 >= 0x5F60810 )
      break;
    Sleep(*(_DWORD *)(a1 + 60));
    v10 = GetTickCount64();
    if ( 10000 * v10 < v5 )
    {
      std::wstring::wstring(v22, L"nowTicks >= startTicks is false");
      cxl::Throw::AssertionFailed(v22);
    }
  }
  while ( 10000 * v10 - v5 < 0x5F5E100 );
  if ( *(_BYTE *)(a1 + 56) )
    goto LABEL_16;
  if ( AddrInfoW == 11001 )
  {
    v11 = cxl::TraceManager::Instance();
    v12 = "{0} Host not registered address family {1}.";
    goto LABEL_12;
  }
  if ( AddrInfoW != 11004 )
  {
LABEL_16:
    std::wstring::wstring(v22);
    cxl::StringWriter::StringWriter(v23, v22);
    cxl::TextWriter::Write<char,std::wstring,std::wstring,int>(
      (struct cxl::TextWriter *)v23,
      v13,
      a1 + 72,
      a1,
      (__int64)&v17);
    v20[0] = AddrInfoW;
    v20[1] = 3;
    cxl::Exception::Exception(pExceptionObject, v20, v22);
    throw (cxl::Exception *)pExceptionObject;
  }
  v11 = cxl::TraceManager::Instance();
  v12 = "{0} Host registered, but no records of type {1}";
LABEL_12:
  cxl::TextWriter::WriteLine<char,std::wstring,int>((struct cxl::TraceManager *)((char *)v11 + 160), v12);
LABEL_24:
  cxl::pinger_private::AutoFreeAddrInfoW::~AutoFreeAddrInfoW((cxl::pinger_private::AutoFreeAddrInfoW *)&p_ppResult);
}

```

## disassembly

```asm
0x180078e48  push    rbp
0x180078e4a  push    rbx
0x180078e4b  push    rsi
0x180078e4c  push    rdi
0x180078e4d  push    r14
0x180078e4f  lea     rbp, [rsp-50h]
0x180078e54  sub     rsp, 150h
0x180078e5b  mov     rax, cs:__security_cookie
0x180078e62  xor     rax, rsp
0x180078e65  mov     [rbp+70h+var_30], rax
0x180078e69  mov     r14, r8
0x180078e6c  mov     rdi, rcx
0x180078e6f  mov     dword ptr [rsp+170h+var_140], edx
0x180078e73  mov     [rsp+170h+ppResult], 0
0x180078e7c  lea     rax, [rsp+170h+ppResult]
0x180078e81  mov     [rsp+170h+var_130], rax
0x180078e86  xorps   xmm0, xmm0
0x180078e89  movups  xmmword ptr [rsp+170h+pHints.ai_flags], xmm0
0x180078e8e  movups  xmmword ptr [rsp+170h+pHints.ai_addrlen], xmm0
0x180078e93  movups  xmmword ptr [rsp+170h+pHints.ai_addr], xmm0
0x180078e98  mov     [rsp+170h+pHints.ai_family], edx
0x180078e9c  call    cs:__imp_GetTickCount64
0x180078ea2  imul    rbx, rax, 2710h
0x180078ea9  mov     rcx, rdi
0x180078eac  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180078eb1  lea     r9, [rsp+170h+ppResult]; ppResult
0x180078eb6  lea     r8, [rsp+170h+pHints]; pHints
0x180078ebb  xor     edx, edx; pServiceName
0x180078ebd  mov     rcx, rax; pNodeName
0x180078ec0  call    cs:__imp_GetAddrInfoW
0x180078ec6  mov     esi, eax
0x180078ec8  test    eax, eax
0x180078eca  jz      loc_180079015
0x180078ed0  cmp     byte ptr [rdi+39h], 0
0x180078ed4  jz      short loc_180078EE7
0x180078ed6  mov     rcx, rdi
0x180078ed9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180078ede  mov     rcx, rax
0x180078ee1  call    cs:__imp_DnsFlushResolverCacheEntry_W
0x180078ee7  call    cs:__imp_GetTickCount64
0x180078eed  imul    rcx, rax, 2710h
0x180078ef4  cmp     rcx, rbx
0x180078ef7  jb      loc_180078FFA
0x180078efd  sub     rcx, rbx
0x180078f00  cmp     rcx, 5F60810h
0x180078f07  jnb     short loc_180078F34
0x180078f09  mov     ecx, [rdi+3Ch]; dwMilliseconds
0x180078f0c  call    cs:__imp_Sleep
0x180078f12  call    cs:__imp_GetTickCount64
0x180078f18  imul    rcx, rax, 2710h
0x180078f1f  cmp     rcx, rbx
0x180078f22  jb      short loc_180078F68
0x180078f24  sub     rcx, rbx
0x180078f27  cmp     rcx, 5F5E100h
0x180078f2e  jb      loc_180078EA9
0x180078f34  cmp     byte ptr [rdi+38h], 0
0x180078f38  jnz     short loc_180078F99
0x180078f3a  cmp     esi, 2AF9h
0x180078f40  jnz     short loc_180078F83
0x180078f42  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180078f47  lea     rdx, a0HostNotRegist; "{0} Host not registered address family "...
0x180078f4e  lea     r8, [rdi+48h]
0x180078f52  lea     r9, [rsp+170h+var_140]
0x180078f57  lea     rcx, [rax+0A0h]; struct cxl::TextWriter *
0x180078f5e  call    ??$WriteLine@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBH@Z; cxl::TextWriter::WriteLine<char,std::wstring,int>(char const *,std::wstring const &,int const &)
0x180078f63  jmp     loc_180079050
0x180078f68  lea     rdx, aNowticksStartt; "nowTicks >= startTicks is false"
0x180078f6f  lea     rcx, [rbp+70h+var_F0]
0x180078f73  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180078f78  nop
0x180078f79  lea     rcx, [rbp+70h+var_F0]
0x180078f7d  call    ?AssertionFailed@Throw@cxl@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Throw::AssertionFailed(std::wstring const &)
0x180078f83  cmp     esi, 2AFCh
0x180078f89  jnz     short loc_180078F99
0x180078f8b  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180078f90  lea     rdx, a0HostRegistere; "{0} Host registered, but no records of "...
0x180078f97  jmp     short loc_180078F4E
0x180078f99  lea     rcx, [rbp+70h+var_F0]
0x180078f9d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180078fa2  nop
0x180078fa3  lea     rdx, [rbp+70h+var_F0]
0x180078fa7  lea     rcx, [rbp+70h+var_D0]
0x180078fab  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180078fb0  nop
0x180078fb1  lea     r8, [rdi+48h]
0x180078fb5  lea     rax, [rsp+170h+var_140]
0x180078fba  mov     [rsp+170h+var_150], rax; __int64
0x180078fbf  mov     r9, rdi
0x180078fc2  lea     rcx, [rbp+70h+var_D0]; struct cxl::TextWriter *
0x180078fc6  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@H@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEBH@Z; cxl::TextWriter::Write<char,std::wstring,std::wstring,int>(char const *,std::wstring const &,std::wstring const &,int const &)
0x180078fcb  mov     [rsp+170h+var_128], esi
0x180078fcf  mov     [rsp+170h+var_124], 3
0x180078fd7  lea     r8, [rbp+70h+var_F0]
0x180078fdb  lea     rdx, [rsp+170h+var_128]
0x180078fe0  lea     rcx, [rbp+70h+pExceptionObject]
0x180078fe4  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180078fe9  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180078ff0  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180078ff4  call    _CxxThrowException_0
0x180078ffa  lea     rdx, aNowticksStartt; "nowTicks >= startTicks is false"
0x180079001  lea     rcx, [rbp+70h+var_D0]
0x180079005  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18007900a  nop
0x18007900b  lea     rcx, [rbp+70h+var_D0]
0x18007900f  call    ?AssertionFailed@Throw@cxl@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Throw::AssertionFailed(std::wstring const &)
0x180079015  mov     rbx, [rsp+170h+ppResult]
0x18007901a  jmp     short loc_18007904B
0x18007901c  mov     rdx, rbx; struct addrinfoW *
0x18007901f  lea     rcx, [rbp+70h+pExceptionObject]; this
0x180079023  call    ??0Endpoint@cxl@@QEAA@AEBUaddrinfoW@@@Z; cxl::Endpoint::Endpoint(addrinfoW const &)
0x180079028  mov     rdx, [r14+8]
0x18007902c  mov     rcx, r14
0x18007902f  cmp     rdx, [r14+10h]
0x180079033  jz      short loc_18007903F
0x180079035  mov     rdx, rax
0x180079038  call    ??$_Emplace_back_with_unused_capacity@VEndpoint@cxl@@@?$vector@VEndpoint@cxl@@V?$allocator@VEndpoint@cxl@@@std@@@std@@AEAAAEAVEndpoint@cxl@@$$QEAV23@@Z; std::vector<cxl::Endpoint>::_Emplace_back_with_unused_capacity<cxl::Endpoint>(cxl::Endpoint &&)
0x18007903d  jmp     short loc_180079047
0x18007903f  mov     r8, rax
0x180079042  call    ??$_Emplace_reallocate@VEndpoint@cxl@@@?$vector@VEndpoint@cxl@@V?$allocator@VEndpoint@cxl@@@std@@@std@@AEAAPEAVEndpoint@cxl@@QEAV23@$$QEAV23@@Z; std::vector<cxl::Endpoint>::_Emplace_reallocate<cxl::Endpoint>(cxl::Endpoint * const,cxl::Endpoint &&)
0x180079047  mov     rbx, [rbx+28h]
0x18007904b  test    rbx, rbx
0x18007904e  jnz     short loc_18007901C
0x180079050  lea     rcx, [rsp+170h+var_130]; this
0x180079055  call    ??1AutoFreeAddrInfoW@pinger_private@cxl@@QEAA@XZ; cxl::pinger_private::AutoFreeAddrInfoW::~AutoFreeAddrInfoW(void)
0x18007905a  mov     rcx, [rbp+70h+var_30]
0x18007905e  xor     rcx, rsp; StackCookie
0x180079061  call    __security_check_cookie
0x180079066  add     rsp, 150h
0x18007906d  pop     r14
0x18007906f  pop     rdi
0x180079070  pop     rsi
0x180079071  pop     rbx
0x180079072  pop     rbp
0x180079073  retn
```
