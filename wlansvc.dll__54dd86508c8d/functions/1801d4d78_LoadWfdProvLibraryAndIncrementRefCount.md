# LoadWfdProvLibraryAndIncrementRefCount

- ea: `0x1801d4d78`
- end: `0x1801d5189`
- name: `LoadWfdProvLibraryAndIncrementRefCount`
- size: `1041`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1801d52b0`
- `0x1801d5364`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180106340`
- `0x180107330`
- `0x1801d4d78`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801d5014`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801d5014`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801d506c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801d506c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801d50f8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801d50f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801d512b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801d512b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801d4e32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801d4e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d4f0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d5028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d5077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d4f0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d5028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d5077`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1801d4fd6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1801d4fd6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801d4ec2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801d4f6d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801d4ec2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801d4f6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801d4e63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801d4e63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801d513b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801d513b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1801d4f00`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1801d4f00`

## string_xrefs

- `0x1801d4f54`: `DllEntryPoint`
- `0x1801d4e55`: `System\CurrentControlSet\Services\WlanSvc\Parameters\WfdProvPlugin`

## pseudocode

```c
__int64 LoadWfdProvLibraryAndIncrementRefCount()
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  DWORD LastError; // eax
  HMODULE Library; // rax
  int v6; // edi
  DWORD v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  FARPROC ProcAddress; // rax
  unsigned int v11; // eax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  CHAR MultiByteStr[272]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Data[264]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR v17[264]; // [rsp+370h] [rbp+270h] BYREF
  WCHAR Dst[264]; // [rsp+580h] [rbp+480h] BYREF

  cbData = 260;
  v0 = 0;
  hKey = 0;
  memset_0(Data, 0, 0x208u);
  memset_0(Dst, 0, 0x208u);
  memset_0(v17, 0, 0x208u);
  memset_0(MultiByteStr, 0, 0x104u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_63be870359f23713a74d53f79893314d_Traceguids);
  EnterCriticalSection(&stru_1802A3810);
  if ( g_WFDProvProxyInfo )
    goto LABEL_46;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WlanSvc\\Parameters\\WfdProvPlugin",
         0,
         1u,
         &hKey);
  v0 = v1;
  if ( v1 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 11;
LABEL_9:
      WPP_SF_d(v2[2], v3, WPP_63be870359f23713a74d53f79893314d_Traceguids, v1);
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  v1 = RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)Data, &cbData);
  v0 = v1;
  if ( !v1 )
  {
    if ( ExpandEnvironmentStringsW(Data, Dst, 0x104u) )
    {
      v1 = RegQueryValueExW(hKey, L"DllEntryPoint", 0, 0, (LPBYTE)v17, &cbData);
      v0 = v1;
      if ( v1 )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v3 = 14;
          goto LABEL_9;
        }
        goto LABEL_47;
      }
      cbData = WideCharToMultiByte(0xFDE9u, 0x80u, v17, -1, MultiByteStr, 260, 0, 0);
      if ( !cbData && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_63be870359f23713a74d53f79893314d_Traceguids, 0);
    }
    else
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_63be870359f23713a74d53f79893314d_Traceguids, LastError);
      if ( v0 )
        goto LABEL_47;
    }
    Library = LoadLibraryExW(Dst, 0, 0);
    g_WFDProvProxyInfo = Library;
    if ( Library )
    {
      v6 = 1;
      ProcAddress = GetProcAddress(Library, MultiByteStr);
      if ( ProcAddress )
      {
        v11 = ((__int64 (__fastcall *)(__int128 *))ProcAddress)(&xmmword_1802A3840);
        v0 = v11;
        if ( v11 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_63be870359f23713a74d53f79893314d_Traceguids, v11);
LABEL_45:
          FreeLibrary(g_WFDProvProxyInfo);
          g_WFDProvProxyInfo = 0;
          xmmword_1802A3840 = 0;
          xmmword_1802A3850 = 0;
          goto LABEL_47;
        }
        if ( dword_1802A3808 )
        {
LABEL_46:
          _InterlockedAdd(&dword_1802A3808, 1u);
          goto LABEL_47;
        }
        v0 = ((__int64 (*)(void))xmmword_1802A3840)();
      }
      else
      {
        v7 = GetLastError();
        v0 = v7;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 17;
          goto LABEL_32;
        }
      }
    }
    else
    {
      v6 = 0;
      v7 = GetLastError();
      v0 = v7;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 16;
LABEL_32:
        WPP_SF_d(v8[2], v9, WPP_63be870359f23713a74d53f79893314d_Traceguids, v7);
      }
    }
    if ( v0 )
    {
      if ( !v6 )
        goto LABEL_47;
      goto LABEL_45;
    }
    goto LABEL_46;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v3 = 12;
    goto LABEL_9;
  }
