# SetGlobals(void)

- ea: `0x18005d404`
- end: `0x18005d8f3`
- name: `?SetGlobals@@YAJXZ`
- size: `1263`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007a694`

## callees

- `0x18005d404`
- `0x18005d8fc`
- `0x18005db28`
- `0x18005dd10`
- `0x18005e1c0`
- `0x18008a2d0`
- `0x180094c24`
- `0x1800a3fd4`
- `0x1800a4b40`
- `0x1800a5580`
- `0x1800af5b0`
- `0x18011a41c`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d8c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d8c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d43b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d43b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18005d477`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18005d477`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x18005d880`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x18005d880`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18005d4ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18005d4ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d864`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d8ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d864`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d8ad`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18005d847`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18005d847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d541`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x18005d531`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x18005d531`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x18005d517`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x18005d517`
- `api-ms-win-core-file-l1-2-2!GetTempPathA` at `0x18005d570`
- `api-ms-win-core-file-l1-2-2!GetTempPathA` at `0x18005d570`

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
  if ( dword_18016B5D8 )
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
  byte_180168663 = 0;
  byte_180168553 = 0;
  OcxCacheDirForMachineScope = GetOcxCacheDirForMachineScope(hKey, v1);
  if ( OcxCacheDirForMachineScope >= 0 )
    OcxCacheDirForMachineScope = GetOcxCacheDirForUserScope(v4);
  if ( !OcxCacheDirForMachineScope )
  {
    Type = 4;
    cbData = 4;
    RegQueryValueExA(hKey, "CodeDownloadFlags", 0, &Type, &g_dwCodeDownloadSetupFlags, &cbData);
    COleAutDll::Init(v5);
    FileAttributesA = GetFileAttributesA(g_szOCXCacheDirMachineScope);
    if ( FileAttributesA == -1 )
    {
      if ( !CreateDirectoryA(g_szOCXCacheDirMachineScope, 0) )
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
    qword_1801669C8 = (__int64)v31;
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
        dword_18016B5D8 = 1;
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
0x18005d404  push    rbp
0x18005d406  push    rbx
0x18005d407  push    rsi
0x18005d408  push    rdi
0x18005d409  push    r12
0x18005d40b  push    r14
0x18005d40d  lea     rbp, [rsp-1A8h]
0x18005d415  sub     rsp, 2A8h
0x18005d41c  mov     rax, cs:__security_cookie
0x18005d423  xor     rax, rsp
0x18005d426  mov     [rbp+1D0h+var_40], rax
0x18005d42d  xor     esi, esi
0x18005d42f  lea     rcx, ?g_mxsCodeDownloadGlobals@@3VCMutexSem@@A; lpCriticalSection
0x18005d436  mov     [rsp+2D0h+hKey], rsi
0x18005d43b  call    cs:__imp_EnterCriticalSection
0x18005d442  nop     dword ptr [rax+rax+00h]
0x18005d447  cmp     cs:dword_18016B5D8, esi
0x18005d44d  jnz     loc_18005D8A1
0x18005d453  lea     rax, [rsp+2D0h+hKey]
0x18005d458  mov     r12, 0FFFFFFFF80000002h
0x18005d45f  mov     rcx, r12; hKey
0x18005d462  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18005d467  mov     r9d, 20019h; samDesired
0x18005d46d  lea     rdx, aSoftwareMicros_61; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005d474  xor     r8d, r8d; ulOptions
0x18005d477  call    cs:__imp_RegOpenKeyExA
0x18005d47e  nop     dword ptr [rax+rax+00h]
0x18005d483  mov     ebx, eax
0x18005d485  test    eax, eax
0x18005d487  jz      short loc_18005D49D
0x18005d489  jle     loc_18005D8A3
0x18005d48f  movzx   ebx, ax
0x18005d492  or      ebx, 80070000h
0x18005d498  jmp     loc_18005D8A3
0x18005d49d  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18005d4a2  mov     cs:byte_180168663, sil
0x18005d4a9  mov     cs:byte_180168553, sil
0x18005d4b0  call    ?GetOcxCacheDirForMachineScope@@YAJPEAUHKEY__@@PEAD@Z; GetOcxCacheDirForMachineScope(HKEY__ *,char *)
0x18005d4b5  mov     ebx, eax
0x18005d4b7  test    eax, eax
0x18005d4b9  js      short loc_18005D4C2
0x18005d4bb  call    ?GetOcxCacheDirForUserScope@@YAJPEAD@Z; GetOcxCacheDirForUserScope(char *)
0x18005d4c0  mov     ebx, eax
0x18005d4c2  test    ebx, ebx
0x18005d4c4  jnz     loc_18005D8A3
0x18005d4ca  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18005d4cf  lea     eax, [rbx+4]
0x18005d4d2  mov     [rsp+2D0h+Type], eax
0x18005d4d6  lea     r9, [rsp+2D0h+Type]; lpType
0x18005d4db  mov     [rsp+2D0h+cbData], eax
0x18005d4df  lea     rdx, aCodedownloadfl; "CodeDownloadFlags"
0x18005d4e6  lea     rax, [rsp+2D0h+cbData]
0x18005d4eb  xor     r8d, r8d; lpReserved
0x18005d4ee  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x18005d4f3  lea     rax, ?g_dwCodeDownloadSetupFlags@@3KA; ulong g_dwCodeDownloadSetupFlags
0x18005d4fa  mov     [rsp+2D0h+phkResult], rax; lpData
0x18005d4ff  call    cs:__imp_RegQueryValueExA
0x18005d506  nop     dword ptr [rax+rax+00h]
0x18005d50b  call    ?Init@COleAutDll@@QEAAJXZ; COleAutDll::Init(void)
0x18005d510  lea     rcx, ?g_szOCXCacheDirMachineScope@@3PADA; lpFileName
0x18005d517  call    cs:__imp_GetFileAttributesA
0x18005d51e  nop     dword ptr [rax+rax+00h]
0x18005d523  cmp     eax, 0FFFFFFFFh
0x18005d526  jnz     short loc_18005D556
0x18005d528  xor     edx, edx; lpSecurityAttributes
0x18005d52a  lea     rcx, ?g_szOCXCacheDirMachineScope@@3PADA; lpPathName
0x18005d531  call    cs:__imp_CreateDirectoryA
0x18005d538  nop     dword ptr [rax+rax+00h]
0x18005d53d  test    eax, eax
0x18005d53f  jnz     short loc_18005D560
0x18005d541  call    cs:__imp_GetLastError
0x18005d548  nop     dword ptr [rax+rax+00h]
0x18005d54d  mov     ebx, eax
0x18005d54f  test    eax, eax
0x18005d551  jmp     loc_18005D489
0x18005d556  and     al, 11h
0x18005d558  cmp     al, 10h
0x18005d55a  jnz     loc_18005D89A
0x18005d560  mov     r14d, 104h
0x18005d566  lea     rdx, ?g_szOCXTempDir@@3PADA; lpBuffer
0x18005d56d  mov     ecx, r14d; nBufferLength
0x18005d570  call    cs:__imp_GetTempPathA
0x18005d577  nop     dword ptr [rax+rax+00h]
0x18005d57c  test    eax, eax
0x18005d57e  jz      short loc_18005D541
0x18005d580  call    ?DetermineOSAndCPUVersion@@YAXXZ; DetermineOSAndCPUVersion(void)
0x18005d585  call    ?InitBrowserLangStrings@@YAJXZ; InitBrowserLangStrings(void)
0x18005d58a  cmp     cs:?g_CPUType@@3HA, 0FFFFh; int g_CPUType
0x18005d594  lea     rbx, ?g_szProcessorTypes@@3QBQEBDB; char const * const near * const g_szProcessorTypes
0x18005d59b  mov     eax, esi
0x18005d59d  mov     [rsp+2D0h+var_280], rsi
0x18005d5a2  cmovnz  eax, cs:?g_CPUType@@3HA; int g_CPUType
0x18005d5a9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005d5ad  cdqe
0x18005d5af  mov     [rsp+2D0h+var_278], rsi
0x18005d5b4  mov     rbx, [rbx+rax*8]
0x18005d5b8  mov     rax, rdi
0x18005d5bb  inc     rax
0x18005d5be  cmp     [rbx+rax], sil
0x18005d5c2  jnz     short loc_18005D5BB
0x18005d5c4  add     rax, 0Ch
0x18005d5c8  cmp     rax, 11h
0x18005d5cc  ja      loc_18005D653
0x18005d5d2  lea     rax, [rsp+2D0h+var_278]
0x18005d5d7  mov     dword ptr [rsp+2D0h+lpcbData], 100h; unsigned int
0x18005d5df  lea     r9, [rsp+2D0h+var_280]; char **
0x18005d5e4  mov     [rsp+2D0h+phkResult], rax; int
0x18005d5e9  lea     r8, aFileWin32; "file-win32-"
0x18005d5f0  mov     edx, 11h; unsigned __int64
0x18005d5f5  lea     rcx, ?g_szPlatform@@3PADA; pszDest
0x18005d5fc  call    ?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x18005d601  test    eax, eax
0x18005d603  jns     short loc_18005D621
0x18005d605  mov     rcx, [rbp+1D8h]; this
0x18005d60c  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\urlmon\\download"...
0x18005d613  mov     r9d, eax; char *
0x18005d616  mov     edx, 29Bh; void *
0x18005d61b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005d621  mov     rdx, [rsp+2D0h+var_278]; unsigned __int64
0x18005d626  mov     r8, rbx; char *
0x18005d629  mov     rcx, [rsp+2D0h+var_280]; char *
0x18005d62e  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18005d633  test    eax, eax
0x18005d635  jns     short loc_18005D653
0x18005d637  mov     rcx, [rbp+1D8h]; this
0x18005d63e  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\urlmon\\download"...
0x18005d645  mov     r9d, eax; char *
0x18005d648  mov     edx, 29Ch; void *
0x18005d64d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005d653  mov     rax, rdi
0x18005d656  inc     rax
0x18005d659  cmp     [rbx+rax], sil
0x18005d65d  jnz     short loc_18005D656
0x18005d65f  add     rax, 1Dh
0x18005d663  cmp     rax, r14
0x18005d666  ja      short loc_18005D6E5
0x18005d668  lea     rax, [rsp+2D0h+var_278]
0x18005d66d  mov     dword ptr [rsp+2D0h+lpcbData], 100h; unsigned int
0x18005d675  lea     r9, [rsp+2D0h+var_280]; char **
0x18005d67a  mov     [rsp+2D0h+phkResult], rax; int
0x18005d67f  lea     r8, aApplicationXCa; "application/x-cabinet-win32-"
0x18005d686  mov     rdx, r14; unsigned __int64
0x18005d689  lea     rcx, [rsp+2D0h+pszDest]; pszDest
0x18005d68e  call    ?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x18005d693  test    eax, eax
0x18005d695  jns     short loc_18005D6B3
0x18005d697  mov     rcx, [rbp+1D8h]; this
0x18005d69e  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\urlmon\\download"...
0x18005d6a5  mov     r9d, eax; char *
0x18005d6a8  mov     edx, 2A9h; void *
0x18005d6ad  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005d6b3  mov     rdx, [rsp+2D0h+var_278]; unsigned __int64
0x18005d6b8  mov     r8, rbx; char *
0x18005d6bb  mov     rcx, [rsp+2D0h+var_280]; char *
0x18005d6c0  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18005d6c5  test    eax, eax
0x18005d6c7  jns     short loc_18005D6E5
0x18005d6c9  mov     rcx, [rbp+1D8h]; this
0x18005d6d0  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\urlmon\\download"...
0x18005d6d7  mov     r9d, eax; char *
0x18005d6da  mov     edx, 2AAh; void *
0x18005d6df  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005d6e5  inc     rdi
0x18005d6e8  cmp     [rbx+rdi], sil
0x18005d6ec  jnz     short loc_18005D6E5
0x18005d6ee  lea     rax, [rdi+18h]
0x18005d6f2  cmp     rax, r14
0x18005d6f5  ja      short loc_18005D776
0x18005d6f7  lea     rax, [rsp+2D0h+var_278]
0x18005d6fc  mov     dword ptr [rsp+2D0h+lpcbData], 100h; unsigned int
0x18005d704  lea     r9, [rsp+2D0h+var_280]; char **
0x18005d709  mov     [rsp+2D0h+phkResult], rax; int
0x18005d70e  lea     r8, aApplicationXPe; "application/x-pe-win32-"
0x18005d715  mov     rdx, r14; unsigned __int64
0x18005d718  lea     rcx, [rbp+1D0h+var_150]; pszDest
0x18005d71f  call    ?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x18005d724  test    eax, eax
0x18005d726  jns     short loc_18005D744
0x18005d728  mov     rcx, [rbp+1D8h]; this
0x18005d72f  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\urlmon\\download"...
0x18005d736  mov     r9d, eax; char *
0x18005d739  mov     edx, 2B1h; void *
0x18005d73e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005d744  mov     rdx, [rsp+2D0h+var_278]; unsigned __int64
0x18005d749  mov     r8, rbx; char *
0x18005d74c  mov     rcx, [rsp+2D0h+var_280]; char *
0x18005d751  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18005d756  test    eax, eax
0x18005d758  jns     short loc_18005D776
0x18005d75a  mov     rcx, [rbp+1D8h]; this
0x18005d761  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\urlmon\\download"...
0x18005d768  mov     r9d, eax; char *
0x18005d76b  mov     edx, 2B2h; void *
0x18005d770  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005d776  lea     rax, [rsp+2D0h+pszDest]
0x18005d77b  mov     ecx, 5; ctypes
0x18005d780  mov     cs:?g_rgszMediaStr@@3PAPEBDA, rax; char const * near * g_rgszMediaStr
0x18005d787  lea     r14, ?g_rgclFormat@@3PAGA; ushort near * g_rgclFormat
0x18005d78e  lea     rax, [rbp+1D0h+var_150]
0x18005d795  mov     r8, r14; rgcfTypes
0x18005d798  lea     rdx, ?g_rgszMediaStr@@3PAPEBDA; rgszTypes
0x18005d79f  mov     cs:qword_1801669C8, rax
0x18005d7a6  call    RegisterMediaTypes
0x18005d7ab  mov     ebx, eax
0x18005d7ad  test    eax, eax
0x18005d7af  js      loc_18005D8A3
0x18005d7b5  mov     r8, rsi
0x18005d7b8  lea     rdx, ?g_rgfmtetc@@3PAUtagFORMATETC@@A; rgfmtetc
0x18005d7bf  mov     rcx, rsi
0x18005d7c2  mov     edi, 1
0x18005d7c7  movzx   eax, word ptr [r14+r8*2]
0x18005d7cc  add     r8, rdi
0x18005d7cf  mov     [rcx+rdx], ax
0x18005d7d3  mov     [rcx+rdx+18h], esi
0x18005d7d7  mov     [rcx+rdx+10h], edi
0x18005d7db  mov     [rcx+rdx+8], rsi
0x18005d7e0  lea     rcx, [rcx+20h]
0x18005d7e4  cmp     r8, 5
0x18005d7e8  jnz     short loc_18005D7C7
0x18005d7ea  lea     r8, ?g_pEFmtETC@@3PEAUIEnumFORMATETC@@EA; ppenumfmtetc
0x18005d7f1  mov     ecx, 5; cfmtetc
0x18005d7f6  call    CreateFormatEnumerator
0x18005d7fb  mov     ebx, eax
0x18005d7fd  test    eax, eax
0x18005d7ff  js      loc_18005D8A3
0x18005d805  call    ?IsMICHighProcess@@YAHXZ; IsMICHighProcess(void)
0x18005d80a  test    eax, eax
0x18005d80c  jz      loc_18005D892
0x18005d812  mov     [rsp+2D0h+lpdwDisposition], rsi; lpdwDisposition
0x18005d817  lea     rax, [rsp+2D0h+var_280]
0x18005d81c  mov     [rsp+2D0h+var_298], rax; phkResult
0x18005d821  lea     rdx, aSoftwareMicros_75; "Software\\Microsoft\\Code Store Databas"...
0x18005d828  mov     [rsp+2D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18005d82d  xor     r9d, r9d; lpClass
0x18005d830  mov     dword ptr [rsp+2D0h+lpcbData], 2000000h; samDesired
0x18005d838  xor     r8d, r8d; Reserved
0x18005d83b  mov     rcx, r12; hKey
0x18005d83e  mov     dword ptr [rsp+2D0h+phkResult], esi; dwOptions
0x18005d842  mov     [rsp+2D0h+var_280], rsi
0x18005d847  call    cs:__imp_RegCreateKeyExA
0x18005d84e  nop     dword ptr [rax+rax+00h]
0x18005d853  test    eax, eax
0x18005d855  jz      short loc_18005D85F
0x18005d857  mov     cs:?g_bLockedDown@@3HA, edi; int g_bLockedDown
0x18005d85d  jmp     short loc_18005D892
0x18005d85f  mov     rcx, [rsp+2D0h+var_280]; hKey
0x18005d864  call    cs:__imp_RegCloseKey
0x18005d86b  nop     dword ptr [rax+rax+00h]
0x18005d870  xor     r9d, r9d; Reserved
0x18005d873  lea     rdx, aSoftwareMicros_75; "Software\\Microsoft\\Code Store Databas"...
0x18005d87a  xor     r8d, r8d; samDesired
0x18005d87d  mov     rcx, r12; hKey
0x18005d880  call    cs:__imp_RegDeleteKeyExA
0x18005d887  nop     dword ptr [rax+rax+00h]
0x18005d88c  mov     cs:?g_bLockedDown@@3HA, esi; int g_bLockedDown
0x18005d892  mov     cs:dword_18016B5D8, edi
0x18005d898  jmp     short loc_18005D8A3
0x18005d89a  mov     ebx, 80040006h
0x18005d89f  jmp     short loc_18005D8A3
0x18005d8a1  mov     ebx, esi
0x18005d8a3  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18005d8a8  test    rcx, rcx
0x18005d8ab  jz      short loc_18005D8BE
0x18005d8ad  call    cs:__imp_RegCloseKey
0x18005d8b4  nop     dword ptr [rax+rax+00h]
0x18005d8b9  mov     [rsp+2D0h+hKey], rsi
0x18005d8be  lea     rcx, ?g_mxsCodeDownloadGlobals@@3VCMutexSem@@A; lpCriticalSection
0x18005d8c5  call    cs:__imp_LeaveCriticalSection
0x18005d8cc  nop     dword ptr [rax+rax+00h]
0x18005d8d1  mov     eax, ebx
0x18005d8d3  mov     rcx, [rbp+1D0h+var_40]
0x18005d8da  xor     rcx, rsp; StackCookie
0x18005d8dd  call    __security_check_cookie
0x18005d8e2  add     rsp, 2A8h
0x18005d8e9  pop     r14
0x18005d8eb  pop     r12
0x18005d8ed  pop     rdi
0x18005d8ee  pop     rsi
0x18005d8ef  pop     rbx
0x18005d8f0  pop     rbp
0x18005d8f1  retn
```
