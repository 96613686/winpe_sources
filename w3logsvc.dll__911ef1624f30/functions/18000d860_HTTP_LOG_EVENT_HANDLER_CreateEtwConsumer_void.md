# HTTP_LOG_EVENT_HANDLER::CreateEtwConsumer(void)

- ea: `0x18000d860`
- end: `0x18000da67`
- name: `?CreateEtwConsumer@HTTP_LOG_EVENT_HANDLER@@AEAAJXZ`
- size: `519`
- prototype: `__int64 __fastcall(HTTP_LOG_EVENT_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bfc0`

## callees

- `0x18000d860`
- `0x18000e97a`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d91d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d91d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9fe`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000d9eb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000d9eb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000d99b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000d99b`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18000d907`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18000d907`
- `iisutil!PuDbgPrintError` at `0x18000d966`
- `iisutil!PuDbgPrintError` at `0x18000da3b`
- `iisutil!PuDbgPrintError` at `0x18000d966`
- `iisutil!PuDbgPrintError` at `0x18000da3b`

## string_xrefs

- `0x18000d9cb`: `CreateThread() failed\n`
- `0x18000d95f`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\http_log_event_handler.cxx`
- `0x18000da34`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\http_log_event_handler.cxx`
- `0x18000d942`: `OpenTrace() failed\n`
- `0x18000d94e`: `HTTP_LOG_EVENT_HANDLER::CreateEtwConsumer`
- `0x18000da2d`: `HTTP_LOG_EVENT_HANDLER::CreateEtwConsumer`
- `0x18000da10`: `Failed to boost thread priority \n`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_EVENT_HANDLER::CreateEtwConsumer(HTTP_LOG_EVENT_HANDLER *this)
{
  TRACEHANDLE v2; // rax
  _QWORD *v3; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  HANDLE Thread; // rax
  signed int v7; // eax
  signed int v8; // eax
  DWORD ThreadId[4]; // [rsp+30h] [rbp-D0h] BYREF
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+40h] [rbp-C0h] BYREF

  ThreadId[0] = 0;
  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.CurrentTime = 0;
  Logfile.LoggerName = (LPWSTR)L"HTTPSYS-IISEventTraceSession";
  Logfile.BuffersRead = 0;
  Logfile.EventCallback = (PEVENT_CALLBACK)HTTP_LOG_EVENT_HANDLER::EvtRecCallback;
  Logfile.LogFileMode = 268435712;
  memset(&Logfile.BufferCallback, 0, 20);
  Logfile.Context = this;
  v2 = OpenTraceW(&Logfile);
  v3 = (_QWORD *)((char *)this + 208);
  *((_QWORD *)this + 26) = v2;
  if ( v2 == -1 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
        518,
        "HTTP_LOG_EVENT_HANDLER::CreateEtwConsumer",
        v5,
        "OpenTrace() failed\n",
        *(_QWORD *)ThreadId);
    *v3 = 0;
  }
  else
  {
    Thread = CreateThread(
               0,
               0x8000u,
               HTTP_LOG_EVENT_HANDLER::HTTPLogEventConsumerThreadProc,
               (char *)this + 208,
               0,
               ThreadId);
    *((_QWORD *)this + 27) = Thread;
    if ( Thread )
    {
      v5 = 0;
      if ( !SetThreadPriority(Thread, 1) && (g_dwDebugFlags & 0xF) != 0 )
      {
        v8 = GetLastError();
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
          554,
          "HTTP_LOG_EVENT_HANDLER::CreateEtwConsumer",
          v8,
          "Failed to boost thread priority \n",
          *(_QWORD *)ThreadId);
      }
    }
    else
    {
      v7 = GetLastError();
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
          541,
          "HTTP_LOG_EVENT_HANDLER::CreateEtwConsumer",
          v5,
          "CreateThread() failed\n",
          *(_QWORD *)ThreadId);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000d860  mov     [rsp-8+arg_8], rbx
