# HTTP_LOG_EVENT_HANDLER::DeleteEtwConsumer(void)

- ea: `0x18000dd54`
- end: `0x18000de5b`
- name: `?DeleteEtwConsumer@HTTP_LOG_EVENT_HANDLER@@AEAAJXZ`
- size: `263`
- prototype: `__int64 __fastcall(HTTP_LOG_EVENT_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e400`

## callees

- `0x18000dd54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dde7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dde7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000dddc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000dddc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de3d`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18000dd68`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18000dd68`
- `iisutil!PuDbgPrintError` at `0x18000ddc0`
- `iisutil!PuDbgPrintError` at `0x18000de30`
- `iisutil!PuDbgPrintError` at `0x18000ddc0`
- `iisutil!PuDbgPrintError` at `0x18000de30`

## string_xrefs

- `0x18000ddb9`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\http_log_event_handler.cxx`
- `0x18000de29`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\http_log_event_handler.cxx`
- `0x18000dda8`: `HTTP_LOG_EVENT_HANDLER::DeleteEtwConsumer`
- `0x18000de18`: `HTTP_LOG_EVENT_HANDLER::DeleteEtwConsumer`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_EVENT_HANDLER::DeleteEtwConsumer(HTTP_LOG_EVENT_HANDLER *this)
{
  signed int v2; // eax
  unsigned int v3; // ebx
  void *v4; // rcx
  signed int LastError; // eax

  v2 = CloseTrace(*((_QWORD *)this + 26));
  v3 = v2;
  if ( !v2 || v2 == 7007 )
  {
    v4 = (void *)*((_QWORD *)this + 27);
    v3 = 0;
    if ( v4 )
    {
      if ( WaitForSingleObject(v4, 0xFFFFFFFF) == -1 )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
            606,
            "HTTP_LOG_EVENT_HANDLER::DeleteEtwConsumer",
            v3,
            "WaitForSingleObject() failed\n");
      }
      CloseHandle(*((HANDLE *)this + 27));
      *((_QWORD *)this + 27) = 0;
    }
  }
  else
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\http_log_event_handler.cxx",
        595,
        "HTTP_LOG_EVENT_HANDLER::DeleteEtwConsumer",
        v3,
        "CloseTrace() failed\n");
  }
  return v3;
}

```

## disassembly

```asm
0x18000dd54  mov     [rsp+arg_0], rbx
0x18000dd59  push    rdi
0x18000dd5a  sub     rsp, 30h
0x18000dd5e  mov     rdi, rcx
0x18000dd61  mov     rcx, [rcx+0D0h]; TraceHandle
0x18000dd68  call    cs:__imp_CloseTrace
0x18000dd6e  mov     ebx, eax
0x18000dd70  test    eax, eax
0x18000dd72  jz      short loc_18000DDCB
0x18000dd74  cmp     eax, 1B5Fh
0x18000dd79  jz      short loc_18000DDCB
0x18000dd7b  test    eax, eax
0x18000dd7d  jle     short loc_18000DD88
0x18000dd7f  movzx   ebx, ax
0x18000dd82  or      ebx, 80070000h
0x18000dd88  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000dd8f  jz      loc_18000DE4E
0x18000dd95  mov     rcx, cs:g_pDebug
0x18000dd9c  lea     rax, aClosetraceFail; "CloseTrace() failed\n"
0x18000dda3  mov     [rsp+38h+var_10], rax
0x18000dda8  lea     r9, aHttpLogEventHa_5; "HTTP_LOG_EVENT_HANDLER::DeleteEtwConsum"...
0x18000ddaf  mov     r8d, 253h
0x18000ddb5  mov     [rsp+38h+var_18], ebx
0x18000ddb9  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000ddc0  call    cs:__imp_PuDbgPrintError
0x18000ddc6  jmp     loc_18000DE4E
0x18000ddcb  mov     rcx, [rdi+0D8h]; hHandle
0x18000ddd2  xor     ebx, ebx
0x18000ddd4  test    rcx, rcx
0x18000ddd7  jz      short loc_18000DE4E
0x18000ddd9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000dddc  call    cs:__imp_WaitForSingleObject
0x18000dde2  cmp     eax, 0FFFFFFFFh
0x18000dde5  jnz     short loc_18000DE36
0x18000dde7  call    cs:__imp_GetLastError
0x18000dded  mov     ebx, eax
0x18000ddef  test    eax, eax
0x18000ddf1  jle     short loc_18000DDFC
0x18000ddf3  movzx   ebx, ax
0x18000ddf6  or      ebx, 80070000h
0x18000ddfc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000de03  jz      short loc_18000DE36
0x18000de05  mov     rcx, cs:g_pDebug
0x18000de0c  lea     rax, aWaitforsingleo; "WaitForSingleObject() failed\n"
0x18000de13  mov     [rsp+38h+var_10], rax
0x18000de18  lea     r9, aHttpLogEventHa_5; "HTTP_LOG_EVENT_HANDLER::DeleteEtwConsum"...
0x18000de1f  mov     r8d, 25Eh
0x18000de25  mov     [rsp+38h+var_18], ebx
0x18000de29  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000de30  call    cs:__imp_PuDbgPrintError
0x18000de36  mov     rcx, [rdi+0D8h]; hObject
0x18000de3d  call    cs:__imp_CloseHandle
0x18000de43  mov     qword ptr [rdi+0D8h], 0
0x18000de4e  mov     eax, ebx
0x18000de50  mov     rbx, [rsp+38h+arg_0]
0x18000de55  add     rsp, 30h
0x18000de59  pop     rdi
0x18000de5a  retn
```
