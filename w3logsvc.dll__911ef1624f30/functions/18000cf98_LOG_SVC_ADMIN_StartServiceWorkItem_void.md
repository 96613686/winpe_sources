# LOG_SVC_ADMIN::StartServiceWorkItem(void)

- ea: `0x18000cf98`
- end: `0x18000d081`
- name: `?StartServiceWorkItem@LOG_SVC_ADMIN@@AEAAJXZ`
- size: `233`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b560`

## callees

- `0x18000b154`
- `0x18000b5dc`
- `0x18000bfc0`
- `0x18000cf98`
- `0x18000d088`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d046`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d046`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000d066`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000d066`
- `iisutil!PuDbgPrintError` at `0x18000d039`
- `iisutil!PuDbgPrintError` at `0x18000d039`

## string_xrefs

- `0x18000d02e`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000cfbd`: `Initializing internal components failed\n`
- `0x18000d022`: `LOG_SVC_ADMIN::StartServiceWorkItem`
- `0x18000cfe8`: `couldn't transition to service start pending\n`

## pseudocode

```c
__int64 __fastcall LOG_SVC_ADMIN::StartServiceWorkItem(HANDLE *this)
{
  signed int v2; // ebx

  v2 = LOG_SVC_ADMIN::InitializeInternalComponents((LOG_SVC_ADMIN *)this);
  if ( v2 >= 0 )
  {
    v2 = LOG_SVC_ADMIN::BeginStateTransition((LOG_SVC_ADMIN *)this, 2);
    if ( v2 >= 0 )
    {
      v2 = LOG_SVC_ADMIN::FinishStateTransition((LOG_SVC_ADMIN *)this);
      if ( v2 < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
          566,
          "LOG_SVC_ADMIN::StartServiceWorkItem",
          v2,
          "Couldn't finish transition into the running state\n");
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        554,
        "LOG_SVC_ADMIN::StartServiceWorkItem",
        v2,
        "couldn't transition to service start pending\n");
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
      541,
      "LOG_SVC_ADMIN::StartServiceWorkItem",
      v2,
      "Initializing internal components failed\n");
  }
  SetEvent(this[262]);
  if ( v2 < 0 )
  {
    EVENT_LOG::LogEvent((EVENT_LOG *)(this + 237), 0xC0001771, 0, 0, v2);
    LOG_SVC_ADMIN::StopServiceWorkItem((LOG_SVC_ADMIN *)this);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000cf98  mov     [rsp+arg_0], rbx
0x18000cf9d  push    rdi
0x18000cf9e  sub     rsp, 30h
0x18000cfa2  mov     rdi, rcx
0x18000cfa5  call    ?InitializeInternalComponents@LOG_SVC_ADMIN@@AEAAJXZ; LOG_SVC_ADMIN::InitializeInternalComponents(void)
0x18000cfaa  mov     ebx, eax
0x18000cfac  test    eax, eax
0x18000cfae  jns     short loc_18000CFCC
0x18000cfb0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000cfb7  jz      loc_18000D03F
0x18000cfbd  lea     rax, aInitializingIn; "Initializing internal components failed"...
0x18000cfc4  mov     r8d, 21Dh
0x18000cfca  jmp     short loc_18000D01B
0x18000cfcc  mov     edx, 2; unsigned int
0x18000cfd1  mov     rcx, rdi; this
0x18000cfd4  call    ?BeginStateTransition@LOG_SVC_ADMIN@@AEAAJK@Z; LOG_SVC_ADMIN::BeginStateTransition(ulong)
0x18000cfd9  mov     ebx, eax
0x18000cfdb  test    eax, eax
0x18000cfdd  jns     short loc_18000CFF7
0x18000cfdf  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000cfe6  jz      short loc_18000D03F
0x18000cfe8  lea     rax, aCouldnTTransit_0; "couldn't transition to service start pe"...
0x18000cfef  mov     r8d, 22Ah
0x18000cff5  jmp     short loc_18000D01B
0x18000cff7  mov     rcx, rdi; this
0x18000cffa  call    ?FinishStateTransition@LOG_SVC_ADMIN@@AEAAJKK@Z; LOG_SVC_ADMIN::FinishStateTransition(ulong,ulong)
0x18000cfff  mov     ebx, eax
0x18000d001  test    eax, eax
0x18000d003  jns     short loc_18000D03F
0x18000d005  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d00c  jz      short loc_18000D03F
0x18000d00e  lea     rax, aCouldnTFinishT; "Couldn't finish transition into the run"...
0x18000d015  mov     r8d, 236h
0x18000d01b  mov     rcx, cs:g_pDebug
0x18000d022  lea     r9, aLogSvcAdminSta; "LOG_SVC_ADMIN::StartServiceWorkItem"
0x18000d029  mov     [rsp+38h+var_10], rax
0x18000d02e  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000d035  mov     [rsp+38h+var_18], ebx
0x18000d039  call    cs:__imp_PuDbgPrintError
0x18000d03f  mov     rcx, [rdi+830h]; hEvent
0x18000d046  call    cs:__imp_SetEvent
0x18000d04c  test    ebx, ebx
0x18000d04e  jns     short loc_18000D074
0x18000d050  xor     r8d, r8d
0x18000d053  mov     [rsp+38h+var_18], ebx
0x18000d057  lea     rcx, [rdi+768h]
0x18000d05e  xor     r9d, r9d
0x18000d061  mov     edx, 0C0001771h
0x18000d066  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000d06c  mov     rcx, rdi; this
0x18000d06f  call    ?StopServiceWorkItem@LOG_SVC_ADMIN@@AEAAXXZ; LOG_SVC_ADMIN::StopServiceWorkItem(void)
0x18000d074  mov     eax, ebx
0x18000d076  mov     rbx, [rsp+38h+arg_0]
0x18000d07b  add     rsp, 30h
0x18000d07f  pop     rdi
0x18000d080  retn
```
