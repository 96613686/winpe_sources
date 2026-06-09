# cxl::Sid::MakeSid(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,_SID_NAME_USE *)

- ea: `0x1800188e4`
- end: `0x180018abb`
- name: `?MakeSid@Sid@cxl@@QEAAXPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAW4_SID_NAME_USE@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(cxl::SidBase *this)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180060e9c`
- `0x1800667cc`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000ed38`
- `0x180012028`
- `0x180013134`
- `0x1800145a0`
- `0x180015054`
- `0x1800153e4`
- `0x1800154ac`
- `0x1800188e4`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a86`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180018a5d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180018a5d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001895a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180018a1b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18001895a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180018a1b`

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
    cxl::TextWriter::Write<52>((__int64)v16);
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
    cxl::TextWriter::Write<26>((__int64)v14);
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
0x1800188e4  mov     [rsp-8+arg_8], rbx
0x1800188e9  push    rbp
0x1800188ea  push    rsi
0x1800188eb  push    rdi
0x1800188ec  lea     rbp, [rsp-40h]
0x1800188f1  sub     rsp, 140h
0x1800188f8  mov     rax, cs:__security_cookie
0x1800188ff  xor     rax, rsp
0x180018902  mov     [rbp+50h+var_20], rax
0x180018906  mov     rsi, r8
0x180018909  mov     rdi, rcx
0x18001890c  mov     rax, [rcx]
0x18001890f  mov     rax, [rax+8]
0x180018913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018918  mov     [rsp+150h+cbSid], 0
0x180018920  mov     [rsp+150h+var_10C], 0
0x180018928  mov     [rsp+150h+var_104], 7
0x180018930  lea     rax, [rsp+150h+var_104]
0x180018935  mov     [rsp+150h+peUse], rax; peUse
0x18001893a  lea     rax, [rsp+150h+var_10C]
0x18001893f  mov     [rsp+150h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180018944  mov     [rsp+150h+ReferencedDomainName], 0; ReferencedDomainName
0x18001894d  lea     r9, [rsp+150h+cbSid]; cbSid
0x180018952  xor     r8d, r8d; Sid
0x180018955  mov     rdx, rsi; lpAccountName
0x180018958  xor     ecx, ecx; lpSystemName
0x18001895a  call    cs:__imp_LookupAccountNameW
0x180018960  test    eax, eax
0x180018962  jnz     short loc_1800189C8
0x180018964  call    cs:__imp_GetLastError
0x18001896a  cmp     eax, 7Ah ; 'z'
0x18001896d  jz      short loc_1800189C8
0x18001896f  lea     rcx, [rsp+150h+var_D8]
0x180018974  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018979  nop
0x18001897a  lea     rdx, [rsp+150h+var_D8]
0x18001897f  lea     rcx, [rbp+50h+var_B8]
0x180018983  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180018988  nop
0x180018989  lea     rcx, [rbp+50h+var_B8]
0x18001898d  call    ??$Write@$0DE@@TextWriter@cxl@@QEAAAEAV01@AEAY0DE@$$CBD@Z; cxl::TextWriter::Write<52>(char const (&)[52])
0x180018992  call    cs:__imp_GetLastError
0x180018998  mov     [rsp+150h+var_100], eax
0x18001899c  mov     [rsp+150h+var_FC], 0
0x1800189a4  lea     r8, [rsp+150h+var_D8]
0x1800189a9  lea     rdx, [rsp+150h+var_100]
0x1800189ae  lea     rcx, [rbp+50h+pExceptionObject]
0x1800189b2  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800189b7  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800189be  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x1800189c2  call    _CxxThrowException_0
0x1800189c8  mov     [rsp+150h+var_110], 0
0x1800189cd  mov     edx, [rsp+150h+var_10C]
0x1800189d1  add     rdx, rdx
0x1800189d4  lea     r8, [rsp+150h+var_110]
0x1800189d9  lea     rcx, [rsp+150h+var_D8]
0x1800189de  call    ??$?0V?$allocator@D@std@@$0A@@?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBDAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,char const &,std::allocator<char> const &)
0x1800189e3  nop
0x1800189e4  mov     ecx, [rsp+150h+cbSid]; uBytes
0x1800189e8  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x1800189ed  mov     rbx, rax
0x1800189f0  lea     rax, [rsp+150h+var_104]
0x1800189f5  mov     [rsp+150h+peUse], rax; peUse
0x1800189fa  lea     rax, [rsp+150h+var_10C]
0x1800189ff  mov     [rsp+150h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180018a04  mov     r8, [rsp+150h+var_D8]
0x180018a09  mov     [rsp+150h+ReferencedDomainName], r8; ReferencedDomainName
0x180018a0e  lea     r9, [rsp+150h+cbSid]; cbSid
0x180018a13  mov     r8, rbx; Sid
0x180018a16  mov     rdx, rsi; lpAccountName
0x180018a19  xor     ecx, ecx; lpSystemName
0x180018a1b  call    cs:__imp_LookupAccountNameW
0x180018a21  test    eax, eax
0x180018a23  jz      short loc_180018A5A
0x180018a25  mov     rdx, rbx; struct _SID *
0x180018a28  mov     rcx, rdi; this
0x180018a2b  call    ?Attach@SidBase@cxl@@QEAAXPEAU_SID@@@Z; cxl::SidBase::Attach(_SID *)
0x180018a30  nop
0x180018a31  lea     rcx, [rsp+150h+var_D8]
0x180018a36  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180018a3b  mov     rcx, [rbp+50h+var_20]
0x180018a3f  xor     rcx, rsp; StackCookie
0x180018a42  call    __security_check_cookie
0x180018a47  mov     rbx, [rsp+150h+arg_8]
0x180018a4f  add     rsp, 140h
0x180018a56  pop     rdi
0x180018a57  pop     rsi
0x180018a58  pop     rbp
0x180018a59  retn
0x180018a5a  mov     rcx, rbx; pSid
0x180018a5d  call    cs:__imp_FreeSid
0x180018a63  lea     rcx, [rbp+50h+var_B8]
0x180018a67  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018a6c  nop
0x180018a6d  lea     rdx, [rbp+50h+var_B8]
0x180018a71  lea     rcx, [rsp+150h+var_F8]
0x180018a76  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180018a7b  nop
0x180018a7c  lea     rcx, [rsp+150h+var_F8]
0x180018a81  call    ??$Write@$0BK@@TextWriter@cxl@@QEAAAEAV01@AEAY0BK@$$CBD@Z; cxl::TextWriter::Write<26>(char const (&)[26])
0x180018a86  call    cs:__imp_GetLastError
0x180018a8c  mov     [rsp+150h+var_100], eax
0x180018a90  mov     [rsp+150h+var_FC], 0
0x180018a98  lea     r8, [rbp+50h+var_B8]
0x180018a9c  lea     rdx, [rsp+150h+var_100]
0x180018aa1  lea     rcx, [rbp+50h+pExceptionObject]
0x180018aa5  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018aaa  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018ab1  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180018ab5  call    _CxxThrowException_0
```
