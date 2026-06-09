# HTTP_LOG_EVENT_HANDLER::CreateEtwSession(void)

- ea: `0x18000da70`
- end: `0x18000dc9a`
- name: `?CreateEtwSession@HTTP_LOG_EVENT_HANDLER@@AEAAJXZ`
- size: `554`
- prototype: `__int64 __fastcall(HTTP_LOG_EVENT_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bfc0`

## callees

- `0x18000da70`
- `0x18000e97a`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18000dc4e`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18000dc4e`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x18000dab1`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x18000dab1`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18000dbc0`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18000dbc0`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x18000db5d`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x18000db7d`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x18000db9e`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x18000db5d`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x18000db7d`
- `iisutil!ReadDwordParameterValueFromAnyService` at `0x18000db9e`
- `iisutil!PuDbgPrintError` at `0x18000dc0f`
- `iisutil!PuDbgPrintError` at `0x18000dc0f`

## string_xrefs

- `0x18000dae5`: `System\CurrentControlSet\Services\W3LogSvc\Parameters`
- `0x18000dbf8`: `HTTP_LOG_EVENT_HANDLER::CreateEtwSession`
- `0x18000dc04`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\http_log_event_handler.cxx`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_EVENT_HANDLER::CreateEtwSession(HTTP_LOG_EVENT_HANDLER *this)
{
  signed int started; // eax
  unsigned int v3; // ebx
  signed int v4; // eax

  memset_0(*((void **)this + 25), 0, 0xB2u);
  **((_DWORD **)this + 25) = 178;
  StopTraceW(0, L"HTTPSYS-IISEventTraceSession", *((PEVENT_TRACE_PROPERTIES *)this + 25));
  memset_0(*((void **)this + 25), 0, 0xB2u);
  **((_DWORD **)this + 25) = 178;
  *(_DWORD *)(*((_QWORD *)this + 25) + 44LL) = 0x20000;
  *(_DWORD *)(*((_QWORD *)this + 25) + 40LL) = 1;
  *(_OWORD *)(*((_QWORD *)this + 25) + 24LL) = xmmword_180013A18;
  *(_DWORD *)(*((_QWORD *)this + 25) + 64LL) = 268435712;
  *(_DWORD *)(*((_QWORD *)this + 25) + 68LL) = 3;
  *(_DWORD *)(*((_QWORD *)this + 25) + 60LL) = 30;
  *(_DWORD *)(*((_QWORD *)this + 25) + 116LL) = 120;
  *(_DWORD *)(*((_QWORD *)this + 25) + 112LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 25) + 48LL) = ReadDwordParameterValueFromAnyService(
                                                 L"System\\CurrentControlSet\\Services\\W3LogSvc\\Parameters",
                                                 L"ETWBufferSize",
                                                 0x400u);
  *(_DWORD *)(*((_QWORD *)this + 25) + 52LL) = ReadDwordParameterValueFromAnyService(
                                                 L"System\\CurrentControlSet\\Services\\W3LogSvc\\Parameters",
                                                 L"ETWMinBuffer",
                                                 4u);
  *(_DWORD *)(*((_QWORD *)this + 25) + 56LL) = ReadDwordParameterValueFromAnyService(
                                                 L"System\\CurrentControlSet\\Services\\W3LogSvc\\Parameters",
                                                 L"ETWMaxBuffer",
                                                 0x30u);
  started = StartTraceW(
              (PTRACEHANDLE)this + 1,
              L"HTTPSYS-IISEventTraceSession",
              *((PEVENT_TRACE_PROPERTIES *)this + 25));
  v3 = started;
  if ( started )
  {
    if ( started > 0 )
      v3 = (unsigned __int16)started | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
        346,
        "HTTP_LOG_EVENT_HANDLER::CreateEtwSession",
        v3,
        "StartTrace() failed\n");
  }
  else
  {
    v4 = EnableTraceEx2(*((_QWORD *)this + 1), &Buf1, 1u, 4u, 0, 0, 0, 0);
    v3 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
          371,
          "HTTP_LOG_EVENT_HANDLER::CreateEtwSession",
          v3,
          "EnableTraceEx2() failed\n");
    }
    else
    {
      v3 = 0;
      *(_DWORD *)this = 1;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000da70  mov     [rsp+arg_0], rbx
0x18000da75  mov     [rsp+arg_8], rsi
0x18000da7a  push    rdi
0x18000da7b  sub     rsp, 40h
0x18000da7f  mov     rdi, rcx
0x18000da82  mov     ebx, 0B2h
0x18000da87  mov     rcx, [rcx+0C8h]; void *
0x18000da8e  mov     r8d, ebx; Size
0x18000da91  xor     edx, edx; Val
0x18000da93  call    memset_0
0x18000da98  mov     rax, [rdi+0C8h]
0x18000da9f  lea     rdx, InstanceName; "HTTPSYS-IISEventTraceSession"
0x18000daa6  xor     ecx, ecx; TraceHandle
0x18000daa8  mov     [rax], ebx
0x18000daaa  mov     r8, [rdi+0C8h]; Properties
0x18000dab1  call    cs:__imp_StopTraceW
0x18000dab7  mov     rcx, [rdi+0C8h]; void *
0x18000dabe  mov     r8d, ebx; Size
0x18000dac1  xor     edx, edx; Val
0x18000dac3  call    memset_0
0x18000dac8  mov     rax, [rdi+0C8h]
0x18000dacf  lea     rdx, aEtwbuffersize; "ETWBufferSize"
0x18000dad6  movups  xmm0, cs:xmmword_180013A18
0x18000dadd  mov     r8d, 400h
0x18000dae3  mov     [rax], ebx
0x18000dae5  lea     rbx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\W3"...
0x18000daec  mov     rax, [rdi+0C8h]
0x18000daf3  mov     rcx, rbx
0x18000daf6  mov     dword ptr [rax+2Ch], 20000h
0x18000dafd  mov     rax, [rdi+0C8h]
0x18000db04  mov     dword ptr [rax+28h], 1
0x18000db0b  mov     rax, [rdi+0C8h]
0x18000db12  movdqu  xmmword ptr [rax+18h], xmm0
0x18000db17  mov     rax, [rdi+0C8h]
0x18000db1e  mov     dword ptr [rax+40h], 10000100h
0x18000db25  mov     rax, [rdi+0C8h]
0x18000db2c  mov     dword ptr [rax+44h], 3
0x18000db33  mov     rax, [rdi+0C8h]
0x18000db3a  mov     dword ptr [rax+3Ch], 1Eh
0x18000db41  mov     rax, [rdi+0C8h]
0x18000db48  mov     dword ptr [rax+74h], 78h ; 'x'
0x18000db4f  mov     rax, [rdi+0C8h]
0x18000db56  mov     dword ptr [rax+70h], 0
0x18000db5d  call    cs:__imp_?ReadDwordParameterValueFromAnyService@@YAKPEBG0K@Z; ReadDwordParameterValueFromAnyService(ushort const *,ushort const *,ulong)
0x18000db63  mov     rdx, [rdi+0C8h]
0x18000db6a  mov     r8d, 4
0x18000db70  mov     rcx, rbx
0x18000db73  mov     [rdx+30h], eax
0x18000db76  lea     rdx, aEtwminbuffer; "ETWMinBuffer"
0x18000db7d  call    cs:__imp_?ReadDwordParameterValueFromAnyService@@YAKPEBG0K@Z; ReadDwordParameterValueFromAnyService(ushort const *,ushort const *,ulong)
0x18000db83  mov     r8, [rdi+0C8h]
0x18000db8a  lea     rdx, aEtwmaxbuffer; "ETWMaxBuffer"
0x18000db91  mov     rcx, rbx
0x18000db94  mov     [r8+34h], eax
0x18000db98  mov     r8d, 30h ; '0'
0x18000db9e  call    cs:__imp_?ReadDwordParameterValueFromAnyService@@YAKPEBG0K@Z; ReadDwordParameterValueFromAnyService(ushort const *,ushort const *,ulong)
0x18000dba4  mov     rcx, [rdi+0C8h]
0x18000dbab  lea     rdx, InstanceName; "HTTPSYS-IISEventTraceSession"
0x18000dbb2  mov     [rcx+38h], eax
0x18000dbb5  lea     rcx, [rdi+8]; TraceHandle
0x18000dbb9  mov     r8, [rdi+0C8h]; Properties
0x18000dbc0  call    cs:__imp_StartTraceW
0x18000dbc6  mov     ebx, eax
0x18000dbc8  test    eax, eax
0x18000dbca  jz      short loc_18000DC17
0x18000dbcc  jle     short loc_18000DBD7
0x18000dbce  movzx   ebx, ax
0x18000dbd1  or      ebx, 80070000h
0x18000dbd7  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000dbde  jz      loc_18000DC88
0x18000dbe4  lea     rax, aStarttraceFail; "StartTrace() failed\n"
0x18000dbeb  mov     r8d, 15Ah
0x18000dbf1  mov     rcx, cs:g_pDebug
0x18000dbf8  lea     r9, aHttpLogEventHa_0; "HTTP_LOG_EVENT_HANDLER::CreateEtwSessio"...
0x18000dbff  mov     [rsp+48h+MatchAllKeyword], rax
0x18000dc04  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000dc0b  mov     dword ptr [rsp+48h+MatchAnyKeyword], ebx
0x18000dc0f  call    cs:__imp_PuDbgPrintError
0x18000dc15  jmp     short loc_18000DC88
0x18000dc17  mov     rcx, [rdi+8]; TraceHandle
0x18000dc1b  lea     rdx, Buf1; ProviderId
0x18000dc22  mov     [rsp+48h+EnableParameters], 0; EnableParameters
0x18000dc2b  mov     r9b, 4; Level
0x18000dc2e  mov     [rsp+48h+Timeout], 0; Timeout
0x18000dc36  mov     r8d, 1; ControlCode
0x18000dc3c  mov     [rsp+48h+MatchAllKeyword], 0; MatchAllKeyword
0x18000dc45  mov     [rsp+48h+MatchAnyKeyword], 0; MatchAnyKeyword
0x18000dc4e  call    cs:__imp_EnableTraceEx2
0x18000dc54  mov     ebx, eax
0x18000dc56  test    eax, eax
0x18000dc58  jz      short loc_18000DC80
0x18000dc5a  jle     short loc_18000DC65
0x18000dc5c  movzx   ebx, ax
0x18000dc5f  or      ebx, 80070000h
0x18000dc65  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000dc6c  jz      short loc_18000DC88
0x18000dc6e  lea     rax, aEnabletraceex2; "EnableTraceEx2() failed\n"
0x18000dc75  mov     r8d, 173h
0x18000dc7b  jmp     loc_18000DBF1
0x18000dc80  xor     ebx, ebx
0x18000dc82  mov     dword ptr [rdi], 1
0x18000dc88  mov     rsi, [rsp+48h+arg_8]
0x18000dc8d  mov     eax, ebx
0x18000dc8f  mov     rbx, [rsp+48h+arg_0]
0x18000dc94  add     rsp, 40h
0x18000dc98  pop     rdi
0x18000dc99  retn
```
