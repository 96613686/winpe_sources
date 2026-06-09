# HTTP_LOG_EVENT_HANDLER::CreateEtwStatusTimer(void)

- ea: `0x18000dca0`
- end: `0x18000dd4c`
- name: `?CreateEtwStatusTimer@HTTP_LOG_EVENT_HANDLER@@AEAAJXZ`
- size: `172`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bfc0`

## callees

- `0x18000dca0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcd1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000dd3e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000dd3e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000dcbf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000dcbf`
- `iisutil!PuDbgPrintError` at `0x18000dd1a`
- `iisutil!PuDbgPrintError` at `0x18000dd1a`

## string_xrefs

- `0x18000dd13`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\http_log_event_handler.cxx`
- `0x18000dcf6`: `CreateThreadpoolTimer() failed\n`
- `0x18000dd02`: `HTTP_LOG_EVENT_HANDLER::CreateEtwStatusTimer`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_EVENT_HANDLER::CreateEtwStatusTimer(PVOID pv)
{
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  pftDueTime = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(HTTP_LOG_EVENT_HANDLER::EtwSessionStatusTimerCallback, pv, 0);
  *((_QWORD *)pv + 29) = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    pftDueTime = (struct _FILETIME)-50000000LL;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0x1388u, 0);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
        653,
        "HTTP_LOG_EVENT_HANDLER::CreateEtwStatusTimer",
        v4,
        "CreateThreadpoolTimer() failed\n");
    return v4;
  }
}

```

## disassembly

```asm
0x18000dca0  push    rbx
0x18000dca2  sub     rsp, 30h
0x18000dca6  mov     rbx, rcx
0x18000dca9  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0
0x18000dcb2  mov     rdx, rcx; pv
0x18000dcb5  xor     r8d, r8d; pcbe
0x18000dcb8  lea     rcx, ?EtwSessionStatusTimerCallback@HTTP_LOG_EVENT_HANDLER@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000dcbf  call    cs:__imp_CreateThreadpoolTimer
0x18000dcc5  mov     [rbx+0E8h], rax
0x18000dccc  test    rax, rax
0x18000dccf  jnz     short loc_18000DD24
0x18000dcd1  call    cs:__imp_GetLastError
0x18000dcd7  mov     ebx, eax
0x18000dcd9  test    eax, eax
0x18000dcdb  jle     short loc_18000DCE6
0x18000dcdd  movzx   ebx, ax
0x18000dce0  or      ebx, 80070000h
0x18000dce6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000dced  jz      short loc_18000DD20
0x18000dcef  mov     rcx, cs:g_pDebug
0x18000dcf6  lea     rax, aCreatethreadpo; "CreateThreadpoolTimer() failed\n"
0x18000dcfd  mov     [rsp+38h+var_10], rax
0x18000dd02  lea     r9, aHttpLogEventHa_6; "HTTP_LOG_EVENT_HANDLER::CreateEtwStatus"...
0x18000dd09  mov     r8d, 28Dh
0x18000dd0f  mov     [rsp+38h+var_18], ebx
0x18000dd13  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000dd1a  call    cs:__imp_PuDbgPrintError
0x18000dd20  mov     eax, ebx
0x18000dd22  jmp     short loc_18000DD46
0x18000dd24  xor     r9d, r9d; msWindowLength
0x18000dd27  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000dd30  mov     r8d, 1388h; msPeriod
0x18000dd36  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000dd3b  mov     rcx, rax; pti
0x18000dd3e  call    cs:__imp_SetThreadpoolTimer
0x18000dd44  xor     eax, eax
0x18000dd46  add     rsp, 30h
0x18000dd4a  pop     rbx
0x18000dd4b  retn
```
