# KeepProcessAliveInWcow(void *)

- ea: `0x10043f1c0`
- end: `0x10043f699`
- name: `?KeepProcessAliveInWcow@@YAPEAXPEAX@Z`
- size: `1241`
- prototype: `void *__fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x100401580`
- `0x100404a30`
- `0x1004095e0`
- `0x10043f1c0`
- `0x1004404f0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x10043f3ef`
- `KERNEL32!WaitForSingleObject` at `0x10043f3ef`
- `KERNEL32!CreateProcessW` at `0x10043f347`
- `KERNEL32!CreateProcessW` at `0x10043f347`
- `KERNEL32!GetExitCodeProcess` at `0x10043f3fd`
- `KERNEL32!GetExitCodeProcess` at `0x10043f3fd`
- `KERNEL32!CloseHandle` at `0x10043f4f0`
- `KERNEL32!CloseHandle` at `0x10043f4f0`
- `KERNEL32!GetLastError` at `0x10043f4fb`
- `KERNEL32!GetLastError` at `0x10043f4fb`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043f635`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043f644`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043f653`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043f661`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043f635`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043f644`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043f653`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043f661`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x10043f21f`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x10043f626`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x10043f21f`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x10043f626`
- `hostregdll!HostReg_ReportApplicationHealth` at `0x10043f2ea`
- `hostregdll!HostReg_ReportApplicationHealth` at `0x10043f3bc`
- `hostregdll!HostReg_ReportApplicationHealth` at `0x10043f4c7`
- `hostregdll!HostReg_ReportApplicationHealth` at `0x10043f598`
- `hostregdll!HostReg_ReportApplicationHealth` at `0x10043f2ea`
- `hostregdll!HostReg_ReportApplicationHealth` at `0x10043f3bc`
- `hostregdll!HostReg_ReportApplicationHealth` at `0x10043f4c7`
- `hostregdll!HostReg_ReportApplicationHealth` at `0x10043f598`
- `hostregdll!HostReg_GetNodeName` at `0x10043f2a0`
- `hostregdll!HostReg_GetNodeName` at `0x10043f375`
- `hostregdll!HostReg_GetNodeName` at `0x10043f480`
- `hostregdll!HostReg_GetNodeName` at `0x10043f551`
- `hostregdll!HostReg_GetNodeName` at `0x10043f2a0`
- `hostregdll!HostReg_GetNodeName` at `0x10043f375`
- `hostregdll!HostReg_GetNodeName` at `0x10043f480`
- `hostregdll!HostReg_GetNodeName` at `0x10043f551`
- `hostregdll!HostReg_GetApplicationName` at `0x10043f2af`
- `hostregdll!HostReg_GetApplicationName` at `0x10043f383`
- `hostregdll!HostReg_GetApplicationName` at `0x10043f48e`
- `hostregdll!HostReg_GetApplicationName` at `0x10043f55f`
- `hostregdll!HostReg_GetApplicationName` at `0x10043f2af`
- `hostregdll!HostReg_GetApplicationName` at `0x10043f383`
- `hostregdll!HostReg_GetApplicationName` at `0x10043f48e`
- `hostregdll!HostReg_GetApplicationName` at `0x10043f55f`

## string_xrefs

