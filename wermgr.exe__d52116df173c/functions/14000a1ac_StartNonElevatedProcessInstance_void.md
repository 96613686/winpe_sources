# StartNonElevatedProcessInstance(void)

- ea: `0x14000a1ac`
- end: `0x14000a626`
- name: `?StartNonElevatedProcessInstance@@YAJXZ`
- size: `1146`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000e49c`

## callees

- `0x140002fbc`
- `0x140002fd4`
- `0x140008c40`
- `0x140008c88`
- `0x14000a1ac`
- `0x14000c664`
- `0x14001aaa4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14000a3a3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14000a3a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a3b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a5f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a3b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a5f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a29f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a2b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a312`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a405`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a414`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a43e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a44d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a46b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a47f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a533`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a547`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a29f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a2b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a312`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a405`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a414`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a43e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a44d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a46b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a47f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a533`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a547`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14000a234`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14000a234`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14000a2fe`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14000a42a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14000a457`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14000a51f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14000a2fe`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14000a42a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14000a457`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14000a51f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000a329`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000a329`
- `ext-ms-win-shell-shell32-l1-2-0!ShellExecuteExW` at `0x14000a5e7`
- `ext-ms-win-shell-shell32-l1-2-0!ShellExecuteExW` at `0x14000a5e7`

## string_xrefs

- `0x14000a3d4`: `CreateProcess failed`

## pseudocode

