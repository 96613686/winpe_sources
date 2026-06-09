# cxl::SidBase::TryLookupAccount(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,_SID_NAME_USE *)

- ea: `0x180016450`
- end: `0x1800165c8`
- name: `?TryLookupAccount@SidBase@cxl@@QEBAKPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0PEAW4_SID_NAME_USE@@@Z`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a240`

## callees

- `0x18000f89c`
- `0x180012330`
- `0x1800137cc`
- `0x180016318`
- `0x180016450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001658a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001658a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800164be`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001654b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800164be`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001654b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall cxl::SidBase::TryLookupAccount(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        enum _SID_NAME_USE *a5)
{
  DWORD LastError; // ebx
  DWORD cchName; // [rsp+40h] [rbp-40h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-3Ch] BYREF
  LPWSTR ReferencedDomainName[3]; // [rsp+48h] [rbp-38h] BYREF
  LPWSTR Name[4]; // [rsp+60h] [rbp-20h] BYREF
  DWORD cchReferencedDomainName; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v15; // [rsp+B0h] [rbp+30h] BYREF

  v15 = a3;
  if ( Wsp::Health::Sid::IsValidSid(*(const struct _SID **)(a1 + 16)) )
  {
    cchName = 0;
    cchReferencedDomainName = 0;
    peUse = SidTypeDeletedAccount;
    if ( LookupAccountSidW(0, *(PSID *)(a1 + 16), 0, &cchName, 0, &cchReferencedDomainName, &peUse)
      || GetLastError() == 122 )
    {
      LOBYTE(v15) = 0;
      std::vector<char>::vector<char>(Name, 2LL * cchName, &v15);
      LOBYTE(v15) = 0;
      std::vector<char>::vector<char>(ReferencedDomainName, 2LL * cchReferencedDomainName, &v15);
      if ( LookupAccountSidW(
             0,
             *(PSID *)(a1 + 16),
             Name[0],
             &cchName,
             ReferencedDomainName[0],
             &cchReferencedDomainName,
             &peUse) )
      {
        LastError = 0;
        std::wstring::assign(a2, Name[0]);
        if ( a4 )
          std::wstring::assign(a4, ReferencedDomainName[0]);
        if ( a5 )
          *a5 = peUse;
      }
      else
      {
        LastError = GetLastError();
      }
      std::vector<unsigned char>::_Tidy(ReferencedDomainName);
      std::vector<unsigned char>::_Tidy(Name);
    }
    else
    {
      return GetLastError();
    }
  }
  else
  {
    return 1337;
  }
  return LastError;
}