- `0x10043f26f`: `[%hs] INFO: %s process to be created.\n`
- `0x10043f5f0`: `[%hs] ERROR: process %s PID %lu exited with code 0x%08X (already exists).\n`
- `0x10043f355`: `The child process was created successfully.`
- `0x10043f27b`: `Initiating CreateProcess.`
- `0x10043f5fe`: `[%hs] ERROR: %s process failed to be created with CreateProcess last error 0x%08X.\n`
- `0x10043f531`: `%s process failed to be created with error 0x%08X.`
- `0x10043f51d`: `[%hs] INFO: %s process failed to be created with CreateProcess last error 0x%08X .\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall KeepProcessAliveInWcow(char *a1)
{
  int NodeName; // eax
  _QWORD *v3; // rbx
  __int64 v4; // rdi
  int ApplicationName; // eax
  __int64 v6; // rdi
  HANDLE hThread; // r14
  BOOL ExitCodeProcess; // eax
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // rdi
  DWORD LastError; // eax
  DWORD v13; // edi
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // rdi
  BOOL bInheritHandles[2]; // [rsp+28h] [rbp-E0h]
  DWORD dwCreationFlags[2]; // [rsp+30h] [rbp-D8h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-B0h] BYREF
  _BOOL8 v21; // [rsp+70h] [rbp-98h]
  __int64 v22; // [rsp+78h] [rbp-90h] BYREF
  __int64 v23; // [rsp+80h] [rbp-88h] BYREF
  __int64 v24; // [rsp+88h] [rbp-80h] BYREF
  __int64 v25; // [rsp+90h] [rbp-78h] BYREF
  __int64 v26; // [rsp+98h] [rbp-70h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v28; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-58h] BYREF
  int v30; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v31; // [rsp+C0h] [rbp-48h]
  __int64 v32; // [rsp+C8h] [rbp-40h]
  __int64 v33; // [rsp+D0h] [rbp-38h]
  __int64 v34; // [rsp+D8h] [rbp-30h]
  __int64 v35; // [rsp+E0h] [rbp-28h]
  char *v36; // [rsp+E8h] [rbp-20h]
  struct _STARTUPINFOW StartupInfo; // [rsp+F8h] [rbp-10h] BYREF
  wchar_t Buffer[504]; // [rsp+168h] [rbp+60h] BYREF

  v35 = -2;
  if ( !a1 )
  {
    log_unlocalized(L"[%hs] ERROR: Failed to init cmdline parameters.", "KeepProcessAliveInWcow");
    SOS_OS::KillProcess(0x3FBu);
  }
  v36 = a1;
  while ( 1 )
  {
    memset(&StartupInfo.cb + 1, 0, 100);
    *(_OWORD *)&ProcessInformation.hThread = 0;
    v21 = 0;
    StartupInfo.cb = 104;
    log_unlocalized(L"[%hs] INFO: %s process to be created.\n", "KeepProcessAliveInWcow", *((_QWORD *)a1 + 1));
    NodeName = StringCchPrintfW(Buffer, 0x1F5u, L"Initiating CreateProcess.");
    v3 = a1 + 16;
    if ( NodeName < 0
      || (v4 = *v3, NodeName = HostReg_GetNodeName(&v22), NodeName < 0)
      || (NodeName = HostReg_GetApplicationName(&v23), NodeName < 0)
      || (NodeName = HostReg_ReportApplicationHealth(v23, 0, v22, Buffer, 1, L"ProcessInWcowHealth", 0, 0, v4, 0),
          NodeName < 0) )
    {
      _mm_lfence();
      log_unlocalized(
        L"[%hs] ERROR: Unable to report health for process %s. (HRESULT 0x%x)\n",
        "KeepProcessAliveInWcow",
        *v3,
        (unsigned int)NodeName);
    }
    if ( !CreateProcessW(
            *(LPCWSTR *)a1,
            *((LPWSTR *)a1 + 1),
            0,
            0,
            0,
            0x9010000u,
            0,
            0,
            &StartupInfo,
            (LPPROCESS_INFORMATION)&ProcessInformation.hThread) )
      break;
    ApplicationName = StringCchPrintfW(Buffer, 0x1F5u, L"The child process was created successfully.");
    if ( ApplicationName < 0
      || (v6 = *v3, ApplicationName = HostReg_GetNodeName(&v24), ApplicationName < 0)
      || (ApplicationName = HostReg_GetApplicationName(&v25), ApplicationName < 0)
      || (ApplicationName = HostReg_ReportApplicationHealth(v25, 0, v24, Buffer, 1, L"ProcessInWcowHealth", 0, 0, v6, 0),
          ApplicationName < 0) )
    {
      _mm_lfence();
      log_unlocalized(
        L"[%hs] ERROR: Unable to report health for process %s. (HRESULT 0x%x)\n",
        "KeepProcessAliveInWcow",
        *v3,
        (unsigned int)ApplicationName);
    }
    hThread = ProcessInformation.hThread;
    WaitForSingleObject(ProcessInformation.hThread, 0xFFFFFFFF);
    ExitCodeProcess = GetExitCodeProcess(hThread, (LPDWORD)&ProcessInformation);
    v9 = *((_QWORD *)a1 + 1);
    if ( ExitCodeProcess )
    {
      if ( LODWORD(ProcessInformation.hProcess) == 183 )
      {
        bInheritHandles[0] = 183;
        log_unlocalized(
          L"[%hs] ERROR: process %s PID %lu exited with code 0x%08X (already exists).\n",
          "KeepProcessAliveInWcow",
          v9,
          v21,
          *(_QWORD *)bInheritHandles);
        goto LABEL_35;
      }
      bInheritHandles[0] = (BOOL)ProcessInformation.hProcess;
      log_unlocalized(
        L"[%hs] INFO: process %s PID %lu exited with code 0x%08X.\n",
        "KeepProcessAliveInWcow",
        v9,
        v21,
        *(_QWORD *)bInheritHandles);
    }
    else
    {
      log_unlocalized(L"[%hs] INFO: process %s PID %lu exited.\n", "KeepProcessAliveInWcow", v9, v21);
    }
    if ( LODWORD(ProcessInformation.hProcess) )
    {
      dwCreationFlags[0] = (DWORD)ProcessInformation.hProcess;
      bInheritHandles[0] = v21;
      v10 = StringCchPrintfW(
              Buffer,
              0x1F5u,
              L"Process %s PID %lu exited with code 0x%08X.",
              *((_QWORD *)a1 + 1),
              *(_QWORD *)bInheritHandles,
              *(_QWORD *)dwCreationFlags);
      if ( v10 < 0
        || (v11 = *v3, v10 = HostReg_GetNodeName(&v26), v10 < 0)
        || (v10 = HostReg_GetApplicationName(&v27), v10 < 0)
        || (v10 = HostReg_ReportApplicationHealth(v27, 0, v26, Buffer, 3, L"ProcessInWcowHealth", 0, 0, v11, 0), v10 < 0) )
      {
        _mm_lfence();
        log_unlocalized(
          L"[%hs] ERROR: Unable to report health for process %s. (HRESULT 0x%x)\n",
          "KeepProcessAliveInWcow",
          *v3,
          (unsigned int)v10);
      }
    }
    CloseHandle(hThread);
LABEL_32:
    v30 = 4194400;
    v31 = 0;
    v33 = 0;
    v32 = 0;
    v34 = 0;
    SOS_Task::Sleep(0xEA60u, (const struct SOS_WaitInfo *)&v30);
  }
  LastError = GetLastError();
  v13 = LastError;
  v14 = *((_QWORD *)a1 + 1);
  if ( LastError - 2 > 1 )
  {
    log_unlocalized(
      L"[%hs] INFO: %s process failed to be created with CreateProcess last error 0x%08X .\n",
      "KeepProcessAliveInWcow",
      v14,
      LastError);
    bInheritHandles[0] = v13;
    v15 = StringCchPrintfW(
            Buffer,
            0x1F5u,
            L"%s process failed to be created with error 0x%08X.",
            *((_QWORD *)a1 + 1),
            *(_QWORD *)bInheritHandles);
    if ( v15 < 0
      || (v16 = *v3, v15 = HostReg_GetNodeName(&v28), v15 < 0)
      || (v15 = HostReg_GetApplicationName(&v29), v15 < 0)
      || (v15 = HostReg_ReportApplicationHealth(v29, 0, v28, Buffer, 3, L"ProcessInWcowHealth", 0, 0, v16, 0), v15 < 0) )
    {
      _mm_lfence();
      log_unlocalized(
        L"[%hs] ERROR: Unable to report health for process %s. (HRESULT 0x%x)\n",
        "KeepProcessAliveInWcow",
        *v3,
        (unsigned int)v15);
    }
    goto LABEL_32;
  }
  log_unlocalized(
    L"[%hs] ERROR: %s process failed to be created with CreateProcess last error 0x%08X.\n",
    "KeepProcessAliveInWcow",
    v14,
    LastError);
LABEL_35:
  log_unlocalized(L"[%hs] ERROR: Failed to keep %s process alive.", "KeepProcessAliveInWcow", *((_QWORD *)a1 + 2));
  SOS_OS::KillProcess(0x3FBu);
  operator delete(*(void **)a1, 2u);
  operator delete(*((void **)a1 + 1), 2u);
  operator delete(*((void **)a1 + 2), 2u);
  operator delete(a1, 0x18u);
  return 0;
}

```

