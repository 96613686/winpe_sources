# HTTP_LOG_EVENT_HANDLER::EtwSessionStatusTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18000dfc0`
- end: `0x18000e19a`
- name: `?EtwSessionStatusTimerCallback@HTTP_LOG_EVENT_HANDLER@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `474`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _DWORD *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000dfc0`
- `0x18000e97a`
- `0x18000e9a0`

## import_xrefs

- `msvcrt!_ultow` at `0x18000e120`
- `msvcrt!_ultow` at `0x18000e120`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000e102`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000e163`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000e102`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000e163`
- `api-ms-win-eventing-legacy-l1-1-0!QueryTraceW` at `0x18000e024`
- `api-ms-win-eventing-legacy-l1-1-0!QueryTraceW` at `0x18000e024`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000e156`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000e156`
- `iisutil!PuDbgPrintError` at `0x18000e070`
- `iisutil!PuDbgPrintError` at `0x18000e0e9`
- `iisutil!PuDbgPrintError` at `0x18000e070`
- `iisutil!PuDbgPrintError` at `0x18000e0e9`

## string_xrefs

- `0x18000e065`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\http_log_event_handler.cxx`
- `0x18000e0a4`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\http_log_event_handler.cxx`

## pseudocode

```c
void __fastcall HTTP_LOG_EVENT_HANDLER::EtwSessionStatusTimerCallback(
        PTP_CALLBACK_INSTANCE Instance,
        _DWORD *Context,
        PTP_TIMER Timer)
{
  int v4; // eax
  signed int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  _QWORD *v8; // rbx
  wchar_t *v9; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Buffer[12]; // [rsp+68h] [rbp-98h] BYREF
  _EVENT_TRACE_PROPERTIES Properties; // [rsp+80h] [rbp-80h] BYREF

  memset_0(&Properties.Wnode.ProviderId, 0, 0xAEu);
  v4 = Context[56];
  v9 = 0;
  if ( !v4 )
  {
    Properties.Wnode.BufferSize = 178;
    v5 = QueryTraceW(0, L"HTTPSYS-IISEventTraceSession", &Properties);
    if ( v5 )
    {
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
          832,
          "HTTP_LOG_EVENT_HANDLER::EtwSessionStatusTimerCallback",
          v5,
          "QueryTrace() failed\n");
    }
    else
    {
      v6 = Properties.EventsLost - dword_180018730;
      if ( Properties.EventsLost != dword_180018730 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
            852,
            "HTTP_LOG_EVENT_HANDLER::EtwSessionStatusTimerCallback",
            0,
            "dwLastEventsLost = %d BufferSize = %d MinimumBuffers= %d MaximumBuffers = %d NumberOfBuffers = %d FreeBuffers = %d \n",
            Properties.EventsLost - dword_180018730,
            Properties.BufferSize,
            Properties.MinimumBuffers,
            Properties.MaximumBuffers,
            Properties.NumberOfBuffers,
            Properties.FreeBuffers);
        v7 = *((_QWORD *)g_pLogSvcAdmin + 245);
        if ( !v7 || GetTickCount64() - v7 > 0x36EE80 )
        {
          _ultow(v6, Buffer, 10);
          v9 = Buffer;
          EVENT_LOG::LogEvent(
            (EVENT_LOG *)((char *)g_pLogSvcAdmin + 1896),
            0xC000177B,
            1u,
            (const unsigned __int16 **const)&v9,
            0);
          v8 = g_pLogSvcAdmin;
          v8[245] = GetTickCount64();
        }
      }
      dword_180018730 = Properties.EventsLost;
    }
  }
}

```

## disassembly

