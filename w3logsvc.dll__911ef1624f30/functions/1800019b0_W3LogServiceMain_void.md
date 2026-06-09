# W3LogServiceMain(void)

- ea: `0x1800019b0`
- end: `0x180001bc9`
- name: `?W3LogServiceMain@@YAXXZ`
- size: `537`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001980`

## callees

- `0x1800019b0`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001ba7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001ba7`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180001b6e`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180001b6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001aba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001aba`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001a00`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001a00`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180001ab0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180001ab0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001a6e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001a6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b3c`
- `iisutil!PuDbgPrintError` at `0x180001a5b`
- `iisutil!PuDbgPrintError` at `0x180001b33`
- `iisutil!PuDbgPrintError` at `0x180001a5b`
- `iisutil!PuDbgPrintError` at `0x180001b33`

## string_xrefs

- `0x180001a54`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\main.cpp`
- `0x180001b28`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\main.cpp`
- `0x180001a37`: `CreateThread() failed\n`
- `0x180001a43`: `W3LogServiceMain`
- `0x180001b1c`: `W3LogServiceMain`
- `0x180001ad8`: `GetExitCodeThread() failed\n`
- `0x180001b08`: `W3LogServiceThreadProc() failed\n`

## pseudocode

```c
void W3LogServiceMain(void)
{
  HANDLE v0; // rax
  void *v1; // rdi
  signed int v2; // eax
  signed int v3; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  SERVICE_STATUS_HANDLE v6; // rax
  DWORD ExitCode; // [rsp+30h] [rbp-30h] BYREF
  DWORD ThreadId; // [rsp+34h] [rbp-2Ch] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-28h] BYREF

  ExitCode = 0;
  ThreadId = 0;
  v0 = CreateThread(0, 0x8000u, W3LogServiceThreadProc, 0, 0, &ThreadId);
  v1 = v0;
  if ( v0 )
  {
    if ( WaitForSingleObject(v0, 0xFFFFFFFF) == -1 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\main.cpp",
          311,
          "W3LogServiceMain",
          v3,
          "WaitForSingleObject() failed\n");
    }
    else if ( GetExitCodeThread(v1, &ExitCode) )
    {
      v3 = 0;
      if ( ExitCode )
      {
        v3 = (int)ExitCode > 0 ? (unsigned __int16)ExitCode | 0x80070000 : ExitCode;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\main.cpp",
            348,
            "W3LogServiceMain",
            v3,
            "W3LogServiceThreadProc() failed\n");
      }
    }
    else
    {
      v5 = GetLastError();
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\main.cpp",
          330,
          "W3LogServiceMain",
          v3,
          "GetExitCodeThread() failed\n");
    }
    CloseHandle(v1);
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\main.cpp",
        296,
        "W3LogServiceMain",
        v3,
        "CreateThread() failed\n");
  }
  if ( !g_RegisterServiceCalled )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( v3 >= 0 )
      v3 = -2147467259;
    v6 = RegisterServiceCtrlHandlerW(L"w3logsvc", HTTP_LOG_SITE_TABLE::Dereference);
    if ( v6 )
    {
      ServiceStatus.dwServiceType = 32;
      ServiceStatus.dwControlsAccepted = 5;
      ServiceStatus.dwCurrentState = 1;
      ServiceStatus.dwWin32ExitCode = 1066;
      ServiceStatus.dwServiceSpecificExitCode = v3;
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
      SetServiceStatus(v6, &ServiceStatus);
    }
  }
}

