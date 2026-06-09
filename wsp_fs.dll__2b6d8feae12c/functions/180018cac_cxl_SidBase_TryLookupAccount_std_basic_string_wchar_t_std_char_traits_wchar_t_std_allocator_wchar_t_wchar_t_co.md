# cxl::SidBase::TryLookupAccount(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,_SID_NAME_USE *)

- ea: `0x180018cac`
- end: `0x180018e06`
- name: `?TryLookupAccount@SidBase@cxl@@QEBAKPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0PEAW4_SID_NAME_USE@@@Z`
- size: `346`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c91c`
- `0x180066b84`

## callees

- `0x18001072c`
- `0x180013134`
- `0x1800145a0`
- `0x180018cac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018dcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018dcf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180018cd0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180018cd0`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180018d1b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180018d96`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180018d1b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180018d96`

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
        std::wstring::assign(a2);
        if ( a4 )
          std::wstring::assign(a4);
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
0x180018cac  mov     [rsp-18h+arg_8], rbx
0x180018cb1  mov     [rsp-18h+arg_10], r8
0x180018cb6  push    rbp
0x180018cb7  push    rsi
0x180018cb8  push    rdi
0x180018cb9  mov     rbp, rsp
0x180018cbc  sub     rsp, 80h
0x180018cc3  mov     rdi, r9
0x180018cc6  mov     rsi, rdx
0x180018cc9  mov     rbx, rcx
0x180018ccc  mov     rcx, [rcx+10h]; pSid
0x180018cd0  call    cs:__imp_IsValidSid
0x180018cd6  test    eax, eax
0x180018cd8  jz      loc_180018DEC
0x180018cde  mov     [rbp+cchName], 0
0x180018ce5  mov     [rbp+arg_0], 0
0x180018cec  mov     [rbp+var_3C], 6
0x180018cf3  lea     rax, [rbp+var_3C]
0x180018cf7  mov     [rsp+80h+peUse], rax; peUse
0x180018cfc  lea     rax, [rbp+arg_0]
0x180018d00  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180018d05  mov     [rsp+80h+ReferencedDomainName], 0; ReferencedDomainName
0x180018d0e  lea     r9, [rbp+cchName]; cchName
0x180018d12  xor     r8d, r8d; Name
0x180018d15  mov     rdx, [rbx+10h]; Sid
0x180018d19  xor     ecx, ecx; lpSystemName
0x180018d1b  call    cs:__imp_LookupAccountSidW
0x180018d21  test    eax, eax
0x180018d23  jnz     short loc_180018D3D
0x180018d25  call    cs:__imp_GetLastError
0x180018d2b  cmp     eax, 7Ah ; 'z'
0x180018d2e  jz      short loc_180018D3D
0x180018d30  call    cs:__imp_GetLastError
0x180018d36  mov     ebx, eax
0x180018d38  jmp     loc_180018DF1
0x180018d3d  mov     byte ptr [rbp+arg_10], 0
0x180018d41  mov     edx, [rbp+cchName]
0x180018d44  add     rdx, rdx
0x180018d47  lea     r8, [rbp+arg_10]
0x180018d4b  lea     rcx, [rbp+Name]
0x180018d4f  call    ??$?0V?$allocator@D@std@@$0A@@?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBDAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,char const &,std::allocator<char> const &)
0x180018d54  nop
0x180018d55  mov     byte ptr [rbp+arg_10], 0
0x180018d59  mov     edx, [rbp+arg_0]
0x180018d5c  add     rdx, rdx
0x180018d5f  lea     r8, [rbp+arg_10]
0x180018d63  lea     rcx, [rbp+var_38]
0x180018d67  call    ??$?0V?$allocator@D@std@@$0A@@?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBDAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,char const &,std::allocator<char> const &)
0x180018d6c  nop
0x180018d6d  mov     rax, [rbp+var_38]
0x180018d71  lea     rcx, [rbp+var_3C]
0x180018d75  mov     [rsp+80h+peUse], rcx; peUse
0x180018d7a  lea     rcx, [rbp+arg_0]
0x180018d7e  mov     [rsp+80h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180018d83  mov     [rsp+80h+ReferencedDomainName], rax; ReferencedDomainName
0x180018d88  lea     r9, [rbp+cchName]; cchName
0x180018d8c  mov     r8, [rbp+Name]; Name
0x180018d90  mov     rdx, [rbx+10h]; Sid
0x180018d94  xor     ecx, ecx; lpSystemName
0x180018d96  call    cs:__imp_LookupAccountSidW
0x180018d9c  test    eax, eax
0x180018d9e  jz      short loc_180018DCF
0x180018da0  xor     ebx, ebx
0x180018da2  mov     rdx, [rbp+Name]
0x180018da6  mov     rcx, rsi
0x180018da9  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180018dae  test    rdi, rdi
0x180018db1  jz      short loc_180018DBF
0x180018db3  mov     rdx, [rbp+var_38]
0x180018db7  mov     rcx, rdi
0x180018dba  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180018dbf  mov     rcx, [rbp+arg_20]
0x180018dc3  test    rcx, rcx
0x180018dc6  jz      short loc_180018DD7
0x180018dc8  mov     eax, [rbp+var_3C]
0x180018dcb  mov     [rcx], eax
0x180018dcd  jmp     short loc_180018DD7
0x180018dcf  call    cs:__imp_GetLastError
0x180018dd5  mov     ebx, eax
0x180018dd7  lea     rcx, [rbp+var_38]
0x180018ddb  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180018de0  nop
0x180018de1  lea     rcx, [rbp+Name]
0x180018de5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180018dea  jmp     short loc_180018DF1
0x180018dec  mov     ebx, 539h
0x180018df1  mov     eax, ebx
0x180018df3  mov     rbx, [rsp+80h+arg_8]
0x180018dfb  add     rsp, 80h
0x180018e02  pop     rdi
0x180018e03  pop     rsi
0x180018e04  pop     rbp
0x180018e05  retn
```