```c
__int64 StartNonElevatedProcessInstance(void)
{
  signed int NonElevationInfo; // ebx
  void *v2; // rdi
  HANDLE hThread; // rsi
  const WCHAR *v4; // rax
  const WCHAR *v5; // r14
  signed int LastError; // eax
  bool v7; // cc
  int v8; // ecx
  signed int v9; // eax
  const char *v10; // rax
  __int64 v11; // rdx
  const WCHAR *lpVerb; // rax
  signed int v13; // eax
  wil::details *dwNumberOfBytesToMap; // [rsp+20h] [rbp-89h]
  wil::details *dwNumberOfBytesToMapa; // [rsp+20h] [rbp-89h]
  wil::details *dwNumberOfBytesToMapb; // [rsp+20h] [rbp-89h]
  const char *lpEnvironment; // [rsp+30h] [rbp-79h]
  const char *lpEnvironmenta; // [rsp+30h] [rbp-79h]
  struct _PROCESS_INFORMATION hFileMappingObject; // [rsp+50h] [rbp-59h] BYREF
  SHELLEXECUTEINFOW StartupInfo; // [rsp+70h] [rbp-39h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+108h] [rbp+5Fh]

  memset(&hFileMappingObject, 0, sizeof(hFileMappingObject));
  NonElevationInfo = UtilGetNonElevationInfo((struct _WERSVC_NON_ELEVATION_INFO *)&hFileMappingObject);
  if ( NonElevationInfo < 0 )
  {
    LODWORD(dwNumberOfBytesToMap) = NonElevationInfo;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x48F,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "StartNonElevatedProcessInstance",
      dwNumberOfBytesToMap,
      (int)"UtilGetNonElevationInfo failed",
      lpEnvironment);
    return (unsigned int)NonElevationInfo;
  }
  v2 = *(void **)&hFileMappingObject.dwProcessId;
  hThread = hFileMappingObject.hThread;
  v4 = (const WCHAR *)MapViewOfFile(hFileMappingObject.hThread, 4u, 0, 0, 0);
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    NonElevationInfo = LastError;
    if ( LastError > 0 )
      NonElevationInfo = (unsigned __int16)LastError | 0x80070000;
    if ( NonElevationInfo >= 0 )
      NonElevationInfo = -2147467259;
    LODWORD(dwNumberOfBytesToMapa) = NonElevationInfo;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x4A7,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "StartNonElevatedProcessInstance",
      dwNumberOfBytesToMapa,
      (int)"MapViewOfFile failed",
      lpEnvironment);
    goto LABEL_10;
  }
  if ( *(_DWORD *)v4 != 1568 )
  {
    LODWORD(dwNumberOfBytesToMapa) = -2147024883;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x4AE,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "StartNonElevatedProcessInstance",
      dwNumberOfBytesToMapa,
      (int)"Invalid size passed in section",
      lpEnvironment);
    UnmapViewOfFile(v5);
    if ( (unsigned __int64)hThread + 1 > 1 )
      CloseHandle(hThread);
    v7 = (unsigned __int64)v2 + 1 <= 1;
LABEL_45:
    if ( !v7 )
      CloseHandle(v2);
    return 2147942413LL;
  }
  SetEvent(v2);
  v8 = *((_DWORD *)v5 + 1);
  if ( v8 )
  {
    if ( (unsigned int)(v8 - 1) <= 1 )
    {
      if ( (unsigned __int8)IsShellExecuteExWPresent() )
      {
        memset_0(&StartupInfo.fMask, 0, 0x6Cu);
        StartupInfo.cbSize = 112;
        if ( *((_DWORD *)v5 + 1) == 1 )
        {
          lpVerb = L"open";
        }
        else
        {
          lpVerb = L"explore";
          if ( *((_DWORD *)v5 + 1) != 2 )
            lpVerb = StartupInfo.lpVerb;
        }
        StartupInfo.lpVerb = lpVerb;
        StartupInfo.lpFile = v5 + 264;
        StartupInfo.nShow = 1;
        if ( ShellExecuteExW(&StartupInfo) )
          goto LABEL_34;
        v13 = GetLastError();
        NonElevationInfo = v13;
        if ( v13 > 0 )
          NonElevationInfo = (unsigned __int16)v13 | 0x80070000;
        if ( NonElevationInfo >= 0 )
          NonElevationInfo = -2147467259;
        v10 = "ShellExecuteEx failed";
        v11 = 1258;
      }
      else
      {
        v10 = "ShellExecuteEx api not present";
        NonElevationInfo = -2147024846;
        v11 = 1235;
      }
      LODWORD(dwNumberOfBytesToMapa) = NonElevationInfo;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
        "StartNonElevatedProcessInstance",
        dwNumberOfBytesToMapa,
        (int)v10,
        lpEnvironment);
LABEL_29:
      UnmapViewOfFile(v5);
LABEL_10:
      if ( (unsigned __int64)hThread + 1 > 1 )
        CloseHandle(hThread);
      if ( (unsigned __int64)v2 + 1 > 1 )
        CloseHandle(v2);
      return (unsigned int)NonElevationInfo;
    }
    if ( v8 != 3 )
    {
      LODWORD(dwNumberOfBytesToMapa) = -2147024883;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x4F6,
        (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
        "StartNonElevatedProcessInstance",
        dwNumberOfBytesToMapa,
        (int)"Invalid launch type passed",
        lpEnvironment);
      UnmapViewOfFile(v5);
      if ( (unsigned __int64)hThread + 1 > 1 )
        CloseHandle(hThread);
      v7 = (unsigned __int64)v2 + 1 <= 1;
      goto LABEL_45;
    }
    LODWORD(dwNumberOfBytesToMapa) = UtilShowHelp(v5 + 264);
    wil::details::in1diag4::Log_IfFailedMsg(
      retaddr,
      (void *)0x4F1,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "StartNonElevatedProcessInstance",
      (const char *)dwNumberOfBytesToMapa,
      (int)"Failed to show the help content %ws",
      (const char *)v5 + 528);
  }
  else
  {
    memset_0(&StartupInfo.fMask, 0, 0x64u);
    StartupInfo.cbSize = 104;
    memset(&hFileMappingObject, 0, sizeof(hFileMappingObject));
    if ( !CreateProcessW(v5 + 4, (LPWSTR)v5 + 264, 0, 0, 0, 0, 0, 0, (LPSTARTUPINFOW)&StartupInfo, &hFileMappingObject) )
    {
      v9 = GetLastError();
      NonElevationInfo = v9;
      if ( v9 > 0 )
        NonElevationInfo = (unsigned __int16)v9 | 0x80070000;
      if ( NonElevationInfo >= 0 )
        NonElevationInfo = -2147467259;
      LODWORD(dwNumberOfBytesToMapb) = NonElevationInfo;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x4C9,
        (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
        "StartNonElevatedProcessInstance",
        dwNumberOfBytesToMapb,
        (int)"CreateProcess failed",
        lpEnvironmenta);
      if ( hFileMappingObject.hProcess )
        CloseHandle(hFileMappingObject.hProcess);
      if ( hFileMappingObject.hThread )
        CloseHandle(hFileMappingObject.hThread);
      memset(&hFileMappingObject, 0, sizeof(hFileMappingObject));
      goto LABEL_29;
    }
    if ( hFileMappingObject.hProcess )
      CloseHandle(hFileMappingObject.hProcess);
    if ( hFileMappingObject.hThread )
      CloseHandle(hFileMappingObject.hThread);
  }
LABEL_34:
  UnmapViewOfFile(v5);
  if ( (unsigned __int64)hThread + 1 > 1 )
    CloseHandle(hThread);
  if ( (unsigned __int64)v2 + 1 > 1 )
    CloseHandle(v2);
  return 0;
}

```

