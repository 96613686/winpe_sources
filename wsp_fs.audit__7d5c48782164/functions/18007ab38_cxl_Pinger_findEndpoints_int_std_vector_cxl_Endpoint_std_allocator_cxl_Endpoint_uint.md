# cxl::Pinger::findEndpoints(int,std::vector<cxl::Endpoint,std::allocator<cxl::Endpoint>> &,uint)

- ea: `0x18007ab38`
- end: `0x18007ad89`
- name: `?findEndpoints@Pinger@cxl@@AEAAXHAEAV?$vector@VEndpoint@cxl@@V?$allocator@VEndpoint@cxl@@@std@@@std@@I@Z`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x18007a418`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000e14c`
- `0x18000eb18`
- `0x180010fdc`
- `0x1800124ac`
- `0x180079f20`
- `0x180079f70`
- `0x18007a070`
- `0x18007a09c`
- `0x18007a970`
- `0x18007ab38`
- `0x18007b2f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007ab8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007abe9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007ac20`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007ab8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007abe9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18007ac20`
- `WS2_32!GetAddrInfoW` at `0x18007abb6`
- `WS2_32!GetAddrInfoW` at `0x18007abb6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007ac14`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007ac14`
- `DNSAPI!DnsFlushResolverCacheEntry_W` at `0x18007abdd`
- `DNSAPI!DnsFlushResolverCacheEntry_W` at `0x18007abdd`

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
  PADDRINFOW i; // rbx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  PADDRINFOW ppResult; // [rsp+38h] [rbp-C8h] BYREF
  PADDRINFOW *p_ppResult; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v19[2]; // [rsp+48h] [rbp-B8h] BYREF
  ADDRINFOW pHints; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v22[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[128]; // [rsp+C0h] [rbp-40h] BYREF

  LODWORD(v16) = a2;
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
        v14 = cxl::Endpoint::Endpoint((cxl::Endpoint *)pExceptionObject, i);
        v15 = *(_QWORD *)(a3 + 8);
        if ( v15 == *(_QWORD *)(a3 + 16) )
          std::vector<cxl::Endpoint>::_Emplace_reallocate<cxl::Endpoint>(a3, v15, v14);
        else
          std::vector<cxl::Endpoint>::_Emplace_back_with_unused_capacity<cxl::Endpoint>(a3, v14);
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
      std::wstring::wstring(v22, L"nowTicks >= startTicks is false");
      cxl::Throw::AssertionFailed(v22);
    }
    if ( 10000 * TickCount64 - v5 >= 0x5F60810 )
      break;
    Sleep(*(_DWORD *)(a1 + 60));
    v10 = GetTickCount64();
    if ( 10000 * v10 < v5 )
    {
      std::wstring::wstring(v21, L"nowTicks >= startTicks is false");
      cxl::Throw::AssertionFailed(v21);
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
    std::wstring::wstring(v21);
    cxl::StringWriter::StringWriter(v22, v21);
    cxl::TextWriter::Write<char,std::wstring,std::wstring,int>((struct cxl::TextWriter *)v22, (__int64)&v16);
    v19[0] = AddrInfoW;
    v19[1] = 3;
    cxl::Exception::Exception(pExceptionObject, v19, v21);
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
0x18007ab38  push    rbp
0x18007ab3a  push    rbx
0x18007ab3b  push    rsi
0x18007ab3c  push    rdi
0x18007ab3d  push    r14
0x18007ab3f  lea     rbp, [rsp-50h]
0x18007ab44  sub     rsp, 150h
0x18007ab4b  mov     rax, cs:__security_cookie
0x18007ab52  xor     rax, rsp
0x18007ab55  mov     [rbp+70h+var_30], rax
0x18007ab59  mov     r14, r8
0x18007ab5c  mov     rdi, rcx
0x18007ab5f  mov     dword ptr [rsp+170h+var_140], edx
0x18007ab63  mov     [rsp+170h+ppResult], 0
0x18007ab6c  lea     rax, [rsp+170h+ppResult]
0x18007ab71  mov     [rsp+170h+var_130], rax
0x18007ab76  xorps   xmm0, xmm0
0x18007ab79  movups  xmmword ptr [rsp+170h+pHints.ai_flags], xmm0
0x18007ab7e  movups  xmmword ptr [rsp+170h+pHints.ai_addrlen], xmm0
0x18007ab83  movups  xmmword ptr [rsp+170h+pHints.ai_addr], xmm0
0x18007ab88  mov     [rsp+170h+pHints.ai_family], edx
0x18007ab8c  call    cs:__imp_GetTickCount64
0x18007ab93  nop     dword ptr [rax+rax+00h]
0x18007ab98  imul    rbx, rax, 2710h
0x18007ab9f  mov     rcx, rdi
0x18007aba2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18007aba7  lea     r9, [rsp+170h+ppResult]; ppResult
0x18007abac  lea     r8, [rsp+170h+pHints]; pHints
0x18007abb1  xor     edx, edx; pServiceName
0x18007abb3  mov     rcx, rax; pNodeName
0x18007abb6  call    cs:__imp_GetAddrInfoW
0x18007abbd  nop     dword ptr [rax+rax+00h]
0x18007abc2  mov     esi, eax
0x18007abc4  test    eax, eax
0x18007abc6  jz      loc_18007AD29
0x18007abcc  cmp     byte ptr [rdi+39h], 0
0x18007abd0  jz      short loc_18007ABE9
0x18007abd2  mov     rcx, rdi
0x18007abd5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18007abda  mov     rcx, rax
0x18007abdd  call    cs:__imp_DnsFlushResolverCacheEntry_W
0x18007abe4  nop     dword ptr [rax+rax+00h]
0x18007abe9  call    cs:__imp_GetTickCount64
0x18007abf0  nop     dword ptr [rax+rax+00h]
0x18007abf5  imul    rcx, rax, 2710h
0x18007abfc  cmp     rcx, rbx
0x18007abff  jb      loc_18007AD0E
0x18007ac05  sub     rcx, rbx
0x18007ac08  cmp     rcx, 5F60810h
0x18007ac0f  jnb     short loc_18007AC48
0x18007ac11  mov     ecx, [rdi+3Ch]; dwMilliseconds
0x18007ac14  call    cs:__imp_Sleep
0x18007ac1b  nop     dword ptr [rax+rax+00h]
0x18007ac20  call    cs:__imp_GetTickCount64
0x18007ac27  nop     dword ptr [rax+rax+00h]
0x18007ac2c  imul    rcx, rax, 2710h
0x18007ac33  cmp     rcx, rbx
0x18007ac36  jb      short loc_18007AC7C
0x18007ac38  sub     rcx, rbx
0x18007ac3b  cmp     rcx, 5F5E100h
0x18007ac42  jb      loc_18007AB9F
0x18007ac48  cmp     byte ptr [rdi+38h], 0
0x18007ac4c  jnz     short loc_18007ACAD
0x18007ac4e  cmp     esi, 2AF9h
0x18007ac54  jnz     short loc_18007AC97
0x18007ac56  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18007ac5b  lea     rdx, a0HostNotRegist; "{0} Host not registered address family "...
0x18007ac62  lea     r8, [rdi+48h]
0x18007ac66  lea     r9, [rsp+170h+var_140]
0x18007ac6b  lea     rcx, [rax+0A0h]; struct cxl::TextWriter *
0x18007ac72  call    ??$WriteLine@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBH@Z; cxl::TextWriter::WriteLine<char,std::wstring,int>(char const *,std::wstring const &,int const &)
0x18007ac77  jmp     loc_18007AD64
0x18007ac7c  lea     rdx, aNowticksStartt; "nowTicks >= startTicks is false"
0x18007ac83  lea     rcx, [rbp+70h+var_F0]
0x18007ac87  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18007ac8c  nop
0x18007ac8d  lea     rcx, [rbp+70h+var_F0]
0x18007ac91  call    ?AssertionFailed@Throw@cxl@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Throw::AssertionFailed(std::wstring const &)
0x18007ac97  cmp     esi, 2AFCh
0x18007ac9d  jnz     short loc_18007ACAD
0x18007ac9f  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18007aca4  lea     rdx, a0HostRegistere; "{0} Host registered, but no records of "...
0x18007acab  jmp     short loc_18007AC62
0x18007acad  lea     rcx, [rbp+70h+var_F0]
0x18007acb1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18007acb6  nop
0x18007acb7  lea     rdx, [rbp+70h+var_F0]
0x18007acbb  lea     rcx, [rbp+70h+var_D0]
0x18007acbf  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18007acc4  nop
0x18007acc5  lea     r8, [rdi+48h]
0x18007acc9  lea     rax, [rsp+170h+var_140]
0x18007acce  mov     [rsp+170h+var_150], rax; __int64
0x18007acd3  mov     r9, rdi
0x18007acd6  lea     rcx, [rbp+70h+var_D0]; struct cxl::TextWriter *
0x18007acda  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@H@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEBH@Z; cxl::TextWriter::Write<char,std::wstring,std::wstring,int>(char const *,std::wstring const &,std::wstring const &,int const &)
0x18007acdf  mov     [rsp+170h+var_128], esi
0x18007ace3  mov     [rsp+170h+var_124], 3
0x18007aceb  lea     r8, [rbp+70h+var_F0]
0x18007acef  lea     rdx, [rsp+170h+var_128]
0x18007acf4  lea     rcx, [rbp+70h+pExceptionObject]
0x18007acf8  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18007acfd  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18007ad04  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x18007ad08  call    _CxxThrowException_0
0x18007ad0e  lea     rdx, aNowticksStartt; "nowTicks >= startTicks is false"
0x18007ad15  lea     rcx, [rbp+70h+var_D0]
0x18007ad19  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18007ad1e  nop
0x18007ad1f  lea     rcx, [rbp+70h+var_D0]
0x18007ad23  call    ?AssertionFailed@Throw@cxl@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Throw::AssertionFailed(std::wstring const &)
0x18007ad29  mov     rbx, [rsp+170h+ppResult]
0x18007ad2e  jmp     short loc_18007AD5F
0x18007ad30  mov     rdx, rbx; struct addrinfoW *
0x18007ad33  lea     rcx, [rbp+70h+pExceptionObject]; this
0x18007ad37  call    ??0Endpoint@cxl@@QEAA@AEBUaddrinfoW@@@Z; cxl::Endpoint::Endpoint(addrinfoW const &)
0x18007ad3c  mov     rdx, [r14+8]
0x18007ad40  mov     rcx, r14
0x18007ad43  cmp     rdx, [r14+10h]
0x18007ad47  jz      short loc_18007AD53
0x18007ad49  mov     rdx, rax
0x18007ad4c  call    ??$_Emplace_back_with_unused_capacity@VEndpoint@cxl@@@?$vector@VEndpoint@cxl@@V?$allocator@VEndpoint@cxl@@@std@@@std@@AEAAAEAVEndpoint@cxl@@$$QEAV23@@Z; std::vector<cxl::Endpoint>::_Emplace_back_with_unused_capacity<cxl::Endpoint>(cxl::Endpoint &&)
0x18007ad51  jmp     short loc_18007AD5B
0x18007ad53  mov     r8, rax
0x18007ad56  call    ??$_Emplace_reallocate@VEndpoint@cxl@@@?$vector@VEndpoint@cxl@@V?$allocator@VEndpoint@cxl@@@std@@@std@@AEAAPEAVEndpoint@cxl@@QEAV23@$$QEAV23@@Z; std::vector<cxl::Endpoint>::_Emplace_reallocate<cxl::Endpoint>(cxl::Endpoint * const,cxl::Endpoint &&)
0x18007ad5b  mov     rbx, [rbx+28h]
0x18007ad5f  test    rbx, rbx
0x18007ad62  jnz     short loc_18007AD30
0x18007ad64  lea     rcx, [rsp+170h+var_130]; this
0x18007ad69  call    ??1AutoFreeAddrInfoW@pinger_private@cxl@@QEAA@XZ; cxl::pinger_private::AutoFreeAddrInfoW::~AutoFreeAddrInfoW(void)
0x18007ad6e  mov     rcx, [rbp+70h+var_30]
0x18007ad72  xor     rcx, rsp; StackCookie
0x18007ad75  call    __security_check_cookie
0x18007ad7a  add     rsp, 150h
0x18007ad81  pop     r14
0x18007ad83  pop     rdi
0x18007ad84  pop     rsi
0x18007ad85  pop     rbx
0x18007ad86  pop     rbp
0x18007ad87  retn
```
