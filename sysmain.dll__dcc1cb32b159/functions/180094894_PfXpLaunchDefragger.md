# PfXpLaunchDefragger

- ea: `0x180094894`
- end: `0x180094ca3`
- name: `PfXpLaunchDefragger`
- size: `1039`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180018ec0`

## callees

- `0x180039f94`
- `0x18003bafc`
- `0x180049d6c`
- `0x180058c2c`
- `0x180094894`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180094939`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180094939`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180094bf1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180094bf1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180094b82`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180094c6f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180094b82`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180094c6f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180094b63`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180094bb0`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180094b63`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180094bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094c12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094c12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094b1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094bfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094c33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094c41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094b1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094bfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094c33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094c41`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18009497b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18009497b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180094b08`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180094b08`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180094bcc`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180094bcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009490e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009490e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180094c2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180094c2a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180094a32`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180094a32`

## pseudocode

```c
__int64 __fastcall PfXpLaunchDefragger(__int64 a1)
{
  __int64 v2; // rcx
  DWORD LastError; // ebx
  DWORD CurrentProcessId; // eax
  HANDLE EventW; // rax
  void *v6; // rsi
  HANDLE hProcess; // rdi
  UINT SystemDirectoryW; // eax
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  SIZE_T v13; // rbx
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  unsigned int i; // r15d
  DWORD v17; // ecx
  DWORD v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  int v21; // ebx
  bool v22; // zf
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v25[6]; // [rsp+54h] [rbp-ACh] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-A0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  HANDLE Handles[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v29; // [rsp+100h] [rbp+0h]
  wchar_t pszDest[40]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t pszSrc[40]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR Buffer[264]; // [rsp+1B0h] [rbp+B0h] BYREF

  v29 = 0;
  ExitCode = 0;
  *(_OWORD *)Handles = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  LOBYTE(v2) = 1;
  StartupInfo.cb = 104;
  if ( !(unsigned __int8)PfXpAllowedToRunDefragger(v2) )
    return 5;
  CurrentProcessId = GetCurrentProcessId();
  StringCbPrintfW(pszDest, 0x46u, L"-p %x ", CurrentProcessId);
  EventW = CreateEventW(0, 1, 0, 0);
  v6 = EventW;
  if ( !EventW )
    return GetLastError();
  hProcess = 0;
  StringCbPrintfW(pszSrc, 0x46u, L"-s %p ", EventW);
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
  {
    LastError = GetLastError();
    goto LABEL_36;
  }
  if ( SystemDirectoryW >= 0x104 )
  {
    LastError = 122;
    goto LABEL_36;
  }
  v25[0] = Buffer[0];
  v25[1] = Buffer[1];
  v9 = -1;
  v10 = -1;
  Buffer[259] = 0;
  v25[2] = 0;
  do
    ++v10;
  while ( pszDest[v10] );
  v11 = -1;
  do
    ++v11;
  while ( pszSrc[v11] );
  v12 = -1;
  do
    ++v12;
  while ( Buffer[v12] );
  do
    ++v9;
  while ( v25[v9] );
  v13 = (unsigned int)(2 * (v10 + v11 + v12 + v9) + 66);
  v14 = (wchar_t *)HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v13);
  v15 = v14;
  if ( !v14 )
  {
    LastError = 8;
    goto LABEL_36;
  }
  StringCbCopyW(v14, v13, L"\"");
  StringCbCatW(v15, v13, Buffer);
  StringCbCatW(v15, v13, L"\\defrag.exe\" ");
  StringCbCatW(v15, v13, pszDest);
  StringCbCatW(v15, v13, pszSrc);
  StringCbCatW(v15, v13, L"-b -OnlyPreferred ");
  StringCbCatW(v15, v13, v25);
  LastError = 298;
  for ( i = 0; ; ++i )
  {
    hProcess = 0;
    if ( i >= 0x14 )
      goto LABEL_35;
    if ( !CreateProcessW(0, v15, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
      goto LABEL_34;
    CloseHandle(ProcessInformation.hThread);
    hProcess = ProcessInformation.hProcess;
    Handles[0] = ProcessInformation.hProcess;
    Handles[1] = *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 880LL);
    v17 = 2;
    if ( a1 )
    {
      v17 = 3;
      v29 = *(_QWORD *)(a1 + 72);
    }
    v18 = WaitForMultipleObjectsEx(v17, Handles, 0, 0xFFFFFFFF, 0);
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        if ( v19 != 1 )
          goto LABEL_34;
        SetEvent(v6);
        Handles[0] = hProcess;
        Handles[1] = *(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 880LL);
        v20 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
        if ( !v20 )
        {
          v21 = 0;
          goto LABEL_29;
        }
        if ( v20 != 1 )
        {
LABEL_34:
          LastError = GetLastError();
          goto LABEL_35;
        }
      }
      else
      {
        SetEvent(v6);
      }
      LastError = 1115;
      goto LABEL_35;
    }
    v21 = 1;
LABEL_29:
    if ( !GetExitCodeProcess(hProcess, &ExitCode) )
      goto LABEL_34;
    v22 = v21 == 0;
    LastError = ExitCode;
    if ( v22 )
      break;
    if ( ExitCode != 1237 )
      goto LABEL_43;
    ResetEvent(v6);
    CloseHandle(hProcess);
    LastError = 1235;
  }
  if ( ExitCode == 1223 )
  {
    LastError = 1237;
  }
  else
  {
LABEL_43:
    if ( (ExitCode & 0xC0000000) == 0xC0000000 )
      dword_1800D3C28 = ExitCode;
  }
LABEL_35:
  HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v15);
LABEL_36:
  CloseHandle(v6);
  if ( hProcess )
    CloseHandle(hProcess);
  return LastError;
}

```

