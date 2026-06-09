# DavQueryWinInetCookies

- ea: `0x1800135b4`
- end: `0x180013aea`
- name: `DavQueryWinInetCookies`
- size: `1334`
- prototype: `__int64 __fastcall(HINTERNET hInternet)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012468`

## callees

- `0x18000b728`
- `0x18000b7dc`
- `0x18000b99c`
- `0x1800135b4`
- `0x180029c84`
- `0x18002cf62`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001364a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001373d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001385a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001364a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001373d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001385a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013a6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013a7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013a8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013a6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013a7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013a8e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800139ca`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800139ca`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800139b5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800139b5`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18001394f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18001394f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013967`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013967`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180013733`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180013733`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180013640`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180013640`
- `KERNEL32!LocalFree` at `0x180013a9c`
- `KERNEL32!LocalFree` at `0x180013aba`
- `KERNEL32!LocalFree` at `0x180013a9c`
- `KERNEL32!LocalFree` at `0x180013aba`
- `KERNEL32!LocalAlloc` at `0x18001384c`
- `KERNEL32!LocalAlloc` at `0x18001384c`
- `USERENV!DestroyEnvironmentBlock` at `0x180013aac`
- `USERENV!DestroyEnvironmentBlock` at `0x180013aac`
- `USERENV!CreateEnvironmentBlock` at `0x1800136c5`
- `USERENV!CreateEnvironmentBlock` at `0x1800136c5`

## string_xrefs

- `0x1800138b3`: `davclnt.dll`
- `0x1800137ac`: `rundll32.exe`
- `0x1800138a0`: `rundll32.exe`

## pseudocode

```c
__int64 __fastcall DavQueryWinInetCookies(HINTERNET hInternet, __int64 a2, void *a3)
{
  DWORD LastError; // eax
  WCHAR *v7; // rbx
  _WORD *PathFromRequest; // rdi
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  UINT SystemDirectoryW; // eax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // esi
  wchar_t *v18; // rax
  DWORD v19; // eax
  DWORD v20; // eax
  _QWORD *v21; // rcx
  int v22; // edx
  DWORD ExitCode; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hToken; // [rsp+68h] [rbp-98h] BYREF
  LPVOID Environment; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-88h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t pszDest[264]; // [rsp+310h] [rbp+210h] BYREF

  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo, 0, 0x64u);
  hToken = 0;
  Environment = 0;
  ExitCode = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !DuplicateTokenEx(a3, 0x2000000u, 0, SecurityImpersonation, TokenPrimary, &hToken) )
  {
    LastError = GetLastError();
    ExitCode = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 254, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, LastError);
    return ExitCode;
  }
  v7 = 0;
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateEnvironmentBlock(&Environment, hToken, 0) )
  {
    PathFromRequest = 0;
    v9 = GetLastError();
    ExitCode = v9;
    Environment = 0;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_54;
    v11 = 255;
    goto LABEL_9;
  }
  PathFromRequest = (_WORD *)DavQueryPathFromRequest(hInternet);
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
  {
    v9 = GetLastError();
    ExitCode = v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_54;
    v11 = 256;
    goto LABEL_9;
  }
  if ( SystemDirectoryW > 0x104 )
  {
    v12 = 13;
    ExitCode = 13;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_54;
    v11 = 257;
    goto LABEL_10;
  }
  v9 = StringCchPrintfW(pszDest, 0x104u, L"%ws\\%ws", Buffer, L"rundll32.exe");
  if ( v9 < 0 )
  {
    v9 = (unsigned __int16)v9;
    ExitCode = (unsigned __int16)v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_54;
    v11 = 258;
    goto LABEL_9;
  }
  v14 = -1;
  v15 = -1;
  do
    ++v15;
  while ( Buffer[v15] );
  v16 = -1;
  do
    ++v16;
  while ( PathFromRequest[v16] );
  do
    ++v14;
  while ( *(_WORD *)(a2 + 2 * v14) );
  v17 = v16 + 42 + v15 + v14;
  v18 = (wchar_t *)LocalAlloc(0x40u, 2LL * v17);
  v7 = v18;
  if ( !v18 )
  {
    v9 = GetLastError();
    ExitCode = v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_54;
    v11 = 259;
    goto LABEL_9;
  }
  v9 = StringCchPrintfW(
         v18,
         v17,
         L"%ws %ws\\%ws,%ws %ws %ws",
         L"rundll32.exe",
         Buffer,
         L"davclnt.dll",
         L"DavSetCookie",
         a2,
         PathFromRequest);
  if ( v9 < 0 )
  {
    v9 = (unsigned __int16)v9;
    ExitCode = (unsigned __int16)v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_54;
    v11 = 260;
LABEL_9:
    v12 = (unsigned int)v9;
LABEL_10:
    WPP_SF_d(v10[2], v11, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v12);
    goto LABEL_54;
  }
  if ( CreateProcessAsUserW(hToken, pszDest, v7, 0, 0, 0, 0x8000400u, Environment, 0, &StartupInfo, &ProcessInformation) )
  {
    v19 = WaitForSingleObject(ProcessInformation.hProcess, 0x3A98u);
    ExitCode = v19;
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          261,
          (unsigned int)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
          (_DWORD)v7,
          v19);
        v19 = ExitCode;
      }
      TerminateProcess(ProcessInformation.hProcess, v19);
      goto LABEL_54;
    }
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
    {
      LOBYTE(v20) = ExitCode;
      if ( !ExitCode )
        goto LABEL_54;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_54;
      v22 = 263;
    }
    else
    {
      v20 = GetLastError();
      ExitCode = v20;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_54;
      v22 = 262;
    }
  }
  else
  {
    v20 = GetLastError();
    ExitCode = v20;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_54;
    v22 = 264;
  }
  WPP_SF_Sd(v21[2], v22, (unsigned int)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, (_DWORD)v7, v20);