```

## disassembly

```asm
0x180016450  mov     [rsp-18h+arg_8], rbx
0x180016455  mov     [rsp-18h+arg_10], r8
0x18001645a  push    rbp
0x18001645b  push    rsi
0x18001645c  push    rdi
0x18001645d  mov     rbp, rsp
0x180016460  sub     rsp, 80h
0x180016467  mov     rdi, r9
0x18001646a  mov     rsi, rdx
0x18001646d  mov     rbx, rcx
0x180016470  mov     rcx, [rcx+10h]; struct _SID *
0x180016474  call    ?IsValidSid@Sid@Health@Wsp@@SA_NPEBU_SID@@@Z; Wsp::Health::Sid::IsValidSid(_SID const *)
0x180016479  test    al, al
0x18001647b  jz      loc_1800165AD
0x180016481  mov     [rbp+cchName], 0
0x180016488  mov     [rbp+arg_0], 0
0x18001648f  mov     [rbp+var_3C], 6
0x180016496  lea     rax, [rbp+var_3C]
0x18001649a  mov     [rsp+80h+peUse], rax; peUse
0x18001649f  lea     rax, [rbp+arg_0]
0x1800164a3  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800164a8  mov     [rsp+80h+ReferencedDomainName], 0; ReferencedDomainName
0x1800164b1  lea     r9, [rbp+cchName]; cchName
0x1800164b5  xor     r8d, r8d; Name
0x1800164b8  mov     rdx, [rbx+10h]; Sid
0x1800164bc  xor     ecx, ecx; lpSystemName
0x1800164be  call    cs:__imp_LookupAccountSidW
0x1800164c5  nop     dword ptr [rax+rax+00h]
0x1800164ca  test    eax, eax
0x1800164cc  jnz     short loc_1800164F2
0x1800164ce  call    cs:__imp_GetLastError
0x1800164d5  nop     dword ptr [rax+rax+00h]
0x1800164da  cmp     eax, 7Ah ; 'z'
0x1800164dd  jz      short loc_1800164F2
0x1800164df  call    cs:__imp_GetLastError
0x1800164e6  nop     dword ptr [rax+rax+00h]
0x1800164eb  mov     ebx, eax
0x1800164ed  jmp     loc_1800165B2
0x1800164f2  mov     byte ptr [rbp+arg_10], 0
0x1800164f6  mov     edx, [rbp+cchName]
0x1800164f9  add     rdx, rdx
0x1800164fc  lea     r8, [rbp+arg_10]
0x180016500  lea     rcx, [rbp+Name]
0x180016504  call    ??$?0V?$allocator@D@std@@$0A@@?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBDAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,char const &,std::allocator<char> const &)
0x180016509  nop
0x18001650a  mov     byte ptr [rbp+arg_10], 0
0x18001650e  mov     edx, [rbp+arg_0]
0x180016511  add     rdx, rdx
0x180016514  lea     r8, [rbp+arg_10]
0x180016518  lea     rcx, [rbp+var_38]
0x18001651c  call    ??$?0V?$allocator@D@std@@$0A@@?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBDAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,char const &,std::allocator<char> const &)
0x180016521  nop
0x180016522  mov     rax, [rbp+var_38]
0x180016526  lea     rcx, [rbp+var_3C]
0x18001652a  mov     [rsp+80h+peUse], rcx; peUse
0x18001652f  lea     rcx, [rbp+arg_0]
0x180016533  mov     [rsp+80h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180016538  mov     [rsp+80h+ReferencedDomainName], rax; ReferencedDomainName
0x18001653d  lea     r9, [rbp+cchName]; cchName
0x180016541  mov     r8, [rbp+Name]; Name
0x180016545  mov     rdx, [rbx+10h]; Sid
0x180016549  xor     ecx, ecx; lpSystemName
0x18001654b  call    cs:__imp_LookupAccountSidW
0x180016552  nop     dword ptr [rax+rax+00h]
0x180016557  test    eax, eax
0x180016559  jz      short loc_18001658A
0x18001655b  xor     ebx, ebx
0x18001655d  mov     rdx, [rbp+Name]
0x180016561  mov     rcx, rsi
0x180016564  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180016569  test    rdi, rdi
0x18001656c  jz      short loc_18001657A
0x18001656e  mov     rdx, [rbp+var_38]
0x180016572  mov     rcx, rdi
0x180016575  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18001657a  mov     rcx, [rbp+arg_20]
0x18001657e  test    rcx, rcx
0x180016581  jz      short loc_180016598
0x180016583  mov     eax, [rbp+var_3C]
0x180016586  mov     [rcx], eax
0x180016588  jmp     short loc_180016598
0x18001658a  call    cs:__imp_GetLastError
0x180016591  nop     dword ptr [rax+rax+00h]
0x180016596  mov     ebx, eax
0x180016598  lea     rcx, [rbp+var_38]
0x18001659c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800165a1  nop
0x1800165a2  lea     rcx, [rbp+Name]
0x1800165a6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800165ab  jmp     short loc_1800165B2
0x1800165ad  mov     ebx, 539h
0x1800165b2  mov     eax, ebx
0x1800165b4  mov     rbx, [rsp+80h+arg_8]
0x1800165bc  add     rsp, 80h
0x1800165c3  pop     rdi
0x1800165c4  pop     rsi
0x1800165c5  pop     rbp
0x1800165c6  retn
```
