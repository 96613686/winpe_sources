# SpoolerStartChildProcess(void * *)

- ea: `0x14003e980`
- end: `0x14003ec95`
- name: `?SpoolerStartChildProcess@@YAJPEAPEAX@Z`
- size: `789`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140040270`

## callees

- `0x14001748c`
- `0x1400177c4`
- `0x14002d0a0`
- `0x14002dd20`
- `0x14003e46c`
- `0x14003e5e4`
- `0x14003e980`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003ec3b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003ec3b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003eaf4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003eaf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ea56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ead1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003eb97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ebb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ebc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ebd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ec0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ea56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ead1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003eb97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ebb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ebc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ebd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ec0c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14003eb87`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14003eb87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ec54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ec6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ec54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ec6a`
- `KERNEL32!SetInformationJobObject` at `0x14003eac1`
- `KERNEL32!SetInformationJobObject` at `0x14003eac1`
- `KERNEL32!AssignProcessToJobObject` at `0x14003ebfc`
- `KERNEL32!AssignProcessToJobObject` at `0x14003ebfc`
- `KERNEL32!CreateJobObjectW` at `0x14003ea3b`
- `KERNEL32!CreateJobObjectW` at `0x14003ea3b`

## string_xrefs

- `0x14003ea11`: `Failed to logon spooler service account %d`
- `0x14003e9e6`: `Failed to create print spooler virtual service account %d`
- `0x14003ea62`: `Failed to create job object for child worker processes %d`
- `0x14003eb08`: `Failed to allocate command line arguments buffer`
- `0x14003eba6`: `Failed to create child spooler process %d`

## pseudocode

```c
__int64 __fastcall SpoolerStartChildProcess(void **a1)
{
  int ServiceAccount; // eax
  signed int v3; // ebx
  int v4; // eax
  HANDLE v5; // rbx
  DWORD LastError; // eax
  unsigned __int16 *v7; // rdx
  unsigned __int16 *v8; // rax
  WCHAR *v9; // rdi
  DWORD v10; // eax
  DWORD v11; // eax
  HANDLE hToken; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  int JobObjectInformation; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v17[12]; // [rsp+F4h] [rbp-Ch] BYREF
  int v18; // [rsp+100h] [rbp+0h]

  hToken = 0;
  *(_QWORD *)&StartupInfo.cb = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  ServiceAccount = SpoolerCreateServiceAccount();
  v3 = ServiceAccount;
  if ( ServiceAccount < 0 )
  {
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "SpoolerStartChildProcess",
      L"Failed to create print spooler virtual service account %d",
      (unsigned int)ServiceAccount);
    goto LABEL_24;
  }
  v4 = SpoolerLogonServiceAccount(&hToken);
  v3 = v4;
  if ( v4 >= 0 )
  {
    if ( !g_hSpoolerJobObject )
    {
      g_hSpoolerJobObject = CreateJobObjectW(0, 0);
      v5 = g_hSpoolerJobObject;
      if ( !g_hSpoolerJobObject )
      {
        LastError = GetLastError();
        v7 = L"Failed to create job object for child worker processes %d";
        goto LABEL_8;
      }
      JobObjectInformation = 0;
      memset_0(v17, 0, 0x8Cu);
      v18 = 0x2000;
      if ( !SetInformationJobObject(v5, JobObjectExtendedLimitInformation, &JobObjectInformation, 0x90u) )
      {
        LastError = GetLastError();
        v7 = L"Failed to set job object limit information %d";
LABEL_8:
        v3 = LastError;
        SpoolerServiceTelemetry::WriteDbgTraceError("SpoolerStartChildProcess", v7, LastError);
        if ( v3 > 0 )
          v3 = (unsigned __int16)v3 | 0xC0070000;
        goto LABEL_22;
      }
    }
    StartupInfo.cb = 112;
    v8 = (unsigned __int16 *)malloc(0x104u);
    v9 = v8;
    if ( v8 )
    {
      StringCchPrintfW(v8, 0x104u, L"SplWorker");
      if ( CreateProcessAsUserW(
             hToken,
             L"spoolsvworker.exe",
             v9,
             0,
             0,
             1,
             0x80000u,
             0,
             0,
             &StartupInfo,
             &ProcessInformation) )
      {
        if ( !AssignProcessToJobObject(g_hSpoolerJobObject, ProcessInformation.hProcess) )
        {
          v11 = GetLastError();
          SpoolerServiceTelemetry::WriteDbgTraceError(
            "SpoolerStartChildProcess",
            L"Failed to assign child worker process to job object %d",
            v11);
        }
        v3 = 0;
        *a1 = ProcessInformation.hProcess;
      }
      else
      {
        v10 = GetLastError();
        SpoolerServiceTelemetry::WriteDbgTraceError(
          "SpoolerStartChildProcess",
          L"Failed to create child spooler process %d",
          v10);
        if ( (int)GetLastError() > 0 )
          v3 = (unsigned __int16)GetLastError() | 0xC0070000;
        else
          v3 = GetLastError();
      }
      free(v9);
    }
    else
    {
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "SpoolerStartChildProcess",
        L"Failed to allocate command line arguments buffer");
      v3 = -1073741801;
    }
    goto LABEL_22;
  }
  SpoolerServiceTelemetry::WriteDbgTraceError(
    "SpoolerStartChildProcess",
    L"Failed to logon spooler service account %d",
    (unsigned int)v4);
