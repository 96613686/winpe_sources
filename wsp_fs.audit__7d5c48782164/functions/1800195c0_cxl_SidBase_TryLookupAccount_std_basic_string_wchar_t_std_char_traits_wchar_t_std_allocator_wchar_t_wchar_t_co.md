# cxl::SidBase::TryLookupAccount(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,_SID_NAME_USE *)

- ea: `0x1800195c0`
- end: `0x180019738`
- name: `?TryLookupAccount@SidBase@cxl@@QEBAKPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0PEAW4_SID_NAME_USE@@@Z`
- size: `376`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d418`
- `0x180067e54`

## callees

- `0x180010b90`
- `0x180013630`
- `0x180014bfc`
- `0x180019198`
- `0x1800195c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001963e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001964f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001963e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001964f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196fa`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001962e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800196bb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001962e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800196bb`

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
0x1800195c0  mov     [rsp-18h+arg_8], rbx
0x1800195c5  mov     [rsp-18h+arg_10], r8
0x1800195ca  push    rbp
0x1800195cb  push    rsi
0x1800195cc  push    rdi
0x1800195cd  mov     rbp, rsp
0x1800195d0  sub     rsp, 80h
0x1800195d7  mov     rdi, r9
0x1800195da  mov     rsi, rdx
0x1800195dd  mov     rbx, rcx
0x1800195e0  mov     rcx, [rcx+10h]; struct _SID *
0x1800195e4  call    ?IsValidSid@Sid@Health@Wsp@@SA_NPEBU_SID@@@Z; Wsp::Health::Sid::IsValidSid(_SID const *)
0x1800195e9  test    al, al
0x1800195eb  jz      loc_18001971D
0x1800195f1  mov     [rbp+cchName], 0
0x1800195f8  mov     [rbp+arg_0], 0
0x1800195ff  mov     [rbp+var_3C], 6
0x180019606  lea     rax, [rbp+var_3C]
0x18001960a  mov     [rsp+80h+peUse], rax; peUse
0x18001960f  lea     rax, [rbp+arg_0]
0x180019613  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180019618  mov     [rsp+80h+ReferencedDomainName], 0; ReferencedDomainName
0x180019621  lea     r9, [rbp+cchName]; cchName
0x180019625  xor     r8d, r8d; Name
0x180019628  mov     rdx, [rbx+10h]; Sid
0x18001962c  xor     ecx, ecx; lpSystemName
0x18001962e  call    cs:__imp_LookupAccountSidW
0x180019635  nop     dword ptr [rax+rax+00h]
0x18001963a  test    eax, eax
0x18001963c  jnz     short loc_180019662
0x18001963e  call    cs:__imp_GetLastError
0x180019645  nop     dword ptr [rax+rax+00h]
0x18001964a  cmp     eax, 7Ah ; 'z'
0x18001964d  jz      short loc_180019662
0x18001964f  call    cs:__imp_GetLastError
0x180019656  nop     dword ptr [rax+rax+00h]
0x18001965b  mov     ebx, eax
0x18001965d  jmp     loc_180019722
0x180019662  mov     byte ptr [rbp+arg_10], 0
0x180019666  mov     edx, [rbp+cchName]
0x180019669  add     rdx, rdx
0x18001966c  lea     r8, [rbp+arg_10]
0x180019670  lea     rcx, [rbp+Name]
0x180019674  call    ??$?0V?$allocator@D@std@@$0A@@?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBDAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,char const &,std::allocator<char> const &)
0x180019679  nop
0x18001967a  mov     byte ptr [rbp+arg_10], 0
0x18001967e  mov     edx, [rbp+arg_0]
0x180019681  add     rdx, rdx
0x180019684  lea     r8, [rbp+arg_10]
0x180019688  lea     rcx, [rbp+var_38]
0x18001968c  call    ??$?0V?$allocator@D@std@@$0A@@?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBDAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,char const &,std::allocator<char> const &)
0x180019691  nop
0x180019692  mov     rax, [rbp+var_38]
0x180019696  lea     rcx, [rbp+var_3C]
0x18001969a  mov     [rsp+80h+peUse], rcx; peUse
0x18001969f  lea     rcx, [rbp+arg_0]
0x1800196a3  mov     [rsp+80h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x1800196a8  mov     [rsp+80h+ReferencedDomainName], rax; ReferencedDomainName
0x1800196ad  lea     r9, [rbp+cchName]; cchName
0x1800196b1  mov     r8, [rbp+Name]; Name
0x1800196b5  mov     rdx, [rbx+10h]; Sid
0x1800196b9  xor     ecx, ecx; lpSystemName
0x1800196bb  call    cs:__imp_LookupAccountSidW
0x1800196c2  nop     dword ptr [rax+rax+00h]
0x1800196c7  test    eax, eax
0x1800196c9  jz      short loc_1800196FA
0x1800196cb  xor     ebx, ebx
0x1800196cd  mov     rdx, [rbp+Name]
0x1800196d1  mov     rcx, rsi
0x1800196d4  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800196d9  test    rdi, rdi
0x1800196dc  jz      short loc_1800196EA
0x1800196de  mov     rdx, [rbp+var_38]
0x1800196e2  mov     rcx, rdi
0x1800196e5  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800196ea  mov     rcx, [rbp+arg_20]
0x1800196ee  test    rcx, rcx
0x1800196f1  jz      short loc_180019708
0x1800196f3  mov     eax, [rbp+var_3C]
0x1800196f6  mov     [rcx], eax
0x1800196f8  jmp     short loc_180019708
0x1800196fa  call    cs:__imp_GetLastError
0x180019701  nop     dword ptr [rax+rax+00h]
0x180019706  mov     ebx, eax
0x180019708  lea     rcx, [rbp+var_38]
0x18001970c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180019711  nop
0x180019712  lea     rcx, [rbp+Name]
0x180019716  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001971b  jmp     short loc_180019722
0x18001971d  mov     ebx, 539h
0x180019722  mov     eax, ebx
0x180019724  mov     rbx, [rsp+80h+arg_8]
0x18001972c  add     rsp, 80h
0x180019733  pop     rdi
0x180019734  pop     rsi
0x180019735  pop     rbp
0x180019736  retn
```
