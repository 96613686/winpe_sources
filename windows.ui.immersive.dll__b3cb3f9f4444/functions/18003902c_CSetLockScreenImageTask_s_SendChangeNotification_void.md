# CSetLockScreenImageTask::s_SendChangeNotification(void)

- ea: `0x18003902c`
- end: `0x1800391ed`
- name: `?s_SendChangeNotification@CSetLockScreenImageTask@@SAXXZ`
- size: `449`
- prototype: `void(void)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180038c40`
- `0x180038e90`
- `0x1800391f4`
- `0x1800b48e8`
- `0x1800bb3ec`
- `0x1800bc140`

## callees

- `0x18000a46c`
- `0x18000af00`
- `0x18000da00`
- `0x18001c020`
- `0x18003902c`
- `0x18003c554`
- `0x18003d244`
- `0x180054130`
- `0x1800c09d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039079`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800390ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039079`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800390ef`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003917a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003917a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180039166`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180039166`
- `ntdll!RtlPublishWnfStateData` at `0x18003919b`
- `ntdll!RtlPublishWnfStateData` at `0x18003919b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180039149`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180039149`

## string_xrefs

- `0x18003911b`: `LoggedOnUserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void CSetLockScreenImageTask::s_SendChangeNotification(void)
{
  LSTATUS v0; // eax
  bool v1; // sf
  LSTATUS v2; // eax
  bool v3; // sf
  DWORD LengthSid; // eax
  PSID Sid; // [rsp+30h] [rbp-50h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR StringSid[3]; // [rsp+48h] [rbp-38h] BYREF
  WCHAR SubKey[8]; // [rsp+60h] [rbp-20h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\SessionData",
         0,
         8u,
         &hKey);
  v1 = v0 < 0;
  if ( v0 > 0 )
    v1 = 1;
  if ( !v1 && (int)StringCchPrintfW(SubKey, 8u, L"%d", NtCurrentPeb()->SessionId) >= 0 )
  {
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v2 = RegOpenKeyExW(hKey, SubKey, 0, 1u, &phkResult);
    v3 = v2 < 0;
    if ( v2 > 0 )
      v3 = 1;
    if ( !v3 )
    {
      memset(StringSid, 0, sizeof(StringSid));
      if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
                  StringSid,
                  phkResult,
                  L"LoggedOnUserSID") >= 0
        && StringSid[0]
        && *StringSid[0] )
      {
        Sid = 0;
        if ( ConvertStringSidToSidW(StringSid[0], &Sid) || (int)ResultFromKnownLastError() >= 0 )
        {
          if ( IsValidSid(Sid) )
          {
            LengthSid = GetLengthSid(Sid);
            RtlPublishWnfStateData(WNF_SHEL_LOCKSCREEN_IMAGE_CHANGED, 0, Sid, LengthSid, 0);
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(StringSid);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18003902c  mov     [rsp-8+arg_0], rbx
0x180039031  push    rbp
0x180039032  mov     rbp, rsp
0x180039035  sub     rsp, 80h
0x18003903c  mov     rax, cs:__security_cookie
0x180039043  xor     rax, rsp
0x180039046  mov     [rbp+var_10], rax
0x18003904a  xor     ebx, ebx
0x18003904c  mov     [rbp+hKey], rbx
0x180039050  xor     edx, edx
0x180039052  lea     rcx, [rbp+hKey]
0x180039056  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003905b  lea     rax, [rbp+hKey]
0x18003905f  mov     [rsp+80h+phkResult], rax; phkResult
0x180039064  lea     r9d, [rbx+8]; samDesired
0x180039068  xor     r8d, r8d; ulOptions
0x18003906b  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039072  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039079  call    cs:__imp_RegOpenKeyExW
0x180039080  nop     dword ptr [rax+rax+00h]
0x180039085  test    eax, eax
0x180039087  jle     short loc_180039093
0x180039089  movzx   eax, ax
0x18003908c  or      eax, 80070000h
0x180039091  test    eax, eax
0x180039093  js      loc_1800391C6
0x180039099  mov     r9, gs:60h
0x1800390a2  mov     r9d, [r9+2C0h]
0x1800390a9  lea     r8, aD; "%d"
0x1800390b0  mov     edx, 8; unsigned __int64
0x1800390b5  lea     rcx, [rbp+SubKey]; unsigned __int16 *
0x1800390b9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800390be  test    eax, eax
0x1800390c0  js      loc_1800391C6
0x1800390c6  mov     [rbp+var_48], rbx
0x1800390ca  xor     edx, edx
0x1800390cc  lea     rcx, [rbp+var_48]
0x1800390d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800390d5  lea     rax, [rbp+var_48]
0x1800390d9  mov     [rsp+80h+phkResult], rax; phkResult
0x1800390de  mov     r9d, 1; samDesired
0x1800390e4  xor     r8d, r8d; ulOptions
0x1800390e7  lea     rdx, [rbp+SubKey]; lpSubKey
0x1800390eb  mov     rcx, [rbp+hKey]; hKey
0x1800390ef  call    cs:__imp_RegOpenKeyExW
0x1800390f6  nop     dword ptr [rax+rax+00h]
0x1800390fb  test    eax, eax
0x1800390fd  jle     short loc_180039109
0x1800390ff  movzx   eax, ax
0x180039102  or      eax, 80070000h
0x180039107  test    eax, eax
0x180039109  js      loc_1800391BC
0x18003910f  mov     [rbp+StringSid], rbx
0x180039113  mov     [rbp+var_30], rbx
0x180039117  mov     [rbp+var_28], rbx
0x18003911b  lea     r8, aLoggedonusersi; "LoggedOnUserSID"
0x180039122  mov     rdx, [rbp+var_48]
0x180039126  lea     rcx, [rbp+StringSid]
0x18003912a  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18003912f  test    eax, eax
0x180039131  js      short loc_1800391B2
0x180039133  mov     rcx, [rbp+StringSid]; StringSid
0x180039137  test    rcx, rcx
0x18003913a  jz      short loc_1800391B2
0x18003913c  cmp     [rcx], bx
0x18003913f  jz      short loc_1800391B2
0x180039141  mov     [rbp+Sid], rbx
0x180039145  lea     rdx, [rbp+Sid]; Sid
0x180039149  call    cs:__imp_ConvertStringSidToSidW
0x180039150  nop     dword ptr [rax+rax+00h]
0x180039155  test    eax, eax
0x180039157  jnz     short loc_180039162
0x180039159  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003915e  test    eax, eax
0x180039160  js      short loc_1800391A8
0x180039162  mov     rcx, [rbp+Sid]; pSid
0x180039166  call    cs:__imp_IsValidSid
0x18003916d  nop     dword ptr [rax+rax+00h]
0x180039172  test    eax, eax
0x180039174  jz      short loc_1800391A8
0x180039176  mov     rcx, [rbp+Sid]; pSid
0x18003917a  call    cs:__imp_GetLengthSid
0x180039181  nop     dword ptr [rax+rax+00h]
0x180039186  mov     [rsp+80h+phkResult], rbx
0x18003918b  mov     r9d, eax
0x18003918e  mov     r8, [rbp+Sid]
0x180039192  xor     edx, edx
0x180039194  mov     rcx, cs:WNF_SHEL_LOCKSCREEN_IMAGE_CHANGED
0x18003919b  call    cs:__imp_RtlPublishWnfStateData
0x1800391a2  nop     dword ptr [rax+rax+00h]
0x1800391a7  nop
0x1800391a8  lea     rcx, [rbp+Sid]
0x1800391ac  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800391b1  nop
0x1800391b2  lea     rcx, [rbp+StringSid]
0x1800391b6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800391bb  nop
0x1800391bc  lea     rcx, [rbp+var_48]
0x1800391c0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800391c5  nop
0x1800391c6  lea     rcx, [rbp+hKey]
0x1800391ca  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800391cf  mov     rcx, [rbp+var_10]
0x1800391d3  xor     rcx, rsp; StackCookie
0x1800391d6  call    __security_check_cookie
0x1800391db  mov     rbx, [rsp+80h+arg_0]
0x1800391e3  add     rsp, 80h
0x1800391ea  pop     rbp
0x1800391eb  retn
```