LABEL_22:
  if ( hToken )
    CloseHandle(hToken);
LABEL_24:
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14003e980  push    rbp
0x14003e982  push    rbx
0x14003e983  push    rdi
0x14003e984  push    r14
0x14003e986  lea     rbp, [rsp-98h]
0x14003e98e  sub     rsp, 198h
0x14003e995  mov     rax, cs:__security_cookie
0x14003e99c  xor     rax, rsp
0x14003e99f  mov     [rbp+0B0h+var_30], rax
0x14003e9a6  xor     edx, edx; Val
0x14003e9a8  mov     [rsp+1B0h+hToken], 0
0x14003e9b1  mov     r14, rcx
0x14003e9b4  mov     qword ptr [rbp+0B0h+StartupInfo.cb], 0
0x14003e9bc  lea     rcx, [rbp+0B0h+StartupInfo.lpReserved]; void *
0x14003e9c0  lea     r8d, [rdx+68h]; Size
0x14003e9c4  call    memset_0
0x14003e9c9  xorps   xmm0, xmm0
0x14003e9cc  xor     eax, eax
0x14003e9ce  movups  xmmword ptr [rsp+1B0h+ProcessInformation.hProcess], xmm0
0x14003e9d3  mov     qword ptr [rsp+1B0h+ProcessInformation.dwProcessId], rax
0x14003e9d8  call    ?SpoolerCreateServiceAccount@@YAJXZ; SpoolerCreateServiceAccount(void)
0x14003e9dd  mov     ebx, eax
0x14003e9df  test    eax, eax
0x14003e9e1  jns     short loc_14003E9FE
0x14003e9e3  mov     r8d, eax
0x14003e9e6  lea     rdx, aFailedToCreate_4; "Failed to create print spooler virtual "...
0x14003e9ed  lea     rcx, aSpoolerstartch; "SpoolerStartChildProcess"
0x14003e9f4  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003e9f9  jmp     loc_14003EC60
0x14003e9fe  lea     rcx, [rsp+1B0h+hToken]; void **
0x14003ea03  call    ?SpoolerLogonServiceAccount@@YAJPEAPEAX@Z; SpoolerLogonServiceAccount(void * *)
0x14003ea08  mov     ebx, eax
0x14003ea0a  test    eax, eax
0x14003ea0c  jns     short loc_14003EA29
0x14003ea0e  mov     r8d, eax
0x14003ea11  lea     rdx, aFailedToLogonS; "Failed to logon spooler service account"...
0x14003ea18  lea     rcx, aSpoolerstartch; "SpoolerStartChildProcess"
0x14003ea1f  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003ea24  jmp     loc_14003EC47
0x14003ea29  cmp     cs:?g_hSpoolerJobObject@@3PEAXEA, 0; void * g_hSpoolerJobObject
0x14003ea31  jnz     loc_14003EAE6
0x14003ea37  xor     edx, edx; lpName
0x14003ea39  xor     ecx, ecx; lpJobAttributes
0x14003ea3b  call    cs:__imp_CreateJobObjectW
0x14003ea42  nop     dword ptr [rax+rax+00h]
0x14003ea47  mov     cs:?g_hSpoolerJobObject@@3PEAXEA, rax; void * g_hSpoolerJobObject
0x14003ea4e  mov     rbx, rax
0x14003ea51  test    rax, rax
0x14003ea54  jnz     short loc_14003EA90
0x14003ea56  call    cs:__imp_GetLastError
0x14003ea5d  nop     dword ptr [rax+rax+00h]
0x14003ea62  lea     rdx, aFailedToCreate; "Failed to create job object for child w"...
0x14003ea69  mov     r8d, eax
0x14003ea6c  lea     rcx, aSpoolerstartch; "SpoolerStartChildProcess"
0x14003ea73  mov     ebx, eax
0x14003ea75  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003ea7a  test    ebx, ebx
0x14003ea7c  jle     loc_14003EC47
0x14003ea82  movzx   ebx, bx
0x14003ea85  or      ebx, 0C0070000h
0x14003ea8b  jmp     loc_14003EC47
0x14003ea90  xor     edx, edx; Val
0x14003ea92  mov     [rbp+0B0h+JobObjectInformation], 0
0x14003ea99  mov     r8d, 8Ch; Size
0x14003ea9f  lea     rcx, [rbp+0B0h+var_BC]; void *
0x14003eaa3  call    memset_0
0x14003eaa8  mov     r9d, 90h; cbJobObjectInformationLength
0x14003eaae  mov     [rbp+0B0h+var_B0], 2000h
0x14003eab5  lea     r8, [rbp+0B0h+JobObjectInformation]; lpJobObjectInformation
0x14003eab9  mov     edx, 9; JobObjectInformationClass
0x14003eabe  mov     rcx, rbx; hJob
0x14003eac1  call    cs:__imp_SetInformationJobObject
0x14003eac8  nop     dword ptr [rax+rax+00h]
0x14003eacd  test    eax, eax
0x14003eacf  jnz     short loc_14003EAE6
0x14003ead1  call    cs:__imp_GetLastError
0x14003ead8  nop     dword ptr [rax+rax+00h]
0x14003eadd  lea     rdx, aFailedToSetJob; "Failed to set job object limit informat"...
0x14003eae4  jmp     short loc_14003EA69
0x14003eae6  mov     ebx, 104h
0x14003eaeb  mov     [rbp+0B0h+StartupInfo.cb], 70h ; 'p'
0x14003eaf2  mov     ecx, ebx; Size
0x14003eaf4  call    cs:__imp_malloc
0x14003eafb  nop     dword ptr [rax+rax+00h]
0x14003eb00  mov     rdi, rax
0x14003eb03  test    rax, rax
0x14003eb06  jnz     short loc_14003EB25
0x14003eb08  lea     rdx, aFailedToAlloca_2; "Failed to allocate command line argumen"...
0x14003eb0f  lea     rcx, aSpoolerstartch; "SpoolerStartChildProcess"
0x14003eb16  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003eb1b  mov     ebx, 0C0000017h
0x14003eb20  jmp     loc_14003EC47
0x14003eb25  lea     r8, aSplworker; "SplWorker"
0x14003eb2c  mov     rdx, rbx; unsigned __int64
0x14003eb2f  mov     rcx, rdi; unsigned __int16 *
0x14003eb32  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003eb37  mov     rcx, [rsp+1B0h+hToken]; hToken
0x14003eb3c  lea     rax, [rsp+1B0h+ProcessInformation]
0x14003eb41  mov     [rsp+1B0h+lpProcessInformation], rax; lpProcessInformation
0x14003eb46  lea     rdx, ApplicationName; "spoolsvworker.exe"
0x14003eb4d  lea     rax, [rbp+0B0h+StartupInfo]
0x14003eb51  xor     r9d, r9d; lpProcessAttributes
0x14003eb54  mov     [rsp+1B0h+lpStartupInfo], rax; lpStartupInfo
0x14003eb59  mov     r8, rdi; lpCommandLine
0x14003eb5c  mov     [rsp+1B0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x14003eb65  mov     [rsp+1B0h+lpEnvironment], 0; lpEnvironment
0x14003eb6e  mov     [rsp+1B0h+dwCreationFlags], 80000h; dwCreationFlags
0x14003eb76  mov     [rsp+1B0h+bInheritHandles], 1; bInheritHandles
0x14003eb7e  mov     [rsp+1B0h+lpThreadAttributes], 0; lpThreadAttributes
0x14003eb87  call    cs:__imp_CreateProcessAsUserW
0x14003eb8e  nop     dword ptr [rax+rax+00h]
0x14003eb93  test    eax, eax
0x14003eb95  jnz     short loc_14003EBF0
0x14003eb97  call    cs:__imp_GetLastError
0x14003eb9e  nop     dword ptr [rax+rax+00h]
0x14003eba3  mov     r8d, eax
0x14003eba6  lea     rdx, aFailedToCreate_5; "Failed to create child spooler process "...
0x14003ebad  lea     rcx, aSpoolerstartch; "SpoolerStartChildProcess"
0x14003ebb4  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003ebb9  call    cs:__imp_GetLastError
0x14003ebc0  nop     dword ptr [rax+rax+00h]
0x14003ebc5  test    eax, eax
0x14003ebc7  jg      short loc_14003EBD9
0x14003ebc9  call    cs:__imp_GetLastError
0x14003ebd0  nop     dword ptr [rax+rax+00h]
0x14003ebd5  mov     ebx, eax
0x14003ebd7  jmp     short loc_14003EC38
0x14003ebd9  call    cs:__imp_GetLastError
0x14003ebe0  nop     dword ptr [rax+rax+00h]
0x14003ebe5  movzx   ebx, ax
0x14003ebe8  or      ebx, 0C0070000h
0x14003ebee  jmp     short loc_14003EC38
0x14003ebf0  mov     rdx, [rsp+1B0h+ProcessInformation.hProcess]; hProcess
0x14003ebf5  mov     rcx, cs:?g_hSpoolerJobObject@@3PEAXEA; hJob
0x14003ebfc  call    cs:__imp_AssignProcessToJobObject
0x14003ec03  nop     dword ptr [rax+rax+00h]
0x14003ec08  test    eax, eax
0x14003ec0a  jnz     short loc_14003EC2E
0x14003ec0c  call    cs:__imp_GetLastError
0x14003ec13  nop     dword ptr [rax+rax+00h]
0x14003ec18  mov     r8d, eax
0x14003ec1b  lea     rdx, aFailedToAssign; "Failed to assign child worker process t"...
0x14003ec22  lea     rcx, aSpoolerstartch; "SpoolerStartChildProcess"
0x14003ec29  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003ec2e  mov     rax, [rsp+1B0h+ProcessInformation.hProcess]
0x14003ec33  xor     ebx, ebx
0x14003ec35  mov     [r14], rax
0x14003ec38  mov     rcx, rdi; Block
0x14003ec3b  call    cs:__imp_free
0x14003ec42  nop     dword ptr [rax+rax+00h]
0x14003ec47  cmp     [rsp+1B0h+hToken], 0
0x14003ec4d  jz      short loc_14003EC60
0x14003ec4f  mov     rcx, [rsp+1B0h+hToken]; hObject
0x14003ec54  call    cs:__imp_CloseHandle
0x14003ec5b  nop     dword ptr [rax+rax+00h]
0x14003ec60  mov     rcx, [rsp+1B0h+ProcessInformation.hThread]; hObject
0x14003ec65  test    rcx, rcx
0x14003ec68  jz      short loc_14003EC76
0x14003ec6a  call    cs:__imp_CloseHandle
0x14003ec71  nop     dword ptr [rax+rax+00h]
0x14003ec76  mov     eax, ebx
0x14003ec78  mov     rcx, [rbp+0B0h+var_30]
0x14003ec7f  xor     rcx, rsp; StackCookie
0x14003ec82  call    __security_check_cookie
0x14003ec87  add     rsp, 198h
0x14003ec8e  pop     r14
0x14003ec90  pop     rdi
0x14003ec91  pop     rbx
0x14003ec92  pop     rbp
0x14003ec93  retn
```
