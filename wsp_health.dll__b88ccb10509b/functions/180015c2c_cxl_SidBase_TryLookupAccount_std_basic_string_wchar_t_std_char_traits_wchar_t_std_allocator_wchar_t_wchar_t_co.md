# cxl::SidBase::TryLookupAccount(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,_SID_NAME_USE *)

- ea: `0x180015c2c`
- end: `0x180015d86`
- name: `?TryLookupAccount@SidBase@cxl@@QEBAKPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0PEAW4_SID_NAME_USE@@@Z`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019838`

## callees

- `0x18000f3e8`
- `0x180011dc4`
- `0x180013110`
- `0x180015c2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015cb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015cb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d4f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015c50`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015c50`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180015c9b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180015d16`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180015c9b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180015d16`

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
  if ( IsValidSid(*(PSID *)(a1 + 16)) )
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
0x180015c2c  mov     [rsp-18h+arg_8], rbx
0x180015c31  mov     [rsp-18h+arg_10], r8
0x180015c36  push    rbp
0x180015c37  push    rsi
0x180015c38  push    rdi
0x180015c39  mov     rbp, rsp
0x180015c3c  sub     rsp, 80h
0x180015c43  mov     rdi, r9
0x180015c46  mov     rsi, rdx
0x180015c49  mov     rbx, rcx
0x180015c4c  mov     rcx, [rcx+10h]; pSid
0x180015c50  call    cs:__imp_IsValidSid
0x180015c56  test    eax, eax
0x180015c58  jz      loc_180015D6C
0x180015c5e  mov     [rbp+cchName], 0
0x180015c65  mov     [rbp+arg_0], 0
0x180015c6c  mov     [rbp+var_3C], 6
0x180015c73  lea     rax, [rbp+var_3C]
0x180015c77  mov     [rsp+80h+peUse], rax; peUse
0x180015c7c  lea     rax, [rbp+arg_0]
0x180015c80  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180015c85  mov     [rsp+80h+ReferencedDomainName], 0; ReferencedDomainName
0x180015c8e  lea     r9, [rbp+cchName]; cchName
0x180015c92  xor     r8d, r8d; Name
0x180015c95  mov     rdx, [rbx+10h]; Sid
0x180015c99  xor     ecx, ecx; lpSystemName
0x180015c9b  call    cs:__imp_LookupAccountSidW
0x180015ca1  test    eax, eax
0x180015ca3  jnz     short loc_180015CBD
0x180015ca5  call    cs:__imp_GetLastError
0x180015cab  cmp     eax, 7Ah ; 'z'
0x180015cae  jz      short loc_180015CBD
0x180015cb0  call    cs:__imp_GetLastError
0x180015cb6  mov     ebx, eax
0x180015cb8  jmp     loc_180015D71
0x180015cbd  mov     byte ptr [rbp+arg_10], 0
0x180015cc1  mov     edx, [rbp+cchName]
0x180015cc4  add     rdx, rdx
0x180015cc7  lea     r8, [rbp+arg_10]
0x180015ccb  lea     rcx, [rbp+Name]
0x180015ccf  call    ??$?0V?$allocator@D@std@@$0A@@?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBDAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,char const &,std::allocator<char> const &)
0x180015cd4  nop
0x180015cd5  mov     byte ptr [rbp+arg_10], 0
0x180015cd9  mov     edx, [rbp+arg_0]
0x180015cdc  add     rdx, rdx
0x180015cdf  lea     r8, [rbp+arg_10]
0x180015ce3  lea     rcx, [rbp+var_38]
0x180015ce7  call    ??$?0V?$allocator@D@std@@$0A@@?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBDAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,char const &,std::allocator<char> const &)
0x180015cec  nop
0x180015ced  mov     rax, [rbp+var_38]
0x180015cf1  lea     rcx, [rbp+var_3C]
0x180015cf5  mov     [rsp+80h+peUse], rcx; peUse
0x180015cfa  lea     rcx, [rbp+arg_0]
0x180015cfe  mov     [rsp+80h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180015d03  mov     [rsp+80h+ReferencedDomainName], rax; ReferencedDomainName
0x180015d08  lea     r9, [rbp+cchName]; cchName
0x180015d0c  mov     r8, [rbp+Name]; Name
0x180015d10  mov     rdx, [rbx+10h]; Sid
0x180015d14  xor     ecx, ecx; lpSystemName
0x180015d16  call    cs:__imp_LookupAccountSidW
0x180015d1c  test    eax, eax
0x180015d1e  jz      short loc_180015D4F
0x180015d20  xor     ebx, ebx
0x180015d22  mov     rdx, [rbp+Name]
0x180015d26  mov     rcx, rsi
0x180015d29  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180015d2e  test    rdi, rdi
0x180015d31  jz      short loc_180015D3F
0x180015d33  mov     rdx, [rbp+var_38]
0x180015d37  mov     rcx, rdi
0x180015d3a  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180015d3f  mov     rcx, [rbp+arg_20]
0x180015d43  test    rcx, rcx
0x180015d46  jz      short loc_180015D57
0x180015d48  mov     eax, [rbp+var_3C]
0x180015d4b  mov     [rcx], eax
0x180015d4d  jmp     short loc_180015D57
0x180015d4f  call    cs:__imp_GetLastError
0x180015d55  mov     ebx, eax
0x180015d57  lea     rcx, [rbp+var_38]
0x180015d5b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180015d60  nop
0x180015d61  lea     rcx, [rbp+Name]
0x180015d65  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180015d6a  jmp     short loc_180015D71
0x180015d6c  mov     ebx, 539h
0x180015d71  mov     eax, ebx
0x180015d73  mov     rbx, [rsp+80h+arg_8]
0x180015d7b  add     rsp, 80h
0x180015d82  pop     rdi
0x180015d83  pop     rsi
0x180015d84  pop     rbp
0x180015d85  retn
```
