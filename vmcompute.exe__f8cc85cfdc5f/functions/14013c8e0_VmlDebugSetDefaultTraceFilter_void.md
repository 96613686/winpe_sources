# VmlDebugSetDefaultTraceFilter(void)

- ea: `0x14013c8e0`
- end: `0x14013cbd5`
- name: `?VmlDebugSetDefaultTraceFilter@@YAXXZ`
- size: `757`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14013cbe0`
- `0x14013e26c`
- `0x14013e4e0`

## callees

- `0x1400a94dc`
- `0x1400f4da8`
- `0x1401332f0`
- `0x140137544`
- `0x14013c8e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14013c964`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14013c9ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14013cadd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14013c964`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14013c9ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14013cadd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013c9f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013ca2b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013ca62`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013ca99`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013cb30`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013cb89`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013c9f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013ca2b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013ca62`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013ca99`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013cb30`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013cb89`

## pseudocode

```c
void VmlDebugSetDefaultTraceFilter(void)
{
  __int64 i; // rcx
  int j; // ebx
  DWORD pcbData; // [rsp+40h] [rbp-29h] BYREF
  int pvData; // [rsp+44h] [rbp-25h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-11h] BYREF
  volatile __int64 *v7; // [rsp+60h] [rbp-9h] BYREF
  WCHAR Value[12]; // [rsp+68h] [rbp-1h] BYREF

  g_TraceLevel = 2;
  for ( i = 0; i != 32; ++i )
    _InterlockedExchange64((volatile __int64 *)&(&g_TraceEnabled)[i], qword_14030EBA0[i]);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
          0,
          0x20019u,
          &hKey) )
  {
    pvData = 0;
    pcbData = 0;
    v7 = 0;
    hkey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    if ( !RegOpenKeyExW(hKey, L"VML", 0, 0x20019u, &hkey) )
    {
      pcbData = 4;
      RegGetValueW(hkey, 0, L"TraceFlags", 0x10u, 0, &pvData, &pcbData);
      pcbData = 4;
      RegGetValueW(hkey, 0, L"StopLevel", 0x10u, 0, &pvData, &pcbData);
      pcbData = 4;
      RegGetValueW(hkey, 0, L"DebugBreakEnabled", 0x10u, 0, &pvData, &pcbData);
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, L"TraceLevel", 0x10u, 0, &pvData, &pcbData) )
        g_TraceLevel = pvData;
      phkResult = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      if ( !RegOpenKeyExW(hkey, L"TraceLevelsEnabled", 0, 0x20019u, &phkResult) )
      {
        for ( j = 0; j < 32; ++j )
        {
          swprintf_s<10>(Value, L"Trace%i", (unsigned int)j);
          pcbData = 8;
          if ( !RegGetValueW(phkResult, 0, Value, 0x40u, 0, &v7, &pcbData) )
            (&g_TraceEnabled)[j] = v7;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
    pcbData = 4;
    if ( !RegGetValueW(hKey, 0, L"ClientAssertMask", 0x10u, 0, &pvData, &pcbData) )
      g_BreakOnChildAssert = pvData & 1;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x14013c8e0  push    rbp
0x14013c8e2  push    rbx
0x14013c8e3  push    rsi
0x14013c8e4  push    rdi
0x14013c8e5  push    r14
0x14013c8e7  push    r15
0x14013c8e9  lea     rbp, [rsp-2Fh]
0x14013c8ee  sub     rsp, 98h
0x14013c8f5  mov     rax, cs:__security_cookie
0x14013c8fc  xor     rax, rsp
0x14013c8ff  mov     [rbp+57h+var_40], rax
0x14013c903  mov     eax, 2
0x14013c908  lea     rsi, __ImageBase
0x14013c90f  xor     edi, edi
0x14013c911  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x14013c918  mov     ecx, edi
0x14013c91a  mov     rax, ds:rva qword_14030EBA0[rsi+rcx*8]
0x14013c922  xchg    rax, rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8]; __int64 volatile near * volatile g_TraceEnabled ...
0x14013c92a  inc     rcx
0x14013c92d  cmp     rcx, 20h ; ' '
0x14013c931  jnz     short loc_14013C91A
0x14013c933  xor     edx, edx
0x14013c935  mov     [rbp+57h+hKey], rdi
0x14013c939  lea     rcx, [rbp+57h+hKey]
0x14013c93d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x14013c942  lea     rax, [rbp+57h+hKey]
0x14013c946  mov     ebx, 20019h
0x14013c94b  mov     r9d, ebx; samDesired
0x14013c94e  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14013c953  xor     r8d, r8d; ulOptions
0x14013c956  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14013c95d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14013c964  call    cs:__imp_RegOpenKeyExW
0x14013c96b  nop     dword ptr [rax+rax+00h]
0x14013c970  test    eax, eax
0x14013c972  jnz     loc_14013CBAF
0x14013c978  xor     edx, edx
0x14013c97a  mov     [rbp+57h+var_7C], edi
0x14013c97d  lea     rcx, [rbp+57h+hkey]
0x14013c981  mov     [rbp+57h+var_80], edi
0x14013c984  mov     [rbp+57h+var_60], rdi
0x14013c988  mov     [rbp+57h+hkey], rdi
0x14013c98c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x14013c991  mov     rcx, [rbp+57h+hKey]; hKey
0x14013c995  lea     rax, [rbp+57h+hkey]
0x14013c999  mov     r9d, ebx; samDesired
0x14013c99c  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14013c9a1  xor     r8d, r8d; ulOptions
0x14013c9a4  lea     rdx, ?g_VmlRegistryKeyName@Vml@@3QBGB; "VML"
0x14013c9ab  call    cs:__imp_RegOpenKeyExW
0x14013c9b2  nop     dword ptr [rax+rax+00h]
0x14013c9b7  mov     r14d, 4
0x14013c9bd  lea     r15d, [r14+0Ch]
0x14013c9c1  test    eax, eax
0x14013c9c3  jnz     loc_14013CB5E
0x14013c9c9  mov     rcx, [rbp+57h+hkey]; hkey
0x14013c9cd  lea     rax, [rbp+57h+var_80]
0x14013c9d1  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14013c9d6  lea     r8, aTraceflags; "TraceFlags"
0x14013c9dd  lea     rax, [rbp+57h+var_7C]
0x14013c9e1  mov     [rbp+57h+var_80], r14d
0x14013c9e5  mov     [rsp+0C0h+pvData], rax; pvData
0x14013c9ea  mov     r9d, r15d; dwFlags
0x14013c9ed  xor     edx, edx; lpSubKey
0x14013c9ef  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14013c9f4  call    cs:__imp_RegGetValueW
0x14013c9fb  nop     dword ptr [rax+rax+00h]
0x14013ca00  mov     rcx, [rbp+57h+hkey]; hkey
0x14013ca04  lea     rax, [rbp+57h+var_80]
0x14013ca08  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14013ca0d  lea     r8, aStoplevel; "StopLevel"
0x14013ca14  lea     rax, [rbp+57h+var_7C]
0x14013ca18  mov     [rbp+57h+var_80], r14d
0x14013ca1c  mov     [rsp+0C0h+pvData], rax; pvData
0x14013ca21  mov     r9d, r15d; dwFlags
0x14013ca24  xor     edx, edx; lpSubKey
0x14013ca26  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14013ca2b  call    cs:__imp_RegGetValueW
0x14013ca32  nop     dword ptr [rax+rax+00h]
0x14013ca37  mov     rcx, [rbp+57h+hkey]; hkey
0x14013ca3b  lea     rax, [rbp+57h+var_80]
0x14013ca3f  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14013ca44  lea     r8, aDebugbreakenab; "DebugBreakEnabled"
0x14013ca4b  lea     rax, [rbp+57h+var_7C]
0x14013ca4f  mov     [rbp+57h+var_80], r14d
0x14013ca53  mov     [rsp+0C0h+pvData], rax; pvData
0x14013ca58  mov     r9d, r15d; dwFlags
0x14013ca5b  xor     edx, edx; lpSubKey
0x14013ca5d  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14013ca62  call    cs:__imp_RegGetValueW
0x14013ca69  nop     dword ptr [rax+rax+00h]
0x14013ca6e  mov     rcx, [rbp+57h+hkey]; hkey
0x14013ca72  lea     rax, [rbp+57h+var_80]
0x14013ca76  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14013ca7b  lea     r8, aTracelevel; "TraceLevel"
0x14013ca82  lea     rax, [rbp+57h+var_7C]
0x14013ca86  mov     [rbp+57h+var_80], r14d
0x14013ca8a  mov     [rsp+0C0h+pvData], rax; pvData
0x14013ca8f  mov     r9d, r15d; dwFlags
0x14013ca92  xor     edx, edx; lpSubKey
0x14013ca94  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14013ca99  call    cs:__imp_RegGetValueW
0x14013caa0  nop     dword ptr [rax+rax+00h]
0x14013caa5  test    eax, eax
0x14013caa7  jnz     short loc_14013CAB4
0x14013caa9  movzx   eax, word ptr [rbp+57h+var_7C]
0x14013caad  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x14013cab4  xor     edx, edx
0x14013cab6  mov     [rbp+57h+var_68], rdi
0x14013caba  lea     rcx, [rbp+57h+var_68]
0x14013cabe  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x14013cac3  mov     rcx, [rbp+57h+hkey]; hKey
0x14013cac7  lea     rax, [rbp+57h+var_68]
0x14013cacb  mov     r9d, ebx; samDesired
0x14013cace  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14013cad3  xor     r8d, r8d; ulOptions
0x14013cad6  lea     rdx, aTracelevelsena; "TraceLevelsEnabled"
0x14013cadd  call    cs:__imp_RegOpenKeyExW
0x14013cae4  nop     dword ptr [rax+rax+00h]
0x14013cae9  test    eax, eax
0x14013caeb  jnz     short loc_14013CB55
0x14013caed  mov     ebx, edi
0x14013caef  mov     r8d, ebx
0x14013caf2  lea     rdx, aTraceI; "Trace%i"
0x14013caf9  lea     rcx, [rbp+57h+Value]
0x14013cafd  call    ??$swprintf_s@$09@@YAHAEAY09GPEBGZZ; swprintf_s<10>(ushort (&)[10],ushort const *,...)
0x14013cb02  mov     rcx, [rbp+57h+var_68]; hkey
0x14013cb06  lea     rax, [rbp+57h+var_80]
0x14013cb0a  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14013cb0f  lea     r8, [rbp+57h+Value]; lpValue
0x14013cb13  lea     rax, [rbp+57h+var_60]
0x14013cb17  mov     [rbp+57h+var_80], 8
0x14013cb1e  mov     [rsp+0C0h+pvData], rax; pvData
0x14013cb23  mov     r9d, 40h ; '@'; dwFlags
0x14013cb29  xor     edx, edx; lpSubKey
0x14013cb2b  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14013cb30  call    cs:__imp_RegGetValueW
0x14013cb37  nop     dword ptr [rax+rax+00h]
0x14013cb3c  test    eax, eax
0x14013cb3e  jnz     short loc_14013CB4E
0x14013cb40  mov     rax, [rbp+57h+var_60]
0x14013cb44  mov     ecx, ebx
0x14013cb46  mov     rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8], rax; __int64 volatile near * volatile g_TraceEnabled ...
0x14013cb4e  inc     ebx
0x14013cb50  cmp     ebx, 20h ; ' '
0x14013cb53  jl      short loc_14013CAEF
0x14013cb55  lea     rcx, [rbp+57h+var_68]
0x14013cb59  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14013cb5e  mov     rcx, [rbp+57h+hKey]; hkey
0x14013cb62  lea     rax, [rbp+57h+var_80]
0x14013cb66  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14013cb6b  lea     r8, ?g_DvClientAssertsMaskName@@3QBGB; "ClientAssertMask"
0x14013cb72  lea     rax, [rbp+57h+var_7C]
0x14013cb76  mov     [rbp+57h+var_80], r14d
0x14013cb7a  mov     [rsp+0C0h+pvData], rax; pvData
0x14013cb7f  mov     r9d, r15d; dwFlags
0x14013cb82  xor     edx, edx; lpSubKey
0x14013cb84  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14013cb89  call    cs:__imp_RegGetValueW
0x14013cb90  nop     dword ptr [rax+rax+00h]
0x14013cb95  test    eax, eax
0x14013cb97  jnz     short loc_14013CBA6
0x14013cb99  movzx   eax, byte ptr [rbp+57h+var_7C]
0x14013cb9d  and     eax, 1
0x14013cba0  mov     cs:?g_BreakOnChildAssert@@3HA, eax; int g_BreakOnChildAssert
0x14013cba6  lea     rcx, [rbp+57h+hkey]
0x14013cbaa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14013cbaf  lea     rcx, [rbp+57h+hKey]
0x14013cbb3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14013cbb8  mov     rcx, [rbp+57h+var_40]
0x14013cbbc  xor     rcx, rsp; StackCookie
0x14013cbbf  call    __security_check_cookie
0x14013cbc4  add     rsp, 98h
0x14013cbcb  pop     r15
0x14013cbcd  pop     r14
0x14013cbcf  pop     rdi
0x14013cbd0  pop     rsi
0x14013cbd1  pop     rbx
0x14013cbd2  pop     rbp
0x14013cbd3  retn
```
