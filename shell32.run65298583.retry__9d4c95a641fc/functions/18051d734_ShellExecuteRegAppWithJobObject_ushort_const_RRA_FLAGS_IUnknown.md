# _ShellExecuteRegAppWithJobObject(ushort const *,RRA_FLAGS,IUnknown *)

- ea: `0x18051d734`
- end: `0x18051da20`
- name: `?_ShellExecuteRegAppWithJobObject@@YAJPEBGW4RRA_FLAGS@@PEAUIUnknown@@@Z`
- size: `748`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18051dc80`

## callees

- `0x1800208d8`
- `0x18003eab0`
- `0x18010f134`
- `0x180233280`
- `0x1802342fc`
- `0x1804dc43c`
- `0x18051d734`
- `0x18051db74`
- `0x18051dbe8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18051d904`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18051d97a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18051d983`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18051d9e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18051d9f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18051d9f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18051d904`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18051d97a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18051d983`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18051d9e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18051d9f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18051d9f9`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18051d9b4`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18051d9b4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18051d943`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18051d943`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18051d9da`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18051d9da`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18051d965`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18051d990`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18051d965`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18051d990`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18051d876`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18051d876`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18051d7d1`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18051d7d1`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18051d8cd`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18051d8cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18051d78c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18051d78c`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18051d8f7`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18051d8f7`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18051d766`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18051d766`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18051d897`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18051d897`

## string_xrefs

- `0x18051d7c1`: `RunDLL32.EXE`
- `0x18051d7ea`: `RunDLL32.EXE Shell32.DLL,ShellExec_RunDLL ?0x%X?%s`

## pseudocode

