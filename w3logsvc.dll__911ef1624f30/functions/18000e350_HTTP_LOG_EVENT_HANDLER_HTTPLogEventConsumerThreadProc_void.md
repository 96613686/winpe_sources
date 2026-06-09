# HTTP_LOG_EVENT_HANDLER::HTTPLogEventConsumerThreadProc(void *)

- ea: `0x18000e350`
- end: `0x18000e3bc`
- name: `?HTTPLogEventConsumerThreadProc@HTTP_LOG_EVENT_HANDLER@@CAKPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(ULONG64 *Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e350`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18000e361`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18000e361`
- `iisutil!PuDbgPrintError` at `0x18000e3ae`
- `iisutil!PuDbgPrintError` at `0x18000e3ae`

## string_xrefs

- `0x18000e3a7`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\http_log_event_handler.cxx`
- `0x18000e396`: `HTTP_LOG_EVENT_HANDLER::HTTPLogEventConsumerThreadProc`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_EVENT_HANDLER::HTTPLogEventConsumerThreadProc(ULONG64 *Parameter)
{
  unsigned int v1; // ebx
  signed int v2; // eax

  v1 = 0;
  v2 = ProcessTrace(Parameter, 1u, 0, 0);
  if ( v2 )
  {
    if ( v2 > 0 )
      v1 = (unsigned __int16)v2 | 0x80070000;
    else
      v1 = v2;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
        766,
        "HTTP_LOG_EVENT_HANDLER::HTTPLogEventConsumerThreadProc",
        v1,
        "ProcessTrace() failed\n");
  }
  return v1;
}

```

## disassembly

```asm
0x18000e350  push    rbx
0x18000e352  sub     rsp, 30h
0x18000e356  xor     ebx, ebx
0x18000e358  xor     r9d, r9d; EndTime
0x18000e35b  xor     r8d, r8d; StartTime
0x18000e35e  lea     edx, [rbx+1]; HandleCount
0x18000e361  call    cs:__imp_ProcessTrace
0x18000e367  test    eax, eax
0x18000e369  jz      short loc_18000E3B4
0x18000e36b  jg      short loc_18000E371
0x18000e36d  mov     ebx, eax
0x18000e36f  jmp     short loc_18000E37A
0x18000e371  movzx   ebx, ax
0x18000e374  or      ebx, 80070000h
0x18000e37a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000e381  jz      short loc_18000E3B4
0x18000e383  mov     rcx, cs:g_pDebug
0x18000e38a  lea     rax, aProcesstraceFa; "ProcessTrace() failed\n"
0x18000e391  mov     [rsp+38h+var_10], rax
0x18000e396  lea     r9, aHttpLogEventHa_4; "HTTP_LOG_EVENT_HANDLER::HTTPLogEventCon"...
0x18000e39d  mov     r8d, 2FEh
0x18000e3a3  mov     [rsp+38h+var_18], ebx
0x18000e3a7  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000e3ae  call    cs:__imp_PuDbgPrintError
0x18000e3b4  mov     eax, ebx
0x18000e3b6  add     rsp, 30h
0x18000e3ba  pop     rbx
0x18000e3bb  retn
```
