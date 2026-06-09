# SetGlobals(void)

- ea: `0x180057a44`
- end: `0x180057ee6`
- name: `?SetGlobals@@YAJXZ`
- size: `1186`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180074e2c`

## callees

- `0x180057a44`
- `0x180057eec`
- `0x1800580cc`
- `0x180058270`
- `0x180058738`
- `0x180084720`
- `0x18008e898`
- `0x18009d338`
- `0x18009dec0`
- `0x18009e74c`
- `0x1800a856c`
- `0x18010e71c`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057ebf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057ebf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057a7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057a7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180057ab1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180057ab1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x180057e86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x180057e86`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180057b33`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180057b33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057e70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057ead`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057e70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057ead`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180057e59`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180057e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057b63`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x180057b59`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x180057b59`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x180057b45`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x180057b45`
- `api-ms-win-core-file-l1-2-2!GetTempPathA` at `0x180057b8c`
- `api-ms-win-core-file-l1-2-2!GetTempPathA` at `0x180057b8c`

## pseudocode

```c
__int64 SetGlobals(void)
{
  signed int LastError; // eax
  char *v1; // rdx
  int OcxCacheDirForMachineScope; // ebx
  bool v3; // cc
  char *v4; // rcx
  COleAutDll *v5; // rcx
  DWORD FileAttributesA; // eax
  int v7; // eax
  __int64 v8; // rdi
  const char *v9; // rbx
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 v18; // r8
  unsigned __int64 v19; // rcx
  CLIPFORMAT v20; // ax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY v25; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v26; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-94h] BYREF
  char pszDest[272]; // [rsp+70h] [rbp-90h] BYREF
  char v31[272]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  hKey = 0;
  EnterCriticalSection(&g_mxsCodeDownloadGlobals);
  if ( dword_18015E4D8 )
  {
    OcxCacheDirForMachineScope = 0;
    goto LABEL_46;
  }
  LastError = RegOpenKeyExA(
                HKEY_LOCAL_MACHINE,
                "Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
                0,
                0x20019u,
                &hKey);
  OcxCacheDirForMachineScope = LastError;
  v3 = LastError <= 0;
  if ( LastError )
    goto LABEL_3;
  byte_18015B563 = 0;
  byte_18015B453 = 0;
  OcxCacheDirForMachineScope = GetOcxCacheDirForMachineScope(hKey, v1);
  if ( OcxCacheDirForMachineScope >= 0 )
    OcxCacheDirForMachineScope = GetOcxCacheDirForUserScope(v4);
  if ( !OcxCacheDirForMachineScope )
  {
    Type = 4;
    cbData = 4;
    RegQueryValueExA(hKey, "CodeDownloadFlags", 0, &Type, &g_dwCodeDownloadSetupFlags, &cbData);
    COleAutDll::Init(v5);
    FileAttributesA = GetFileAttributesA(&g_szOCXCacheDirMachineScope);
    if ( FileAttributesA == -1 )
    {
      if ( !CreateDirectoryA(&g_szOCXCacheDirMachineScope, 0) )
      {
LABEL_10:
        LastError = GetLastError();
        OcxCacheDirForMachineScope = LastError;
        v3 = LastError <= 0;
LABEL_3:
        if ( !v3 )
          OcxCacheDirForMachineScope = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_46;
      }
    }
    else if ( (FileAttributesA & 0x11) != 0x10 )
    {
      OcxCacheDirForMachineScope = -2147221498;
      goto LABEL_46;
    }
    if ( !GetTempPathA(0x104u, g_szOCXTempDir) )
      goto LABEL_10;
    DetermineOSAndCPUVersion();
    InitBrowserLangStrings();
    v7 = 0;
    v25 = 0;
    if ( g_CPUType != 0xFFFF )
      v7 = g_CPUType;
    v8 = -1;
    v26 = 0;
    v9 = (const char *)(&g_szProcessorTypes)[v7];
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    if ( (unsigned __int64)(v10 + 12) <= 0x11 )
    {
      v11 = StringCchCopyExA(g_szPlatform, 0x11u, "file-win32-", (char **)&v25, &v26, 0x100u);
      if ( v11 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x29B,
          (unsigned int)"onecoreuap\\inetcore\\urlmon\\download\\cdlapi.cxx",
          (const char *)(unsigned int)v11,
          phkResult);
      v12 = StringCchCatA((char *)v25, v26, v9);
      if ( v12 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x29C,
          (unsigned int)"onecoreuap\\inetcore\\urlmon\\download\\cdlapi.cxx",
          (const char *)(unsigned int)v12,
          phkResult);
    }
    v13 = -1;
    do
      ++v13;
    while ( v9[v13] );
    if ( (unsigned __int64)(v13 + 29) <= 0x104 )
    {
      v14 = StringCchCopyExA(pszDest, 0x104u, "application/x-cabinet-win32-", (char **)&v25, &v26, 0x100u);
      if ( v14 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x2A9,
          (unsigned int)"onecoreuap\\inetcore\\urlmon\\download\\cdlapi.cxx",
          (const char *)(unsigned int)v14,
          phkResulta);
      v15 = StringCchCatA((char *)v25, v26, v9);
      if ( v15 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x2AA,
          (unsigned int)"onecoreuap\\inetcore\\urlmon\\download\\cdlapi.cxx",
          (const char *)(unsigned int)v15,
          phkResulta);
    }
    do
      ++v8;
    while ( v9[v8] );
    if ( (unsigned __int64)(v8 + 24) <= 0x104 )
    {
      v16 = StringCchCopyExA(v31, 0x104u, "application/x-pe-win32-", (char **)&v25, &v26, 0x100u);
      if ( v16 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x2B1,
          (unsigned int)"onecoreuap\\inetcore\\urlmon\\download\\cdlapi.cxx",
          (const char *)(unsigned int)v16,
          phkResultb);
      v17 = StringCchCatA((char *)v25, v26, v9);
      if ( v17 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x2B2,
          (unsigned int)"onecoreuap\\inetcore\\urlmon\\download\\cdlapi.cxx",
          (const char *)(unsigned int)v17,
          phkResultb);
    }
    g_rgszMediaStr = pszDest;
    qword_1801599C8 = (__int64)v31;
    OcxCacheDirForMachineScope = RegisterMediaTypes(5u, &g_rgszMediaStr, &g_rgclFormat);
    if ( OcxCacheDirForMachineScope >= 0 )
    {
      v18 = 0;
      v19 = 0;
      do
      {
        v20 = *(&g_rgclFormat + v18++);
        *(CLIPFORMAT *)((char *)&g_rgfmtetc.cfFormat + v19) = v20;
        *(DWORD *)((char *)&g_rgfmtetc.tymed + v19) = 0;
        *(DWORD *)((char *)&g_rgfmtetc.dwAspect + v19) = 1;
        (&g_rgfmtetc.ptd)[v19 / 8] = 0;
        v19 += 32LL;
      }
      while ( v18 != 5 );
      OcxCacheDirForMachineScope = CreateFormatEnumerator(5u, &g_rgfmtetc, &g_pEFmtETC);
      if ( OcxCacheDirForMachineScope >= 0 )
      {
        if ( (unsigned int)IsMICHighProcess() )
        {
          v25 = 0;
          if ( RegCreateKeyExA(
                 HKEY_LOCAL_MACHINE,
                 "Software\\Microsoft\\Code Store Database\\NT5LockDownTest",
                 0,
                 0,
                 0,
                 0x2000000u,
                 0,
                 &v25,
                 0) )
          {
            g_bLockedDown = 1;
          }
          else
          {
            RegCloseKey(v25);
            RegDeleteKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Code Store Database\\NT5LockDownTest", 0, 0);
            g_bLockedDown = 0;
          }
        }
        dword_18015E4D8 = 1;
      }
    }
  }
LABEL_46:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  LeaveCriticalSection(&g_mxsCodeDownloadGlobals);
  return (unsigned int)OcxCacheDirForMachineScope;
}