```c
__int64 __fastcall _ShellExecuteRegAppWithJobObject(__int64 a1, char a2)
{
  HANDLE JobObjectW; // rsi
  int Error; // ebx
  __int64 v6; // rcx
  UINT SystemDirectoryW; // r14d
  HANDLE IoCompletionPort; // rax
  void *v9; // rdi
  HANDLE v10; // r14
  HWND v11; // rcx
  __int64 v12; // rcx
  DWORD ProcessId; // eax
  __int64 v14; // rcx
  DWORD ThreadId; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD JobObjectInformation[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR CommandLine[520]; // [rsp+300h] [rbp+200h] BYREF

  JobObjectW = CreateJobObjectW(0, 0);
  if ( JobObjectW || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x2000) != 0 )
      McTemplateU0z_EventWriteTransfer(v6, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Start, a1);
    Error = -2147467259;
    if ( SystemDirectoryW - 1 > 0x102 )
      goto LABEL_30;
    if ( PathCchAppend(Buffer, 0x104u, L"RunDLL32.EXE") < 0 )
      goto LABEL_30;
    if ( (int)StringCchPrintfW(CommandLine, 0x208u, L"RunDLL32.EXE Shell32.DLL,ShellExec_RunDLL ?0x%X?%s", 1024, a1) < 0 )
      goto LABEL_30;
    *(_QWORD *)&StartupInfo.cb = 104;
    memset_0(&StartupInfo.lpReserved, 0, 0x60u);
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( !CreateProcessW(Buffer, CommandLine, 0, 0, 0, 4u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_30;
    }
    if ( AssignProcessToJobObject(JobObjectW, ProcessInformation.hProcess) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_28:
        TerminateProcess(ProcessInformation.hProcess, 5u);
LABEL_29:
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
LABEL_30:
        CloseHandle(JobObjectW);
        return (unsigned int)Error;
      }
    }
    if ( (a2 & 2) == 0 )
    {
      ResumeThread(ProcessInformation.hThread);
      if ( (a2 & 0x40) != 0 )
        IUnknown_WaitForSteadyState(v12, ProcessInformation.hProcess);
LABEL_25:
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x2000) != 0 )
      {
        ProcessId = GetProcessId(ProcessInformation.hProcess);
        McTemplateU0qz_EventWriteTransfer(v14, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Stop, ProcessId, a1);
      }
      if ( Error >= 0 )
        goto LABEL_29;
      goto LABEL_28;
    }
    IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u);
    v9 = IoCompletionPort;
    if ( IoCompletionPort )
    {
      JobObjectInformation[0] = JobObjectW;
      JobObjectInformation[1] = IoCompletionPort;
      if ( SetInformationJobObject(JobObjectW, JobObjectAssociateCompletionPortInformation, JobObjectInformation, 0x10u) )
        goto LABEL_18;
      CloseHandle(v9);
      v9 = 0;
    }
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_25;
LABEL_18:
    ThreadId = 0;
    v10 = CreateThread(0, 0, _JobObjectWaitingThreadProc, v9, 0, &ThreadId);
    if ( v10 )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_22:
        CloseHandle(v9);
        goto LABEL_25;
      }
    }
    ResumeThread(ProcessInformation.hThread);
    SHProcessMessagesUntilEvent(v11, v10, 0xFFFFFFFF);
    CloseHandle(v10);
    goto LABEL_22;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18051d734  push    rbp
0x18051d736  push    rbx
0x18051d737  push    rsi
0x18051d738  push    rdi
0x18051d739  push    r14
0x18051d73b  push    r15
0x18051d73d  lea     rbp, [rsp-628h]
0x18051d745  sub     rsp, 728h
0x18051d74c  mov     rax, cs:__security_cookie
0x18051d753  xor     rax, rsp
0x18051d756  mov     [rbp+650h+var_40], rax
0x18051d75d  mov     edi, edx
0x18051d75f  mov     r15, rcx
0x18051d762  xor     edx, edx; lpName
0x18051d764  xor     ecx, ecx; lpJobAttributes
0x18051d766  call    cs:__imp_CreateJobObjectW
0x18051d76c  mov     rsi, rax
0x18051d76f  test    rax, rax
0x18051d772  jnz     short loc_18051D783
0x18051d774  call    ResultFromKnownLastError
0x18051d779  mov     ebx, eax
0x18051d77b  test    eax, eax
0x18051d77d  js      loc_18051D9FF
0x18051d783  mov     edx, 104h; uSize
0x18051d788  lea     rcx, [rbp+650h+Buffer]; lpBuffer
0x18051d78c  call    cs:__imp_GetSystemDirectoryW
0x18051d792  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+1, 20h
0x18051d799  mov     r14d, eax
0x18051d79c  jz      short loc_18051D7AD
0x18051d79e  mov     r8, r15
0x18051d7a1  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Start
0x18051d7a8  call    McTemplateU0z_EventWriteTransfer
0x18051d7ad  lea     eax, [r14-1]
0x18051d7b1  mov     ebx, 80004005h
0x18051d7b6  cmp     eax, 102h
0x18051d7bb  ja      loc_18051D9F6
0x18051d7c1  lea     r8, aRundll32Exe_0; "RunDLL32.EXE"
0x18051d7c8  mov     edx, 104h; cchPath
0x18051d7cd  lea     rcx, [rbp+650h+Buffer]; pszPath
0x18051d7d1  call    cs:__imp_PathCchAppend
0x18051d7d7  test    eax, eax
0x18051d7d9  js      loc_18051D9F6
0x18051d7df  mov     r9d, 400h
0x18051d7e5  mov     qword ptr [rsp+750h+bInheritHandles], r15
0x18051d7ea  lea     r8, aRundll32ExeShe_0; "RunDLL32.EXE Shell32.DLL,ShellExec_RunD"...
0x18051d7f1  mov     edx, 208h; unsigned __int64
0x18051d7f6  lea     rcx, [rbp+650h+CommandLine]; unsigned __int16 *
0x18051d7fd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18051d802  test    eax, eax
0x18051d804  js      loc_18051D9F6
0x18051d80a  xor     edx, edx; Val
0x18051d80c  mov     qword ptr [rbp+650h+StartupInfo.cb], 68h ; 'h'
0x18051d814  lea     rcx, [rbp+650h+StartupInfo.lpReserved]; void *
0x18051d818  lea     r8d, [rdx+60h]; Size
0x18051d81c  call    memset_0
0x18051d821  xor     eax, eax
0x18051d823  lea     rdx, [rbp+650h+CommandLine]; lpCommandLine
0x18051d82a  mov     qword ptr [rsp+750h+ProcessInformation.dwProcessId], rax
0x18051d82f  lea     rcx, [rbp+650h+Buffer]; lpApplicationName
0x18051d833  lea     rax, [rsp+750h+ProcessInformation]
0x18051d838  xorps   xmm0, xmm0
0x18051d83b  mov     [rsp+750h+lpProcessInformation], rax; lpProcessInformation
0x18051d840  xor     r9d, r9d; lpThreadAttributes
0x18051d843  lea     rax, [rbp+650h+StartupInfo]
0x18051d847  xor     r8d, r8d; lpProcessAttributes
0x18051d84a  mov     [rsp+750h+lpStartupInfo], rax; lpStartupInfo
0x18051d84f  mov     [rsp+750h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18051d858  mov     [rsp+750h+lpEnvironment], 0; lpEnvironment
0x18051d861  mov     [rsp+750h+dwCreationFlags], 4; dwCreationFlags
0x18051d869  mov     [rsp+750h+bInheritHandles], 0; bInheritHandles
0x18051d871  movups  xmmword ptr [rsp+750h+ProcessInformation.hProcess], xmm0
0x18051d876  call    cs:__imp_CreateProcessW
0x18051d87c  test    eax, eax
0x18051d87e  jnz     short loc_18051D88F
0x18051d880  call    ResultFromKnownLastError
0x18051d885  mov     ebx, eax
0x18051d887  test    eax, eax
0x18051d889  js      loc_18051D9F6
0x18051d88f  mov     rdx, [rsp+750h+ProcessInformation.hProcess]; hProcess
0x18051d894  mov     rcx, rsi; hJob
0x18051d897  call    cs:__imp_AssignProcessToJobObject
0x18051d89d  test    eax, eax
0x18051d89f  jz      short loc_18051D8A5
0x18051d8a1  xor     ebx, ebx
0x18051d8a3  jmp     short loc_18051D8B4
0x18051d8a5  call    ResultFromKnownLastError
0x18051d8aa  mov     ebx, eax
0x18051d8ac  test    eax, eax
0x18051d8ae  js      loc_18051D9D0
0x18051d8b4  test    dil, 2
0x18051d8b8  jz      loc_18051D98B
0x18051d8be  mov     r9d, 1; NumberOfConcurrentThreads
0x18051d8c4  xor     r8d, r8d; CompletionKey
0x18051d8c7  xor     edx, edx; ExistingCompletionPort
0x18051d8c9  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18051d8cd  call    cs:__imp_CreateIoCompletionPort
0x18051d8d3  mov     rdi, rax
0x18051d8d6  test    rax, rax
0x18051d8d9  jz      short loc_18051D90C
0x18051d8db  mov     r9d, 10h; cbJobObjectInformationLength
0x18051d8e1  mov     [rsp+750h+JobObjectInformation], rsi
0x18051d8e6  lea     r8, [rsp+750h+JobObjectInformation]; lpJobObjectInformation
0x18051d8eb  mov     [rsp+750h+var_6D8], rax
0x18051d8f0  mov     rcx, rsi; hJob
0x18051d8f3  lea     edx, [r9-9]; JobObjectInformationClass
0x18051d8f7  call    cs:__imp_SetInformationJobObject
0x18051d8fd  test    eax, eax
0x18051d8ff  jnz     short loc_18051D91B
0x18051d901  mov     rcx, rdi; hObject
0x18051d904  call    cs:__imp_CloseHandle
0x18051d90a  xor     edi, edi
0x18051d90c  call    ResultFromKnownLastError
0x18051d911  mov     ebx, eax
0x18051d913  test    eax, eax
0x18051d915  js      loc_18051D9A6
0x18051d91b  lea     rax, [rsp+750h+ThreadId]
0x18051d920  mov     [rsp+750h+ThreadId], 0
0x18051d928  mov     qword ptr [rsp+750h+dwCreationFlags], rax; lpThreadId
0x18051d92d  lea     r8, ?_JobObjectWaitingThreadProc@@YAKPEAX@Z; lpStartAddress
0x18051d934  mov     r9, rdi; lpParameter
0x18051d937  mov     [rsp+750h+bInheritHandles], 0; dwCreationFlags
0x18051d93f  xor     edx, edx; dwStackSize
0x18051d941  xor     ecx, ecx; lpThreadAttributes
0x18051d943  call    cs:__imp_CreateThread
0x18051d949  mov     r14, rax
0x18051d94c  test    rax, rax
0x18051d94f  jz      short loc_18051D955
0x18051d951  xor     ebx, ebx
0x18051d953  jmp     short loc_18051D960
0x18051d955  call    ResultFromKnownLastError
0x18051d95a  mov     ebx, eax
0x18051d95c  test    eax, eax
0x18051d95e  js      short loc_18051D980
0x18051d960  mov     rcx, [rsp+750h+ProcessInformation.hThread]; hThread
0x18051d965  call    cs:__imp_ResumeThread
0x18051d96b  or      r8d, 0FFFFFFFFh; unsigned int
0x18051d96f  mov     rdx, r14; void *
0x18051d972  call    ?SHProcessMessagesUntilEvent@@YAKPEAUHWND__@@PEAXK@Z; SHProcessMessagesUntilEvent(HWND__ *,void *,ulong)
0x18051d977  mov     rcx, r14; hObject
0x18051d97a  call    cs:__imp_CloseHandle
0x18051d980  mov     rcx, rdi; hObject
0x18051d983  call    cs:__imp_CloseHandle
0x18051d989  jmp     short loc_18051D9A6
0x18051d98b  mov     rcx, [rsp+750h+ProcessInformation.hThread]; hThread
0x18051d990  call    cs:__imp_ResumeThread
0x18051d996  test    dil, 40h
0x18051d99a  jz      short loc_18051D9A6
0x18051d99c  mov     rdx, [rsp+750h+ProcessInformation.hProcess]
0x18051d9a1  call    IUnknown_WaitForSteadyState
0x18051d9a6  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+1, 20h
0x18051d9ad  jz      short loc_18051D9CC
0x18051d9af  mov     rcx, [rsp+750h+ProcessInformation.hProcess]; Process
0x18051d9b4  call    cs:__imp_GetProcessId
0x18051d9ba  mov     r9, r15
0x18051d9bd  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Stop
0x18051d9c4  mov     r8d, eax
0x18051d9c7  call    McTemplateU0qz_EventWriteTransfer
0x18051d9cc  test    ebx, ebx
0x18051d9ce  jns     short loc_18051D9E0
0x18051d9d0  mov     rcx, [rsp+750h+ProcessInformation.hProcess]; hProcess
0x18051d9d5  mov     edx, 5; uExitCode
0x18051d9da  call    cs:__imp_TerminateProcess
0x18051d9e0  mov     rcx, [rsp+750h+ProcessInformation.hProcess]; hObject
0x18051d9e5  call    cs:__imp_CloseHandle
0x18051d9eb  mov     rcx, [rsp+750h+ProcessInformation.hThread]; hObject
0x18051d9f0  call    cs:__imp_CloseHandle
0x18051d9f6  mov     rcx, rsi; hObject
0x18051d9f9  call    cs:__imp_CloseHandle
0x18051d9ff  mov     eax, ebx
0x18051da01  mov     rcx, [rbp+650h+var_40]
0x18051da08  xor     rcx, rsp; StackCookie
0x18051da0b  call    __security_check_cookie
0x18051da10  add     rsp, 728h
0x18051da17  pop     r15
0x18051da19  pop     r14
0x18051da1b  pop     rdi
0x18051da1c  pop     rsi
0x18051da1d  pop     rbx
0x18051da1e  pop     rbp
0x18051da1f  retn
```