## disassembly

```asm
0x14000a1ac  push    rbp
0x14000a1ae  push    rbx
0x14000a1af  push    rsi
0x14000a1b0  push    rdi
0x14000a1b1  push    r14
0x14000a1b3  lea     rbp, [rsp-37h]
0x14000a1b8  sub     rsp, 0E0h
0x14000a1bf  xorps   xmm0, xmm0
0x14000a1c2  xor     eax, eax
0x14000a1c4  movups  xmmword ptr [rbp+57h+hFileMappingObject], xmm0
0x14000a1c8  mov     [rbp+57h+hObject], rax
0x14000a1cc  lea     rcx, [rbp+57h+hFileMappingObject]; struct _WERSVC_NON_ELEVATION_INFO *
0x14000a1d0  call    ?UtilGetNonElevationInfo@@YAJPEAU_WERSVC_NON_ELEVATION_INFO@@@Z; UtilGetNonElevationInfo(_WERSVC_NON_ELEVATION_INFO *)
0x14000a1d5  mov     ebx, eax
0x14000a1d7  test    eax, eax
0x14000a1d9  jns     short loc_14000A20E
0x14000a1db  mov     rcx, [rbp+5Fh]; this
0x14000a1df  lea     rax, aUtilgetnonelev; "UtilGetNonElevationInfo failed"
0x14000a1e6  mov     qword ptr [rsp+100h+dwCreationFlags], rax; int
0x14000a1eb  mov     dword ptr [rsp+100h+dwNumberOfBytesToMap], ebx; wil::details *
0x14000a1ef  lea     r9, aStartnonelevat_0; "StartNonElevatedProcessInstance"
0x14000a1f6  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x14000a1fd  mov     edx, 48Fh; void *
0x14000a202  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14000a207  mov     eax, ebx
0x14000a209  jmp     loc_14000A487
0x14000a20e  mov     rdi, [rbp+57h+hObject]
0x14000a212  mov     [rbp+57h+arg_0], rdi
0x14000a216  mov     rsi, [rbp+57h+hFileMappingObject+8]
0x14000a21a  mov     [rbp+57h+arg_8], rsi
0x14000a21e  mov     [rsp+100h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x14000a227  xor     r9d, r9d; dwFileOffsetLow
0x14000a22a  xor     r8d, r8d; dwFileOffsetHigh
0x14000a22d  lea     edx, [r9+4]; dwDesiredAccess
0x14000a231  mov     rcx, rsi; hFileMappingObject
0x14000a234  call    cs:__imp_MapViewOfFile
0x14000a23a  mov     r14, rax
0x14000a23d  mov     [rbp+57h+arg_10], rax
0x14000a241  test    rax, rax
0x14000a244  jnz     short loc_14000A2C2
0x14000a246  call    cs:__imp_GetLastError
0x14000a24c  mov     ebx, eax
0x14000a24e  test    eax, eax
0x14000a250  jle     short loc_14000A25B
0x14000a252  movzx   ebx, ax
0x14000a255  or      ebx, 80070000h
0x14000a25b  mov     eax, 80004005h
0x14000a260  test    ebx, ebx
0x14000a262  cmovns  ebx, eax
0x14000a265  mov     rcx, [rbp+5Fh]; this
0x14000a269  lea     rax, aMapviewoffileF; "MapViewOfFile failed"
0x14000a270  mov     qword ptr [rsp+100h+dwCreationFlags], rax; int
0x14000a275  mov     dword ptr [rsp+100h+dwNumberOfBytesToMap], ebx; wil::details *
0x14000a279  lea     r9, aStartnonelevat_0; "StartNonElevatedProcessInstance"
0x14000a280  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x14000a287  mov     edx, 4A7h; void *
0x14000a28c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14000a291  nop
0x14000a292  lea     rax, [rsi+1]
0x14000a296  cmp     rax, 1
0x14000a29a  jbe     short loc_14000A2A6
0x14000a29c  mov     rcx, rsi; hObject
0x14000a29f  call    cs:__imp_CloseHandle
0x14000a2a5  nop
0x14000a2a6  lea     rcx, [rdi+1]
0x14000a2aa  cmp     rcx, 1
0x14000a2ae  jbe     loc_14000A207
0x14000a2b4  mov     rcx, rdi; hObject
0x14000a2b7  call    cs:__imp_CloseHandle
0x14000a2bd  jmp     loc_14000A207
0x14000a2c2  cmp     dword ptr [rax], 620h
0x14000a2c8  jz      short loc_14000A326
0x14000a2ca  mov     rcx, [rbp+5Fh]; this
0x14000a2ce  lea     rax, aInvalidSizePas; "Invalid size passed in section"
0x14000a2d5  mov     qword ptr [rsp+100h+dwCreationFlags], rax; int
0x14000a2da  mov     dword ptr [rsp+100h+dwNumberOfBytesToMap], 8007000Dh; wil::details *
0x14000a2e2  lea     r9, aStartnonelevat_0; "StartNonElevatedProcessInstance"
0x14000a2e9  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x14000a2f0  mov     edx, 4AEh; void *
0x14000a2f5  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14000a2fa  nop
0x14000a2fb  mov     rcx, r14; lpBaseAddress
0x14000a2fe  call    cs:__imp_UnmapViewOfFile
0x14000a304  nop
0x14000a305  lea     rax, [rsi+1]
0x14000a309  cmp     rax, 1
0x14000a30d  jbe     short loc_14000A319
0x14000a30f  mov     rcx, rsi; hObject
0x14000a312  call    cs:__imp_CloseHandle
0x14000a318  nop
0x14000a319  lea     rax, [rdi+1]
0x14000a31d  cmp     rax, 1
0x14000a321  jmp     loc_14000A542
0x14000a326  mov     rcx, rdi; hEvent
0x14000a329  call    cs:__imp_SetEvent
0x14000a32f  mov     ecx, [r14+4]
0x14000a333  test    ecx, ecx
0x14000a335  jnz     loc_14000A495
0x14000a33b  xor     edx, edx; Val
0x14000a33d  lea     r8d, [rcx+64h]; Size
0x14000a341  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x14000a345  call    memset_0
0x14000a34a  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x14000a351  xorps   xmm0, xmm0
0x14000a354  xor     eax, eax
0x14000a356  movups  xmmword ptr [rbp+57h+hFileMappingObject], xmm0
0x14000a35a  mov     [rbp+57h+hObject], rax
0x14000a35e  lea     rdx, [r14+210h]; lpCommandLine
0x14000a365  lea     rcx, [r14+8]; lpApplicationName
0x14000a369  lea     rax, [rbp+57h+hFileMappingObject]
0x14000a36d  mov     [rsp+100h+lpProcessInformation], rax; lpProcessInformation
0x14000a372  lea     rax, [rbp+57h+StartupInfo]
0x14000a376  mov     [rsp+100h+lpStartupInfo], rax; lpStartupInfo
0x14000a37b  mov     [rsp+100h+lpCurrentDirectory], 0; lpCurrentDirectory
0x14000a384  mov     [rsp+100h+lpEnvironment], 0; char *
0x14000a38d  mov     [rsp+100h+dwCreationFlags], 0; dwCreationFlags
0x14000a395  mov     dword ptr [rsp+100h+dwNumberOfBytesToMap], 0; bInheritHandles
0x14000a39d  xor     r9d, r9d; lpThreadAttributes
0x14000a3a0  xor     r8d, r8d; lpProcessAttributes
0x14000a3a3  call    cs:__imp_CreateProcessW
0x14000a3a9  test    eax, eax
0x14000a3ab  jnz     loc_14000A435
0x14000a3b1  call    cs:__imp_GetLastError
0x14000a3b7  mov     ebx, eax
0x14000a3b9  test    eax, eax
0x14000a3bb  jle     short loc_14000A3C6
0x14000a3bd  movzx   ebx, ax
0x14000a3c0  or      ebx, 80070000h
0x14000a3c6  mov     eax, 80004005h
0x14000a3cb  test    ebx, ebx
0x14000a3cd  cmovns  ebx, eax
0x14000a3d0  mov     rcx, [rbp+5Fh]; this
0x14000a3d4  lea     rax, aCreateprocessF; "CreateProcess failed"
0x14000a3db  mov     qword ptr [rsp+100h+dwCreationFlags], rax; int
0x14000a3e0  mov     dword ptr [rsp+100h+dwNumberOfBytesToMap], ebx; wil::details *
0x14000a3e4  lea     r9, aStartnonelevat_0; "StartNonElevatedProcessInstance"
0x14000a3eb  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x14000a3f2  mov     edx, 4C9h; void *
0x14000a3f7  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14000a3fc  mov     rcx, [rbp+57h+hFileMappingObject]; hObject
0x14000a400  test    rcx, rcx
0x14000a403  jz      short loc_14000A40B
0x14000a405  call    cs:__imp_CloseHandle
0x14000a40b  mov     rcx, [rbp+57h+hFileMappingObject+8]; hObject
0x14000a40f  test    rcx, rcx
0x14000a412  jz      short loc_14000A41A
0x14000a414  call    cs:__imp_CloseHandle
0x14000a41a  xorps   xmm0, xmm0
0x14000a41d  xor     eax, eax
0x14000a41f  movups  xmmword ptr [rbp+57h+hFileMappingObject], xmm0
0x14000a423  mov     [rbp+57h+hObject], rax
0x14000a427  mov     rcx, r14; lpBaseAddress
0x14000a42a  call    cs:__imp_UnmapViewOfFile
0x14000a430  jmp     loc_14000A292
0x14000a435  mov     rcx, [rbp+57h+hFileMappingObject]; hObject
0x14000a439  test    rcx, rcx
0x14000a43c  jz      short loc_14000A444
0x14000a43e  call    cs:__imp_CloseHandle
0x14000a444  mov     rcx, [rbp+57h+hFileMappingObject+8]; hObject
0x14000a448  test    rcx, rcx
0x14000a44b  jz      short loc_14000A454
0x14000a44d  call    cs:__imp_CloseHandle
0x14000a453  nop
0x14000a454  mov     rcx, r14; lpBaseAddress
0x14000a457  call    cs:__imp_UnmapViewOfFile
0x14000a45d  nop
0x14000a45e  lea     rax, [rsi+1]
0x14000a462  cmp     rax, 1
0x14000a466  jbe     short loc_14000A472
0x14000a468  mov     rcx, rsi; hObject
0x14000a46b  call    cs:__imp_CloseHandle
0x14000a471  nop
0x14000a472  lea     rax, [rdi+1]
0x14000a476  cmp     rax, 1
0x14000a47a  jbe     short loc_14000A485
0x14000a47c  mov     rcx, rdi; hObject
0x14000a47f  call    cs:__imp_CloseHandle
0x14000a485  xor     eax, eax
0x14000a487  add     rsp, 0E0h
0x14000a48e  pop     r14
0x14000a490  pop     rdi
0x14000a491  pop     rsi
0x14000a492  pop     rbx
0x14000a493  pop     rbp
0x14000a494  retn
0x14000a495  lea     eax, [rcx-1]
0x14000a498  cmp     eax, 1
0x14000a49b  jbe     loc_14000A557
0x14000a4a1  cmp     ecx, 3
0x14000a4a4  jnz     short loc_14000A4EB
0x14000a4a6  lea     rbx, [r14+210h]
0x14000a4ad  mov     rcx, rbx; psz
0x14000a4b0  call    ?UtilShowHelp@@YAJPEB_W@Z; UtilShowHelp(wchar_t const *)
0x14000a4b5  mov     rcx, [rbp+5Fh]; this
0x14000a4b9  mov     [rsp+100h+lpEnvironment], rbx; char *
0x14000a4be  lea     rdx, aFailedToShowTh; "Failed to show the help content %ws"
0x14000a4c5  mov     qword ptr [rsp+100h+dwCreationFlags], rdx; int
0x14000a4ca  mov     dword ptr [rsp+100h+dwNumberOfBytesToMap], eax; char *
0x14000a4ce  lea     r9, aStartnonelevat_0; "StartNonElevatedProcessInstance"
0x14000a4d5  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x14000a4dc  mov     edx, 4F1h; void *
0x14000a4e1  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14000a4e6  jmp     loc_14000A454
0x14000a4eb  mov     rcx, [rbp+5Fh]; this
0x14000a4ef  lea     rax, aInvalidLaunchT; "Invalid launch type passed"
0x14000a4f6  mov     qword ptr [rsp+100h+dwCreationFlags], rax; int
0x14000a4fb  mov     dword ptr [rsp+100h+dwNumberOfBytesToMap], 8007000Dh; wil::details *
0x14000a503  lea     r9, aStartnonelevat_0; "StartNonElevatedProcessInstance"
0x14000a50a  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x14000a511  mov     edx, 4F6h; void *
0x14000a516  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14000a51b  nop
0x14000a51c  mov     rcx, r14; lpBaseAddress
0x14000a51f  call    cs:__imp_UnmapViewOfFile
0x14000a525  nop
0x14000a526  lea     rax, [rsi+1]
0x14000a52a  cmp     rax, 1
0x14000a52e  jbe     short loc_14000A53A
0x14000a530  mov     rcx, rsi; hObject
0x14000a533  call    cs:__imp_CloseHandle
0x14000a539  nop
0x14000a53a  lea     rcx, [rdi+1]
0x14000a53e  cmp     rcx, 1
0x14000a542  jbe     short loc_14000A54D
0x14000a544  mov     rcx, rdi; hObject
0x14000a547  call    cs:__imp_CloseHandle
0x14000a54d  mov     eax, 8007000Dh
0x14000a552  jmp     loc_14000A487
0x14000a557  call    IsShellExecuteExWPresent
0x14000a55c  test    al, al
0x14000a55e  jnz     short loc_14000A596
0x14000a560  lea     rax, aShellexecuteex_1; "ShellExecuteEx api not present"
0x14000a567  mov     ebx, 80070032h
0x14000a56c  mov     edx, 4D3h; void *
0x14000a571  mov     qword ptr [rsp+100h+dwCreationFlags], rax; int
0x14000a576  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x14000a57d  lea     r9, aStartnonelevat_0; "StartNonElevatedProcessInstance"
0x14000a584  mov     dword ptr [rsp+100h+dwNumberOfBytesToMap], ebx; wil::details *
0x14000a588  mov     rcx, [rbp+5Fh]; this
0x14000a58c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14000a591  jmp     loc_14000A427
0x14000a596  xor     edx, edx; Val
0x14000a598  lea     r8d, [rdx+6Ch]; Size
0x14000a59c  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x14000a5a0  call    memset_0
0x14000a5a5  mov     [rbp+57h+StartupInfo.cb], 70h ; 'p'
0x14000a5ac  cmp     dword ptr [r14+4], 1
0x14000a5b1  jnz     short loc_14000A5BC
0x14000a5b3  lea     rax, aOpen; "open"
0x14000a5ba  jmp     short loc_14000A5CD
0x14000a5bc  lea     rax, aExplore; "explore"
0x14000a5c3  cmp     dword ptr [r14+4], 2
0x14000a5c8  cmovnz  rax, [rbp+57h+StartupInfo.lpDesktop]
0x14000a5cd  mov     [rbp+57h+StartupInfo.lpDesktop], rax
0x14000a5d1  lea     rax, [r14+210h]
0x14000a5d8  mov     [rbp+57h+StartupInfo.lpTitle], rax
0x14000a5dc  mov     [rbp+57h+StartupInfo.dwXCountChars], 1
0x14000a5e3  lea     rcx, [rbp+57h+StartupInfo]; pExecInfo
0x14000a5e7  call    cs:__imp_ShellExecuteExW
0x14000a5ed  test    eax, eax
0x14000a5ef  jnz     loc_14000A454
0x14000a5f5  call    cs:__imp_GetLastError
0x14000a5fb  mov     ebx, eax
0x14000a5fd  test    eax, eax
0x14000a5ff  jle     short loc_14000A60A
0x14000a601  movzx   ebx, ax
0x14000a604  or      ebx, 80070000h
0x14000a60a  mov     eax, 80004005h
0x14000a60f  test    ebx, ebx
0x14000a611  cmovns  ebx, eax
0x14000a614  lea     rax, aShellexecuteex_0; "ShellExecuteEx failed"
0x14000a61b  mov     edx, 4EAh
0x14000a620  jmp     loc_14000A571
```