```

## disassembly

```asm
0x180057a44  push    rbp
0x180057a46  push    rbx
0x180057a47  push    rsi
0x180057a48  push    rdi
0x180057a49  push    r12
0x180057a4b  push    r14
0x180057a4d  lea     rbp, [rsp-1A8h]
0x180057a55  sub     rsp, 2A8h
0x180057a5c  mov     rax, cs:__security_cookie
0x180057a63  xor     rax, rsp
0x180057a66  mov     [rbp+1D0h+var_40], rax
0x180057a6d  xor     esi, esi
0x180057a6f  lea     rcx, ?g_mxsCodeDownloadGlobals@@3VCMutexSem@@A; lpCriticalSection
0x180057a76  mov     [rsp+2D0h+hKey], rsi
0x180057a7b  call    cs:__imp_EnterCriticalSection
0x180057a81  cmp     cs:dword_18015E4D8, esi
0x180057a87  jnz     loc_180057EA1
0x180057a8d  lea     rax, [rsp+2D0h+hKey]
0x180057a92  mov     r12, 0FFFFFFFF80000002h
0x180057a99  mov     rcx, r12; hKey
0x180057a9c  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180057aa1  mov     r9d, 20019h; samDesired
0x180057aa7  lea     rdx, aSoftwareMicros_61; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180057aae  xor     r8d, r8d; ulOptions
0x180057ab1  call    cs:__imp_RegOpenKeyExA
0x180057ab7  mov     ebx, eax
0x180057ab9  test    eax, eax
0x180057abb  jz      short loc_180057AD1
0x180057abd  jle     loc_180057EA3
0x180057ac3  movzx   ebx, ax
0x180057ac6  or      ebx, 80070000h
0x180057acc  jmp     loc_180057EA3
0x180057ad1  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180057ad6  mov     cs:byte_18015B563, sil
0x180057add  mov     cs:byte_18015B453, sil
0x180057ae4  call    ?GetOcxCacheDirForMachineScope@@YAJPEAUHKEY__@@PEAD@Z; GetOcxCacheDirForMachineScope(HKEY__ *,char *)
0x180057ae9  mov     ebx, eax
0x180057aeb  test    eax, eax
0x180057aed  js      short loc_180057AF6
0x180057aef  call    ?GetOcxCacheDirForUserScope@@YAJPEAD@Z; GetOcxCacheDirForUserScope(char *)
0x180057af4  mov     ebx, eax
0x180057af6  test    ebx, ebx
0x180057af8  jnz     loc_180057EA3
0x180057afe  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180057b03  lea     eax, [rbx+4]
0x180057b06  mov     [rsp+2D0h+Type], eax
0x180057b0a  lea     r9, [rsp+2D0h+Type]; lpType
0x180057b0f  mov     [rsp+2D0h+cbData], eax
0x180057b13  lea     rdx, aCodedownloadfl; "CodeDownloadFlags"
0x180057b1a  lea     rax, [rsp+2D0h+cbData]
0x180057b1f  xor     r8d, r8d; lpReserved
0x180057b22  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180057b27  lea     rax, ?g_dwCodeDownloadSetupFlags@@3KA; ulong g_dwCodeDownloadSetupFlags
0x180057b2e  mov     [rsp+2D0h+phkResult], rax; lpData
0x180057b33  call    cs:__imp_RegQueryValueExA
0x180057b39  call    ?Init@COleAutDll@@QEAAJXZ; COleAutDll::Init(void)
0x180057b3e  lea     rcx, ?g_szOCXCacheDirMachineScope@@3PADA; lpFileName
0x180057b45  call    cs:__imp_GetFileAttributesA
0x180057b4b  cmp     eax, 0FFFFFFFFh
0x180057b4e  jnz     short loc_180057B72
0x180057b50  xor     edx, edx; lpSecurityAttributes
0x180057b52  lea     rcx, ?g_szOCXCacheDirMachineScope@@3PADA; lpPathName
0x180057b59  call    cs:__imp_CreateDirectoryA
0x180057b5f  test    eax, eax
0x180057b61  jnz     short loc_180057B7C
0x180057b63  call    cs:__imp_GetLastError
0x180057b69  mov     ebx, eax
0x180057b6b  test    eax, eax
0x180057b6d  jmp     loc_180057ABD
0x180057b72  and     al, 11h
0x180057b74  cmp     al, 10h
0x180057b76  jnz     loc_180057E9A
0x180057b7c  mov     r14d, 104h
0x180057b82  lea     rdx, ?g_szOCXTempDir@@3PADA; lpBuffer
0x180057b89  mov     ecx, r14d; nBufferLength
0x180057b8c  call    cs:__imp_GetTempPathA
0x180057b92  test    eax, eax
0x180057b94  jz      short loc_180057B63
0x180057b96  call    ?DetermineOSAndCPUVersion@@YAXXZ; DetermineOSAndCPUVersion(void)
0x180057b9b  call    ?InitBrowserLangStrings@@YAJXZ; InitBrowserLangStrings(void)
0x180057ba0  cmp     cs:?g_CPUType@@3HA, 0FFFFh; int g_CPUType
0x180057baa  lea     rbx, ?g_szProcessorTypes@@3QBQEBDB; char const * const near * const g_szProcessorTypes
0x180057bb1  mov     eax, esi
0x180057bb3  mov     [rsp+2D0h+var_280], rsi
0x180057bb8  cmovnz  eax, cs:?g_CPUType@@3HA; int g_CPUType
0x180057bbf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180057bc3  cdqe
0x180057bc5  mov     [rsp+2D0h+var_278], rsi
0x180057bca  mov     rbx, [rbx+rax*8]
0x180057bce  mov     rax, rdi
0x180057bd1  inc     rax
0x180057bd4  cmp     [rbx+rax], sil
0x180057bd8  jnz     short loc_180057BD1
0x180057bda  add     rax, 0Ch
0x180057bde  cmp     rax, 11h
0x180057be2  ja      loc_180057C69
0x180057be8  lea     rax, [rsp+2D0h+var_278]
0x180057bed  mov     dword ptr [rsp+2D0h+lpcbData], 100h; unsigned int
0x180057bf5  lea     r9, [rsp+2D0h+var_280]; char **
0x180057bfa  mov     [rsp+2D0h+phkResult], rax; int
0x180057bff  lea     r8, aFileWin32; "file-win32-"
0x180057c06  mov     edx, 11h; unsigned __int64
0x180057c0b  lea     rcx, ?g_szPlatform@@3PADA; pszDest
0x180057c12  call    ?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x180057c17  test    eax, eax
0x180057c19  jns     short loc_180057C37
0x180057c1b  mov     rcx, [rbp+1D8h]; this
0x180057c22  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\urlmon\\download"...
0x180057c29  mov     r9d, eax; char *
0x180057c2c  mov     edx, 29Bh; void *
0x180057c31  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180057c37  mov     rdx, [rsp+2D0h+var_278]; unsigned __int64
0x180057c3c  mov     r8, rbx; char *
0x180057c3f  mov     rcx, [rsp+2D0h+var_280]; char *
0x180057c44  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180057c49  test    eax, eax
0x180057c4b  jns     short loc_180057C69
0x180057c4d  mov     rcx, [rbp+1D8h]; this
0x180057c54  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\urlmon\\download"...
0x180057c5b  mov     r9d, eax; char *
0x180057c5e  mov     edx, 29Ch; void *
0x180057c63  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180057c69  mov     rax, rdi
0x180057c6c  inc     rax
0x180057c6f  cmp     [rbx+rax], sil
0x180057c73  jnz     short loc_180057C6C
0x180057c75  add     rax, 1Dh
0x180057c79  cmp     rax, r14
0x180057c7c  ja      short loc_180057CFB
0x180057c7e  lea     rax, [rsp+2D0h+var_278]
0x180057c83  mov     dword ptr [rsp+2D0h+lpcbData], 100h; unsigned int
0x180057c8b  lea     r9, [rsp+2D0h+var_280]; char **
0x180057c90  mov     [rsp+2D0h+phkResult], rax; int
0x180057c95  lea     r8, aApplicationXCa; "application/x-cabinet-win32-"
0x180057c9c  mov     rdx, r14; unsigned __int64
0x180057c9f  lea     rcx, [rsp+2D0h+pszDest]; pszDest
0x180057ca4  call    ?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x180057ca9  test    eax, eax
0x180057cab  jns     short loc_180057CC9
0x180057cad  mov     rcx, [rbp+1D8h]; this
0x180057cb4  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\urlmon\\download"...
0x180057cbb  mov     r9d, eax; char *
0x180057cbe  mov     edx, 2A9h; void *
0x180057cc3  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180057cc9  mov     rdx, [rsp+2D0h+var_278]; unsigned __int64
0x180057cce  mov     r8, rbx; char *
0x180057cd1  mov     rcx, [rsp+2D0h+var_280]; char *
0x180057cd6  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180057cdb  test    eax, eax
0x180057cdd  jns     short loc_180057CFB
0x180057cdf  mov     rcx, [rbp+1D8h]; this
0x180057ce6  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\urlmon\\download"...
0x180057ced  mov     r9d, eax; char *
0x180057cf0  mov     edx, 2AAh; void *
0x180057cf5  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180057cfb  inc     rdi
0x180057cfe  cmp     [rbx+rdi], sil
0x180057d02  jnz     short loc_180057CFB
0x180057d04  lea     rax, [rdi+18h]
0x180057d08  cmp     rax, r14
0x180057d0b  ja      short loc_180057D8C
0x180057d0d  lea     rax, [rsp+2D0h+var_278]
0x180057d12  mov     dword ptr [rsp+2D0h+lpcbData], 100h; unsigned int
0x180057d1a  lea     r9, [rsp+2D0h+var_280]; char **
0x180057d1f  mov     [rsp+2D0h+phkResult], rax; int
0x180057d24  lea     r8, aApplicationXPe; "application/x-pe-win32-"
0x180057d2b  mov     rdx, r14; unsigned __int64
0x180057d2e  lea     rcx, [rbp+1D0h+var_150]; pszDest
0x180057d35  call    ?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x180057d3a  test    eax, eax
0x180057d3c  jns     short loc_180057D5A
0x180057d3e  mov     rcx, [rbp+1D8h]; this
0x180057d45  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\urlmon\\download"...
0x180057d4c  mov     r9d, eax; char *
0x180057d4f  mov     edx, 2B1h; void *
0x180057d54  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180057d5a  mov     rdx, [rsp+2D0h+var_278]; unsigned __int64
0x180057d5f  mov     r8, rbx; char *
0x180057d62  mov     rcx, [rsp+2D0h+var_280]; char *
0x180057d67  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180057d6c  test    eax, eax
0x180057d6e  jns     short loc_180057D8C
0x180057d70  mov     rcx, [rbp+1D8h]; this
0x180057d77  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\urlmon\\download"...
0x180057d7e  mov     r9d, eax; char *
0x180057d81  mov     edx, 2B2h; void *
0x180057d86  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180057d8c  lea     rax, [rsp+2D0h+pszDest]
0x180057d91  mov     ecx, 5; ctypes
0x180057d96  mov     cs:?g_rgszMediaStr@@3PAPEBDA, rax; char const * near * g_rgszMediaStr
0x180057d9d  lea     r14, ?g_rgclFormat@@3PAGA; ushort near * g_rgclFormat
0x180057da4  lea     rax, [rbp+1D0h+var_150]
0x180057dab  mov     r8, r14; rgcfTypes
0x180057dae  lea     rdx, ?g_rgszMediaStr@@3PAPEBDA; rgszTypes
0x180057db5  mov     cs:qword_1801599C8, rax
0x180057dbc  call    RegisterMediaTypes
0x180057dc1  mov     ebx, eax
0x180057dc3  test    eax, eax
0x180057dc5  js      loc_180057EA3
0x180057dcb  mov     r8, rsi
0x180057dce  lea     rdx, ?g_rgfmtetc@@3PAUtagFORMATETC@@A; rgfmtetc
0x180057dd5  mov     rcx, rsi
0x180057dd8  mov     edi, 1
0x180057ddd  movzx   eax, word ptr [r14+r8*2]
0x180057de2  add     r8, rdi
0x180057de5  mov     [rcx+rdx], ax
0x180057de9  mov     [rcx+rdx+18h], esi
0x180057ded  mov     [rcx+rdx+10h], edi
0x180057df1  mov     [rcx+rdx+8], rsi
0x180057df6  lea     rcx, [rcx+20h]
0x180057dfa  cmp     r8, 5
0x180057dfe  jnz     short loc_180057DDD
0x180057e00  lea     r8, ?g_pEFmtETC@@3PEAUIEnumFORMATETC@@EA; ppenumfmtetc
0x180057e07  mov     ecx, 5; cfmtetc
0x180057e0c  call    CreateFormatEnumerator
0x180057e11  mov     ebx, eax
0x180057e13  test    eax, eax
0x180057e15  js      loc_180057EA3
0x180057e1b  call    ?IsMICHighProcess@@YAHXZ; IsMICHighProcess(void)
0x180057e20  test    eax, eax
0x180057e22  jz      short loc_180057E92
0x180057e24  mov     [rsp+2D0h+lpdwDisposition], rsi; lpdwDisposition
0x180057e29  lea     rax, [rsp+2D0h+var_280]
0x180057e2e  mov     [rsp+2D0h+var_298], rax; phkResult
0x180057e33  lea     rdx, aSoftwareMicros_75; "Software\\Microsoft\\Code Store Databas"...
0x180057e3a  mov     [rsp+2D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180057e3f  xor     r9d, r9d; lpClass
0x180057e42  mov     dword ptr [rsp+2D0h+lpcbData], 2000000h; samDesired
0x180057e4a  xor     r8d, r8d; Reserved
0x180057e4d  mov     rcx, r12; hKey
0x180057e50  mov     dword ptr [rsp+2D0h+phkResult], esi; dwOptions
0x180057e54  mov     [rsp+2D0h+var_280], rsi
0x180057e59  call    cs:__imp_RegCreateKeyExA
0x180057e5f  test    eax, eax
0x180057e61  jz      short loc_180057E6B
0x180057e63  mov     cs:?g_bLockedDown@@3HA, edi; int g_bLockedDown
0x180057e69  jmp     short loc_180057E92
0x180057e6b  mov     rcx, [rsp+2D0h+var_280]; hKey
0x180057e70  call    cs:__imp_RegCloseKey
0x180057e76  xor     r9d, r9d; Reserved
0x180057e79  lea     rdx, aSoftwareMicros_75; "Software\\Microsoft\\Code Store Databas"...
0x180057e80  xor     r8d, r8d; samDesired
0x180057e83  mov     rcx, r12; hKey
0x180057e86  call    cs:__imp_RegDeleteKeyExA
0x180057e8c  mov     cs:?g_bLockedDown@@3HA, esi; int g_bLockedDown
0x180057e92  mov     cs:dword_18015E4D8, edi
0x180057e98  jmp     short loc_180057EA3
0x180057e9a  mov     ebx, 80040006h
0x180057e9f  jmp     short loc_180057EA3
0x180057ea1  mov     ebx, esi
0x180057ea3  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180057ea8  test    rcx, rcx
0x180057eab  jz      short loc_180057EB8
0x180057ead  call    cs:__imp_RegCloseKey
0x180057eb3  mov     [rsp+2D0h+hKey], rsi
0x180057eb8  lea     rcx, ?g_mxsCodeDownloadGlobals@@3VCMutexSem@@A; lpCriticalSection
0x180057ebf  call    cs:__imp_LeaveCriticalSection
0x180057ec5  mov     eax, ebx
0x180057ec7  mov     rcx, [rbp+1D0h+var_40]
0x180057ece  xor     rcx, rsp; StackCookie
0x180057ed1  call    __security_check_cookie
0x180057ed6  add     rsp, 2A8h
0x180057edd  pop     r14
0x180057edf  pop     r12
0x180057ee1  pop     rdi
0x180057ee2  pop     rsi
0x180057ee3  pop     rbx
0x180057ee4  pop     rbp
0x180057ee5  retn
```
