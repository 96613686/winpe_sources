# _ShellExecuteRegAppWithJobObject(ushort const *,RRA_FLAGS,IUnknown *)

- ea: `0x18055b51c`
- end: `0x18055b828`
- name: `?_ShellExecuteRegAppWithJobObject@@YAJPEBGW4RRA_FLAGS@@PEAUIUnknown@@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18055bab8`

## callees

- `0x180018e4c`
- `0x18003a3e0`
- `0x18011be94`
- `0x180249490`
- `0x18024a53c`
- `0x180516af0`
- `0x18055b498`
- `0x18055b51c`
- `0x18055b9a8`
- `0x18055ba20`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18055b751`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18055b760`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18055b7da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18055b7eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18055b7fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18055b751`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18055b760`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18055b7da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18055b7eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18055b7fa`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18055b736`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18055b773`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18055b736`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18055b773`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18055b79d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18055b79d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18055b7c9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18055b7c9`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18055b673`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18055b673`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18055b70e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18055b70e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18055b5c5`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18055b5c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18055b57a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18055b57a`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18055b54e`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18055b54e`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18055b69a`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18055b69a`

## string_xrefs

- `0x18055b5e4`: `RunDLL32.EXE Shell32.DLL,ShellExec_RunDLL ?0x%X?%s`
- `0x18055b5b5`: `RunDLL32.EXE`

## pseudocode

