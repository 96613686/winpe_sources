# SpoolerStartChildProcess(void * *)

- ea: `0x14003b27c`
- end: `0x14003b536`
- name: `?SpoolerStartChildProcess@@YAJPEAPEAX@Z`
- size: `698`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003c9d0`

## callees

- `0x1400160a0`
- `0x1400163ec`
- `0x14002abc0`
- `0x14002b810`
- `0x14003ae08`
- `0x14003af60`
- `0x14003b27c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003b4ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003b4ef`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003b3d8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003b3d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b34c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b3bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b48b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b4c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b34c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b3bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b48b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b4c6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14003b465`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14003b465`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b502`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b512`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b502`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b512`
- `KERNEL32!SetInformationJobObject` at `0x14003b3b1`
- `KERNEL32!SetInformationJobObject` at `0x14003b3b1`
- `KERNEL32!AssignProcessToJobObject` at `0x14003b4bc`
- `KERNEL32!AssignProcessToJobObject` at `0x14003b4bc`
- `KERNEL32!CreateJobObjectW` at `0x14003b337`
- `KERNEL32!CreateJobObjectW` at `0x14003b337`

## string_xrefs

- `0x14003b30d`: `Failed to logon spooler service account %d`
- `0x14003b2e2`: `Failed to create print spooler virtual service account %d`
- `0x14003b352`: `Failed to create job object for child worker processes %d`
- `0x14003b3e6`: `Failed to allocate command line arguments buffer`
- `0x14003b478`: `Failed to create child spooler process %d`

## pseudocode

```c
__int64 __fastcall SpoolerStartChildProcess(void **a1)
{
  NTSTATUS ServiceAccount; // eax
  signed int v3; // ebx
  signed int v4; // eax
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
0x14003b27c  push    rbp
0x14003b27e  push    rbx
0x14003b27f  push    rdi
0x14003b280  push    r14
0x14003b282  lea     rbp, [rsp-98h]
0x14003b28a  sub     rsp, 198h
0x14003b291  mov     rax, cs:__security_cookie
0x14003b298  xor     rax, rsp
0x14003b29b  mov     [rbp+0B0h+var_30], rax
0x14003b2a2  xor     edx, edx; Val
0x14003b2a4  mov     [rsp+1B0h+hToken], 0
0x14003b2ad  mov     r14, rcx
0x14003b2b0  mov     qword ptr [rbp+0B0h+StartupInfo.cb], 0
0x14003b2b8  lea     rcx, [rbp+0B0h+StartupInfo.lpReserved]; void *
0x14003b2bc  lea     r8d, [rdx+68h]; Size
0x14003b2c0  call    memset_0
0x14003b2c5  xorps   xmm0, xmm0
0x14003b2c8  xor     eax, eax
0x14003b2ca  movups  xmmword ptr [rsp+1B0h+ProcessInformation.hProcess], xmm0
0x14003b2cf  mov     qword ptr [rsp+1B0h+ProcessInformation.dwProcessId], rax
0x14003b2d4  call    ?SpoolerCreateServiceAccount@@YAJXZ; SpoolerCreateServiceAccount(void)
0x14003b2d9  mov     ebx, eax
0x14003b2db  test    eax, eax
0x14003b2dd  jns     short loc_14003B2FA
0x14003b2df  mov     r8d, eax
0x14003b2e2  lea     rdx, aFailedToCreate_4; "Failed to create print spooler virtual "...
0x14003b2e9  lea     rcx, aSpoolerstartch; "SpoolerStartChildProcess"
0x14003b2f0  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b2f5  jmp     loc_14003B508
0x14003b2fa  lea     rcx, [rsp+1B0h+hToken]; void **
0x14003b2ff  call    ?SpoolerLogonServiceAccount@@YAJPEAPEAX@Z; SpoolerLogonServiceAccount(void * *)
0x14003b304  mov     ebx, eax
0x14003b306  test    eax, eax
0x14003b308  jns     short loc_14003B325
0x14003b30a  mov     r8d, eax
0x14003b30d  lea     rdx, aFailedToLogonS; "Failed to logon spooler service account"...
0x14003b314  lea     rcx, aSpoolerstartch; "SpoolerStartChildProcess"
0x14003b31b  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b320  jmp     loc_14003B4F5
0x14003b325  cmp     cs:?g_hSpoolerJobObject@@3PEAXEA, 0; void * g_hSpoolerJobObject
0x14003b32d  jnz     loc_14003B3CA
0x14003b333  xor     edx, edx; lpName
0x14003b335  xor     ecx, ecx; lpJobAttributes
0x14003b337  call    cs:__imp_CreateJobObjectW
0x14003b33d  mov     cs:?g_hSpoolerJobObject@@3PEAXEA, rax; void * g_hSpoolerJobObject
0x14003b344  mov     rbx, rax
0x14003b347  test    rax, rax
0x14003b34a  jnz     short loc_14003B380
0x14003b34c  call    cs:__imp_GetLastError
0x14003b352  lea     rdx, aFailedToCreate; "Failed to create job object for child w"...
0x14003b359  mov     r8d, eax
0x14003b35c  lea     rcx, aSpoolerstartch; "SpoolerStartChildProcess"
0x14003b363  mov     ebx, eax
0x14003b365  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b36a  test    ebx, ebx
0x14003b36c  jle     loc_14003B4F5
0x14003b372  movzx   ebx, bx
0x14003b375  or      ebx, 0C0070000h
0x14003b37b  jmp     loc_14003B4F5
0x14003b380  xor     edx, edx; Val
0x14003b382  mov     [rbp+0B0h+JobObjectInformation], 0
0x14003b389  mov     r8d, 8Ch; Size
0x14003b38f  lea     rcx, [rbp+0B0h+var_BC]; void *
0x14003b393  call    memset_0
0x14003b398  mov     r9d, 90h; cbJobObjectInformationLength
0x14003b39e  mov     [rbp+0B0h+var_B0], 2000h
0x14003b3a5  lea     r8, [rbp+0B0h+JobObjectInformation]; lpJobObjectInformation
0x14003b3a9  mov     edx, 9; JobObjectInformationClass
0x14003b3ae  mov     rcx, rbx; hJob
0x14003b3b1  call    cs:__imp_SetInformationJobObject
0x14003b3b7  test    eax, eax
0x14003b3b9  jnz     short loc_14003B3CA
0x14003b3bb  call    cs:__imp_GetLastError
0x14003b3c1  lea     rdx, aFailedToSetJob; "Failed to set job object limit informat"...
0x14003b3c8  jmp     short loc_14003B359
0x14003b3ca  mov     ebx, 104h
0x14003b3cf  mov     [rbp+0B0h+StartupInfo.cb], 70h ; 'p'
0x14003b3d6  mov     ecx, ebx; Size
0x14003b3d8  call    cs:__imp_malloc
0x14003b3de  mov     rdi, rax
0x14003b3e1  test    rax, rax
0x14003b3e4  jnz     short loc_14003B403
0x14003b3e6  lea     rdx, aFailedToAlloca_2; "Failed to allocate command line argumen"...
0x14003b3ed  lea     rcx, aSpoolerstartch; "SpoolerStartChildProcess"
0x14003b3f4  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b3f9  mov     ebx, 0C0000017h
0x14003b3fe  jmp     loc_14003B4F5
0x14003b403  lea     r8, aSplworker; "SplWorker"
0x14003b40a  mov     rdx, rbx; unsigned __int64
0x14003b40d  mov     rcx, rdi; unsigned __int16 *
0x14003b410  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003b415  mov     rcx, [rsp+1B0h+hToken]; hToken
0x14003b41a  lea     rax, [rsp+1B0h+ProcessInformation]
0x14003b41f  mov     [rsp+1B0h+lpProcessInformation], rax; lpProcessInformation
0x14003b424  lea     rdx, ApplicationName; "spoolsvworker.exe"
0x14003b42b  lea     rax, [rbp+0B0h+StartupInfo]
0x14003b42f  xor     r9d, r9d; lpProcessAttributes
0x14003b432  mov     [rsp+1B0h+lpStartupInfo], rax; lpStartupInfo
0x14003b437  mov     r8, rdi; lpCommandLine
0x14003b43a  mov     [rsp+1B0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x14003b443  mov     [rsp+1B0h+lpEnvironment], 0; lpEnvironment
0x14003b44c  mov     [rsp+1B0h+dwCreationFlags], 80000h; dwCreationFlags
0x14003b454  mov     [rsp+1B0h+bInheritHandles], 1; bInheritHandles
0x14003b45c  mov     [rsp+1B0h+lpThreadAttributes], 0; lpThreadAttributes
0x14003b465  call    cs:__imp_CreateProcessAsUserW
0x14003b46b  test    eax, eax
0x14003b46d  jnz     short loc_14003B4B0
0x14003b46f  call    cs:__imp_GetLastError
0x14003b475  mov     r8d, eax
0x14003b478  lea     rdx, aFailedToCreate_5; "Failed to create child spooler process "...
0x14003b47f  lea     rcx, aSpoolerstartch; "SpoolerStartChildProcess"
0x14003b486  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b48b  call    cs:__imp_GetLastError
0x14003b491  test    eax, eax
0x14003b493  jg      short loc_14003B49F
0x14003b495  call    cs:__imp_GetLastError
0x14003b49b  mov     ebx, eax
0x14003b49d  jmp     short loc_14003B4EC
0x14003b49f  call    cs:__imp_GetLastError
0x14003b4a5  movzx   ebx, ax
0x14003b4a8  or      ebx, 0C0070000h
0x14003b4ae  jmp     short loc_14003B4EC
0x14003b4b0  mov     rdx, [rsp+1B0h+ProcessInformation.hProcess]; hProcess
0x14003b4b5  mov     rcx, cs:?g_hSpoolerJobObject@@3PEAXEA; hJob
0x14003b4bc  call    cs:__imp_AssignProcessToJobObject
0x14003b4c2  test    eax, eax
0x14003b4c4  jnz     short loc_14003B4E2
0x14003b4c6  call    cs:__imp_GetLastError
0x14003b4cc  mov     r8d, eax
0x14003b4cf  lea     rdx, aFailedToAssign; "Failed to assign child worker process t"...
0x14003b4d6  lea     rcx, aSpoolerstartch; "SpoolerStartChildProcess"
0x14003b4dd  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003b4e2  mov     rax, [rsp+1B0h+ProcessInformation.hProcess]
0x14003b4e7  xor     ebx, ebx
0x14003b4e9  mov     [r14], rax
0x14003b4ec  mov     rcx, rdi; Block
0x14003b4ef  call    cs:__imp_free
0x14003b4f5  cmp     [rsp+1B0h+hToken], 0
0x14003b4fb  jz      short loc_14003B508
0x14003b4fd  mov     rcx, [rsp+1B0h+hToken]; hObject
0x14003b502  call    cs:__imp_CloseHandle
0x14003b508  mov     rcx, [rsp+1B0h+ProcessInformation.hThread]; hObject
0x14003b50d  test    rcx, rcx
0x14003b510  jz      short loc_14003B518
0x14003b512  call    cs:__imp_CloseHandle
0x14003b518  mov     eax, ebx
0x14003b51a  mov     rcx, [rbp+0B0h+var_30]
0x14003b521  xor     rcx, rsp; StackCookie
0x14003b524  call    __security_check_cookie
0x14003b529  add     rsp, 198h
0x14003b530  pop     r14
0x14003b532  pop     rdi
0x14003b533  pop     rbx
0x14003b534  pop     rbp
0x14003b535  retn
```
