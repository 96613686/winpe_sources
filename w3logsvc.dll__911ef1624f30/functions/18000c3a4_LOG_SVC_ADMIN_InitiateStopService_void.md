# LOG_SVC_ADMIN::InitiateStopService(void)

- ea: `0x18000c3a4`
- end: `0x18000c466`
- name: `?InitiateStopService@LOG_SVC_ADMIN@@QEAAJXZ`
- size: `194`
- prototype: `__int64 __fastcall(LOG_SVC_ADMIN *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000cc70`

## callees

- `0x18000b154`
- `0x18000c3a4`
- `0x18000e4c4`

## import_xrefs

- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000c453`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000c453`
- `iisutil!PuDbgPrintError` at `0x18000c437`
- `iisutil!PuDbgPrintError` at `0x18000c437`

## string_xrefs

- `0x18000c42c`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000c3d9`: `Couldn't transition to service stop pending\n`
- `0x18000c420`: `LOG_SVC_ADMIN::InitiateStopService`
- `0x18000c40c`: `Couldn't queue StopLogServiceWorkItem\n`

## pseudocode

```c
__int64 __fastcall LOG_SVC_ADMIN::InitiateStopService(LOG_SVC_ADMIN *this)
{
  signed int v3; // ebx

  if ( *((_DWORD *)this + 517) == 3 )
    return 0;
  v3 = LOG_SVC_ADMIN::BeginStateTransition(this, 3);
  if ( v3 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        1364,
        "LOG_SVC_ADMIN::InitiateStopService",
        v3,
        "Couldn't transition to service stop pending\n");
LABEL_9:
    EVENT_LOG::LogEvent((LOG_SVC_ADMIN *)((char *)this + 1896), 0xC0001777, 0, 0, v3);
    return (unsigned int)v3;
  }
  v3 = MULTI_WORK_QUEUE::GetAndQueueWorkItem((LOG_SVC_ADMIN *)((char *)this + 1584), this, 2);
  if ( v3 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        1378,
        "LOG_SVC_ADMIN::InitiateStopService",
        v3,
        "Couldn't queue StopLogServiceWorkItem\n");
    goto LABEL_9;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000c3a4  mov     [rsp+arg_0], rbx
0x18000c3a9  push    rdi
0x18000c3aa  sub     rsp, 30h
0x18000c3ae  mov     edx, 3; unsigned int
0x18000c3b3  mov     rdi, rcx
0x18000c3b6  cmp     [rcx+814h], edx
0x18000c3bc  jnz     short loc_18000C3C5
0x18000c3be  xor     eax, eax
0x18000c3c0  jmp     loc_18000C45B
0x18000c3c5  call    ?BeginStateTransition@LOG_SVC_ADMIN@@AEAAJK@Z; LOG_SVC_ADMIN::BeginStateTransition(ulong)
0x18000c3ca  mov     ebx, eax
0x18000c3cc  test    eax, eax
0x18000c3ce  jns     short loc_18000C3E8
0x18000c3d0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000c3d7  jz      short loc_18000C43D
0x18000c3d9  lea     rax, aCouldnTTransit; "Couldn't transition to service stop pen"...
0x18000c3e0  mov     r8d, 554h
0x18000c3e6  jmp     short loc_18000C419
0x18000c3e8  lea     rcx, [rdi+630h]; this
0x18000c3ef  mov     r8d, 2; unsigned __int64
0x18000c3f5  mov     rdx, rdi; struct MULTI_WORK_DISPATCH *
0x18000c3f8  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x18000c3fd  mov     ebx, eax
0x18000c3ff  test    eax, eax
0x18000c401  jns     short loc_18000C459
0x18000c403  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000c40a  jz      short loc_18000C43D
0x18000c40c  lea     rax, aCouldnTQueueSt; "Couldn't queue StopLogServiceWorkItem\n"
0x18000c413  mov     r8d, 562h
0x18000c419  mov     rcx, cs:g_pDebug
0x18000c420  lea     r9, aLogSvcAdminIni_1; "LOG_SVC_ADMIN::InitiateStopService"
0x18000c427  mov     [rsp+38h+var_10], rax
0x18000c42c  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000c433  mov     [rsp+38h+var_18], ebx
0x18000c437  call    cs:__imp_PuDbgPrintError
0x18000c43d  xor     r8d, r8d
0x18000c440  mov     [rsp+38h+var_18], ebx
0x18000c444  lea     rcx, [rdi+768h]
0x18000c44b  xor     r9d, r9d
0x18000c44e  mov     edx, 0C0001777h
0x18000c453  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000c459  mov     eax, ebx
0x18000c45b  mov     rbx, [rsp+38h+arg_0]
0x18000c460  add     rsp, 30h
0x18000c464  pop     rdi
0x18000c465  retn
```