```c
__int64 __fastcall _ShellExecuteRegAppWithJobObject(__int64 a1, char a2)
{
  HANDLE JobObjectW; // rsi
  int Error; // ebx
  __int64 v6; // rcx
  UINT SystemDirectoryW; // r14d
  void *v8; // rdi
  HANDLE v9; // r14
  HWND v10; // rcx
  __int64 v11; // rcx
  DWORD ProcessId; // eax
  __int64 v13; // rcx
  DWORD ThreadId; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR CommandLine[520]; // [rsp+2F0h] [rbp+1F0h] BYREF

  JobObjectW = CreateJobObjectW(0, 0);
  if ( JobObjectW || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x2000) != 0 )
      McTemplateU0z_EventWriteTransfer(v6, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Start, a1);
    Error = -2147467259;
    if ( SystemDirectoryW - 1 > 0x102 )
      goto LABEL_28;
    if ( PathCchAppend(Buffer, 0x104u, L"RunDLL32.EXE") < 0 )
      goto LABEL_28;
    if ( (int)StringCchPrintfW(CommandLine, 0x208u, L"RunDLL32.EXE Shell32.DLL,ShellExec_RunDLL ?0x%X?%s", 1024, a1) < 0 )
      goto LABEL_28;
    *(_QWORD *)&StartupInfo.cb = 104;
    memset_0(&StartupInfo.lpReserved, 0, 0x60u);
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( !CreateProcessW(Buffer, CommandLine, 0, 0, 0, 4u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_28;
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
LABEL_26:
        TerminateProcess(ProcessInformation.hProcess, 5u);
LABEL_27:
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
LABEL_28:
        CloseHandle(JobObjectW);
        return (unsigned int)Error;
      }
    }
    if ( (a2 & 2) != 0 )
    {
      v8 = _SetJobCompletionPort(JobObjectW);
      if ( v8 || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        ThreadId = 0;
        v9 = CreateThread(0, 0, _JobObjectWaitingThreadProc, v8, 0, &ThreadId);
        if ( v9 )
        {
          Error = 0;
        }
        else
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
          {
LABEL_20:
            CloseHandle(v8);
            goto LABEL_23;
          }
        }
        ResumeThread(ProcessInformation.hThread);
        SHProcessMessagesUntilEvent(v10, v9, 0xFFFFFFFF);
        CloseHandle(v9);
        goto LABEL_20;
      }
    }
    else
    {
      ResumeThread(ProcessInformation.hThread);
      if ( (a2 & 0x40) != 0 )
        IUnknown_WaitForSteadyState(v11, ProcessInformation.hProcess);
    }
LABEL_23:
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x2000) != 0 )
    {
      ProcessId = GetProcessId(ProcessInformation.hProcess);
      McTemplateU0qz_EventWriteTransfer(v13, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Stop, ProcessId, a1);
    }
    if ( Error >= 0 )
      goto LABEL_27;
    goto LABEL_26;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18055b51c  push    rbp
0x18055b51e  push    rbx
0x18055b51f  push    rsi
0x18055b520  push    rdi
0x18055b521  push    r14
0x18055b523  push    r15
0x18055b525  lea     rbp, [rsp-618h]
0x18055b52d  sub     rsp, 718h
0x18055b534  mov     rax, cs:__security_cookie
0x18055b53b  xor     rax, rsp
0x18055b53e  mov     [rbp+640h+var_40], rax
0x18055b545  mov     edi, edx
0x18055b547  mov     r15, rcx
0x18055b54a  xor     edx, edx; lpName
0x18055b54c  xor     ecx, ecx; lpJobAttributes
0x18055b54e  call    cs:__imp_CreateJobObjectW
0x18055b555  nop     dword ptr [rax+rax+00h]
0x18055b55a  mov     rsi, rax
0x18055b55d  test    rax, rax
0x18055b560  jnz     short loc_18055B571
0x18055b562  call    ResultFromKnownLastError
0x18055b567  mov     ebx, eax
0x18055b569  test    eax, eax
0x18055b56b  js      loc_18055B806
0x18055b571  mov     edx, 104h; uSize
0x18055b576  lea     rcx, [rbp+640h+Buffer]; lpBuffer
0x18055b57a  call    cs:__imp_GetSystemDirectoryW
0x18055b581  nop     dword ptr [rax+rax+00h]
0x18055b586  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+1, 20h
0x18055b58d  mov     r14d, eax
0x18055b590  jz      short loc_18055B5A1
0x18055b592  mov     r8, r15
0x18055b595  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Start
0x18055b59c  call    McTemplateU0z_EventWriteTransfer
0x18055b5a1  lea     eax, [r14-1]
0x18055b5a5  mov     ebx, 80004005h
0x18055b5aa  cmp     eax, 102h
0x18055b5af  ja      loc_18055B7F7
0x18055b5b5  lea     r8, aRundll32Exe_0; "RunDLL32.EXE"
0x18055b5bc  mov     edx, 104h; cchPath
0x18055b5c1  lea     rcx, [rbp+640h+Buffer]; pszPath
0x18055b5c5  call    cs:__imp_PathCchAppend
0x18055b5cc  nop     dword ptr [rax+rax+00h]
0x18055b5d1  test    eax, eax
0x18055b5d3  js      loc_18055B7F7
0x18055b5d9  mov     r9d, 400h
0x18055b5df  mov     qword ptr [rsp+740h+bInheritHandles], r15
0x18055b5e4  lea     r8, aRundll32ExeShe_0; "RunDLL32.EXE Shell32.DLL,ShellExec_RunD"...
0x18055b5eb  mov     edx, 208h; unsigned __int64
0x18055b5f0  lea     rcx, [rbp+640h+CommandLine]; unsigned __int16 *
0x18055b5f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18055b5fc  test    eax, eax
0x18055b5fe  js      loc_18055B7F7
0x18055b604  xor     edx, edx; Val
0x18055b606  mov     qword ptr [rsp+740h+StartupInfo.cb], 68h ; 'h'
0x18055b60f  lea     rcx, [rsp+740h+StartupInfo.lpReserved]; void *
0x18055b614  lea     r8d, [rdx+60h]; Size
0x18055b618  call    memset_0
0x18055b61d  xor     eax, eax
0x18055b61f  lea     rdx, [rbp+640h+CommandLine]; lpCommandLine
0x18055b626  mov     qword ptr [rsp+740h+ProcessInformation.dwProcessId], rax
0x18055b62b  lea     rcx, [rbp+640h+Buffer]; lpApplicationName
0x18055b62f  lea     rax, [rsp+740h+ProcessInformation]
0x18055b634  xorps   xmm0, xmm0
0x18055b637  mov     [rsp+740h+lpProcessInformation], rax; lpProcessInformation
0x18055b63c  xor     r9d, r9d; lpThreadAttributes
0x18055b63f  lea     rax, [rsp+740h+StartupInfo]
0x18055b644  xor     r8d, r8d; lpProcessAttributes
0x18055b647  mov     [rsp+740h+lpStartupInfo], rax; lpStartupInfo
0x18055b64c  mov     [rsp+740h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18055b655  mov     [rsp+740h+lpEnvironment], 0; lpEnvironment
0x18055b65e  mov     [rsp+740h+dwCreationFlags], 4; dwCreationFlags
0x18055b666  mov     [rsp+740h+bInheritHandles], 0; bInheritHandles
0x18055b66e  movups  xmmword ptr [rsp+740h+ProcessInformation.hProcess], xmm0
0x18055b673  call    cs:__imp_CreateProcessW
0x18055b67a  nop     dword ptr [rax+rax+00h]
0x18055b67f  test    eax, eax
0x18055b681  jnz     short loc_18055B692
0x18055b683  call    ResultFromKnownLastError
0x18055b688  mov     ebx, eax
0x18055b68a  test    eax, eax
0x18055b68c  js      loc_18055B7F7
0x18055b692  mov     rdx, [rsp+740h+ProcessInformation.hProcess]; hProcess
0x18055b697  mov     rcx, rsi; hJob
0x18055b69a  call    cs:__imp_AssignProcessToJobObject
0x18055b6a1  nop     dword ptr [rax+rax+00h]
0x18055b6a6  test    eax, eax
0x18055b6a8  jz      short loc_18055B6AE
0x18055b6aa  xor     ebx, ebx
0x18055b6ac  jmp     short loc_18055B6BD
0x18055b6ae  call    ResultFromKnownLastError
0x18055b6b3  mov     ebx, eax
0x18055b6b5  test    eax, eax
0x18055b6b7  js      loc_18055B7BF
0x18055b6bd  test    dil, 2
0x18055b6c1  jz      loc_18055B76E
0x18055b6c7  mov     rcx, rsi; hJob
0x18055b6ca  call    ?_SetJobCompletionPort@@YAPEAXPEAX@Z; _SetJobCompletionPort(void *)
0x18055b6cf  mov     rdi, rax
0x18055b6d2  test    rax, rax
0x18055b6d5  jnz     short loc_18055B6E6
0x18055b6d7  call    ResultFromKnownLastError
0x18055b6dc  mov     ebx, eax
0x18055b6de  test    eax, eax
0x18055b6e0  js      loc_18055B78F
0x18055b6e6  lea     rax, [rsp+740h+ThreadId]
0x18055b6eb  mov     [rsp+740h+ThreadId], 0
0x18055b6f3  mov     qword ptr [rsp+740h+dwCreationFlags], rax; lpThreadId
0x18055b6f8  lea     r8, ?_JobObjectWaitingThreadProc@@YAKPEAX@Z; lpStartAddress
0x18055b6ff  mov     r9, rdi; lpParameter
0x18055b702  mov     [rsp+740h+bInheritHandles], 0; dwCreationFlags
0x18055b70a  xor     edx, edx; dwStackSize
0x18055b70c  xor     ecx, ecx; lpThreadAttributes
0x18055b70e  call    cs:__imp_CreateThread
0x18055b715  nop     dword ptr [rax+rax+00h]
0x18055b71a  mov     r14, rax
0x18055b71d  test    rax, rax
0x18055b720  jz      short loc_18055B726
0x18055b722  xor     ebx, ebx
0x18055b724  jmp     short loc_18055B731
0x18055b726  call    ResultFromKnownLastError
0x18055b72b  mov     ebx, eax
0x18055b72d  test    eax, eax
0x18055b72f  js      short loc_18055B75D
0x18055b731  mov     rcx, [rsp+740h+ProcessInformation.hThread]; hThread
0x18055b736  call    cs:__imp_ResumeThread
0x18055b73d  nop     dword ptr [rax+rax+00h]
0x18055b742  or      r8d, 0FFFFFFFFh; unsigned int
0x18055b746  mov     rdx, r14; void *
0x18055b749  call    ?SHProcessMessagesUntilEvent@@YAKPEAUHWND__@@PEAXK@Z; SHProcessMessagesUntilEvent(HWND__ *,void *,ulong)
0x18055b74e  mov     rcx, r14; hObject
0x18055b751  call    cs:__imp_CloseHandle
0x18055b758  nop     dword ptr [rax+rax+00h]
0x18055b75d  mov     rcx, rdi; hObject
0x18055b760  call    cs:__imp_CloseHandle
0x18055b767  nop     dword ptr [rax+rax+00h]
0x18055b76c  jmp     short loc_18055B78F
0x18055b76e  mov     rcx, [rsp+740h+ProcessInformation.hThread]; hThread
0x18055b773  call    cs:__imp_ResumeThread
0x18055b77a  nop     dword ptr [rax+rax+00h]
0x18055b77f  test    dil, 40h
0x18055b783  jz      short loc_18055B78F
0x18055b785  mov     rdx, [rsp+740h+ProcessInformation.hProcess]
0x18055b78a  call    IUnknown_WaitForSteadyState
0x18055b78f  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+1, 20h
0x18055b796  jz      short loc_18055B7BB
0x18055b798  mov     rcx, [rsp+740h+ProcessInformation.hProcess]; Process
0x18055b79d  call    cs:__imp_GetProcessId
0x18055b7a4  nop     dword ptr [rax+rax+00h]
0x18055b7a9  mov     r9, r15
0x18055b7ac  lea     rdx, ShellTraceId_Explorer_ExecutingFromRunKeyAsJob_Stop
0x18055b7b3  mov     r8d, eax
0x18055b7b6  call    McTemplateU0qz_EventWriteTransfer
0x18055b7bb  test    ebx, ebx
0x18055b7bd  jns     short loc_18055B7D5
0x18055b7bf  mov     rcx, [rsp+740h+ProcessInformation.hProcess]; hProcess
0x18055b7c4  mov     edx, 5; uExitCode
0x18055b7c9  call    cs:__imp_TerminateProcess
0x18055b7d0  nop     dword ptr [rax+rax+00h]
0x18055b7d5  mov     rcx, [rsp+740h+ProcessInformation.hProcess]; hObject
0x18055b7da  call    cs:__imp_CloseHandle
0x18055b7e1  nop     dword ptr [rax+rax+00h]
0x18055b7e6  mov     rcx, [rsp+740h+ProcessInformation.hThread]; hObject
0x18055b7eb  call    cs:__imp_CloseHandle
0x18055b7f2  nop     dword ptr [rax+rax+00h]
0x18055b7f7  mov     rcx, rsi; hObject
0x18055b7fa  call    cs:__imp_CloseHandle
0x18055b801  nop     dword ptr [rax+rax+00h]
0x18055b806  mov     eax, ebx
0x18055b808  mov     rcx, [rbp+640h+var_40]
0x18055b80f  xor     rcx, rsp; StackCookie
0x18055b812  call    __security_check_cookie
0x18055b817  add     rsp, 718h
0x18055b81e  pop     r15
0x18055b820  pop     r14
0x18055b822  pop     rdi
0x18055b823  pop     rsi
0x18055b824  pop     rbx
0x18055b825  pop     rbp
0x18055b826  retn
```
