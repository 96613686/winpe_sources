# HTTP_LOG_EVENT_HANDLER::DeleteEtwSession(void)

- ea: `0x18000de64`
- end: `0x18000df55`
- name: `?DeleteEtwSession@HTTP_LOG_EVENT_HANDLER@@AEAAJXZ`
- size: `241`
- prototype: `__int64 __fastcall(HTTP_LOG_EVENT_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e400`

## callees

- `0x18000de64`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18000dea6`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18000dea6`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18000deef`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18000deef`
- `iisutil!PuDbgPrintError` at `0x18000df3c`
- `iisutil!PuDbgPrintError` at `0x18000df3c`

## string_xrefs

- `0x18000df31`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\http_log_event_handler.cxx`
- `0x18000df25`: `HTTP_LOG_EVENT_HANDLER::DeleteEtwSession`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_EVENT_HANDLER::DeleteEtwSession(HTTP_LOG_EVENT_HANDLER *this)
{
  unsigned int v1; // ebx
  TRACEHANDLE v3; // rcx
  signed int v4; // eax
  signed int v5; // eax
  __int64 result; // rax

  v1 = 0;
  if ( *(_DWORD *)this )
  {
    v3 = *((_QWORD *)this + 1);
    if ( v3 )
    {
      v4 = EnableTraceEx2(v3, &Buf1, 0, 4u, 0, 0, 0, 0);
      if ( v4 )
      {
        if ( v4 > 0 )
          v1 = (unsigned __int16)v4 | 0x80070000;
        else
          v1 = v4;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
            427,
            "HTTP_LOG_EVENT_HANDLER::DeleteEtwSession",
            v1,
            "EnableTraceEx2() failed\n");
      }
      else
      {
        v5 = ControlTraceW(
               *((_QWORD *)this + 1),
               L"HTTPSYS-IISEventTraceSession",
               *((PEVENT_TRACE_PROPERTIES *)this + 25),
               1u);
        if ( v5 )
        {
          v1 = v5 > 0 ? (unsigned __int16)v5 | 0x80070000 : v5;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
              445,
              "HTTP_LOG_EVENT_HANDLER::DeleteEtwSession",
              v1,
              "ControlTrace() failed\n");
        }
      }
    }
  }
  result = v1;
  *(_DWORD *)this = 0;
  return result;
}

```

## disassembly

```asm
0x18000de64  mov     rax, rsp
0x18000de67  mov     [rax+8], rbx
0x18000de6b  push    rdi
0x18000de6c  sub     rsp, 40h
0x18000de70  xor     ebx, ebx
0x18000de72  mov     rdi, rcx
0x18000de75  cmp     [rcx], ebx
0x18000de77  jz      loc_18000DF42
0x18000de7d  mov     rcx, [rcx+8]; TraceHandle
0x18000de81  test    rcx, rcx
0x18000de84  jz      loc_18000DF42
0x18000de8a  mov     [rax-10h], rbx
0x18000de8e  lea     rdx, Buf1; ProviderId
0x18000de95  mov     [rax-18h], ebx
0x18000de98  mov     r9b, 4; Level
0x18000de9b  mov     [rax-20h], rbx
0x18000de9f  xor     r8d, r8d; ControlCode
0x18000dea2  mov     [rax-28h], rbx
0x18000dea6  call    cs:__imp_EnableTraceEx2
0x18000deac  test    eax, eax
0x18000deae  jz      short loc_18000DED7
0x18000deb0  jg      short loc_18000DEB6
0x18000deb2  mov     ebx, eax
0x18000deb4  jmp     short loc_18000DEBF
0x18000deb6  movzx   ebx, ax
0x18000deb9  or      ebx, 80070000h
0x18000debf  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000dec6  jz      short loc_18000DF42
0x18000dec8  lea     rax, aEnabletraceex2; "EnableTraceEx2() failed\n"
0x18000decf  mov     r8d, 1ABh
0x18000ded5  jmp     short loc_18000DF1E
0x18000ded7  mov     r8, [rdi+0C8h]; Properties
0x18000dede  lea     rdx, InstanceName; "HTTPSYS-IISEventTraceSession"
0x18000dee5  mov     rcx, [rdi+8]; TraceHandle
0x18000dee9  mov     r9d, 1; ControlCode
0x18000deef  call    cs:__imp_ControlTraceW
0x18000def5  test    eax, eax
0x18000def7  jz      short loc_18000DF42
0x18000def9  jg      short loc_18000DEFF
0x18000defb  mov     ebx, eax
0x18000defd  jmp     short loc_18000DF08
0x18000deff  movzx   ebx, ax
0x18000df02  or      ebx, 80070000h
0x18000df08  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000df0f  jz      short loc_18000DF42
0x18000df11  lea     rax, aControltraceFa; "ControlTrace() failed\n"
0x18000df18  mov     r8d, 1BDh
0x18000df1e  mov     rcx, cs:g_pDebug
0x18000df25  lea     r9, aHttpLogEventHa_2; "HTTP_LOG_EVENT_HANDLER::DeleteEtwSessio"...
0x18000df2c  mov     [rsp+48h+var_20], rax
0x18000df31  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000df38  mov     [rsp+48h+var_28], ebx
0x18000df3c  call    cs:__imp_PuDbgPrintError
0x18000df42  mov     eax, ebx
0x18000df44  mov     dword ptr [rdi], 0
0x18000df4a  mov     rbx, [rsp+48h+arg_0]
0x18000df4f  add     rsp, 40h
0x18000df53  pop     rdi
0x18000df54  retn
```