0x18000d865  mov     [rsp-8+arg_10], rdi
0x18000d86a  push    rbp
0x18000d86b  lea     rbp, [rsp-110h]
0x18000d873  sub     rsp, 210h
0x18000d87a  mov     rax, cs:__security_cookie
0x18000d881  xor     rax, rsp
0x18000d884  mov     [rbp+110h+var_10], rax
0x18000d88b  mov     rbx, rcx
0x18000d88e  mov     [rsp+210h+ThreadId], 0
0x18000d896  lea     rcx, [rsp+210h+Logfile]; void *
0x18000d89b  xor     edx, edx; Val
0x18000d89d  mov     r8d, 1C0h; Size
0x18000d8a3  call    memset_0
0x18000d8a8  lea     rax, InstanceName; "HTTPSYS-IISEventTraceSession"
0x18000d8af  mov     [rsp+210h+Logfile.CurrentTime], 0
0x18000d8b8  mov     [rsp+210h+Logfile.LoggerName], rax
0x18000d8bd  lea     rcx, [rsp+210h+Logfile]; Logfile
0x18000d8c2  lea     rax, ?EvtRecCallback@HTTP_LOG_EVENT_HANDLER@@CAXPEAU_EVENT_RECORD@@@Z; HTTP_LOG_EVENT_HANDLER::EvtRecCallback(_EVENT_RECORD *)
0x18000d8c9  mov     [rsp+210h+Logfile.BuffersRead], 0
0x18000d8d1  mov     qword ptr [rbp+110h+Logfile.1A8h], rax
0x18000d8d8  mov     dword ptr [rsp+210h+Logfile.1Ch], 10000100h
0x18000d8e0  mov     [rbp+110h+Logfile.BufferCallback], 0
0x18000d8eb  mov     qword ptr [rbp+110h+Logfile.BufferSize], 0
0x18000d8f6  mov     [rbp+110h+Logfile.EventsLost], 0
0x18000d900  mov     [rbp+110h+Logfile.Context], rbx
0x18000d907  call    cs:__imp_OpenTraceW
0x18000d90d  lea     rdi, [rbx+0D0h]
0x18000d914  mov     [rdi], rax
0x18000d917  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d91b  jnz     short loc_18000D978
0x18000d91d  call    cs:__imp_GetLastError
0x18000d923  mov     ebx, eax
0x18000d925  test    eax, eax
0x18000d927  jle     short loc_18000D932
0x18000d929  movzx   ebx, ax
0x18000d92c  or      ebx, 80070000h
0x18000d932  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d939  jz      short loc_18000D96C
0x18000d93b  mov     rcx, cs:g_pDebug
0x18000d942  lea     rax, aOpentraceFaile; "OpenTrace() failed\n"
0x18000d949  mov     [rsp+210h+lpThreadId], rax
0x18000d94e  lea     r9, aHttpLogEventHa_1; "HTTP_LOG_EVENT_HANDLER::CreateEtwConsum"...
0x18000d955  mov     r8d, 206h
0x18000d95b  mov     [rsp+210h+dwCreationFlags], ebx
0x18000d95f  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000d966  call    cs:__imp_PuDbgPrintError
0x18000d96c  mov     qword ptr [rdi], 0
0x18000d973  jmp     loc_18000DA41
0x18000d978  lea     rax, [rsp+210h+ThreadId]
0x18000d97d  mov     r9, rdi; lpParameter
0x18000d980  mov     [rsp+210h+lpThreadId], rax; lpThreadId
0x18000d985  lea     r8, ?HTTPLogEventConsumerThreadProc@HTTP_LOG_EVENT_HANDLER@@CAKPEAX@Z; lpStartAddress
0x18000d98c  mov     edx, 8000h; dwStackSize
0x18000d991  mov     [rsp+210h+dwCreationFlags], 0; dwCreationFlags
0x18000d999  xor     ecx, ecx; lpThreadAttributes
0x18000d99b  call    cs:__imp_CreateThread
0x18000d9a1  mov     [rbx+0D8h], rax
0x18000d9a8  test    rax, rax
0x18000d9ab  jnz     short loc_18000D9E3
0x18000d9ad  call    cs:__imp_GetLastError
0x18000d9b3  mov     ebx, eax
0x18000d9b5  test    eax, eax
0x18000d9b7  jle     short loc_18000D9C2
0x18000d9b9  movzx   ebx, ax
0x18000d9bc  or      ebx, 80070000h
0x18000d9c2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d9c9  jz      short loc_18000DA41
0x18000d9cb  lea     rax, aCreatethreadFa; "CreateThread() failed\n"
0x18000d9d2  mov     r8d, 21Dh
0x18000d9d8  mov     [rsp+210h+lpThreadId], rax
0x18000d9dd  mov     [rsp+210h+dwCreationFlags], ebx
0x18000d9e1  jmp     short loc_18000DA26
0x18000d9e3  xor     ebx, ebx
0x18000d9e5  mov     rcx, rax; hThread
0x18000d9e8  lea     edx, [rbx+1]; nPriority
0x18000d9eb  call    cs:__imp_SetThreadPriority
0x18000d9f1  test    eax, eax
0x18000d9f3  jnz     short loc_18000DA41
0x18000d9f5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d9fc  jz      short loc_18000DA41
0x18000d9fe  call    cs:__imp_GetLastError
0x18000da04  test    eax, eax
0x18000da06  jle     short loc_18000DA10
0x18000da08  movzx   eax, ax
0x18000da0b  or      eax, 80070000h
0x18000da10  lea     rcx, aFailedToBoostT; "Failed to boost thread priority \n"
0x18000da17  mov     r8d, 22Ah
0x18000da1d  mov     [rsp+210h+lpThreadId], rcx
0x18000da22  mov     [rsp+210h+dwCreationFlags], eax
0x18000da26  mov     rcx, cs:g_pDebug
0x18000da2d  lea     r9, aHttpLogEventHa_1; "HTTP_LOG_EVENT_HANDLER::CreateEtwConsum"...
0x18000da34  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000da3b  call    cs:__imp_PuDbgPrintError
0x18000da41  mov     eax, ebx
0x18000da43  mov     rcx, [rbp+110h+var_10]
0x18000da4a  xor     rcx, rsp; StackCookie
0x18000da4d  call    __security_check_cookie
0x18000da52  lea     r11, [rsp+210h+var_s0]
0x18000da5a  mov     rbx, [r11+18h]
0x18000da5e  mov     rdi, [r11+20h]
0x18000da62  mov     rsp, r11
0x18000da65  pop     rbp
0x18000da66  retn
```
