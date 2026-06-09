# VmlDebugSetDefaultTraceFilter(void)

- ea: `0x18000d52c`
- end: `0x18000d813`
- name: `?VmlDebugSetDefaultTraceFilter@@YAXXZ`
- size: `743`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a258`
- `0x18000d820`

## callees

- `0x180002f50`
- `0x1800060f4`
- `0x18000d52c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d62a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d661`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d698`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d6cf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d75b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d7c0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d62a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d661`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d698`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d6cf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d75b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d7c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d5a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d5e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d708`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d5a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d5e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d708`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d789`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d7d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d7ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d789`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d7d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d7ea`

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
    _InterlockedExchange64((volatile __int64 *)&(&g_TraceEnabled)[i], qword_18008EBD0[i]);
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
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    pcbData = 4;
    RegGetValueW(hKey, 0, L"ClientAssertMask", 0x10u, 0, &pvData, &pcbData);
    if ( hkey )
      RegCloseKey(hkey);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18000d52c  push    rbp
0x18000d52e  push    rbx
0x18000d52f  push    rsi
0x18000d530  push    rdi
0x18000d531  push    r14
0x18000d533  push    r15
0x18000d535  lea     rbp, [rsp-2Fh]
0x18000d53a  sub     rsp, 98h
0x18000d541  mov     rax, cs:__security_cookie
0x18000d548  xor     rax, rsp
0x18000d54b  mov     [rbp+57h+var_40], rax
0x18000d54f  mov     eax, 2
0x18000d554  lea     rsi, __ImageBase
0x18000d55b  xor     edi, edi
0x18000d55d  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x18000d564  mov     ecx, edi
0x18000d566  mov     rax, ds:rva qword_18008EBD0[rsi+rcx*8]
0x18000d56e  xchg    rax, rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8]; __int64 volatile near * volatile g_TraceEnabled ...
0x18000d576  inc     rcx
0x18000d579  cmp     rcx, 20h ; ' '
0x18000d57d  jnz     short loc_18000D566
0x18000d57f  lea     rax, [rbp+57h+hKey]
0x18000d583  mov     [rbp+57h+hKey], rdi
0x18000d587  mov     ebx, 20019h
0x18000d58c  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000d591  mov     r9d, ebx; samDesired
0x18000d594  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000d59b  xor     r8d, r8d; ulOptions
0x18000d59e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d5a5  call    cs:__imp_RegOpenKeyExW
0x18000d5ac  nop     dword ptr [rax+rax+00h]
0x18000d5b1  test    eax, eax
0x18000d5b3  jnz     loc_18000D7E1
0x18000d5b9  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d5bd  lea     rax, [rbp+57h+hkey]
0x18000d5c1  mov     r9d, ebx; samDesired
0x18000d5c4  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000d5c9  xor     r8d, r8d; ulOptions
0x18000d5cc  mov     [rbp+57h+var_7C], edi
0x18000d5cf  lea     rdx, ?g_VmlRegistryKeyName@Vml@@3QBGB; "VML"
0x18000d5d6  mov     [rbp+57h+var_80], edi
0x18000d5d9  mov     [rbp+57h+var_60], rdi
0x18000d5dd  mov     [rbp+57h+hkey], rdi
0x18000d5e1  call    cs:__imp_RegOpenKeyExW
0x18000d5e8  nop     dword ptr [rax+rax+00h]
0x18000d5ed  mov     r14d, 4
0x18000d5f3  lea     r15d, [r14+0Ch]
0x18000d5f7  test    eax, eax
0x18000d5f9  jnz     loc_18000D795
0x18000d5ff  mov     rcx, [rbp+57h+hkey]; hkey
0x18000d603  lea     rax, [rbp+57h+var_80]
0x18000d607  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18000d60c  lea     r8, Value; "TraceFlags"
0x18000d613  lea     rax, [rbp+57h+var_7C]
0x18000d617  mov     [rbp+57h+var_80], r14d
0x18000d61b  mov     [rsp+0C0h+pvData], rax; pvData
0x18000d620  mov     r9d, r15d; dwFlags
0x18000d623  xor     edx, edx; lpSubKey
0x18000d625  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x18000d62a  call    cs:__imp_RegGetValueW
0x18000d631  nop     dword ptr [rax+rax+00h]
0x18000d636  mov     rcx, [rbp+57h+hkey]; hkey
0x18000d63a  lea     rax, [rbp+57h+var_80]
0x18000d63e  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18000d643  lea     r8, aStoplevel; "StopLevel"
0x18000d64a  lea     rax, [rbp+57h+var_7C]
0x18000d64e  mov     [rbp+57h+var_80], r14d
0x18000d652  mov     [rsp+0C0h+pvData], rax; pvData
0x18000d657  mov     r9d, r15d; dwFlags
0x18000d65a  xor     edx, edx; lpSubKey
0x18000d65c  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x18000d661  call    cs:__imp_RegGetValueW
0x18000d668  nop     dword ptr [rax+rax+00h]
0x18000d66d  mov     rcx, [rbp+57h+hkey]; hkey
0x18000d671  lea     rax, [rbp+57h+var_80]
0x18000d675  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18000d67a  lea     r8, aDebugbreakenab; "DebugBreakEnabled"
0x18000d681  lea     rax, [rbp+57h+var_7C]
0x18000d685  mov     [rbp+57h+var_80], r14d
0x18000d689  mov     [rsp+0C0h+pvData], rax; pvData
0x18000d68e  mov     r9d, r15d; dwFlags
0x18000d691  xor     edx, edx; lpSubKey
0x18000d693  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x18000d698  call    cs:__imp_RegGetValueW
0x18000d69f  nop     dword ptr [rax+rax+00h]
0x18000d6a4  mov     rcx, [rbp+57h+hkey]; hkey
0x18000d6a8  lea     rax, [rbp+57h+var_80]
0x18000d6ac  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18000d6b1  lea     r8, aTracelevel; "TraceLevel"
0x18000d6b8  lea     rax, [rbp+57h+var_7C]
0x18000d6bc  mov     [rbp+57h+var_80], r14d
0x18000d6c0  mov     [rsp+0C0h+pvData], rax; pvData
0x18000d6c5  mov     r9d, r15d; dwFlags
0x18000d6c8  xor     edx, edx; lpSubKey
0x18000d6ca  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x18000d6cf  call    cs:__imp_RegGetValueW
0x18000d6d6  nop     dword ptr [rax+rax+00h]
0x18000d6db  test    eax, eax
0x18000d6dd  jnz     short loc_18000D6EA
0x18000d6df  movzx   eax, word ptr [rbp+57h+var_7C]
0x18000d6e3  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x18000d6ea  mov     rcx, [rbp+57h+hkey]; hKey
0x18000d6ee  lea     rax, [rbp+57h+var_68]
0x18000d6f2  mov     r9d, ebx; samDesired
0x18000d6f5  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18000d6fa  xor     r8d, r8d; ulOptions
0x18000d6fd  mov     [rbp+57h+var_68], rdi
0x18000d701  lea     rdx, SubKey; "TraceLevelsEnabled"
0x18000d708  call    cs:__imp_RegOpenKeyExW
0x18000d70f  nop     dword ptr [rax+rax+00h]
0x18000d714  test    eax, eax
0x18000d716  jnz     short loc_18000D780
0x18000d718  mov     ebx, edi
0x18000d71a  mov     r8d, ebx
0x18000d71d  lea     rdx, aTraceI; "Trace%i"
0x18000d724  lea     rcx, [rbp+57h+Value]
0x18000d728  call    ??$swprintf_s@$09@@YAHAEAY09GPEBGZZ; swprintf_s<10>(ushort (&)[10],ushort const *,...)
0x18000d72d  mov     rcx, [rbp+57h+var_68]; hkey
0x18000d731  lea     rax, [rbp+57h+var_80]
0x18000d735  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18000d73a  lea     r8, [rbp+57h+Value]; lpValue
0x18000d73e  lea     rax, [rbp+57h+var_60]
0x18000d742  mov     [rbp+57h+var_80], 8
0x18000d749  mov     [rsp+0C0h+pvData], rax; pvData
0x18000d74e  mov     r9d, 40h ; '@'; dwFlags
0x18000d754  xor     edx, edx; lpSubKey
0x18000d756  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x18000d75b  call    cs:__imp_RegGetValueW
0x18000d762  nop     dword ptr [rax+rax+00h]
0x18000d767  test    eax, eax
0x18000d769  jnz     short loc_18000D779
0x18000d76b  mov     rax, [rbp+57h+var_60]
0x18000d76f  mov     ecx, ebx
0x18000d771  mov     rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8], rax; __int64 volatile near * volatile g_TraceEnabled ...
0x18000d779  inc     ebx
0x18000d77b  cmp     ebx, 20h ; ' '
0x18000d77e  jl      short loc_18000D71A
0x18000d780  mov     rcx, [rbp+57h+var_68]; hKey
0x18000d784  test    rcx, rcx
0x18000d787  jz      short loc_18000D795
0x18000d789  call    cs:__imp_RegCloseKey
0x18000d790  nop     dword ptr [rax+rax+00h]
0x18000d795  mov     rcx, [rbp+57h+hKey]; hkey
0x18000d799  lea     rax, [rbp+57h+var_80]
0x18000d79d  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18000d7a2  lea     r8, ?g_DvClientAssertsMaskName@@3QBGB; "ClientAssertMask"
0x18000d7a9  lea     rax, [rbp+57h+var_7C]
0x18000d7ad  mov     [rbp+57h+var_80], r14d
0x18000d7b1  mov     [rsp+0C0h+pvData], rax; pvData
0x18000d7b6  mov     r9d, r15d; dwFlags
0x18000d7b9  xor     edx, edx; lpSubKey
0x18000d7bb  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x18000d7c0  call    cs:__imp_RegGetValueW
0x18000d7c7  nop     dword ptr [rax+rax+00h]
0x18000d7cc  mov     rcx, [rbp+57h+hkey]; hKey
0x18000d7d0  test    rcx, rcx
0x18000d7d3  jz      short loc_18000D7E1
0x18000d7d5  call    cs:__imp_RegCloseKey
0x18000d7dc  nop     dword ptr [rax+rax+00h]
0x18000d7e1  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d7e5  test    rcx, rcx
0x18000d7e8  jz      short loc_18000D7F6
0x18000d7ea  call    cs:__imp_RegCloseKey
0x18000d7f1  nop     dword ptr [rax+rax+00h]
0x18000d7f6  mov     rcx, [rbp+57h+var_40]
0x18000d7fa  xor     rcx, rsp; StackCookie
0x18000d7fd  call    __security_check_cookie
0x18000d802  add     rsp, 98h
0x18000d809  pop     r15
0x18000d80b  pop     r14
0x18000d80d  pop     rdi
0x18000d80e  pop     rsi
0x18000d80f  pop     rbx
0x18000d810  pop     rbp
0x18000d811  retn
```