## disassembly

```asm
0x10043f1c0  mov     rax, rsp
0x10043f1c3  push    rbp
0x10043f1c4  push    r14
0x10043f1c6  push    r15
0x10043f1c8  lea     rbp, [rax-478h]
0x10043f1cf  sub     rsp, 560h
0x10043f1d6  mov     [rbp+470h+var_498], 0FFFFFFFFFFFFFFFEh
0x10043f1de  mov     [rax+8], rbx
0x10043f1e2  mov     [rax+10h], rsi
0x10043f1e6  mov     [rax+18h], rdi
0x10043f1ea  mov     [rax+20h], r12
0x10043f1ee  mov     rax, cs:__security_cookie
0x10043f1f5  xor     rax, rsp
0x10043f1f8  mov     [rbp+470h+var_20], rax
0x10043f1ff  mov     rsi, rcx
0x10043f202  test    rcx, rcx
0x10043f205  jnz     short loc_10043F225
0x10043f207  lea     rdx, aKeepprocessali; "KeepProcessAliveInWcow"
0x10043f20e  lea     rcx, aHsErrorFailedT_6; "[%hs] ERROR: Failed to init cmdline par"...
0x10043f215  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f21a  mov     ecx, 3FBh
0x10043f21f  call    cs:__imp_?KillProcess@SOS_OS@@SAXK@Z; SOS_OS::KillProcess(ulong)
0x10043f225  mov     [rbp+470h+var_490], rsi
0x10043f229  xor     r15d, r15d
0x10043f22c  lea     r12, aProcessinwcowh; "ProcessInWcowHealth"
0x10043f233  xorps   xmm0, xmm0
0x10043f236  xor     eax, eax
0x10043f238  movups  xmmword ptr [rbp+470h+StartupInfo+4], xmm0
0x10043f23c  movups  xmmword ptr [rbp+470h+StartupInfo.lpDesktop+4], xmm0
0x10043f240  movups  xmmword ptr [rbp+470h+StartupInfo.dwY], xmm0
0x10043f244  movups  xmmword ptr [rbp+470h+StartupInfo.dwYCountChars], xmm0
0x10043f248  movups  xmmword ptr [rbp+470h+StartupInfo+44h], xmm0
0x10043f24c  movups  xmmword ptr [rbp+470h+StartupInfo.hStdInput+4], xmm0
0x10043f250  mov     dword ptr [rbp+470h+StartupInfo.hStdError+4], eax
0x10043f253  movups  xmmword ptr [rsp+570h+ProcessInformation.hThread], xmm0
0x10043f258  mov     [rsp+570h+var_508], rax
0x10043f25d  mov     [rbp+470h+StartupInfo.cb], 68h ; 'h'
0x10043f264  mov     r8, [rsi+8]
0x10043f268  lea     rdx, aKeepprocessali; "KeepProcessAliveInWcow"
0x10043f26f  lea     rcx, aHsInfoSProcess; "[%hs] INFO: %s process to be created.\n"
0x10043f276  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f27b  lea     r8, aInitiatingCrea; "Initiating CreateProcess."
0x10043f282  mov     edx, 1F5h; unsigned __int64
0x10043f287  lea     rcx, [rbp+470h+Buffer]; Buffer
0x10043f28b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10043f290  lea     rbx, [rsi+10h]
0x10043f294  test    eax, eax
0x10043f296  js      short loc_10043F2F4
0x10043f298  mov     rdi, [rbx]
0x10043f29b  lea     rcx, [rsp+570h+var_500]
0x10043f2a0  call    cs:__imp_HostReg_GetNodeName
0x10043f2a6  test    eax, eax
0x10043f2a8  js      short loc_10043F2F4
0x10043f2aa  lea     rcx, [rsp+570h+var_4F8]
0x10043f2af  call    cs:__imp_HostReg_GetApplicationName
0x10043f2b5  test    eax, eax
0x10043f2b7  js      short loc_10043F2F4
0x10043f2b9  mov     dword ptr [rsp+570h+lpProcessInformation], r15d
0x10043f2be  mov     [rsp+570h+lpStartupInfo], rdi
0x10043f2c3  mov     [rsp+570h+lpCurrentDirectory], r15
0x10043f2c8  mov     dword ptr [rsp+570h+lpEnvironment], r15d
0x10043f2cd  mov     qword ptr [rsp+570h+dwCreationFlags], r12
0x10043f2d2  mov     [rsp+570h+bInheritHandles], 1
0x10043f2da  lea     r9, [rbp+470h+Buffer]
0x10043f2de  mov     r8, [rsp+570h+var_500]
0x10043f2e3  xor     edx, edx
0x10043f2e5  mov     rcx, [rsp+570h+var_4F8]
0x10043f2ea  call    cs:__imp_HostReg_ReportApplicationHealth
0x10043f2f0  test    eax, eax
0x10043f2f2  jns     short loc_10043F310
0x10043f2f4  lfence
0x10043f2f7  mov     r9d, eax
0x10043f2fa  mov     r8, [rbx]
0x10043f2fd  lea     rdx, aKeepprocessali; "KeepProcessAliveInWcow"
0x10043f304  lea     rcx, aHsErrorUnableT; "[%hs] ERROR: Unable to report health fo"...
0x10043f30b  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f310  lea     rax, [rsp+570h+ProcessInformation.hThread]
0x10043f315  mov     [rsp+570h+lpProcessInformation], rax; lpProcessInformation
0x10043f31a  lea     rax, [rbp+470h+StartupInfo]
0x10043f31e  mov     [rsp+570h+lpStartupInfo], rax; lpStartupInfo
0x10043f323  mov     [rsp+570h+lpCurrentDirectory], r15; lpCurrentDirectory
0x10043f328  mov     [rsp+570h+lpEnvironment], r15; lpEnvironment
0x10043f32d  mov     [rsp+570h+dwCreationFlags], 9010000h; dwCreationFlags
0x10043f335  mov     [rsp+570h+bInheritHandles], r15d; bInheritHandles
0x10043f33a  xor     r9d, r9d; lpThreadAttributes
0x10043f33d  xor     r8d, r8d; lpProcessAttributes
0x10043f340  mov     rdx, [rsi+8]; lpCommandLine
0x10043f344  mov     rcx, [rsi]; lpApplicationName
0x10043f347  call    cs:__imp_CreateProcessW
0x10043f34d  test    eax, eax
0x10043f34f  jz      loc_10043F4FB
0x10043f355  lea     r8, aTheChildProces; "The child process was created successfu"...
0x10043f35c  mov     edx, 1F5h; unsigned __int64
0x10043f361  lea     rcx, [rbp+470h+Buffer]; Buffer
0x10043f365  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10043f36a  test    eax, eax
0x10043f36c  js      short loc_10043F3C6
0x10043f36e  mov     rdi, [rbx]
0x10043f371  lea     rcx, [rbp+470h+var_4F0]
0x10043f375  call    cs:__imp_HostReg_GetNodeName
0x10043f37b  test    eax, eax
0x10043f37d  js      short loc_10043F3C6
0x10043f37f  lea     rcx, [rbp+470h+var_4E8]
0x10043f383  call    cs:__imp_HostReg_GetApplicationName
0x10043f389  test    eax, eax
0x10043f38b  js      short loc_10043F3C6
0x10043f38d  mov     dword ptr [rsp+570h+lpProcessInformation], r15d
0x10043f392  mov     [rsp+570h+lpStartupInfo], rdi
0x10043f397  mov     [rsp+570h+lpCurrentDirectory], r15
0x10043f39c  mov     dword ptr [rsp+570h+lpEnvironment], r15d
0x10043f3a1  mov     qword ptr [rsp+570h+dwCreationFlags], r12
0x10043f3a6  mov     [rsp+570h+bInheritHandles], 1
0x10043f3ae  lea     r9, [rbp+470h+Buffer]
0x10043f3b2  mov     r8, [rbp+470h+var_4F0]
0x10043f3b6  xor     edx, edx
0x10043f3b8  mov     rcx, [rbp+470h+var_4E8]
0x10043f3bc  call    cs:__imp_HostReg_ReportApplicationHealth
0x10043f3c2  test    eax, eax
0x10043f3c4  jns     short loc_10043F3E2
0x10043f3c6  lfence
0x10043f3c9  mov     r9d, eax
0x10043f3cc  mov     r8, [rbx]
0x10043f3cf  lea     rdx, aKeepprocessali; "KeepProcessAliveInWcow"
0x10043f3d6  lea     rcx, aHsErrorUnableT; "[%hs] ERROR: Unable to report health fo"...
0x10043f3dd  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f3e2  mov     r14, [rsp+570h+ProcessInformation.hThread]
0x10043f3e7  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x10043f3ec  mov     rcx, r14; hHandle
0x10043f3ef  call    cs:__imp_WaitForSingleObject
0x10043f3f5  lea     rdx, [rsp+570h+ProcessInformation]; lpExitCode
0x10043f3fa  mov     rcx, r14; hProcess
0x10043f3fd  call    cs:__imp_GetExitCodeProcess
0x10043f403  mov     r9d, dword ptr [rsp+570h+var_508]
0x10043f408  mov     r8, [rsi+8]
0x10043f40c  lea     rdx, aKeepprocessali; "KeepProcessAliveInWcow"
0x10043f413  test    eax, eax
0x10043f415  jz      short loc_10043F438
0x10043f417  mov     eax, dword ptr [rsp+570h+ProcessInformation.hProcess]
0x10043f41b  cmp     eax, 0B7h
0x10043f420  jz      loc_10043F5E8
0x10043f426  mov     [rsp+570h+bInheritHandles], eax
0x10043f42a  lea     rcx, aHsInfoProcessS; "[%hs] INFO: process %s PID %lu exited w"...
0x10043f431  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f436  jmp     short loc_10043F444
0x10043f438  lea     rcx, aHsInfoProcessS_0; "[%hs] INFO: process %s PID %lu exited."...
0x10043f43f  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f444  mov     eax, dword ptr [rsp+570h+ProcessInformation.hProcess]
0x10043f448  test    eax, eax
0x10043f44a  jz      loc_10043F4ED
0x10043f450  mov     [rsp+570h+dwCreationFlags], eax
0x10043f454  mov     eax, dword ptr [rsp+570h+var_508]
0x10043f458  mov     [rsp+570h+bInheritHandles], eax
0x10043f45c  mov     r9, [rsi+8]
0x10043f460  lea     r8, aProcessSPidLuE; "Process %s PID %lu exited with code 0x%"...
0x10043f467  mov     edx, 1F5h; unsigned __int64
0x10043f46c  lea     rcx, [rbp+470h+Buffer]; Buffer
0x10043f470  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10043f475  test    eax, eax
0x10043f477  js      short loc_10043F4D1
0x10043f479  mov     rdi, [rbx]
0x10043f47c  lea     rcx, [rbp+470h+var_4E0]
0x10043f480  call    cs:__imp_HostReg_GetNodeName
0x10043f486  test    eax, eax
0x10043f488  js      short loc_10043F4D1
0x10043f48a  lea     rcx, [rbp+470h+var_4D8]
0x10043f48e  call    cs:__imp_HostReg_GetApplicationName
0x10043f494  test    eax, eax
0x10043f496  js      short loc_10043F4D1
0x10043f498  mov     dword ptr [rsp+570h+lpProcessInformation], r15d
0x10043f49d  mov     [rsp+570h+lpStartupInfo], rdi
0x10043f4a2  mov     [rsp+570h+lpCurrentDirectory], r15
0x10043f4a7  mov     dword ptr [rsp+570h+lpEnvironment], r15d
0x10043f4ac  mov     qword ptr [rsp+570h+dwCreationFlags], r12
0x10043f4b1  mov     [rsp+570h+bInheritHandles], 3
0x10043f4b9  lea     r9, [rbp+470h+Buffer]
0x10043f4bd  mov     r8, [rbp+470h+var_4E0]
0x10043f4c1  xor     edx, edx
0x10043f4c3  mov     rcx, [rbp+470h+var_4D8]
0x10043f4c7  call    cs:__imp_HostReg_ReportApplicationHealth
0x10043f4cd  test    eax, eax
0x10043f4cf  jns     short loc_10043F4ED
0x10043f4d1  lfence
0x10043f4d4  mov     r9d, eax
0x10043f4d7  mov     r8, [rbx]
0x10043f4da  lea     rdx, aKeepprocessali; "KeepProcessAliveInWcow"
0x10043f4e1  lea     rcx, aHsErrorUnableT; "[%hs] ERROR: Unable to report health fo"...
0x10043f4e8  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f4ed  mov     rcx, r14; hObject
0x10043f4f0  call    cs:__imp_CloseHandle
0x10043f4f6  jmp     loc_10043F5BE
0x10043f4fb  call    cs:__imp_GetLastError
0x10043f501  mov     edi, eax
0x10043f503  lea     ecx, [rax-2]
0x10043f506  mov     r9d, eax
0x10043f509  mov     r8, [rsi+8]
0x10043f50d  lea     rdx, aKeepprocessali; "KeepProcessAliveInWcow"
0x10043f514  cmp     ecx, 1
0x10043f517  jbe     loc_10043F5FE
0x10043f51d  lea     rcx, aHsInfoSProcess_0; "[%hs] INFO: %s process failed to be cre"...
0x10043f524  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f529  mov     [rsp+570h+bInheritHandles], edi
0x10043f52d  mov     r9, [rsi+8]
0x10043f531  lea     r8, aSProcessFailed; "%s process failed to be created with er"...
0x10043f538  mov     edx, 1F5h; unsigned __int64
0x10043f53d  lea     rcx, [rbp+470h+Buffer]; Buffer
0x10043f541  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10043f546  test    eax, eax
0x10043f548  js      short loc_10043F5A2
0x10043f54a  mov     rdi, [rbx]
0x10043f54d  lea     rcx, [rbp+470h+var_4D0]
0x10043f551  call    cs:__imp_HostReg_GetNodeName
0x10043f557  test    eax, eax
0x10043f559  js      short loc_10043F5A2
0x10043f55b  lea     rcx, [rbp+470h+var_4C8]
0x10043f55f  call    cs:__imp_HostReg_GetApplicationName
0x10043f565  test    eax, eax
0x10043f567  js      short loc_10043F5A2
0x10043f569  mov     dword ptr [rsp+570h+lpProcessInformation], r15d
0x10043f56e  mov     [rsp+570h+lpStartupInfo], rdi
0x10043f573  mov     [rsp+570h+lpCurrentDirectory], r15
0x10043f578  mov     dword ptr [rsp+570h+lpEnvironment], r15d
0x10043f57d  mov     qword ptr [rsp+570h+dwCreationFlags], r12
0x10043f582  mov     [rsp+570h+bInheritHandles], 3
0x10043f58a  lea     r9, [rbp+470h+Buffer]
0x10043f58e  mov     r8, [rbp+470h+var_4D0]
0x10043f592  xor     edx, edx
0x10043f594  mov     rcx, [rbp+470h+var_4C8]
0x10043f598  call    cs:__imp_HostReg_ReportApplicationHealth
0x10043f59e  test    eax, eax
0x10043f5a0  jns     short loc_10043F5BE
0x10043f5a2  lfence
0x10043f5a5  mov     r9d, eax
0x10043f5a8  mov     r8, [rbx]
0x10043f5ab  lea     rdx, aKeepprocessali; "KeepProcessAliveInWcow"
0x10043f5b2  lea     rcx, aHsErrorUnableT; "[%hs] ERROR: Unable to report health fo"...
0x10043f5b9  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f5be  mov     [rbp+470h+var_4C0], 400060h
0x10043f5c5  mov     [rbp+470h+var_4B8], r15
0x10043f5c9  mov     [rbp+470h+var_4A8], r15
0x10043f5cd  mov     [rbp+470h+var_4B0], r15
0x10043f5d1  mov     [rbp+470h+var_4A0], r15
0x10043f5d5  lea     rdx, [rbp+470h+var_4C0]
0x10043f5d9  mov     ecx, 0EA60h
0x10043f5de  call    ?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::Sleep(ulong,SOS_WaitInfo const *)
0x10043f5e3  jmp     loc_10043F233
0x10043f5e8  mov     [rsp+570h+bInheritHandles], 0B7h
0x10043f5f0  lea     rcx, aHsErrorProcess; "[%hs] ERROR: process %s PID %lu exited "...
0x10043f5f7  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f5fc  jmp     short loc_10043F60A
0x10043f5fe  lea     rcx, aHsErrorSProces; "[%hs] ERROR: %s process failed to be cr"...
0x10043f605  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f60a  mov     r8, [rsi+10h]
0x10043f60e  lea     rdx, aKeepprocessali; "KeepProcessAliveInWcow"
0x10043f615  lea     rcx, aHsErrorFailedT_5; "[%hs] ERROR: Failed to keep %s process "...
0x10043f61c  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10043f621  mov     ecx, 3FBh
0x10043f626  call    cs:__imp_?KillProcess@SOS_OS@@SAXK@Z; SOS_OS::KillProcess(ulong)
0x10043f62c  nop
0x10043f62d  mov     edx, 2
0x10043f632  mov     rcx, [rsi]
0x10043f635  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10043f63b  mov     edx, 2
0x10043f640  mov     rcx, [rsi+8]
0x10043f644  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10043f64a  mov     edx, 2
0x10043f64f  mov     rcx, [rsi+10h]
0x10043f653  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10043f659  mov     edx, 18h
0x10043f65e  mov     rcx, rsi
0x10043f661  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10043f667  xor     eax, eax
0x10043f669  mov     rcx, [rbp+470h+var_20]
0x10043f670  xor     rcx, rsp; StackCookie
0x10043f673  call    __security_check_cookie
0x10043f678  lea     r11, [rsp+570h+var_10]
0x10043f680  mov     rbx, [r11+20h]
0x10043f684  mov     rsi, [r11+28h]
0x10043f688  mov     rdi, [r11+30h]
0x10043f68c  mov     r12, [r11+38h]
0x10043f690  mov     rsp, r11
0x10043f693  pop     r15
0x10043f695  pop     r14
0x10043f697  pop     rbp
0x10043f698  retn
```
