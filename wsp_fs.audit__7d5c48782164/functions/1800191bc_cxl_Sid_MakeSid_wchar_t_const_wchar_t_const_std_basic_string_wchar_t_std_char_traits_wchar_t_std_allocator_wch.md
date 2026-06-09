# cxl::Sid::MakeSid(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,_SID_NAME_USE *)

- ea: `0x1800191bc`
- end: `0x1800193b8`
- name: `?MakeSid@Sid@cxl@@QEAAXPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAW4_SID_NAME_USE@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(cxl::SidBase *this)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800620cc`
- `0x180067a9c`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f178`
- `0x1800124ac`
- `0x180013630`
- `0x180014bfc`
- `0x180015748`
- `0x180015ae4`
- `0x180015bb0`
- `0x1800191bc`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001937d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001937d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001934e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001934e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180019232`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180019305`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180019232`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180019305`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall cxl::Sid::MakeSid(cxl::SidBase *this, __int64 a2, const WCHAR *a3)
{
  unsigned int v5; // edx
  struct _SID *v6; // rbx
  _BYTE v8[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD LastError; // [rsp+50h] [rbp-B0h] BYREF
  int v13; // [rsp+54h] [rbp-ACh]
  _BYTE v14[32]; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR ReferencedDomainName[4]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v16[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+C0h] [rbp-40h] BYREF

  (*(void (__fastcall **)(cxl::SidBase *))(*(_QWORD *)this + 8LL))(this);
  cbSid = 0;
  cchReferencedDomainName = 0;
  peUse = SidTypeInvalid;
  if ( !LookupAccountNameW(0, a3, 0, &cbSid, 0, &cchReferencedDomainName, &peUse) && GetLastError() != 122 )
  {
    std::wstring::wstring(ReferencedDomainName);
    cxl::StringWriter::StringWriter(v16, ReferencedDomainName);
    cxl::TextWriter::Write<52>(v16);
    LastError = GetLastError();
    v13 = 0;
    cxl::Exception::Exception(pExceptionObject, &LastError, ReferencedDomainName);
    throw (cxl::Exception *)pExceptionObject;
  }
  v8[0] = 0;
  std::vector<char>::vector<char>(ReferencedDomainName, 2LL * cchReferencedDomainName, v8);
  v6 = (struct _SID *)cxl::LocalHeap::Alloc(cbSid, v5);
  if ( !LookupAccountNameW(0, a3, v6, &cbSid, ReferencedDomainName[0], &cchReferencedDomainName, &peUse) )
  {
    FreeSid(v6);
    std::wstring::wstring(v16);
    cxl::StringWriter::StringWriter(v14, v16);
    cxl::TextWriter::Write<26>(v14);
    LastError = GetLastError();
    v13 = 0;
    cxl::Exception::Exception(pExceptionObject, &LastError, v16);
    throw (cxl::Exception *)pExceptionObject;
  }
  cxl::SidBase::Attach(this, v6);
  return std::vector<unsigned char>::_Tidy(ReferencedDomainName);
}

```

## disassembly

