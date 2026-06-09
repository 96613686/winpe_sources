# Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(void * const)

- ea: `0x1800f17f8`
- end: `0x1800f1a23`
- name: `?GetOwnerSecurityOfSid@WiFiCloudStore@Internal@Windows@@YA?AW4ProfileOwnerSecurity@123@QEAX@Z`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180207138`

## callees

- `0x18000a994`
- `0x1800ca87c`
- `0x1800e09a0`
- `0x1800f17f8`
- `0x1801049ac`
- `0x18010e5ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f19f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f19f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f1898`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f18ed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f1898`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f18ed`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800f1813`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800f1827`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800f183b`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800f184f`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800f1813`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800f1827`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800f183b`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800f184f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f1928`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f1928`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800f19ea`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800f19ea`

## string_xrefs

- `0x1800f18ff`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`
- `0x1800f1937`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`
- `0x1800f1883`: `DefaultAccountSID`
- `0x1800f18d8`: `DefaultAccountSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(void *a1)
{
  unsigned int ValueW; // eax
  const char *v4; // r9
  unsigned __int16 *v5; // rax
  int v6; // r8d
  int v7; // ecx
  unsigned int pdwType; // [rsp+20h] [rbp-48h]
  PVOID pvData[5]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD cchName; // [rsp+70h] [rbp+8h] BYREF
  _SID_NAME_USE peUse; // [rsp+78h] [rbp+10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+80h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+88h] [rbp+20h] BYREF

  if ( !a1 )
    return 4;
  if ( IsWellKnownSid(a1, WinWorldSid) || IsWellKnownSid(a1, WinLocalSystemSid) )
    return 2;
  if ( IsWellKnownSid(a1, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid)
    || IsWellKnownSid(a1, WinLocalServiceSid) )
  {
    return 3;
  }
  cchName = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
          L"DefaultAccountSID",
          2u,
          0,
          0,
          &cchName) )
  {
    try
    {
      std::vector<unsigned char>::vector<unsigned char>(pvData, cchName);
      ValueW = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
                 L"DefaultAccountSID",
                 2u,
                 0,
                 pvData[0],
                 &cchName);
      if ( ValueW )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
          (const char *)ValueW,
          pdwType);
      StringSid = 0;
      if ( !ConvertSidToStringSidW(a1, &StringSid) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
          v4);
      v5 = (unsigned __int16 *)pvData[0];
      do
      {
        v6 = *(unsigned __int16 *)((char *)v5 + (char *)StringSid - (char *)pvData[0]);
        v7 = *v5 - v6;
        if ( v7 )
          break;
        ++v5;
      }
      while ( v6 );
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
        v4);
      return 1;
    }
    if ( !v7 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      std::vector<unsigned char>::_Tidy(pvData);
      return 3;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    std::vector<unsigned char>::_Tidy(pvData);
  }
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = SidTypeUnknown;
  if ( LookupAccountSidW(0, a1, 0, &cchName, 0, &cchReferencedDomainName, &peUse) || GetLastError() != 1332 )
    return 1;
  else
    return 3;
}

```

## disassembly

