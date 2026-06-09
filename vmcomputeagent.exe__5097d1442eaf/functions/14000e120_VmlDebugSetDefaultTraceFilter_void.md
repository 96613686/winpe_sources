# VmlDebugSetDefaultTraceFilter(void)

- ea: `0x14000e120`
- end: `0x14000e3be`
- name: `?VmlDebugSetDefaultTraceFilter@@YAXXZ`
- size: `670`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003ce50`
- `0x14003d6c0`

## callees

- `0x140005360`
- `0x14000835c`
- `0x14000e120`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e34d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e38d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e39c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e34d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e38d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e39c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e212`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e243`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e274`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e2a5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e325`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e37e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e212`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e243`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e274`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e2a5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e325`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000e37e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e199`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e1cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e2d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e199`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e1cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e2d8`

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
    _InterlockedExchange64((volatile __int64 *)&(&g_TraceEnabled)[i], qword_140116710[i]);
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
0x14000e120  push    rbp
0x14000e122  push    rbx
0x14000e123  push    rsi
0x14000e124  push    rdi
0x14000e125  push    r14
0x14000e127  push    r15
0x14000e129  lea     rbp, [rsp-2Fh]
0x14000e12e  sub     rsp, 98h
0x14000e135  mov     rax, cs:__security_cookie
0x14000e13c  xor     rax, rsp
0x14000e13f  mov     [rbp+57h+var_40], rax
0x14000e143  mov     eax, 2
0x14000e148  lea     rsi, __ImageBase
0x14000e14f  xor     edi, edi
0x14000e151  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x14000e158  mov     ecx, edi
0x14000e15a  mov     rax, ds:rva qword_140116710[rsi+rcx*8]
0x14000e162  xchg    rax, rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8]; __int64 volatile near * volatile g_TraceEnabled ...
0x14000e16a  inc     rcx
0x14000e16d  cmp     rcx, 20h ; ' '
0x14000e171  jnz     short loc_14000E15A
0x14000e173  lea     rax, [rbp+57h+hKey]
0x14000e177  mov     [rbp+57h+hKey], rdi
0x14000e17b  mov     ebx, 20019h
0x14000e180  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14000e185  mov     r9d, ebx; samDesired
0x14000e188  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000e18f  xor     r8d, r8d; ulOptions
0x14000e192  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000e199  call    cs:__imp_RegOpenKeyExW
0x14000e19f  test    eax, eax
0x14000e1a1  jnz     loc_14000E393
0x14000e1a7  mov     rcx, [rbp+57h+hKey]; hKey
0x14000e1ab  lea     rax, [rbp+57h+hkey]
0x14000e1af  mov     r9d, ebx; samDesired
0x14000e1b2  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14000e1b7  xor     r8d, r8d; ulOptions
0x14000e1ba  mov     [rbp+57h+var_7C], edi
0x14000e1bd  lea     rdx, ?g_VmlRegistryKeyName@Vml@@3QBGB; "VML"
0x14000e1c4  mov     [rbp+57h+var_80], edi
0x14000e1c7  mov     [rbp+57h+var_60], rdi
0x14000e1cb  mov     [rbp+57h+hkey], rdi
0x14000e1cf  call    cs:__imp_RegOpenKeyExW
0x14000e1d5  mov     r14d, 4
0x14000e1db  lea     r15d, [r14+0Ch]
0x14000e1df  test    eax, eax
0x14000e1e1  jnz     loc_14000E353
0x14000e1e7  mov     rcx, [rbp+57h+hkey]; hkey
0x14000e1eb  lea     rax, [rbp+57h+var_80]
0x14000e1ef  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14000e1f4  lea     r8, Value; "TraceFlags"
0x14000e1fb  lea     rax, [rbp+57h+var_7C]
0x14000e1ff  mov     [rbp+57h+var_80], r14d
0x14000e203  mov     [rsp+0C0h+pvData], rax; pvData
0x14000e208  mov     r9d, r15d; dwFlags
0x14000e20b  xor     edx, edx; lpSubKey
0x14000e20d  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14000e212  call    cs:__imp_RegGetValueW
0x14000e218  mov     rcx, [rbp+57h+hkey]; hkey
0x14000e21c  lea     rax, [rbp+57h+var_80]
0x14000e220  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14000e225  lea     r8, aStoplevel; "StopLevel"
0x14000e22c  lea     rax, [rbp+57h+var_7C]
0x14000e230  mov     [rbp+57h+var_80], r14d
0x14000e234  mov     [rsp+0C0h+pvData], rax; pvData
0x14000e239  mov     r9d, r15d; dwFlags
0x14000e23c  xor     edx, edx; lpSubKey
0x14000e23e  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14000e243  call    cs:__imp_RegGetValueW
0x14000e249  mov     rcx, [rbp+57h+hkey]; hkey
0x14000e24d  lea     rax, [rbp+57h+var_80]
0x14000e251  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14000e256  lea     r8, aDebugbreakenab; "DebugBreakEnabled"
0x14000e25d  lea     rax, [rbp+57h+var_7C]
0x14000e261  mov     [rbp+57h+var_80], r14d
0x14000e265  mov     [rsp+0C0h+pvData], rax; pvData
0x14000e26a  mov     r9d, r15d; dwFlags
0x14000e26d  xor     edx, edx; lpSubKey
0x14000e26f  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14000e274  call    cs:__imp_RegGetValueW
0x14000e27a  mov     rcx, [rbp+57h+hkey]; hkey
0x14000e27e  lea     rax, [rbp+57h+var_80]
0x14000e282  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14000e287  lea     r8, aTracelevel; "TraceLevel"
0x14000e28e  lea     rax, [rbp+57h+var_7C]
0x14000e292  mov     [rbp+57h+var_80], r14d
0x14000e296  mov     [rsp+0C0h+pvData], rax; pvData
0x14000e29b  mov     r9d, r15d; dwFlags
0x14000e29e  xor     edx, edx; lpSubKey
0x14000e2a0  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14000e2a5  call    cs:__imp_RegGetValueW
0x14000e2ab  test    eax, eax
0x14000e2ad  jnz     short loc_14000E2BA
0x14000e2af  movzx   eax, word ptr [rbp+57h+var_7C]
0x14000e2b3  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x14000e2ba  mov     rcx, [rbp+57h+hkey]; hKey
0x14000e2be  lea     rax, [rbp+57h+var_68]
0x14000e2c2  mov     r9d, ebx; samDesired
0x14000e2c5  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14000e2ca  xor     r8d, r8d; ulOptions
0x14000e2cd  mov     [rbp+57h+var_68], rdi
0x14000e2d1  lea     rdx, SubKey; "TraceLevelsEnabled"
0x14000e2d8  call    cs:__imp_RegOpenKeyExW
0x14000e2de  test    eax, eax
0x14000e2e0  jnz     short loc_14000E344
0x14000e2e2  mov     ebx, edi
0x14000e2e4  mov     r8d, ebx
0x14000e2e7  lea     rdx, aTraceI; "Trace%i"
0x14000e2ee  lea     rcx, [rbp+57h+Value]
0x14000e2f2  call    ??$swprintf_s@$09@@YAHAEAY09GPEBGZZ; swprintf_s<10>(ushort (&)[10],ushort const *,...)
0x14000e2f7  mov     rcx, [rbp+57h+var_68]; hkey
0x14000e2fb  lea     rax, [rbp+57h+var_80]
0x14000e2ff  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14000e304  lea     r8, [rbp+57h+Value]; lpValue
0x14000e308  lea     rax, [rbp+57h+var_60]
0x14000e30c  mov     [rbp+57h+var_80], 8
0x14000e313  mov     [rsp+0C0h+pvData], rax; pvData
0x14000e318  mov     r9d, 40h ; '@'; dwFlags
0x14000e31e  xor     edx, edx; lpSubKey
0x14000e320  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14000e325  call    cs:__imp_RegGetValueW
0x14000e32b  test    eax, eax
0x14000e32d  jnz     short loc_14000E33D
0x14000e32f  mov     rax, [rbp+57h+var_60]
0x14000e333  mov     ecx, ebx
0x14000e335  mov     rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8], rax; __int64 volatile near * volatile g_TraceEnabled ...
0x14000e33d  inc     ebx
0x14000e33f  cmp     ebx, 20h ; ' '
0x14000e342  jl      short loc_14000E2E4
0x14000e344  mov     rcx, [rbp+57h+var_68]; hKey
0x14000e348  test    rcx, rcx
0x14000e34b  jz      short loc_14000E353
0x14000e34d  call    cs:__imp_RegCloseKey
0x14000e353  mov     rcx, [rbp+57h+hKey]; hkey
0x14000e357  lea     rax, [rbp+57h+var_80]
0x14000e35b  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14000e360  lea     r8, ?g_DvClientAssertsMaskName@@3QBGB; "ClientAssertMask"
0x14000e367  lea     rax, [rbp+57h+var_7C]
0x14000e36b  mov     [rbp+57h+var_80], r14d
0x14000e36f  mov     [rsp+0C0h+pvData], rax; pvData
0x14000e374  mov     r9d, r15d; dwFlags
0x14000e377  xor     edx, edx; lpSubKey
0x14000e379  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14000e37e  call    cs:__imp_RegGetValueW
0x14000e384  mov     rcx, [rbp+57h+hkey]; hKey
0x14000e388  test    rcx, rcx
0x14000e38b  jz      short loc_14000E393
0x14000e38d  call    cs:__imp_RegCloseKey
0x14000e393  mov     rcx, [rbp+57h+hKey]; hKey
0x14000e397  test    rcx, rcx
0x14000e39a  jz      short loc_14000E3A2
0x14000e39c  call    cs:__imp_RegCloseKey
0x14000e3a2  mov     rcx, [rbp+57h+var_40]
0x14000e3a6  xor     rcx, rsp; StackCookie
0x14000e3a9  call    __security_check_cookie
0x14000e3ae  add     rsp, 98h
0x14000e3b5  pop     r15
0x14000e3b7  pop     r14
0x14000e3b9  pop     rdi
0x14000e3ba  pop     rsi
0x14000e3bb  pop     rbx
0x14000e3bc  pop     rbp
0x14000e3bd  retn
```