## disassembly

```asm
0x180094894  push    rbp
0x180094896  push    rbx
0x180094897  push    rsi
0x180094898  push    rdi
0x180094899  push    r12
0x18009489b  push    r13
0x18009489d  push    r14
0x18009489f  push    r15
0x1800948a1  lea     rbp, [rsp-2D8h]
0x1800948a9  sub     rsp, 3D8h
0x1800948b0  mov     rax, cs:__security_cookie
0x1800948b7  xor     rax, rsp
0x1800948ba  mov     [rbp+310h+var_50], rax
0x1800948c1  xor     eax, eax
0x1800948c3  xorps   xmm0, xmm0
0x1800948c6  mov     r13, rcx
0x1800948c9  mov     [rbp+310h+var_310], rax
0x1800948cd  xor     r12d, r12d
0x1800948d0  mov     qword ptr [rsp+410h+ProcessInformation.dwProcessId], rax
0x1800948d5  xor     edx, edx; Val
0x1800948d7  mov     [rsp+410h+ExitCode], r12d
0x1800948dc  lea     r8d, [rax+64h]; Size
0x1800948e0  lea     rcx, [rbp+310h+StartupInfo+4]; void *
0x1800948e4  movups  xmmword ptr [rbp+310h+Handles], xmm0
0x1800948e8  movups  xmmword ptr [rsp+410h+ProcessInformation.hProcess], xmm0
0x1800948ed  call    memset_0
0x1800948f2  mov     cl, 1
0x1800948f4  mov     [rbp+310h+StartupInfo.cb], 68h ; 'h'
0x1800948fb  call    PfXpAllowedToRunDefragger
0x180094900  test    al, al
0x180094902  jnz     short loc_18009490E
0x180094904  lea     ebx, [r12+5]
0x180094909  jmp     loc_180094C47
0x18009490e  call    cs:__imp_GetCurrentProcessId
0x180094914  mov     ebx, 46h ; 'F'
0x180094919  lea     r8, aPX; "-p %x "
0x180094920  mov     r9d, eax
0x180094923  lea     rcx, [rbp+310h+pszDest]; pszDest
0x180094927  mov     edx, ebx; cbDest
0x180094929  call    StringCbPrintfW
0x18009492e  xor     r9d, r9d; lpName
0x180094931  lea     edx, [rbx-45h]; bManualReset
0x180094934  xor     r8d, r8d; bInitialState
0x180094937  xor     ecx, ecx; lpEventAttributes
0x180094939  call    cs:__imp_CreateEventW
0x18009493f  mov     rsi, rax
0x180094942  test    rax, rax
0x180094945  jnz     short loc_180094954
0x180094947  call    cs:__imp_GetLastError
0x18009494d  mov     ebx, eax
0x18009494f  jmp     loc_180094C47
0x180094954  mov     r9, rsi
0x180094957  lea     r8, aSP; "-s %p "
0x18009495e  mov     rdx, rbx; cbDest
0x180094961  lea     rcx, [rbp+310h+pszSrc]; pszDest
0x180094965  mov     rdi, r12
0x180094968  call    StringCbPrintfW
0x18009496d  mov     ebx, 104h
0x180094972  lea     rcx, [rbp+310h+Buffer]; lpBuffer
0x180094979  mov     edx, ebx; uSize
0x18009497b  call    cs:__imp_GetSystemDirectoryW
0x180094981  test    eax, eax
0x180094983  jnz     short loc_180094992
0x180094985  call    cs:__imp_GetLastError
0x18009498b  mov     ebx, eax
0x18009498d  jmp     loc_180094C30
0x180094992  cmp     eax, ebx
0x180094994  jb      short loc_1800949A0
0x180094996  mov     ebx, 7Ah ; 'z'
0x18009499b  jmp     loc_180094C30
0x1800949a0  movzx   eax, [rbp+310h+Buffer]
0x1800949a7  lea     rcx, [rbp+310h+pszDest]
0x1800949ab  mov     [rsp+410h+var_3BC], ax
0x1800949b0  movzx   eax, [rbp+310h+var_25E]
0x1800949b7  mov     [rsp+410h+var_3BA], ax
0x1800949bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800949c0  mov     r8, rax
0x1800949c3  mov     [rbp+310h+var_5A], r12w
0x1800949cb  mov     [rsp+410h+var_3B8], r12w
0x1800949d1  inc     r8
0x1800949d4  cmp     [rcx+r8*2], r12w
0x1800949d9  jnz     short loc_1800949D1
0x1800949db  lea     rcx, [rbp+310h+pszSrc]
0x1800949df  mov     rdx, rax
0x1800949e2  inc     rdx
0x1800949e5  cmp     [rcx+rdx*2], r12w
0x1800949ea  jnz     short loc_1800949E2
0x1800949ec  lea     r9, [rbp+310h+Buffer]
0x1800949f3  mov     rcx, rax
0x1800949f6  inc     rcx
0x1800949f9  cmp     [r9+rcx*2], r12w
0x1800949fe  jnz     short loc_1800949F6
0x180094a00  lea     r9, [rsp+410h+var_3BC]
0x180094a05  inc     rax
0x180094a08  cmp     [r9+rax*2], r12w
0x180094a0d  jnz     short loc_180094A05
0x180094a0f  add     rax, rcx
0x180094a12  mov     rcx, cs:PfSvcGlobals
0x180094a19  add     rax, rdx
0x180094a1c  xor     edx, edx; dwFlags
0x180094a1e  add     rax, r8
0x180094a21  mov     rcx, [rcx+58h]; hHeap
0x180094a25  lea     rax, ds:42h[rax*2]
0x180094a2d  mov     r8d, eax; dwBytes
0x180094a30  mov     ebx, eax
0x180094a32  call    cs:__imp_HeapAlloc
0x180094a38  mov     r14, rax
0x180094a3b  test    rax, rax
0x180094a3e  jnz     short loc_180094A48
0x180094a40  lea     ebx, [rax+8]
0x180094a43  jmp     loc_180094C30
0x180094a48  lea     r8, asc_1800C2A60; "\""
0x180094a4f  mov     rdx, rbx; cbDest
0x180094a52  mov     rcx, r14; pszDest
0x180094a55  call    StringCbCopyW
0x180094a5a  lea     r8, [rbp+310h+Buffer]; pszSrc
0x180094a61  mov     rdx, rbx; cbDest
0x180094a64  mov     rcx, r14; pszDest
0x180094a67  call    StringCbCatW
0x180094a6c  lea     r8, aDefragExe; "\\defrag.exe\" "
0x180094a73  mov     rdx, rbx; cbDest
0x180094a76  mov     rcx, r14; pszDest
0x180094a79  call    StringCbCatW
0x180094a7e  lea     r8, [rbp+310h+pszDest]; pszSrc
0x180094a82  mov     rdx, rbx; cbDest
0x180094a85  mov     rcx, r14; pszDest
0x180094a88  call    StringCbCatW
0x180094a8d  lea     r8, [rbp+310h+pszSrc]; pszSrc
0x180094a91  mov     rdx, rbx; cbDest
0x180094a94  mov     rcx, r14; pszDest
0x180094a97  call    StringCbCatW
0x180094a9c  lea     r8, aBOnlypreferred; "-b -OnlyPreferred "
0x180094aa3  mov     rdx, rbx; cbDest
0x180094aa6  mov     rcx, r14; pszDest
0x180094aa9  call    StringCbCatW
0x180094aae  lea     r8, [rsp+410h+var_3BC]; pszSrc
0x180094ab3  mov     rdx, rbx; cbDest
0x180094ab6  mov     rcx, r14; pszDest
0x180094ab9  call    StringCbCatW
0x180094abe  mov     ebx, 12Ah
0x180094ac3  mov     r15d, r12d
0x180094ac6  mov     rdi, r12
0x180094ac9  cmp     r15d, 14h
0x180094acd  jnb     loc_180094C1A
0x180094ad3  lea     rax, [rsp+410h+ProcessInformation]
0x180094ad8  xor     r9d, r9d; lpThreadAttributes
0x180094adb  mov     [rsp+410h+lpProcessInformation], rax; lpProcessInformation
0x180094ae0  xor     r8d, r8d; lpProcessAttributes
0x180094ae3  lea     rax, [rbp+310h+StartupInfo]
0x180094ae7  mov     rdx, r14; lpCommandLine
0x180094aea  mov     [rsp+410h+lpStartupInfo], rax; lpStartupInfo
0x180094aef  xor     ecx, ecx; lpApplicationName
0x180094af1  mov     [rsp+410h+lpCurrentDirectory], r12; lpCurrentDirectory
0x180094af6  mov     [rsp+410h+lpEnvironment], r12; lpEnvironment
0x180094afb  mov     [rsp+410h+dwCreationFlags], 8000000h; dwCreationFlags
0x180094b03  mov     [rsp+410h+bInheritHandles], r12d; bInheritHandles
0x180094b08  call    cs:__imp_CreateProcessW
0x180094b0e  test    eax, eax
0x180094b10  jz      loc_180094C12
0x180094b16  mov     rcx, [rsp+410h+ProcessInformation.hThread]; hObject
0x180094b1b  call    cs:__imp_CloseHandle
0x180094b21  mov     rax, cs:PfSvcGlobals
0x180094b28  mov     ebx, 2
0x180094b2d  mov     rdi, [rsp+410h+ProcessInformation.hProcess]
0x180094b32  mov     [rbp+310h+Handles], rdi
0x180094b36  mov     rcx, [rax+370h]
0x180094b3d  mov     [rbp+310h+Handles+8], rcx
0x180094b41  mov     ecx, ebx
0x180094b43  test    r13, r13
0x180094b46  jz      short loc_180094B53
0x180094b48  mov     rax, [r13+48h]
0x180094b4c  lea     ecx, [rbx+1]; nCount
0x180094b4f  mov     [rbp+310h+var_310], rax
0x180094b53  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180094b57  mov     [rsp+410h+bInheritHandles], r12d; bAlertable
0x180094b5c  xor     r8d, r8d; bWaitAll
0x180094b5f  lea     rdx, [rbp+310h+Handles]; lpHandles
0x180094b63  call    cs:__imp_WaitForMultipleObjectsEx
0x180094b69  test    eax, eax
0x180094b6b  jz      short loc_180094BBF
0x180094b6d  sub     eax, 1
0x180094b70  jz      loc_180094C6C
0x180094b76  cmp     eax, 1
0x180094b79  jnz     loc_180094C12
0x180094b7f  mov     rcx, rsi; hEvent
0x180094b82  call    cs:__imp_SetEvent
0x180094b88  mov     rax, cs:PfSvcGlobals
0x180094b8f  lea     rdx, [rbp+310h+Handles]; lpHandles
0x180094b93  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180094b97  mov     [rbp+310h+Handles], rdi
0x180094b9b  xor     r8d, r8d; bWaitAll
0x180094b9e  mov     [rsp+410h+bInheritHandles], r12d; bAlertable
0x180094ba3  mov     rcx, [rax+370h]
0x180094baa  mov     [rbp+310h+Handles+8], rcx
0x180094bae  mov     ecx, ebx; nCount
0x180094bb0  call    cs:__imp_WaitForMultipleObjectsEx
0x180094bb6  test    eax, eax
0x180094bb8  jnz     short loc_180094C0D
0x180094bba  mov     ebx, r12d
0x180094bbd  jmp     short loc_180094BC4
0x180094bbf  mov     ebx, 1
0x180094bc4  lea     rdx, [rsp+410h+ExitCode]; lpExitCode
0x180094bc9  mov     rcx, rdi; hProcess
0x180094bcc  call    cs:__imp_GetExitCodeProcess
0x180094bd2  test    eax, eax
0x180094bd4  jz      short loc_180094C12
0x180094bd6  test    ebx, ebx
0x180094bd8  mov     ebx, [rsp+410h+ExitCode]
0x180094bdc  jz      loc_180094C7C
0x180094be2  cmp     ebx, 4D5h
0x180094be8  jnz     loc_180094C8B
0x180094bee  mov     rcx, rsi; hEvent
0x180094bf1  call    cs:__imp_ResetEvent
0x180094bf7  mov     rcx, rdi; hObject
0x180094bfa  call    cs:__imp_CloseHandle
0x180094c00  inc     r15d
0x180094c03  mov     ebx, 4D3h
0x180094c08  jmp     loc_180094AC6
0x180094c0d  cmp     eax, 1
0x180094c10  jz      short loc_180094C75
0x180094c12  call    cs:__imp_GetLastError
0x180094c18  mov     ebx, eax
0x180094c1a  mov     rcx, cs:PfSvcGlobals
0x180094c21  mov     r8, r14; lpMem
0x180094c24  xor     edx, edx; dwFlags
0x180094c26  mov     rcx, [rcx+58h]; hHeap
0x180094c2a  call    cs:__imp_HeapFree
0x180094c30  mov     rcx, rsi; hObject
0x180094c33  call    cs:__imp_CloseHandle
0x180094c39  test    rdi, rdi
0x180094c3c  jz      short loc_180094C47
0x180094c3e  mov     rcx, rdi; hObject
0x180094c41  call    cs:__imp_CloseHandle
0x180094c47  mov     eax, ebx
0x180094c49  mov     rcx, [rbp+310h+var_50]
0x180094c50  xor     rcx, rsp; StackCookie
0x180094c53  call    __security_check_cookie
0x180094c58  add     rsp, 3D8h
0x180094c5f  pop     r15
0x180094c61  pop     r14
0x180094c63  pop     r13
0x180094c65  pop     r12
0x180094c67  pop     rdi
0x180094c68  pop     rsi
0x180094c69  pop     rbx
0x180094c6a  pop     rbp
0x180094c6b  retn
0x180094c6c  mov     rcx, rsi; hEvent
0x180094c6f  call    cs:__imp_SetEvent
0x180094c75  mov     ebx, 45Bh
0x180094c7a  jmp     short loc_180094C1A
0x180094c7c  cmp     ebx, 4C7h
0x180094c82  jnz     short loc_180094C8B
0x180094c84  mov     ebx, 4D5h
0x180094c89  jmp     short loc_180094C1A
0x180094c8b  mov     ecx, 0C0000000h
0x180094c90  mov     eax, ebx
0x180094c92  and     eax, ecx
0x180094c94  cmp     eax, ecx
0x180094c96  jnz     short loc_180094C1A
0x180094c98  mov     cs:dword_1800D3C28, ebx
0x180094c9e  jmp     loc_180094C1A
```