```asm
0x1800f17f8  push    rbx
0x1800f17fa  sub     rsp, 60h
0x1800f17fe  mov     rbx, rcx
0x1800f1801  test    rcx, rcx
0x1800f1804  jnz     short loc_1800F180E
0x1800f1806  lea     eax, [rcx+4]
0x1800f1809  jmp     loc_1800F1A1D
0x1800f180e  mov     edx, 1; WellKnownSidType
0x1800f1813  call    cs:__imp_IsWellKnownSid
0x1800f1819  test    eax, eax
0x1800f181b  jnz     loc_1800F1A11
0x1800f1821  lea     edx, [rax+16h]; WellKnownSidType
0x1800f1824  mov     rcx, rbx; pSid
0x1800f1827  call    cs:__imp_IsWellKnownSid
0x1800f182d  test    eax, eax
0x1800f182f  jnz     loc_1800F1A11
0x1800f1835  lea     edx, [rax+6Eh]; WellKnownSidType
0x1800f1838  mov     rcx, rbx; pSid
0x1800f183b  call    cs:__imp_IsWellKnownSid
0x1800f1841  test    eax, eax
0x1800f1843  jnz     loc_1800F1A0A
0x1800f1849  lea     edx, [rax+17h]; WellKnownSidType
0x1800f184c  mov     rcx, rbx; pSid
0x1800f184f  call    cs:__imp_IsWellKnownSid
0x1800f1855  test    eax, eax
0x1800f1857  jnz     loc_1800F1A0A
0x1800f185d  mov     [rsp+68h+cchName], eax
0x1800f1861  lea     rax, [rsp+68h+cchName]
0x1800f1866  mov     [rsp+68h+pcbData], rax; pcbData
0x1800f186b  mov     [rsp+68h+pvData], 0; pvData
0x1800f1874  mov     [rsp+68h+pdwType], 0; pdwType
0x1800f187d  mov     r9d, 2; dwFlags
0x1800f1883  lea     r8, aDefaultaccount; "DefaultAccountSID"
0x1800f188a  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800f1891  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800f1898  call    cs:__imp_RegGetValueW
0x1800f189e  test    eax, eax
0x1800f18a0  jnz     loc_1800F19A2
0x1800f18a6  mov     edx, [rsp+68h+cchName]
0x1800f18aa  lea     rcx, [rsp+68h+var_28]
0x1800f18af  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800f18b4  nop
0x1800f18b5  mov     rax, [rsp+68h+var_28]
0x1800f18ba  lea     r9, [rsp+68h+cchName]
0x1800f18bf  mov     [rsp+68h+pcbData], r9; pcbData
0x1800f18c4  mov     [rsp+68h+pvData], rax; pvData
0x1800f18c9  mov     [rsp+68h+pdwType], 0; unsigned int
0x1800f18d2  mov     r9d, 2; dwFlags
0x1800f18d8  lea     r8, aDefaultaccount; "DefaultAccountSID"
0x1800f18df  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800f18e6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800f18ed  call    cs:__imp_RegGetValueW
0x1800f18f3  mov     rcx, [rsp+68h]; this
0x1800f18f8  test    eax, eax
0x1800f18fa  jz      short loc_1800F1911
0x1800f18fc  mov     r9d, eax; char *
0x1800f18ff  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x1800f1906  mov     edx, 4Eh ; 'N'; void *
0x1800f190b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800f1911  mov     [rsp+68h+StringSid], 0
0x1800f191d  lea     rdx, [rsp+68h+StringSid]; StringSid
0x1800f1925  mov     rcx, rbx; Sid
0x1800f1928  call    cs:__imp_ConvertSidToStringSidW
0x1800f192e  mov     rcx, [rsp+68h]; this
0x1800f1933  test    eax, eax
0x1800f1935  jnz     short loc_1800F1946
0x1800f1937  lea     r8, aOnecoreNetWifi_0; "onecore\\net\\wificloudstore\\registry"...
0x1800f193e  lea     edx, [rax+51h]; void *
0x1800f1941  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800f1946  mov     rax, [rsp+68h+var_28]
0x1800f194b  mov     rdx, [rsp+68h+StringSid]
0x1800f1953  sub     rdx, rax
0x1800f1956  movzx   ecx, word ptr [rax]
0x1800f1959  movzx   r8d, word ptr [rax+rdx]
0x1800f195e  sub     ecx, r8d
0x1800f1961  jnz     short loc_1800F196C
0x1800f1963  add     rax, 2
0x1800f1967  test    r8d, r8d
0x1800f196a  jnz     short loc_1800F1956
0x1800f196c  test    ecx, ecx
0x1800f196e  lea     rcx, [rsp+68h+StringSid]
0x1800f1976  jnz     short loc_1800F1992
0x1800f1978  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f197d  nop
0x1800f197e  lea     rcx, [rsp+68h+var_28]
0x1800f1983  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800f1988  mov     eax, 3
0x1800f198d  jmp     loc_1800F1A1D
0x1800f1992  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f1997  nop
0x1800f1998  lea     rcx, [rsp+68h+var_28]
0x1800f199d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800f19a2  mov     [rsp+68h+cchName], 0
0x1800f19aa  mov     [rsp+68h+cchReferencedDomainName], 0
0x1800f19b5  mov     [rsp+68h+peUse], 8
0x1800f19bd  lea     rax, [rsp+68h+peUse]
0x1800f19c2  mov     [rsp+68h+pcbData], rax; peUse
0x1800f19c7  lea     rax, [rsp+68h+cchReferencedDomainName]
0x1800f19cf  mov     [rsp+68h+pvData], rax; cchReferencedDomainName
0x1800f19d4  mov     [rsp+68h+pdwType], 0; ReferencedDomainName
0x1800f19dd  lea     r9, [rsp+68h+cchName]; cchName
0x1800f19e2  xor     r8d, r8d; Name
0x1800f19e5  mov     rdx, rbx; Sid
0x1800f19e8  xor     ecx, ecx; lpSystemName
0x1800f19ea  call    cs:__imp_LookupAccountSidW
0x1800f19f0  test    eax, eax
0x1800f19f2  jnz     short loc_1800F1A08
0x1800f19f4  call    cs:__imp_GetLastError
0x1800f19fa  cmp     eax, 534h
0x1800f19ff  jnz     short loc_1800F1A08
0x1800f1a01  mov     eax, 3
0x1800f1a06  jmp     short loc_1800F1A1D
0x1800f1a08  jmp     short loc_1800F1A18
0x1800f1a0a  mov     eax, 3
0x1800f1a0f  jmp     short loc_1800F1A1D
0x1800f1a11  mov     eax, 2
0x1800f1a16  jmp     short loc_1800F1A1D
0x1800f1a18  mov     eax, 1
0x1800f1a1d  add     rsp, 60h
0x1800f1a21  pop     rbx
0x1800f1a22  retn
```