```asm
0x1800191bc  mov     [rsp-8+arg_8], rbx
0x1800191c1  push    rbp
0x1800191c2  push    rsi
0x1800191c3  push    rdi
0x1800191c4  lea     rbp, [rsp-40h]
0x1800191c9  sub     rsp, 140h
0x1800191d0  mov     rax, cs:__security_cookie
0x1800191d7  xor     rax, rsp
0x1800191da  mov     [rbp+50h+var_20], rax
0x1800191de  mov     rsi, r8
0x1800191e1  mov     rdi, rcx
0x1800191e4  mov     rax, [rcx]
0x1800191e7  mov     rax, [rax+8]
0x1800191eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191f0  mov     [rsp+150h+cbSid], 0
0x1800191f8  mov     [rsp+150h+var_10C], 0
0x180019200  mov     [rsp+150h+var_104], 7
0x180019208  lea     rax, [rsp+150h+var_104]
0x18001920d  mov     [rsp+150h+peUse], rax; peUse
0x180019212  lea     rax, [rsp+150h+var_10C]
0x180019217  mov     [rsp+150h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001921c  mov     [rsp+150h+ReferencedDomainName], 0; ReferencedDomainName
0x180019225  lea     r9, [rsp+150h+cbSid]; cbSid
0x18001922a  xor     r8d, r8d; Sid
0x18001922d  mov     rdx, rsi; lpAccountName
0x180019230  xor     ecx, ecx; lpSystemName
0x180019232  call    cs:__imp_LookupAccountNameW
0x180019239  nop     dword ptr [rax+rax+00h]
0x18001923e  test    eax, eax
0x180019240  jnz     short loc_1800192B2
0x180019242  call    cs:__imp_GetLastError
0x180019249  nop     dword ptr [rax+rax+00h]
0x18001924e  cmp     eax, 7Ah ; 'z'
0x180019251  jz      short loc_1800192B2
0x180019253  lea     rcx, [rsp+150h+var_D8]
0x180019258  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001925d  nop
0x18001925e  lea     rdx, [rsp+150h+var_D8]
0x180019263  lea     rcx, [rbp+50h+var_B8]
0x180019267  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001926c  nop
0x18001926d  lea     rcx, [rbp+50h+var_B8]
0x180019271  call    ??$Write@$0DE@@TextWriter@cxl@@QEAAAEAV01@AEAY0DE@$$CBD@Z; cxl::TextWriter::Write<52>(char const (&)[52])
0x180019276  call    cs:__imp_GetLastError
0x18001927d  nop     dword ptr [rax+rax+00h]
0x180019282  mov     [rsp+150h+var_100], eax
0x180019286  mov     [rsp+150h+var_FC], 0
0x18001928e  lea     r8, [rsp+150h+var_D8]
0x180019293  lea     rdx, [rsp+150h+var_100]
0x180019298  lea     rcx, [rbp+50h+pExceptionObject]
0x18001929c  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800192a1  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800192a8  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x1800192ac  call    _CxxThrowException_0
0x1800192b2  mov     [rsp+150h+var_110], 0
0x1800192b7  mov     edx, [rsp+150h+var_10C]
0x1800192bb  add     rdx, rdx
0x1800192be  lea     r8, [rsp+150h+var_110]
0x1800192c3  lea     rcx, [rsp+150h+var_D8]
0x1800192c8  call    ??$?0V?$allocator@D@std@@$0A@@?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBDAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,char const &,std::allocator<char> const &)
0x1800192cd  nop
0x1800192ce  mov     ecx, [rsp+150h+cbSid]; uBytes
0x1800192d2  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x1800192d7  mov     rbx, rax
0x1800192da  lea     rax, [rsp+150h+var_104]
0x1800192df  mov     [rsp+150h+peUse], rax; peUse
0x1800192e4  lea     rax, [rsp+150h+var_10C]
0x1800192e9  mov     [rsp+150h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800192ee  mov     r8, [rsp+150h+var_D8]
0x1800192f3  mov     [rsp+150h+ReferencedDomainName], r8; ReferencedDomainName
0x1800192f8  lea     r9, [rsp+150h+cbSid]; cbSid
0x1800192fd  mov     r8, rbx; Sid
0x180019300  mov     rdx, rsi; lpAccountName
0x180019303  xor     ecx, ecx; lpSystemName
0x180019305  call    cs:__imp_LookupAccountNameW
0x18001930c  nop     dword ptr [rax+rax+00h]
0x180019311  test    eax, eax
0x180019313  jz      short loc_18001934B
0x180019315  mov     rdx, rbx; struct _SID *
0x180019318  mov     rcx, rdi; this
0x18001931b  call    ?Attach@SidBase@cxl@@QEAAXPEAU_SID@@@Z; cxl::SidBase::Attach(_SID *)
0x180019320  nop
0x180019321  lea     rcx, [rsp+150h+var_D8]
0x180019326  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001932b  mov     rcx, [rbp+50h+var_20]
0x18001932f  xor     rcx, rsp; StackCookie
0x180019332  call    __security_check_cookie
0x180019337  mov     rbx, [rsp+150h+arg_8]
0x18001933f  add     rsp, 140h
0x180019346  pop     rdi
0x180019347  pop     rsi
0x180019348  pop     rbp
0x180019349  retn
0x18001934b  mov     rcx, rbx; pSid
0x18001934e  call    cs:__imp_FreeSid
0x180019355  nop     dword ptr [rax+rax+00h]
0x18001935a  lea     rcx, [rbp+50h+var_B8]
0x18001935e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019363  nop
0x180019364  lea     rdx, [rbp+50h+var_B8]
0x180019368  lea     rcx, [rsp+150h+var_F8]
0x18001936d  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180019372  nop
0x180019373  lea     rcx, [rsp+150h+var_F8]
0x180019378  call    ??$Write@$0BK@@TextWriter@cxl@@QEAAAEAV01@AEAY0BK@$$CBD@Z; cxl::TextWriter::Write<26>(char const (&)[26])
0x18001937d  call    cs:__imp_GetLastError
0x180019384  nop     dword ptr [rax+rax+00h]
0x180019389  mov     [rsp+150h+var_100], eax
0x18001938d  mov     [rsp+150h+var_FC], 0
0x180019395  lea     r8, [rbp+50h+var_B8]
0x180019399  lea     rdx, [rsp+150h+var_100]
0x18001939e  lea     rcx, [rbp+50h+pExceptionObject]
0x1800193a2  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800193a7  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800193ae  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x1800193b2  call    _CxxThrowException_0
```
