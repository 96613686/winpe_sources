# GetVerbosityLevel(void)

- ea: `0x1400112a0`
- end: `0x140011480`
- name: `?GetVerbosityLevel@@YAKXZ`
- size: `480`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400111ec`

## callees

- `0x1400112a0`
- `0x140053720`
- `0x1400544e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011359`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400113e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011359`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400113e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001139b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140011445`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001139b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140011445`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400113b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011454`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400113b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011454`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x14001131e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x14001131e`

## pseudocode

```c
__int64 GetVerbosityLevel(void)
{
  __int64 result; // rax
  unsigned int v1; // ebx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF
  char v8; // [rsp+16Ah] [rbp+6Ah]

  result = s_VerbosityLevel;
  if ( s_VerbosityLevel == -1 )
  {
    s_VerbosityLevel = 64;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    v1 = 16;
    if ( GetVersionExW(&VersionInformation) && v8 == 1 )
      s_VerbosityLevel = 16;
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            0,
            0x20019u,
            &hKey) )
    {
      *(_DWORD *)Data = 0;
      Type = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"UIVerbosityLevel", 0, &Type, Data, &cbData) )
        s_VerbosityLevel = *(_DWORD *)Data;
      RegCloseKey(hKey);
    }
    phkResult = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
            0,
            0x20019u,
            &phkResult) )
    {
      *(_DWORD *)Data = 0;
      cbData = 0;
      Type = 4;
      if ( !RegQueryValueExW(phkResult, L"VerboseStatus", 0, &cbData, Data, &Type) )
      {
        if ( *(_DWORD *)Data )
          v1 = 64;
        s_VerbosityLevel = v1;
      }
      RegCloseKey(phkResult);
    }
    return s_VerbosityLevel;
  }
  return result;
}