LABEL_47:
  LeaveCriticalSection(&stru_1802A3810);
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_63be870359f23713a74d53f79893314d_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x1801d4d78  push    rbp
0x1801d4d7a  push    rbx
0x1801d4d7b  push    rdi
0x1801d4d7c  push    r12
0x1801d4d7e  push    r14
0x1801d4d80  push    r15
0x1801d4d82  lea     rbp, [rsp-6A8h]
0x1801d4d8a  sub     rsp, 7A8h
0x1801d4d91  mov     rax, cs:__security_cookie
0x1801d4d98  xor     rax, rsp
0x1801d4d9b  mov     [rbp+6D0h+var_40], rax
0x1801d4da2  mov     edi, 208h
0x1801d4da7  mov     [rsp+7D0h+cbData], 104h
0x1801d4daf  xor     ebx, ebx
0x1801d4db1  lea     rcx, [rbp+6D0h+Data]; void *
0x1801d4db5  mov     r8d, edi; Size
0x1801d4db8  mov     [rsp+7D0h+hKey], rbx
0x1801d4dbd  xor     edx, edx; Val
0x1801d4dbf  call    memset_0
0x1801d4dc4  mov     r8d, edi; Size
0x1801d4dc7  lea     rcx, [rbp+6D0h+Dst]; void *
0x1801d4dce  xor     edx, edx; Val
0x1801d4dd0  call    memset_0
0x1801d4dd5  mov     r8d, edi; Size
0x1801d4dd8  lea     rcx, [rbp+6D0h+var_460]; void *
0x1801d4ddf  xor     edx, edx; Val
0x1801d4de1  call    memset_0
0x1801d4de6  xor     edx, edx; Val
0x1801d4de8  lea     rcx, [rsp+7D0h+MultiByteStr]; void *
0x1801d4ded  mov     r8d, 104h; Size
0x1801d4df3  call    memset_0
0x1801d4df8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d4dff  lea     r15, WPP_GLOBAL_Control
0x1801d4e06  lea     r14d, [rbx+1]
0x1801d4e0a  lea     r12, WPP_63be870359f23713a74d53f79893314d_Traceguids
0x1801d4e11  cmp     rcx, r15
0x1801d4e14  jz      short loc_1801D4E2B
0x1801d4e16  test    [rcx+1Ch], r14b
0x1801d4e1a  jz      short loc_1801D4E2B
0x1801d4e1c  mov     rcx, [rcx+10h]
0x1801d4e20  lea     edx, [rbx+0Ah]
0x1801d4e23  mov     r8, r12
0x1801d4e26  call    WPP_SF_
0x1801d4e2b  lea     rcx, stru_1802A3810; lpCriticalSection
0x1801d4e32  call    cs:__imp_EnterCriticalSection
0x1801d4e38  cmp     cs:g_WFDProvProxyInfo, rbx
0x1801d4e3f  jnz     loc_1801D511C
0x1801d4e45  lea     rax, [rsp+7D0h+hKey]
0x1801d4e4a  mov     r9d, r14d; samDesired
0x1801d4e4d  xor     r8d, r8d; ulOptions
0x1801d4e50  mov     [rsp+7D0h+phkResult], rax; phkResult
0x1801d4e55  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Wl"...
0x1801d4e5c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801d4e63  call    cs:__imp_RegOpenKeyExW
0x1801d4e69  mov     ebx, eax
0x1801d4e6b  test    eax, eax
0x1801d4e6d  jz      short loc_1801D4EA2
0x1801d4e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d4e76  cmp     rcx, r15
0x1801d4e79  jz      loc_1801D5124
0x1801d4e7f  test    [rcx+1Ch], r14b
0x1801d4e83  jz      loc_1801D5124
0x1801d4e89  mov     edx, 0Bh
0x1801d4e8e  mov     rcx, [rcx+10h]
0x1801d4e92  mov     r9d, eax
0x1801d4e95  mov     r8, r12
0x1801d4e98  call    WPP_SF_d
0x1801d4e9d  jmp     loc_1801D5124
0x1801d4ea2  mov     rcx, [rsp+7D0h+hKey]; hKey
0x1801d4ea7  lea     rax, [rsp+7D0h+cbData]
0x1801d4eac  mov     [rsp+7D0h+lpcbData], rax; lpcbData
0x1801d4eb1  xor     r9d, r9d; lpType
0x1801d4eb4  lea     rax, [rbp+6D0h+Data]
0x1801d4eb8  xor     r8d, r8d; lpReserved
0x1801d4ebb  xor     edx, edx; lpValueName
0x1801d4ebd  mov     [rsp+7D0h+phkResult], rax; lpData
0x1801d4ec2  call    cs:__imp_RegQueryValueExW
0x1801d4ec8  mov     ebx, eax
0x1801d4eca  test    eax, eax
0x1801d4ecc  jz      short loc_1801D4EEF
0x1801d4ece  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d4ed5  cmp     rcx, r15
0x1801d4ed8  jz      loc_1801D5124
0x1801d4ede  test    [rcx+1Ch], r14b
0x1801d4ee2  jz      loc_1801D5124
0x1801d4ee8  mov     edx, 0Ch
0x1801d4eed  jmp     short loc_1801D4E8E
0x1801d4eef  mov     r8d, 104h; nSize
0x1801d4ef5  lea     rdx, [rbp+6D0h+Dst]; lpDst
0x1801d4efc  lea     rcx, [rbp+6D0h+Data]; lpSrc
0x1801d4f00  call    cs:__imp_ExpandEnvironmentStringsW
0x1801d4f06  test    eax, eax
0x1801d4f08  jnz     short loc_1801D4F45
0x1801d4f0a  call    cs:__imp_GetLastError
0x1801d4f10  mov     ebx, eax
0x1801d4f12  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d4f19  cmp     rcx, r15
0x1801d4f1c  jz      short loc_1801D4F38
0x1801d4f1e  test    [rcx+1Ch], r14b
0x1801d4f22  jz      short loc_1801D4F38
0x1801d4f24  mov     rcx, [rcx+10h]
0x1801d4f28  mov     edx, 0Dh
0x1801d4f2d  mov     r9d, eax
0x1801d4f30  mov     r8, r12
0x1801d4f33  call    WPP_SF_d
0x1801d4f38  test    ebx, ebx
0x1801d4f3a  jz      loc_1801D5008
0x1801d4f40  jmp     loc_1801D5124
0x1801d4f45  mov     rcx, [rsp+7D0h+hKey]; hKey
0x1801d4f4a  lea     rax, [rsp+7D0h+cbData]
0x1801d4f4f  mov     [rsp+7D0h+lpcbData], rax; lpcbData
0x1801d4f54  lea     rdx, aDllentrypoint; "DllEntryPoint"
0x1801d4f5b  lea     rax, [rbp+6D0h+var_460]
0x1801d4f62  xor     r9d, r9d; lpType
0x1801d4f65  xor     r8d, r8d; lpReserved
0x1801d4f68  mov     [rsp+7D0h+phkResult], rax; lpData
0x1801d4f6d  call    cs:__imp_RegQueryValueExW
0x1801d4f73  mov     ebx, eax
0x1801d4f75  test    eax, eax
0x1801d4f77  jz      short loc_1801D4F9D
0x1801d4f79  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d4f80  cmp     rcx, r15
0x1801d4f83  jz      loc_1801D5124
0x1801d4f89  test    [rcx+1Ch], r14b
0x1801d4f8d  jz      loc_1801D5124
0x1801d4f93  mov     edx, 0Eh
0x1801d4f98  jmp     loc_1801D4E8E
0x1801d4f9d  mov     [rsp+7D0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1801d4fa6  lea     rax, [rsp+7D0h+MultiByteStr]
0x1801d4fab  mov     [rsp+7D0h+lpDefaultChar], 0; lpDefaultChar
0x1801d4fb4  lea     r8, [rbp+6D0h+var_460]; lpWideCharStr
0x1801d4fbb  mov     dword ptr [rsp+7D0h+lpcbData], 104h; cbMultiByte
0x1801d4fc3  or      r9d, 0FFFFFFFFh; cchWideChar
0x1801d4fc7  mov     edx, 80h; dwFlags
0x1801d4fcc  mov     [rsp+7D0h+phkResult], rax; lpMultiByteStr
0x1801d4fd1  mov     ecx, 0FDE9h; CodePage
0x1801d4fd6  call    cs:__imp_WideCharToMultiByte
0x1801d4fdc  mov     [rsp+7D0h+cbData], eax
0x1801d4fe0  test    eax, eax
0x1801d4fe2  jnz     short loc_1801D5008
0x1801d4fe4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d4feb  cmp     rcx, r15
0x1801d4fee  jz      short loc_1801D5008
0x1801d4ff0  test    [rcx+1Ch], r14b
0x1801d4ff4  jz      short loc_1801D5008
0x1801d4ff6  mov     rcx, [rcx+10h]
0x1801d4ffa  lea     edx, [rax+0Fh]
0x1801d4ffd  xor     r9d, r9d
0x1801d5000  mov     r8, r12
0x1801d5003  call    WPP_SF_d
0x1801d5008  xor     r8d, r8d; dwFlags
0x1801d500b  lea     rcx, [rbp+6D0h+Dst]; lpLibFileName
0x1801d5012  xor     edx, edx; hFile
0x1801d5014  call    cs:__imp_LoadLibraryExW
0x1801d501a  mov     cs:g_WFDProvProxyInfo, rax
0x1801d5021  test    rax, rax
0x1801d5024  jnz     short loc_1801D5061
0x1801d5026  xor     edi, edi
0x1801d5028  call    cs:__imp_GetLastError
0x1801d502e  mov     ebx, eax
0x1801d5030  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d5037  cmp     rcx, r15
0x1801d503a  jz      loc_1801D50E9
0x1801d5040  test    [rcx+1Ch], r14b
0x1801d5044  jz      loc_1801D50E9
0x1801d504a  lea     edx, [rdi+10h]
0x1801d504d  mov     rcx, [rcx+10h]
0x1801d5051  mov     r9d, eax
0x1801d5054  mov     r8, r12
0x1801d5057  call    WPP_SF_d
0x1801d505c  jmp     loc_1801D50E9
0x1801d5061  lea     rdx, [rsp+7D0h+MultiByteStr]; lpProcName
0x1801d5066  mov     rcx, rax; hModule
0x1801d5069  mov     edi, r14d
0x1801d506c  call    cs:__imp_GetProcAddress
0x1801d5072  test    rax, rax
0x1801d5075  jnz     short loc_1801D5098
0x1801d5077  call    cs:__imp_GetLastError
0x1801d507d  mov     ebx, eax
0x1801d507f  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d5086  cmp     rcx, r15
0x1801d5089  jz      short loc_1801D50E9
0x1801d508b  test    [rcx+1Ch], r14b
0x1801d508f  jz      short loc_1801D50E9
0x1801d5091  mov     edx, 11h
0x1801d5096  jmp     short loc_1801D504D
0x1801d5098  lea     rcx, xmmword_1802A3840
0x1801d509f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d50a4  mov     ebx, eax
0x1801d50a6  test    eax, eax
0x1801d50a8  jz      short loc_1801D50D2
0x1801d50aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d50b1  cmp     rcx, r15
0x1801d50b4  jz      short loc_1801D50F1
0x1801d50b6  test    [rcx+1Ch], r14b
0x1801d50ba  jz      short loc_1801D50F1
0x1801d50bc  mov     rcx, [rcx+10h]
0x1801d50c0  mov     edx, 12h
0x1801d50c5  mov     r9d, eax
0x1801d50c8  mov     r8, r12
0x1801d50cb  call    WPP_SF_d
0x1801d50d0  jmp     short loc_1801D50F1
0x1801d50d2  cmp     cs:dword_1802A3808, 0
0x1801d50d9  jnz     short loc_1801D511C
0x1801d50db  mov     rax, qword ptr cs:xmmword_1802A3840
0x1801d50e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d50e7  mov     ebx, eax
0x1801d50e9  test    ebx, ebx
0x1801d50eb  jz      short loc_1801D511C
0x1801d50ed  test    edi, edi
0x1801d50ef  jz      short loc_1801D5124
0x1801d50f1  mov     rcx, cs:g_WFDProvProxyInfo; hLibModule
0x1801d50f8  call    cs:__imp_FreeLibrary
0x1801d50fe  xorps   xmm0, xmm0
0x1801d5101  mov     cs:g_WFDProvProxyInfo, 0
0x1801d510c  movups  cs:xmmword_1802A3840, xmm0
0x1801d5113  movups  cs:xmmword_1802A3850, xmm0
0x1801d511a  jmp     short loc_1801D5124
0x1801d511c  lock add cs:dword_1802A3808, r14d
0x1801d5124  lea     rcx, stru_1802A3810; lpCriticalSection
0x1801d512b  call    cs:__imp_LeaveCriticalSection
0x1801d5131  mov     rcx, [rsp+7D0h+hKey]; hKey
0x1801d5136  test    rcx, rcx
0x1801d5139  jz      short loc_1801D5141
0x1801d513b  call    cs:__imp_RegCloseKey
0x1801d5141  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d5148  cmp     rcx, r15
0x1801d514b  jz      short loc_1801D5167
0x1801d514d  test    [rcx+1Ch], r14b
0x1801d5151  jz      short loc_1801D5167
0x1801d5153  mov     rcx, [rcx+10h]
0x1801d5157  mov     edx, 13h
0x1801d515c  mov     r9d, ebx
0x1801d515f  mov     r8, r12
0x1801d5162  call    WPP_SF_d
0x1801d5167  mov     eax, ebx
0x1801d5169  mov     rcx, [rbp+6D0h+var_40]
0x1801d5170  xor     rcx, rsp; StackCookie
0x1801d5173  call    __security_check_cookie
0x1801d5178  add     rsp, 7A8h
0x1801d517f  pop     r15
0x1801d5181  pop     r14
0x1801d5183  pop     r12
0x1801d5185  pop     rdi
0x1801d5186  pop     rbx
0x1801d5187  pop     rbp
0x1801d5188  retn
```