```

## disassembly

```asm
0x1800019b0  mov     [rsp-8+arg_0], rbx
0x1800019b5  mov     [rsp-8+arg_8], rdi
0x1800019ba  push    rbp
0x1800019bb  mov     rbp, rsp
0x1800019be  sub     rsp, 60h
0x1800019c2  mov     rax, cs:__security_cookie
0x1800019c9  xor     rax, rsp
0x1800019cc  mov     [rbp+var_8], rax
0x1800019d0  lea     rax, [rbp+ThreadId]
0x1800019d4  mov     [rbp+ExitCode], 0
0x1800019db  mov     [rsp+60h+lpThreadId], rax; lpThreadId
0x1800019e0  lea     r8, ?W3LogServiceThreadProc@@YAKPEAX@Z; lpStartAddress
0x1800019e7  xor     r9d, r9d; lpParameter
0x1800019ea  mov     [rsp+60h+dwCreationFlags], 0; dwCreationFlags
0x1800019f2  mov     edx, 8000h; dwStackSize
0x1800019f7  mov     [rbp+ThreadId], 0
0x1800019fe  xor     ecx, ecx; lpThreadAttributes
0x180001a00  call    cs:__imp_CreateThread
0x180001a06  mov     rdi, rax
0x180001a09  test    rax, rax
0x180001a0c  jnz     short loc_180001A66
0x180001a0e  call    cs:__imp_GetLastError
0x180001a14  mov     ebx, eax
0x180001a16  test    eax, eax
0x180001a18  jle     short loc_180001A23
0x180001a1a  movzx   ebx, ax
0x180001a1d  or      ebx, 80070000h
0x180001a23  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180001a2a  jz      loc_180001B42
0x180001a30  mov     rcx, cs:g_pDebug
0x180001a37  lea     rax, aCreatethreadFa; "CreateThread() failed\n"
0x180001a3e  mov     [rsp+60h+lpThreadId], rax
0x180001a43  lea     r9, aW3logservicema; "W3LogServiceMain"
0x180001a4a  mov     r8d, 128h
0x180001a50  mov     [rsp+60h+dwCreationFlags], ebx
0x180001a54  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180001a5b  call    cs:__imp_PuDbgPrintError
0x180001a61  jmp     loc_180001B42
0x180001a66  or      ebx, 0FFFFFFFFh
0x180001a69  mov     rcx, rdi; hHandle
0x180001a6c  mov     edx, ebx; dwMilliseconds
0x180001a6e  call    cs:__imp_WaitForSingleObject
0x180001a74  cmp     eax, ebx
0x180001a76  jnz     short loc_180001AA9
0x180001a78  call    cs:__imp_GetLastError
0x180001a7e  mov     ebx, eax
0x180001a80  test    eax, eax
0x180001a82  jle     short loc_180001A8D
0x180001a84  movzx   ebx, ax
0x180001a87  or      ebx, 80070000h
0x180001a8d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180001a94  jz      loc_180001B39
0x180001a9a  lea     rax, aWaitforsingleo; "WaitForSingleObject() failed\n"
0x180001aa1  mov     r8d, 137h
0x180001aa7  jmp     short loc_180001B15
0x180001aa9  lea     rdx, [rbp+ExitCode]; lpExitCode
0x180001aad  mov     rcx, rdi; hThread
0x180001ab0  call    cs:__imp_GetExitCodeThread
0x180001ab6  test    eax, eax
0x180001ab8  jnz     short loc_180001AE7
0x180001aba  call    cs:__imp_GetLastError
0x180001ac0  mov     ebx, eax
0x180001ac2  test    eax, eax
0x180001ac4  jle     short loc_180001ACF
0x180001ac6  movzx   ebx, ax
0x180001ac9  or      ebx, 80070000h
0x180001acf  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180001ad6  jz      short loc_180001B39
0x180001ad8  lea     rax, aGetexitcodethr; "GetExitCodeThread() failed\n"
0x180001adf  mov     r8d, 14Ah
0x180001ae5  jmp     short loc_180001B15
0x180001ae7  mov     eax, [rbp+ExitCode]
0x180001aea  xor     ebx, ebx
0x180001aec  test    eax, eax
0x180001aee  jz      short loc_180001B39
0x180001af0  jg      short loc_180001AF6
0x180001af2  mov     ebx, eax
0x180001af4  jmp     short loc_180001AFF
0x180001af6  movzx   ebx, ax
0x180001af9  or      ebx, 80070000h
0x180001aff  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180001b06  jz      short loc_180001B39
0x180001b08  lea     rax, aW3logserviceth; "W3LogServiceThreadProc() failed\n"
0x180001b0f  mov     r8d, 15Ch
0x180001b15  mov     rcx, cs:g_pDebug
0x180001b1c  lea     r9, aW3logservicema; "W3LogServiceMain"
0x180001b23  mov     [rsp+60h+lpThreadId], rax
0x180001b28  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180001b2f  mov     [rsp+60h+dwCreationFlags], ebx
0x180001b33  call    cs:__imp_PuDbgPrintError
0x180001b39  mov     rcx, rdi; hObject
0x180001b3c  call    cs:__imp_CloseHandle
0x180001b42  cmp     cs:?g_RegisterServiceCalled@@3HA, 0; int g_RegisterServiceCalled
0x180001b49  jnz     short loc_180001BAD
0x180001b4b  xorps   xmm0, xmm0
0x180001b4e  lea     rdx, ?Dereference@HTTP_LOG_SITE_TABLE@@UEAAXXZ; lpHandlerProc
0x180001b55  mov     eax, 80004005h
0x180001b5a  lea     rcx, aW3logsvc_1; "w3logsvc"
0x180001b61  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x180001b65  test    ebx, ebx
0x180001b67  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x180001b6b  cmovns  ebx, eax
0x180001b6e  call    cs:__imp_RegisterServiceCtrlHandlerW
0x180001b74  test    rax, rax
0x180001b77  jz      short loc_180001BAD
0x180001b79  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180001b7d  mov     [rbp+ServiceStatus.dwServiceType], 20h ; ' '
0x180001b84  mov     rcx, rax; hServiceStatus
0x180001b87  mov     [rbp+ServiceStatus.dwControlsAccepted], 5
0x180001b8e  mov     [rbp+ServiceStatus.dwCurrentState], 1
0x180001b95  mov     [rbp+ServiceStatus.dwWin32ExitCode], 42Ah
0x180001b9c  mov     [rbp+ServiceStatus.dwServiceSpecificExitCode], ebx
0x180001b9f  mov     qword ptr [rbp+ServiceStatus.dwCheckPoint], 0
0x180001ba7  call    cs:__imp_SetServiceStatus
0x180001bad  mov     rcx, [rbp+var_8]
0x180001bb1  xor     rcx, rsp; StackCookie
0x180001bb4  call    __security_check_cookie
0x180001bb9  mov     rbx, [rsp+60h+arg_0]
0x180001bbe  mov     rdi, [rsp+60h+arg_8]
0x180001bc3  add     rsp, 60h
0x180001bc7  pop     rbp
0x180001bc8  retn
```