```

## disassembly

```asm
0x1400112a0  push    rbp
0x1400112a2  lea     rbp, [rsp-80h]
0x1400112a7  sub     rsp, 180h
0x1400112ae  mov     rax, cs:__security_cookie
0x1400112b5  xor     rax, rsp
0x1400112b8  mov     [rbp+80h+var_10], rax
0x1400112bc  mov     eax, cs:?s_VerbosityLevel@@3KA; ulong s_VerbosityLevel
0x1400112c2  cmp     eax, 0FFFFFFFFh
0x1400112c5  jz      short loc_1400112DC
0x1400112c7  mov     rcx, [rbp+80h+var_10]
0x1400112cb  xor     rcx, rsp; StackCookie
0x1400112ce  call    __security_check_cookie
0x1400112d3  add     rsp, 180h
0x1400112da  pop     rbp
0x1400112db  retn
0x1400112dc  mov     [rsp+180h+arg_0], rbx
0x1400112e4  lea     rcx, [rsp+180h+VersionInformation.dwMajorVersion]; void *
0x1400112e9  mov     [rsp+180h+arg_8], rsi
0x1400112f1  xor     edx, edx; Val
0x1400112f3  mov     esi, 40h ; '@'
0x1400112f8  mov     [rsp+180h+arg_10], rdi
0x140011300  mov     r8d, 118h; Size
0x140011306  mov     cs:?s_VerbosityLevel@@3KA, esi; ulong s_VerbosityLevel
0x14001130c  call    memset_0
0x140011311  lea     rcx, [rsp+180h+VersionInformation]; lpVersionInformation
0x140011316  mov     [rsp+180h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14001131e  call    cs:__imp_GetVersionExW
0x140011324  mov     ebx, 10h
0x140011329  test    eax, eax
0x14001132b  jnz     loc_14001145C
0x140011331  lea     rax, [rsp+180h+hKey]
0x140011336  xor     edi, edi
0x140011338  mov     r9d, 20019h; samDesired
0x14001133e  mov     [rsp+180h+hKey], rdi
0x140011343  xor     r8d, r8d; ulOptions
0x140011346  mov     [rsp+180h+phkResult], rax; phkResult
0x14001134b  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x140011352  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140011359  call    cs:__imp_RegOpenKeyExW
0x14001135f  test    eax, eax
0x140011361  jnz     short loc_1400113BA
0x140011363  mov     rcx, [rsp+180h+hKey]; hKey
0x140011368  lea     rax, [rsp+180h+cbData]
0x14001136d  mov     [rsp+180h+lpcbData], rax; lpcbData
0x140011372  lea     r9, [rsp+180h+Type]; lpType
0x140011377  lea     rax, [rsp+180h+Data]
0x14001137c  mov     dword ptr [rsp+180h+Data], edi
0x140011380  xor     r8d, r8d; lpReserved
0x140011383  mov     [rsp+180h+phkResult], rax; lpData
0x140011388  lea     rdx, aUiverbositylev; "UIVerbosityLevel"
0x14001138f  mov     [rsp+180h+Type], edi
0x140011393  mov     [rsp+180h+cbData], 4
0x14001139b  call    cs:__imp_RegQueryValueExW
0x1400113a1  test    eax, eax
0x1400113a3  jnz     short loc_1400113AF
0x1400113a5  mov     eax, dword ptr [rsp+180h+Data]
0x1400113a9  mov     cs:?s_VerbosityLevel@@3KA, eax; ulong s_VerbosityLevel
0x1400113af  mov     rcx, [rsp+180h+hKey]; hKey
0x1400113b4  call    cs:__imp_RegCloseKey
0x1400113ba  lea     rax, [rsp+180h+var_138]
0x1400113bf  mov     [rsp+180h+var_138], rdi
0x1400113c4  mov     r9d, 20019h; samDesired
0x1400113ca  mov     [rsp+180h+phkResult], rax; phkResult
0x1400113cf  xor     r8d, r8d; ulOptions
0x1400113d2  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400113d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400113e0  call    cs:__imp_RegOpenKeyExW
0x1400113e6  test    eax, eax
0x1400113e8  jz      short loc_14001140D
0x1400113ea  mov     eax, cs:?s_VerbosityLevel@@3KA; ulong s_VerbosityLevel
0x1400113f0  mov     rsi, [rsp+180h+arg_8]
0x1400113f8  mov     rbx, [rsp+180h+arg_0]
0x140011400  mov     rdi, [rsp+180h+arg_10]
0x140011408  jmp     loc_1400112C7
0x14001140d  mov     rcx, [rsp+180h+var_138]; hKey
0x140011412  lea     rax, [rsp+180h+Type]
0x140011417  mov     [rsp+180h+lpcbData], rax; lpcbData
0x14001141c  lea     r9, [rsp+180h+cbData]; lpType
0x140011421  lea     rax, [rsp+180h+Data]
0x140011426  mov     dword ptr [rsp+180h+Data], edi
0x14001142a  xor     r8d, r8d; lpReserved
0x14001142d  mov     [rsp+180h+phkResult], rax; lpData
0x140011432  lea     rdx, aVerbosestatus; "VerboseStatus"
0x140011439  mov     [rsp+180h+cbData], edi
0x14001143d  mov     [rsp+180h+Type], 4
0x140011445  call    cs:__imp_RegQueryValueExW
0x14001144b  test    eax, eax
0x14001144d  jz      short loc_140011471
0x14001144f  mov     rcx, [rsp+180h+var_138]; hKey
0x140011454  call    cs:__imp_RegCloseKey
0x14001145a  jmp     short loc_1400113EA
0x14001145c  cmp     [rbp+80h+var_16], 1
0x140011460  jnz     loc_140011331
0x140011466  mov     cs:?s_VerbosityLevel@@3KA, ebx; ulong s_VerbosityLevel
0x14001146c  jmp     loc_140011331
0x140011471  cmp     dword ptr [rsp+180h+Data], edi
0x140011475  cmovnz  ebx, esi
0x140011478  mov     cs:?s_VerbosityLevel@@3KA, ebx; ulong s_VerbosityLevel
0x14001147e  jmp     short loc_14001144F
```