```asm
0x18000dfc0  mov     [rsp-8+arg_0], rbx
0x18000dfc5  mov     [rsp-8+arg_8], rdi
0x18000dfca  push    rbp
0x18000dfcb  lea     rbp, [rsp-50h]
0x18000dfd0  sub     rsp, 150h
0x18000dfd7  mov     rax, cs:__security_cookie
0x18000dfde  xor     rax, rsp
0x18000dfe1  mov     [rbp+50h+var_10], rax
0x18000dfe5  mov     rbx, rdx
0x18000dfe8  lea     rcx, [rbp+50h+Properties.Wnode.ProviderId]; void *
0x18000dfec  xor     edx, edx; Val
0x18000dfee  mov     r8d, 0AEh; Size
0x18000dff4  call    memset_0
0x18000dff9  mov     eax, [rbx+0E0h]
0x18000dfff  mov     [rsp+150h+var_F0], 0
0x18000e008  test    eax, eax
0x18000e00a  jnz     loc_18000E179
0x18000e010  lea     r8, [rbp+50h+Properties]; Properties
0x18000e014  mov     [rbp+50h+Properties.Wnode.BufferSize], 0B2h
0x18000e01b  lea     rdx, InstanceName; "HTTPSYS-IISEventTraceSession"
0x18000e022  xor     ecx, ecx; TraceHandle
0x18000e024  call    cs:__imp_QueryTraceW
0x18000e02a  test    eax, eax
0x18000e02c  jz      short loc_18000E07B
0x18000e02e  jle     short loc_18000E038
0x18000e030  movzx   eax, ax
0x18000e033  or      eax, 80070000h
0x18000e038  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000e03f  jz      loc_18000E179
0x18000e045  lea     rcx, aQuerytraceFail; "QueryTrace() failed\n"
0x18000e04c  mov     r8d, 340h
0x18000e052  mov     [rsp+150h+var_128], rcx
0x18000e057  lea     r9, aHttpLogEventHa; "HTTP_LOG_EVENT_HANDLER::EtwSessionStatu"...
0x18000e05e  mov     rcx, cs:g_pDebug
0x18000e065  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000e06c  mov     [rsp+150h+var_130], eax
0x18000e070  call    cs:__imp_PuDbgPrintError
0x18000e076  jmp     loc_18000E179
0x18000e07b  mov     ebx, [rbp+50h+Properties.EventsLost]
0x18000e07e  sub     ebx, cs:dword_180018730
0x18000e084  jz      loc_18000E170
0x18000e08a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000e091  jz      short loc_18000E0EF
0x18000e093  mov     eax, [rbp+50h+Properties.FreeBuffers]
0x18000e096  lea     r9, aHttpLogEventHa; "HTTP_LOG_EVENT_HANDLER::EtwSessionStatu"...
0x18000e09d  mov     rcx, cs:g_pDebug
0x18000e0a4  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000e0ab  mov     [rsp+150h+var_F8], eax
0x18000e0af  mov     r8d, 354h
0x18000e0b5  mov     eax, [rbp+50h+Properties.NumberOfBuffers]
0x18000e0b8  mov     [rsp+150h+var_100], eax
0x18000e0bc  mov     eax, [rbp+50h+Properties.MaximumBuffers]
0x18000e0bf  mov     [rsp+150h+var_108], eax
0x18000e0c3  mov     eax, [rbp+50h+Properties.MinimumBuffers]
0x18000e0c6  mov     [rsp+150h+var_110], eax
0x18000e0ca  mov     eax, [rbp+50h+Properties.BufferSize]
0x18000e0cd  mov     [rsp+150h+var_118], eax
0x18000e0d1  lea     rax, aDwlasteventslo; "dwLastEventsLost = %d BufferSize = %d M"...
0x18000e0d8  mov     [rsp+150h+var_120], ebx
0x18000e0dc  mov     [rsp+150h+var_128], rax
0x18000e0e1  mov     [rsp+150h+var_130], 0
0x18000e0e9  call    cs:__imp_PuDbgPrintError
0x18000e0ef  mov     rax, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000e0f6  mov     rdi, [rax+7A8h]
0x18000e0fd  test    rdi, rdi
0x18000e100  jz      short loc_18000E113
0x18000e102  call    cs:__imp_GetTickCount64
0x18000e108  sub     rax, rdi
0x18000e10b  cmp     rax, 36EE80h
0x18000e111  jbe     short loc_18000E170
0x18000e113  mov     r8d, 0Ah; Radix
0x18000e119  lea     rdx, [rsp+150h+Buffer]; Buffer
0x18000e11e  mov     ecx, ebx; Value
0x18000e120  call    cs:__imp__ultow
0x18000e126  mov     rcx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000e12d  lea     rax, [rsp+150h+Buffer]
0x18000e132  add     rcx, 768h
0x18000e139  mov     [rsp+150h+var_F0], rax
0x18000e13e  mov     r8d, 1
0x18000e144  mov     [rsp+150h+var_130], 0
0x18000e14c  lea     r9, [rsp+150h+var_F0]
0x18000e151  mov     edx, 0C000177Bh
0x18000e156  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000e15c  mov     rbx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000e163  call    cs:__imp_GetTickCount64
0x18000e169  mov     [rbx+7A8h], rax
0x18000e170  mov     eax, [rbp+50h+Properties.EventsLost]
0x18000e173  mov     cs:dword_180018730, eax
0x18000e179  mov     rcx, [rbp+50h+var_10]
0x18000e17d  xor     rcx, rsp; StackCookie
0x18000e180  call    __security_check_cookie
0x18000e185  lea     r11, [rsp+150h+var_s0]
0x18000e18d  mov     rbx, [r11+10h]
0x18000e191  mov     rdi, [r11+18h]
0x18000e195  mov     rsp, r11
0x18000e198  pop     rbp
0x18000e199  retn
```