LABEL_54:
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( hToken )
    CloseHandle(hToken);
  if ( PathFromRequest )
    LocalFree(PathFromRequest);
  if ( Environment )
    DestroyEnvironmentBlock(Environment);
  if ( v7 )
    LocalFree(v7);
  return ExitCode;
}

```

## disassembly

```asm
0x1800135b4  mov     [rsp-8+arg_18], rbx
0x1800135b9  push    rbp
0x1800135ba  push    rsi
0x1800135bb  push    rdi
0x1800135bc  push    r14
0x1800135be  push    r15
0x1800135c0  lea     rbp, [rsp-430h]
0x1800135c8  sub     rsp, 530h
0x1800135cf  mov     rax, cs:__security_cookie
0x1800135d6  xor     rax, rsp
0x1800135d9  mov     [rbp+450h+var_30], rax
0x1800135e0  xor     eax, eax
0x1800135e2  mov     rbx, r8
0x1800135e5  mov     r14, rdx
0x1800135e8  mov     dword ptr [rbp+450h+StartupInfo+4], eax
0x1800135eb  mov     rdi, rcx
0x1800135ee  xor     edx, edx; Val
0x1800135f0  lea     rcx, [rbp+450h+StartupInfo]; void *
0x1800135f4  lea     esi, [rax+64h]
0x1800135f7  mov     r8d, esi; Size
0x1800135fa  call    memset_0
0x1800135ff  xor     eax, eax
0x180013601  lea     r9d, [rsi-62h]; ImpersonationLevel
0x180013605  xor     r15d, r15d
0x180013608  mov     qword ptr [rbp+450h+ProcessInformation.dwProcessId], rax
0x18001360c  lea     rax, [rsp+550h+hToken]
0x180013611  mov     [rsp+550h+hToken], r15
0x180013616  xorps   xmm0, xmm0
0x180013619  mov     [rsp+550h+phNewToken], rax; phNewToken
0x18001361e  xor     r8d, r8d; lpTokenAttributes
0x180013621  mov     [rsp+550h+TokenType], 1; TokenType
0x180013629  mov     edx, 2000000h; dwDesiredAccess
0x18001362e  mov     [rsp+550h+Environment], r15
0x180013633  mov     rcx, rbx; hExistingToken
0x180013636  mov     [rsp+550h+ExitCode], r15d
0x18001363b  movups  xmmword ptr [rsp+550h+ProcessInformation.hProcess], xmm0
0x180013640  call    cs:__imp_DuplicateTokenEx
0x180013646  test    eax, eax
0x180013648  jnz     short loc_180013692
0x18001364a  call    cs:__imp_GetLastError
0x180013650  mov     [rsp+550h+ExitCode], eax
0x180013654  mov     rcx, cs:WPP_GLOBAL_Control
0x18001365b  lea     rdx, WPP_GLOBAL_Control
0x180013662  cmp     rcx, rdx
0x180013665  jz      loc_180013AC0
0x18001366b  test    byte ptr [rcx+1Ch], 1
0x18001366f  jz      loc_180013AC0
0x180013675  mov     rcx, [rcx+10h]
0x180013679  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180013680  mov     edx, 0FEh
0x180013685  mov     r9d, eax
0x180013688  call    WPP_SF_d
0x18001368d  jmp     loc_180013AC0
0x180013692  mov     r8, rsi; Size
0x180013695  lea     rcx, [rbp+450h+StartupInfo+4]; void *
0x180013699  xor     edx, edx; Val
0x18001369b  mov     rbx, r15
0x18001369e  call    memset_0
0x1800136a3  mov     rdx, [rsp+550h+hToken]; hToken
0x1800136a8  lea     rcx, [rsp+550h+Environment]; lpEnvironment
0x1800136ad  xorps   xmm0, xmm0
0x1800136b0  mov     [rbp+450h+StartupInfo.cb], 68h ; 'h'
0x1800136b7  xor     eax, eax
0x1800136b9  xor     r8d, r8d; bInherit
0x1800136bc  movups  xmmword ptr [rsp+550h+ProcessInformation.hProcess], xmm0
0x1800136c1  mov     qword ptr [rbp+450h+ProcessInformation.dwProcessId], rax
0x1800136c5  call    cs:__imp_CreateEnvironmentBlock
0x1800136cb  test    eax, eax
0x1800136cd  jnz     short loc_18001371F
0x1800136cf  mov     rdi, r15
0x1800136d2  call    cs:__imp_GetLastError
0x1800136d8  mov     [rsp+550h+ExitCode], eax
0x1800136dc  mov     [rsp+550h+Environment], r15
0x1800136e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136e8  lea     rdx, WPP_GLOBAL_Control
0x1800136ef  cmp     rcx, rdx
0x1800136f2  jz      loc_180013A65
0x1800136f8  test    byte ptr [rcx+1Ch], 1
0x1800136fc  jz      loc_180013A65
0x180013702  mov     edx, 0FFh
0x180013707  mov     r9d, eax
0x18001370a  mov     rcx, [rcx+10h]
0x18001370e  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180013715  call    WPP_SF_d
0x18001371a  jmp     loc_180013A65
0x18001371f  mov     rcx, rdi; hInternet
0x180013722  call    DavQueryPathFromRequest
0x180013727  mov     edx, 104h; uSize
0x18001372c  lea     rcx, [rbp+450h+Buffer]; lpBuffer
0x180013730  mov     rdi, rax
0x180013733  call    cs:__imp_GetSystemDirectoryW
0x180013739  test    eax, eax
0x18001373b  jnz     short loc_18001376F
0x18001373d  call    cs:__imp_GetLastError
0x180013743  mov     [rsp+550h+ExitCode], eax
0x180013747  mov     rcx, cs:WPP_GLOBAL_Control
0x18001374e  lea     rdx, WPP_GLOBAL_Control
0x180013755  cmp     rcx, rdx
0x180013758  jz      loc_180013A65
0x18001375e  test    byte ptr [rcx+1Ch], 1
0x180013762  jz      loc_180013A65
0x180013768  mov     edx, 100h
0x18001376d  jmp     short loc_180013707
0x18001376f  cmp     eax, 104h
0x180013774  jbe     short loc_1800137AC
0x180013776  mov     r9d, 0Dh
0x18001377c  mov     [rsp+550h+ExitCode], r9d
0x180013781  mov     rcx, cs:WPP_GLOBAL_Control
0x180013788  lea     rdx, WPP_GLOBAL_Control
0x18001378f  cmp     rcx, rdx
0x180013792  jz      loc_180013A65
0x180013798  test    byte ptr [rcx+1Ch], 1
0x18001379c  jz      loc_180013A65
0x1800137a2  mov     edx, 101h
0x1800137a7  jmp     loc_18001370A
0x1800137ac  lea     rax, aRundll32Exe; "rundll32.exe"
0x1800137b3  mov     edx, 104h; cchDest
0x1800137b8  lea     r9, [rbp+450h+Buffer]
0x1800137bc  mov     qword ptr [rsp+550h+TokenType], rax
0x1800137c1  lea     r8, aWsWs; "%ws\\%ws"
0x1800137c8  lea     rcx, [rbp+450h+pszDest]; pszDest
0x1800137cf  call    StringCchPrintfW
0x1800137d4  test    eax, eax
0x1800137d6  jns     short loc_18001380A
0x1800137d8  movzx   eax, ax
0x1800137db  mov     [rsp+550h+ExitCode], eax
0x1800137df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137e6  lea     rdx, WPP_GLOBAL_Control
0x1800137ed  cmp     rcx, rdx
0x1800137f0  jz      loc_180013A65
0x1800137f6  test    byte ptr [rcx+1Ch], 1
0x1800137fa  jz      loc_180013A65
0x180013800  mov     edx, 102h
0x180013805  jmp     loc_180013707
0x18001380a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001380e  lea     rdx, [rbp+450h+Buffer]
0x180013812  mov     rcx, rax
0x180013815  inc     rcx
0x180013818  cmp     [rdx+rcx*2], r15w
0x18001381d  jnz     short loc_180013815
0x18001381f  mov     rdx, rax
0x180013822  inc     rdx
0x180013825  cmp     [rdi+rdx*2], r15w
0x18001382a  jnz     short loc_180013822
0x18001382c  inc     rax
0x18001382f  cmp     [r14+rax*2], r15w
0x180013834  jnz     short loc_18001382C
0x180013836  lea     rsi, [rcx+rax]
0x18001383a  add     rdx, 2Ah ; '*'
0x18001383e  add     rsi, rdx
0x180013841  mov     ecx, 40h ; '@'; uFlags
0x180013846  mov     esi, esi
0x180013848  lea     rdx, [rsi+rsi]; uBytes
0x18001384c  call    cs:__imp_LocalAlloc
0x180013852  mov     rbx, rax
0x180013855  test    rax, rax
0x180013858  jnz     short loc_18001388F
0x18001385a  call    cs:__imp_GetLastError
0x180013860  mov     [rsp+550h+ExitCode], eax
0x180013864  mov     rcx, cs:WPP_GLOBAL_Control
0x18001386b  lea     rdx, WPP_GLOBAL_Control
0x180013872  cmp     rcx, rdx
0x180013875  jz      loc_180013A65
0x18001387b  test    byte ptr [rcx+1Ch], 1
0x18001387f  jz      loc_180013A65
0x180013885  mov     edx, 103h
0x18001388a  jmp     loc_180013707
0x18001388f  mov     [rsp+550h+lpCurrentDirectory], rdi
0x180013894  lea     rax, aDavsetcookie; "DavSetCookie"
0x18001389b  mov     [rsp+550h+lpEnvironment], r14
0x1800138a0  lea     r9, aRundll32Exe; "rundll32.exe"
0x1800138a7  mov     qword ptr [rsp+550h+dwCreationFlags], rax
0x1800138ac  lea     r8, aWsWsWsWsWsWs; "%ws %ws\\%ws,%ws %ws %ws"
0x1800138b3  lea     rax, aDavclntDll; "davclnt.dll"
0x1800138ba  mov     rdx, rsi; cchDest
0x1800138bd  mov     [rsp+550h+phNewToken], rax
0x1800138c2  mov     rcx, rbx; pszDest
0x1800138c5  lea     rax, [rbp+450h+Buffer]
0x1800138c9  mov     qword ptr [rsp+550h+TokenType], rax
0x1800138ce  call    StringCchPrintfW
0x1800138d3  test    eax, eax
0x1800138d5  jns     short loc_180013909
0x1800138d7  movzx   eax, ax
0x1800138da  mov     [rsp+550h+ExitCode], eax
0x1800138de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138e5  lea     rdx, WPP_GLOBAL_Control
0x1800138ec  cmp     rcx, rdx
0x1800138ef  jz      loc_180013A65
0x1800138f5  test    byte ptr [rcx+1Ch], 1
0x1800138f9  jz      loc_180013A65
0x1800138ff  mov     edx, 104h
0x180013904  jmp     loc_180013707
0x180013909  mov     rcx, [rsp+550h+hToken]; hToken
0x18001390e  lea     rax, [rsp+550h+ProcessInformation]
0x180013913  mov     [rsp+550h+lpProcessInformation], rax; lpProcessInformation
0x180013918  lea     rdx, [rbp+450h+pszDest]; lpApplicationName
0x18001391f  lea     rax, [rbp+450h+StartupInfo]
0x180013923  xor     r9d, r9d; lpProcessAttributes
0x180013926  mov     [rsp+550h+lpStartupInfo], rax; lpStartupInfo
0x18001392b  mov     r8, rbx; lpCommandLine
0x18001392e  mov     rax, [rsp+550h+Environment]
0x180013933  mov     [rsp+550h+lpCurrentDirectory], r15; lpCurrentDirectory
0x180013938  mov     [rsp+550h+lpEnvironment], rax; lpEnvironment
0x18001393d  mov     [rsp+550h+dwCreationFlags], 8000400h; dwCreationFlags
0x180013945  mov     dword ptr [rsp+550h+phNewToken], r15d; bInheritHandles
0x18001394a  mov     qword ptr [rsp+550h+TokenType], r15; lpThreadAttributes
0x18001394f  call    cs:__imp_CreateProcessAsUserW
0x180013955  test    eax, eax
0x180013957  jz      loc_180013A26
0x18001395d  mov     rcx, [rsp+550h+ProcessInformation.hProcess]; hHandle
0x180013962  mov     edx, 3A98h; dwMilliseconds
0x180013967  call    cs:__imp_WaitForSingleObject
0x18001396d  mov     [rsp+550h+ExitCode], eax
0x180013971  test    eax, eax
0x180013973  jz      short loc_1800139C0
0x180013975  mov     rcx, cs:WPP_GLOBAL_Control
0x18001397c  lea     rdx, WPP_GLOBAL_Control
0x180013983  cmp     rcx, rdx
0x180013986  jz      short loc_1800139AE
0x180013988  test    byte ptr [rcx+1Ch], 1
0x18001398c  jz      short loc_1800139AE
0x18001398e  mov     rcx, [rcx+10h]
0x180013992  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180013999  mov     edx, 105h
0x18001399e  mov     [rsp+550h+TokenType], eax
0x1800139a2  mov     r9, rbx
0x1800139a5  call    WPP_SF_Sd
0x1800139aa  mov     eax, [rsp+550h+ExitCode]
0x1800139ae  mov     rcx, [rsp+550h+ProcessInformation.hProcess]; hProcess
0x1800139b3  mov     edx, eax; uExitCode
0x1800139b5  call    cs:__imp_TerminateProcess
0x1800139bb  jmp     loc_180013A65
0x1800139c0  mov     rcx, [rsp+550h+ProcessInformation.hProcess]; hProcess
0x1800139c5  lea     rdx, [rsp+550h+ExitCode]; lpExitCode
0x1800139ca  call    cs:__imp_GetExitCodeProcess
0x1800139d0  test    eax, eax
0x1800139d2  jnz     short loc_1800139FE
0x1800139d4  call    cs:__imp_GetLastError
0x1800139da  mov     [rsp+550h+ExitCode], eax
0x1800139de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139e5  lea     rdx, WPP_GLOBAL_Control
0x1800139ec  cmp     rcx, rdx
0x1800139ef  jz      short loc_180013A65
0x1800139f1  test    byte ptr [rcx+1Ch], 1
0x1800139f5  jz      short loc_180013A65
0x1800139f7  mov     edx, 106h
0x1800139fc  jmp     short loc_180013A4E
0x1800139fe  mov     eax, [rsp+550h+ExitCode]
0x180013a02  test    eax, eax
0x180013a04  jz      short loc_180013A65
0x180013a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a0d  lea     rdx, WPP_GLOBAL_Control
0x180013a14  cmp     rcx, rdx
0x180013a17  jz      short loc_180013A65
0x180013a19  test    byte ptr [rcx+1Ch], 1
0x180013a1d  jz      short loc_180013A65
0x180013a1f  mov     edx, 107h
0x180013a24  jmp     short loc_180013A4E
0x180013a26  call    cs:__imp_GetLastError
0x180013a2c  mov     [rsp+550h+ExitCode], eax
0x180013a30  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a37  lea     rdx, WPP_GLOBAL_Control
0x180013a3e  cmp     rcx, rdx
0x180013a41  jz      short loc_180013A65
0x180013a43  test    byte ptr [rcx+1Ch], 1
0x180013a47  jz      short loc_180013A65
0x180013a49  mov     edx, 108h
0x180013a4e  mov     rcx, [rcx+10h]
0x180013a52  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180013a59  mov     r9, rbx
0x180013a5c  mov     [rsp+550h+TokenType], eax
0x180013a60  call    WPP_SF_Sd
0x180013a65  mov     rcx, [rbp+450h+ProcessInformation.hThread]; hObject
0x180013a69  test    rcx, rcx
0x180013a6c  jz      short loc_180013A74
0x180013a6e  call    cs:__imp_CloseHandle
0x180013a74  mov     rcx, [rsp+550h+ProcessInformation.hProcess]; hObject
0x180013a79  test    rcx, rcx
0x180013a7c  jz      short loc_180013A84
0x180013a7e  call    cs:__imp_CloseHandle
0x180013a84  mov     rcx, [rsp+550h+hToken]; hObject
0x180013a89  test    rcx, rcx
0x180013a8c  jz      short loc_180013A94
0x180013a8e  call    cs:__imp_CloseHandle
0x180013a94  test    rdi, rdi
0x180013a97  jz      short loc_180013AA2
0x180013a99  mov     rcx, rdi; hMem
0x180013a9c  call    cs:__imp_LocalFree
0x180013aa2  mov     rcx, [rsp+550h+Environment]; lpEnvironment
0x180013aa7  test    rcx, rcx
0x180013aaa  jz      short loc_180013AB2
0x180013aac  call    cs:__imp_DestroyEnvironmentBlock
0x180013ab2  test    rbx, rbx
0x180013ab5  jz      short loc_180013AC0
0x180013ab7  mov     rcx, rbx; hMem
0x180013aba  call    cs:__imp_LocalFree
0x180013ac0  mov     eax, [rsp+550h+ExitCode]
0x180013ac4  mov     rcx, [rbp+450h+var_30]
0x180013acb  xor     rcx, rsp; StackCookie
0x180013ace  call    __security_check_cookie
  ... truncated ...
```
