# VmlDebugSetDefaultTraceFilter(void)

- ea: `0x140124f14`
- end: `0x1401251f9`
- name: `?VmlDebugSetDefaultTraceFilter@@YAXXZ`
- size: `741`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400653a8`
- `0x140125bac`
- `0x140126f30`

## callees

- `0x14011ea40`
- `0x140121e78`
- `0x140122148`
- `0x140124f14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140124f8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140124fc9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401250f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140124f8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140124fc9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401250f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140125012`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140125049`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140125080`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401250b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140125143`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14012519c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140125012`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140125049`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140125080`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401250b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140125143`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14012519c`

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
    _InterlockedExchange64((volatile __int64 *)&(&g_TraceEnabled)[i], qword_1402F9F70[i]);
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
0x140124f14  push    rbp
0x140124f16  push    rbx
0x140124f17  push    rsi
0x140124f18  push    rdi
0x140124f19  push    r14
0x140124f1b  push    r15
0x140124f1d  lea     rbp, [rsp-2Fh]
0x140124f22  sub     rsp, 98h
0x140124f29  mov     rax, cs:__security_cookie
0x140124f30  xor     rax, rsp
0x140124f33  mov     [rbp+57h+var_40], rax
0x140124f37  mov     eax, 2
0x140124f3c  lea     rsi, __ImageBase
0x140124f43  xor     edi, edi
0x140124f45  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x140124f4c  mov     ecx, edi
0x140124f4e  mov     rax, ds:rva qword_1402F9F70[rsi+rcx*8]
0x140124f56  xchg    rax, rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8]; __int64 volatile near * volatile g_TraceEnabled ...
0x140124f5e  inc     rcx
0x140124f61  cmp     rcx, 20h ; ' '
0x140124f65  jnz     short loc_140124F4E
0x140124f67  lea     rax, [rbp+57h+hKey]
0x140124f6b  mov     [rbp+57h+hKey], rdi
0x140124f6f  mov     ebx, 20019h
0x140124f74  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140124f79  mov     r9d, ebx; samDesired
0x140124f7c  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140124f83  xor     r8d, r8d; ulOptions
0x140124f86  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140124f8d  call    cs:__imp_RegOpenKeyExW
0x140124f94  nop     dword ptr [rax+rax+00h]
0x140124f99  test    eax, eax
0x140124f9b  jnz     loc_1401251D3
0x140124fa1  mov     rcx, [rbp+57h+hKey]; hKey
0x140124fa5  lea     rax, [rbp+57h+hkey]
0x140124fa9  mov     r9d, ebx; samDesired
0x140124fac  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140124fb1  xor     r8d, r8d; ulOptions
0x140124fb4  mov     [rbp+57h+var_7C], edi
0x140124fb7  lea     rdx, ?g_VmlRegistryKeyName@Vml@@3QBGB; "VML"
0x140124fbe  mov     [rbp+57h+var_80], edi
0x140124fc1  mov     [rbp+57h+var_60], rdi
0x140124fc5  mov     [rbp+57h+hkey], rdi
0x140124fc9  call    cs:__imp_RegOpenKeyExW
0x140124fd0  nop     dword ptr [rax+rax+00h]
0x140124fd5  mov     r14d, 4
0x140124fdb  lea     r15d, [r14+0Ch]
0x140124fdf  test    eax, eax
0x140124fe1  jnz     loc_140125171
0x140124fe7  mov     rcx, [rbp+57h+hkey]; hkey
0x140124feb  lea     rax, [rbp+57h+var_80]
0x140124fef  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140124ff4  lea     r8, aTraceflags; "TraceFlags"
0x140124ffb  lea     rax, [rbp+57h+var_7C]
0x140124fff  mov     [rbp+57h+var_80], r14d
0x140125003  mov     [rsp+0C0h+pvData], rax; pvData
0x140125008  mov     r9d, r15d; dwFlags
0x14012500b  xor     edx, edx; lpSubKey
0x14012500d  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140125012  call    cs:__imp_RegGetValueW
0x140125019  nop     dword ptr [rax+rax+00h]
0x14012501e  mov     rcx, [rbp+57h+hkey]; hkey
0x140125022  lea     rax, [rbp+57h+var_80]
0x140125026  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14012502b  lea     r8, aStoplevel; "StopLevel"
0x140125032  lea     rax, [rbp+57h+var_7C]
0x140125036  mov     [rbp+57h+var_80], r14d
0x14012503a  mov     [rsp+0C0h+pvData], rax; pvData
0x14012503f  mov     r9d, r15d; dwFlags
0x140125042  xor     edx, edx; lpSubKey
0x140125044  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140125049  call    cs:__imp_RegGetValueW
0x140125050  nop     dword ptr [rax+rax+00h]
0x140125055  mov     rcx, [rbp+57h+hkey]; hkey
0x140125059  lea     rax, [rbp+57h+var_80]
0x14012505d  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140125062  lea     r8, aDebugbreakenab; "DebugBreakEnabled"
0x140125069  lea     rax, [rbp+57h+var_7C]
0x14012506d  mov     [rbp+57h+var_80], r14d
0x140125071  mov     [rsp+0C0h+pvData], rax; pvData
0x140125076  mov     r9d, r15d; dwFlags
0x140125079  xor     edx, edx; lpSubKey
0x14012507b  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140125080  call    cs:__imp_RegGetValueW
0x140125087  nop     dword ptr [rax+rax+00h]
0x14012508c  mov     rcx, [rbp+57h+hkey]; hkey
0x140125090  lea     rax, [rbp+57h+var_80]
0x140125094  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140125099  lea     r8, aTracelevel; "TraceLevel"
0x1401250a0  lea     rax, [rbp+57h+var_7C]
0x1401250a4  mov     [rbp+57h+var_80], r14d
0x1401250a8  mov     [rsp+0C0h+pvData], rax; pvData
0x1401250ad  mov     r9d, r15d; dwFlags
0x1401250b0  xor     edx, edx; lpSubKey
0x1401250b2  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x1401250b7  call    cs:__imp_RegGetValueW
0x1401250be  nop     dword ptr [rax+rax+00h]
0x1401250c3  test    eax, eax
0x1401250c5  jnz     short loc_1401250D2
0x1401250c7  movzx   eax, word ptr [rbp+57h+var_7C]
0x1401250cb  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x1401250d2  mov     rcx, [rbp+57h+hkey]; hKey
0x1401250d6  lea     rax, [rbp+57h+var_68]
0x1401250da  mov     r9d, ebx; samDesired
0x1401250dd  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1401250e2  xor     r8d, r8d; ulOptions
0x1401250e5  mov     [rbp+57h+var_68], rdi
0x1401250e9  lea     rdx, aTracelevelsena; "TraceLevelsEnabled"
0x1401250f0  call    cs:__imp_RegOpenKeyExW
0x1401250f7  nop     dword ptr [rax+rax+00h]
0x1401250fc  test    eax, eax
0x1401250fe  jnz     short loc_140125168
0x140125100  mov     ebx, edi
0x140125102  mov     r8d, ebx
0x140125105  lea     rdx, aTraceI; "Trace%i"
0x14012510c  lea     rcx, [rbp+57h+Value]
0x140125110  call    ??$swprintf_s@$09@@YAHAEAY09GPEBGZZ; swprintf_s<10>(ushort (&)[10],ushort const *,...)
0x140125115  mov     rcx, [rbp+57h+var_68]; hkey
0x140125119  lea     rax, [rbp+57h+var_80]
0x14012511d  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140125122  lea     r8, [rbp+57h+Value]; lpValue
0x140125126  lea     rax, [rbp+57h+var_60]
0x14012512a  mov     [rbp+57h+var_80], 8
0x140125131  mov     [rsp+0C0h+pvData], rax; pvData
0x140125136  mov     r9d, 40h ; '@'; dwFlags
0x14012513c  xor     edx, edx; lpSubKey
0x14012513e  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140125143  call    cs:__imp_RegGetValueW
0x14012514a  nop     dword ptr [rax+rax+00h]
0x14012514f  test    eax, eax
0x140125151  jnz     short loc_140125161
0x140125153  mov     rax, [rbp+57h+var_60]
0x140125157  mov     ecx, ebx
0x140125159  mov     rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8], rax; __int64 volatile near * volatile g_TraceEnabled ...
0x140125161  inc     ebx
0x140125163  cmp     ebx, 20h ; ' '
0x140125166  jl      short loc_140125102
0x140125168  lea     rcx, [rbp+57h+var_68]
0x14012516c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140125171  mov     rcx, [rbp+57h+hKey]; hkey
0x140125175  lea     rax, [rbp+57h+var_80]
0x140125179  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14012517e  lea     r8, ?g_DvClientAssertsMaskName@@3QBGB; "ClientAssertMask"
0x140125185  lea     rax, [rbp+57h+var_7C]
0x140125189  mov     [rbp+57h+var_80], r14d
0x14012518d  mov     [rsp+0C0h+pvData], rax; pvData
0x140125192  mov     r9d, r15d; dwFlags
0x140125195  xor     edx, edx; lpSubKey
0x140125197  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14012519c  call    cs:__imp_RegGetValueW
0x1401251a3  nop     dword ptr [rax+rax+00h]
0x1401251a8  test    eax, eax
0x1401251aa  jnz     short loc_1401251CA
0x1401251ac  mov     ecx, [rbp+57h+var_7C]
0x1401251af  mov     eax, ecx
0x1401251b1  and     eax, 1
0x1401251b4  not     cl
0x1401251b6  mov     cs:?g_BreakOnChildAssert@@3HA, eax; int g_BreakOnChildAssert
0x1401251bc  movzx   eax, cl
0x1401251bf  shr     eax, 1
0x1401251c1  and     eax, 1
0x1401251c4  mov     cs:?g_RelaxErrorValidation@@3HA, eax; int g_RelaxErrorValidation
0x1401251ca  lea     rcx, [rbp+57h+hkey]
0x1401251ce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401251d3  lea     rcx, [rbp+57h+hKey]
0x1401251d7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401251dc  mov     rcx, [rbp+57h+var_40]
0x1401251e0  xor     rcx, rsp; StackCookie
0x1401251e3  call    __security_check_cookie
0x1401251e8  add     rsp, 98h
0x1401251ef  pop     r15
0x1401251f1  pop     r14
0x1401251f3  pop     rdi
0x1401251f4  pop     rsi
0x1401251f5  pop     rbx
0x1401251f6  pop     rbp
0x1401251f7  retn
```
