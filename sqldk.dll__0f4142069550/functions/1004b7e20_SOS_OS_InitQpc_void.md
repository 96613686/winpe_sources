# SOS_OS::InitQpc(void)

- ea: `0x1004b7e20`
- end: `0x1004b8070`
- name: `?InitQpc@SOS_OS@@CAXXZ`
- size: `592`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100440fd0`

## callees

- `0x100403070`
- `0x100404bf2`
- `0x1004b7e20`
- `0x1005a6fb0`

## import_xrefs

- `KERNEL32!QueryPerformanceFrequency` at `0x1004b8014`
- `KERNEL32!QueryPerformanceFrequency` at `0x1004b8014`
- `ADVAPI32!RegQueryValueExW` at `0x1004b7ed9`
- `ADVAPI32!RegQueryValueExW` at `0x1004b7f59`
- `ADVAPI32!RegQueryValueExW` at `0x1004b7f85`
- `ADVAPI32!RegQueryValueExW` at `0x1004b7fae`
- `ADVAPI32!RegQueryValueExW` at `0x1004b7ff0`
- `ADVAPI32!RegQueryValueExW` at `0x1004b7ed9`
- `ADVAPI32!RegQueryValueExW` at `0x1004b7f59`
- `ADVAPI32!RegQueryValueExW` at `0x1004b7f85`
- `ADVAPI32!RegQueryValueExW` at `0x1004b7fae`
- `ADVAPI32!RegQueryValueExW` at `0x1004b7ff0`
- `ADVAPI32!RegOpenKeyExW` at `0x1004b7ea6`
- `ADVAPI32!RegOpenKeyExW` at `0x1004b7ea6`
- `ADVAPI32!RegCloseKey` at `0x1004b8049`
- `ADVAPI32!RegCloseKey` at `0x1004b8049`
- `VCRUNTIME140!wcschr` at `0x1004b7ef0`
- `VCRUNTIME140!wcschr` at `0x1004b7ef0`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004b7f02`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004b7f12`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004b7fba`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004b7f02`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004b7f12`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004b7fba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void SOS_OS::InitQpc(void)
{
  LSTATUS v0; // ebx
  wchar_t *v1; // rax
  int IsInvariantTscAvailable; // eax
  int v3; // ecx
  HKEY hKey; // [rsp+38h] [rbp-9h] BYREF
  DWORD lpcbData[2]; // [rsp+40h] [rbp-1h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+7h] BYREF
  DWORD v7; // [rsp+4Ch] [rbp+Bh] BYREF
  DWORD v8; // [rsp+50h] [rbp+Fh] BYREF
  __int64 v9; // [rsp+58h] [rbp+17h]
  wchar_t Data[12]; // [rsp+60h] [rbp+1Fh] BYREF
  wchar_t v11[12]; // [rsp+78h] [rbp+37h] BYREF

  v9 = -2;
  hKey = 0;
  cbData = 20;
  v7 = 20;
  v8 = 256;
  memset_0(&dwOSMajorVersion, 0, 0x118u);
  SOS_OS::sm_OSVersionInfo.dwOSVersionInfoSize = 284;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &hKey);
  if ( !v0 )
  {
    v0 = RegQueryValueExW(hKey, L"CurrentVersion", 0, 0, (LPBYTE)Data, &cbData);
    if ( !v0 )
    {
      v1 = wcschr(Data, 0x2Eu);
      if ( v1 )
      {
        *v1 = 0;
        *(_DWORD *)&dwOSMinorVersion = _wtoi(v1 + 1);
      }
      *(_DWORD *)&dwOSMajorVersion = _wtoi(Data);
      if ( *(_DWORD *)&dwOSMajorVersion == 6 && *(_DWORD *)&dwOSMinorVersion == 3 )
      {
        lpcbData[0] = 4;
        RegQueryValueExW(hKey, L"CurrentMajorVersionNumber", 0, 0, &dwOSMajorVersion, lpcbData);
        RegQueryValueExW(hKey, L"CurrentMinorVersionNumber", 0, 0, &dwOSMinorVersion, lpcbData);
      }
      v0 = RegQueryValueExW(hKey, L"CurrentBuild", 0, 0, (LPBYTE)v11, &v7);
    }
  }
  dword_1007AC14C = _wtoi(v11);
  if ( !v0 )
    RegQueryValueExW(hKey, L"CSDVersion", 0, 0, &byte_1007AC154, &v8);
  dword_1007AC150 = 2;
  if ( !Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart )
  {
    *(_QWORD *)lpcbData = 0;
    QueryPerformanceFrequency((LARGE_INTEGER *)lpcbData);
    Base_PublicGlobals::sm_QueryPerformanceFrequency = *(union _LARGE_INTEGER *)lpcbData;
  }
  IsInvariantTscAvailable = TimePriv::IsInvariantTscAvailable();
  v3 = Base_PublicGlobals::sm_invariantTscAvailable;
  if ( IsInvariantTscAvailable )
    v3 = 1;
  Base_PublicGlobals::sm_invariantTscAvailable = v3;
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1004b7e20  mov     rax, rsp
0x1004b7e23  push    rbp
0x1004b7e24  lea     rbp, [rax-5Fh]
0x1004b7e28  sub     rsp, 90h
0x1004b7e2f  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x1004b7e37  mov     [rax+8], rbx
0x1004b7e3b  mov     [rax+10h], rdi
0x1004b7e3f  mov     rax, cs:__security_cookie
0x1004b7e46  xor     rax, rsp
0x1004b7e49  mov     [rbp+57h+var_8], rax
0x1004b7e4d  xor     edi, edi
0x1004b7e4f  mov     [rbp+57h+hKey], rdi
0x1004b7e53  mov     [rbp+57h+cbData], 14h
0x1004b7e5a  mov     [rbp+57h+var_4C], 14h
0x1004b7e61  mov     [rbp+57h+var_48], 100h
0x1004b7e68  xor     edx, edx; Val
0x1004b7e6a  mov     r8d, 118h; Size
0x1004b7e70  lea     rcx, dwOSMajorVersion; void *
0x1004b7e77  call    memset_0
0x1004b7e7c  mov     cs:?sm_OSVersionInfo@SOS_OS@@0U_OSVERSIONINFOEXW@@A, 11Ch; _OSVERSIONINFOEXW SOS_OS::sm_OSVersionInfo
0x1004b7e86  lea     rax, [rbp+57h+hKey]
0x1004b7e8a  mov     [rsp+90h+phkResult], rax; phkResult
0x1004b7e8f  mov     r9d, 20019h; samDesired
0x1004b7e95  xor     r8d, r8d; ulOptions
0x1004b7e98  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1004b7e9f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1004b7ea6  call    cs:__imp_RegOpenKeyExW
0x1004b7eac  mov     ebx, eax
0x1004b7eae  test    eax, eax
0x1004b7eb0  jnz     loc_1004B7FB6
0x1004b7eb6  lea     rax, [rbp+57h+cbData]
0x1004b7eba  mov     [rsp+90h+lpcbData], rax; lpcbData
0x1004b7ebf  lea     rax, [rbp+57h+Data]
0x1004b7ec3  mov     [rsp+90h+phkResult], rax; lpData
0x1004b7ec8  xor     r9d, r9d; lpType
0x1004b7ecb  xor     r8d, r8d; lpReserved
0x1004b7ece  lea     rdx, ValueName; "CurrentVersion"
0x1004b7ed5  mov     rcx, [rbp+57h+hKey]; hKey
0x1004b7ed9  call    cs:__imp_RegQueryValueExW
0x1004b7edf  mov     ebx, eax
0x1004b7ee1  test    eax, eax
0x1004b7ee3  jnz     loc_1004B7FB6
0x1004b7ee9  lea     edx, [rdi+2Eh]; Ch
0x1004b7eec  lea     rcx, [rbp+57h+Data]; Str
0x1004b7ef0  call    cs:__imp_wcschr
0x1004b7ef6  test    rax, rax
0x1004b7ef9  jz      short loc_1004B7F0E
0x1004b7efb  mov     [rax], di
0x1004b7efe  lea     rcx, [rax+2]; String
0x1004b7f02  call    cs:__imp__wtoi
0x1004b7f08  mov     cs:dwOSMinorVersion, eax
0x1004b7f0e  lea     rcx, [rbp+57h+Data]; String
0x1004b7f12  call    cs:__imp__wtoi
0x1004b7f18  mov     cs:dwOSMajorVersion, eax
0x1004b7f1e  cmp     eax, 6
0x1004b7f21  jnz     short loc_1004B7F8B
0x1004b7f23  cmp     cs:dwOSMinorVersion, 3
0x1004b7f2a  jnz     short loc_1004B7F8B
0x1004b7f2c  mov     [rbp+57h+var_58], 4
0x1004b7f33  lea     rax, [rbp+57h+var_58]
0x1004b7f37  mov     [rsp+90h+lpcbData], rax; lpcbData
0x1004b7f3c  lea     rax, dwOSMajorVersion
0x1004b7f43  mov     [rsp+90h+phkResult], rax; lpData
0x1004b7f48  xor     r9d, r9d; lpType
0x1004b7f4b  xor     r8d, r8d; lpReserved
0x1004b7f4e  lea     rdx, aCurrentmajorve; "CurrentMajorVersionNumber"
0x1004b7f55  mov     rcx, [rbp+57h+hKey]; hKey
0x1004b7f59  call    cs:__imp_RegQueryValueExW
0x1004b7f5f  lea     rax, [rbp+57h+var_58]
0x1004b7f63  mov     [rsp+90h+lpcbData], rax; lpcbData
0x1004b7f68  lea     rax, dwOSMinorVersion
0x1004b7f6f  mov     [rsp+90h+phkResult], rax; lpData
0x1004b7f74  xor     r9d, r9d; lpType
0x1004b7f77  xor     r8d, r8d; lpReserved
0x1004b7f7a  lea     rdx, aCurrentminorve; "CurrentMinorVersionNumber"
0x1004b7f81  mov     rcx, [rbp+57h+hKey]; hKey
0x1004b7f85  call    cs:__imp_RegQueryValueExW
0x1004b7f8b  lea     rax, [rbp+57h+var_4C]
0x1004b7f8f  mov     [rsp+90h+lpcbData], rax; lpcbData
0x1004b7f94  lea     rax, [rbp+57h+var_20]
0x1004b7f98  mov     [rsp+90h+phkResult], rax; lpData
0x1004b7f9d  xor     r9d, r9d; lpType
0x1004b7fa0  xor     r8d, r8d; lpReserved
0x1004b7fa3  lea     rdx, aCurrentbuild; "CurrentBuild"
0x1004b7faa  mov     rcx, [rbp+57h+hKey]; hKey
0x1004b7fae  call    cs:__imp_RegQueryValueExW
0x1004b7fb4  mov     ebx, eax
0x1004b7fb6  lea     rcx, [rbp+57h+var_20]; String
0x1004b7fba  call    cs:__imp__wtoi
0x1004b7fc0  mov     cs:dword_1007AC14C, eax
0x1004b7fc6  test    ebx, ebx
0x1004b7fc8  jnz     short loc_1004B7FF6
0x1004b7fca  lea     rax, [rbp+57h+var_48]
0x1004b7fce  mov     [rsp+90h+lpcbData], rax; lpcbData
0x1004b7fd3  lea     rax, byte_1007AC154
0x1004b7fda  mov     [rsp+90h+phkResult], rax; lpData
0x1004b7fdf  xor     r9d, r9d; lpType
0x1004b7fe2  xor     r8d, r8d; lpReserved
0x1004b7fe5  lea     rdx, aCsdversion; "CSDVersion"
0x1004b7fec  mov     rcx, [rbp+57h+hKey]; hKey
0x1004b7ff0  call    cs:__imp_RegQueryValueExW
0x1004b7ff6  mov     cs:dword_1007AC150, 2
0x1004b8000  cmp     cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A, 0; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x1004b8008  jnz     short loc_1004B8025
0x1004b800a  xor     eax, eax
0x1004b800c  mov     qword ptr [rbp+57h+var_58], rax
0x1004b8010  lea     rcx, [rbp+57h+var_58]; lpFrequency
0x1004b8014  call    cs:__imp_QueryPerformanceFrequency
0x1004b801a  mov     rax, qword ptr [rbp+57h+var_58]
0x1004b801e  mov     cs:?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A, rax; _LARGE_INTEGER Base_PublicGlobals::sm_QueryPerformanceFrequency
0x1004b8025  call    ?IsInvariantTscAvailable@TimePriv@@CAHXZ; TimePriv::IsInvariantTscAvailable(void)
0x1004b802a  mov     ecx, cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004b8030  mov     edx, 1
0x1004b8035  test    eax, eax
0x1004b8037  cmovnz  ecx, edx
0x1004b803a  mov     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, ecx; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004b8040  mov     rcx, [rbp+57h+hKey]; hKey
0x1004b8044  test    rcx, rcx
0x1004b8047  jz      short loc_1004B804F
0x1004b8049  call    cs:__imp_RegCloseKey
0x1004b804f  mov     rcx, [rbp+57h+var_8]
0x1004b8053  xor     rcx, rsp; StackCookie
0x1004b8056  call    __security_check_cookie
0x1004b805b  lea     r11, [rsp+90h+var_s0]
0x1004b8063  mov     rbx, [r11+10h]
0x1004b8067  mov     rdi, [r11+18h]
0x1004b806b  mov     rsp, r11
0x1004b806e  pop     rbp
0x1004b806f  retn
```
