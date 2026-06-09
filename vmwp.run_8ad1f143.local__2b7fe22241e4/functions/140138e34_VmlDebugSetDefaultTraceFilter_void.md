# VmlDebugSetDefaultTraceFilter(void)

- ea: `0x140138e34`
- end: `0x140139119`
- name: `?VmlDebugSetDefaultTraceFilter@@YAXXZ`
- size: `741`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400c3838`
- `0x140139acc`
- `0x14013ae50`

## callees

- `0x140132960`
- `0x140135d98`
- `0x140136068`
- `0x140138e34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140138ead`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140138ee9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140139010`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140138ead`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140138ee9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140139010`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138f32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138f69`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138fa0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138fd7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140139063`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401390bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138f32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138f69`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138fa0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138fd7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140139063`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401390bc`

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
    _InterlockedExchange64((volatile __int64 *)&(&g_TraceEnabled)[i], qword_1402F11F0[i]);
  hKey = 0;
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
    {
      g_BreakOnChildAssert = pvData & 1;
      g_RelaxErrorValidation = ((unsigned __int8)~(_BYTE)pvData >> 1) & 1;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x140138e34  push    rbp
0x140138e36  push    rbx
0x140138e37  push    rsi
0x140138e38  push    rdi
0x140138e39  push    r14
0x140138e3b  push    r15
0x140138e3d  lea     rbp, [rsp-2Fh]
0x140138e42  sub     rsp, 98h
0x140138e49  mov     rax, cs:__security_cookie
0x140138e50  xor     rax, rsp
0x140138e53  mov     [rbp+57h+var_40], rax
0x140138e57  mov     eax, 2
0x140138e5c  lea     rsi, __ImageBase
0x140138e63  xor     edi, edi
0x140138e65  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x140138e6c  mov     ecx, edi
0x140138e6e  mov     rax, ds:rva qword_1402F11F0[rsi+rcx*8]
0x140138e76  xchg    rax, rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8]; __int64 volatile near * volatile g_TraceEnabled ...
0x140138e7e  inc     rcx
0x140138e81  cmp     rcx, 20h ; ' '
0x140138e85  jnz     short loc_140138E6E
0x140138e87  lea     rax, [rbp+57h+hKey]
0x140138e8b  mov     [rbp+57h+hKey], rdi
0x140138e8f  mov     ebx, 20019h
0x140138e94  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140138e99  mov     r9d, ebx; samDesired
0x140138e9c  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140138ea3  xor     r8d, r8d; ulOptions
0x140138ea6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140138ead  call    cs:__imp_RegOpenKeyExW
0x140138eb4  nop     dword ptr [rax+rax+00h]
0x140138eb9  test    eax, eax
0x140138ebb  jnz     loc_1401390F3
0x140138ec1  mov     rcx, [rbp+57h+hKey]; hKey
0x140138ec5  lea     rax, [rbp+57h+hkey]
0x140138ec9  mov     r9d, ebx; samDesired
0x140138ecc  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140138ed1  xor     r8d, r8d; ulOptions
0x140138ed4  mov     [rbp+57h+var_7C], edi
0x140138ed7  lea     rdx, ?g_VmlRegistryKeyName@Vml@@3QBGB; "VML"
0x140138ede  mov     [rbp+57h+var_80], edi
0x140138ee1  mov     [rbp+57h+var_60], rdi
0x140138ee5  mov     [rbp+57h+hkey], rdi
0x140138ee9  call    cs:__imp_RegOpenKeyExW
0x140138ef0  nop     dword ptr [rax+rax+00h]
0x140138ef5  mov     r14d, 4
0x140138efb  lea     r15d, [r14+0Ch]
0x140138eff  test    eax, eax
0x140138f01  jnz     loc_140139091
0x140138f07  mov     rcx, [rbp+57h+hkey]; hkey
0x140138f0b  lea     rax, [rbp+57h+var_80]
0x140138f0f  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140138f14  lea     r8, aTraceflags; "TraceFlags"
0x140138f1b  lea     rax, [rbp+57h+var_7C]
0x140138f1f  mov     [rbp+57h+var_80], r14d
0x140138f23  mov     [rsp+0C0h+pvData], rax; pvData
0x140138f28  mov     r9d, r15d; dwFlags
0x140138f2b  xor     edx, edx; lpSubKey
0x140138f2d  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140138f32  call    cs:__imp_RegGetValueW
0x140138f39  nop     dword ptr [rax+rax+00h]
0x140138f3e  mov     rcx, [rbp+57h+hkey]; hkey
0x140138f42  lea     rax, [rbp+57h+var_80]
0x140138f46  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140138f4b  lea     r8, aStoplevel; "StopLevel"
0x140138f52  lea     rax, [rbp+57h+var_7C]
0x140138f56  mov     [rbp+57h+var_80], r14d
0x140138f5a  mov     [rsp+0C0h+pvData], rax; pvData
0x140138f5f  mov     r9d, r15d; dwFlags
0x140138f62  xor     edx, edx; lpSubKey
0x140138f64  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140138f69  call    cs:__imp_RegGetValueW
0x140138f70  nop     dword ptr [rax+rax+00h]
0x140138f75  mov     rcx, [rbp+57h+hkey]; hkey
0x140138f79  lea     rax, [rbp+57h+var_80]
0x140138f7d  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140138f82  lea     r8, aDebugbreakenab; "DebugBreakEnabled"
0x140138f89  lea     rax, [rbp+57h+var_7C]
0x140138f8d  mov     [rbp+57h+var_80], r14d
0x140138f91  mov     [rsp+0C0h+pvData], rax; pvData
0x140138f96  mov     r9d, r15d; dwFlags
0x140138f99  xor     edx, edx; lpSubKey
0x140138f9b  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140138fa0  call    cs:__imp_RegGetValueW
0x140138fa7  nop     dword ptr [rax+rax+00h]
0x140138fac  mov     rcx, [rbp+57h+hkey]; hkey
0x140138fb0  lea     rax, [rbp+57h+var_80]
0x140138fb4  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140138fb9  lea     r8, aTracelevel; "TraceLevel"
0x140138fc0  lea     rax, [rbp+57h+var_7C]
0x140138fc4  mov     [rbp+57h+var_80], r14d
0x140138fc8  mov     [rsp+0C0h+pvData], rax; pvData
0x140138fcd  mov     r9d, r15d; dwFlags
0x140138fd0  xor     edx, edx; lpSubKey
0x140138fd2  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140138fd7  call    cs:__imp_RegGetValueW
0x140138fde  nop     dword ptr [rax+rax+00h]
0x140138fe3  test    eax, eax
0x140138fe5  jnz     short loc_140138FF2
0x140138fe7  movzx   eax, word ptr [rbp+57h+var_7C]
0x140138feb  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x140138ff2  mov     rcx, [rbp+57h+hkey]; hKey
0x140138ff6  lea     rax, [rbp+57h+var_68]
0x140138ffa  mov     r9d, ebx; samDesired
0x140138ffd  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140139002  xor     r8d, r8d; ulOptions
0x140139005  mov     [rbp+57h+var_68], rdi
0x140139009  lea     rdx, aTracelevelsena; "TraceLevelsEnabled"
0x140139010  call    cs:__imp_RegOpenKeyExW
0x140139017  nop     dword ptr [rax+rax+00h]
0x14013901c  test    eax, eax
0x14013901e  jnz     short loc_140139088
0x140139020  mov     ebx, edi
0x140139022  mov     r8d, ebx
0x140139025  lea     rdx, aTraceI; "Trace%i"
0x14013902c  lea     rcx, [rbp+57h+Value]
0x140139030  call    ??$swprintf_s@$09@@YAHAEAY09GPEBGZZ; swprintf_s<10>(ushort (&)[10],ushort const *,...)
0x140139035  mov     rcx, [rbp+57h+var_68]; hkey
0x140139039  lea     rax, [rbp+57h+var_80]
0x14013903d  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140139042  lea     r8, [rbp+57h+Value]; lpValue
0x140139046  lea     rax, [rbp+57h+var_60]
0x14013904a  mov     [rbp+57h+var_80], 8
0x140139051  mov     [rsp+0C0h+pvData], rax; pvData
0x140139056  mov     r9d, 40h ; '@'; dwFlags
0x14013905c  xor     edx, edx; lpSubKey
0x14013905e  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140139063  call    cs:__imp_RegGetValueW
0x14013906a  nop     dword ptr [rax+rax+00h]
0x14013906f  test    eax, eax
0x140139071  jnz     short loc_140139081
0x140139073  mov     rax, [rbp+57h+var_60]
0x140139077  mov     ecx, ebx
0x140139079  mov     rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8], rax; __int64 volatile near * volatile g_TraceEnabled ...
0x140139081  inc     ebx
0x140139083  cmp     ebx, 20h ; ' '
0x140139086  jl      short loc_140139022
0x140139088  lea     rcx, [rbp+57h+var_68]
0x14013908c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140139091  mov     rcx, [rbp+57h+hKey]; hkey
0x140139095  lea     rax, [rbp+57h+var_80]
0x140139099  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14013909e  lea     r8, ?g_DvClientAssertsMaskName@@3QBGB; "ClientAssertMask"
0x1401390a5  lea     rax, [rbp+57h+var_7C]
0x1401390a9  mov     [rbp+57h+var_80], r14d
0x1401390ad  mov     [rsp+0C0h+pvData], rax; pvData
0x1401390b2  mov     r9d, r15d; dwFlags
0x1401390b5  xor     edx, edx; lpSubKey
0x1401390b7  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x1401390bc  call    cs:__imp_RegGetValueW
0x1401390c3  nop     dword ptr [rax+rax+00h]
0x1401390c8  test    eax, eax
0x1401390ca  jnz     short loc_1401390EA
0x1401390cc  mov     ecx, [rbp+57h+var_7C]
0x1401390cf  mov     eax, ecx
0x1401390d1  and     eax, 1
0x1401390d4  not     cl
0x1401390d6  mov     cs:?g_BreakOnChildAssert@@3HA, eax; int g_BreakOnChildAssert
0x1401390dc  movzx   eax, cl
0x1401390df  shr     eax, 1
0x1401390e1  and     eax, 1
0x1401390e4  mov     cs:?g_RelaxErrorValidation@@3HA, eax; int g_RelaxErrorValidation
0x1401390ea  lea     rcx, [rbp+57h+hkey]
0x1401390ee  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401390f3  lea     rcx, [rbp+57h+hKey]
0x1401390f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401390fc  mov     rcx, [rbp+57h+var_40]
0x140139100  xor     rcx, rsp; StackCookie
0x140139103  call    __security_check_cookie
0x140139108  add     rsp, 98h
0x14013910f  pop     r15
0x140139111  pop     r14
0x140139113  pop     rdi
0x140139114  pop     rsi
0x140139115  pop     rbx
0x140139116  pop     rbp
0x140139117  retn
```
