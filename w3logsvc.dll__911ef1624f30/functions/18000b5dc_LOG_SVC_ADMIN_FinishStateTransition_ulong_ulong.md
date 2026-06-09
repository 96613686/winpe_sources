# LOG_SVC_ADMIN::FinishStateTransition(ulong,ulong)

- ea: `0x18000b5dc`
- end: `0x18000b6e8`
- name: `?FinishStateTransition@LOG_SVC_ADMIN@@AEAAJKK@Z`
- size: `268`
- prototype: `__int64 __fastcall(LOG_SVC_ADMIN *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cf98`

## callees

- `0x18000b290`
- `0x18000b5dc`
- `0x18000cba8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b655`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b655`
- `iisutil!PuDbgPrintError` at `0x18000b640`
- `iisutil!PuDbgPrintError` at `0x18000b6c7`
- `iisutil!PuDbgPrintError` at `0x18000b640`
- `iisutil!PuDbgPrintError` at `0x18000b6c7`

## string_xrefs

- `0x18000b639`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000b6c0`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000b6a3`: `Could not update service status\n`

## pseudocode

```c
__int64 __fastcall LOG_SVC_ADMIN::FinishStateTransition(LOG_SVC_ADMIN *this)
{
  int v1; // edi

  v1 = 0;
  if ( *((_DWORD *)this + 517) == 2 )
  {
    v1 = LOG_SVC_ADMIN::CancelPendingServiceStatusTimer(this);
    if ( v1 >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2008));
      *((_DWORD *)this + 518) = 5;
      *((_DWORD *)this + 517) = 4;
      *(_QWORD *)((char *)this + 2076) = 0;
      *(_QWORD *)((char *)this + 2084) = 0;
      v1 = LOG_SVC_ADMIN::ReportServiceStatus(this);
      if ( v1 < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
          1670,
          "LOG_SVC_ADMIN::FinishStateTransition",
          v1,
          "Could not update service status\n");
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2008));
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        1638,
        "LOG_SVC_ADMIN::FinishStateTransition",
        v1,
        "Could not cancel timer\n");
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000b5dc  mov     [rsp+arg_0], rbx
0x18000b5e1  mov     [rsp+arg_8], rsi
0x18000b5e6  push    rdi
0x18000b5e7  sub     rsp, 30h
0x18000b5eb  xor     edi, edi
0x18000b5ed  mov     rbx, rcx
0x18000b5f0  cmp     dword ptr [rcx+814h], 2
0x18000b5f7  jnz     loc_18000B6D6
0x18000b5fd  call    ?CancelPendingServiceStatusTimer@LOG_SVC_ADMIN@@AEAAJXZ; LOG_SVC_ADMIN::CancelPendingServiceStatusTimer(void)
0x18000b602  mov     edi, eax
0x18000b604  test    eax, eax
0x18000b606  jns     short loc_18000B64B
0x18000b608  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000b60f  jz      loc_18000B6D6
0x18000b615  mov     rcx, cs:g_pDebug
0x18000b61c  lea     rax, aCouldNotCancel_0; "Could not cancel timer\n"
0x18000b623  mov     [rsp+38h+var_10], rax
0x18000b628  lea     r9, aLogSvcAdminFin; "LOG_SVC_ADMIN::FinishStateTransition"
0x18000b62f  mov     r8d, 666h
0x18000b635  mov     [rsp+38h+var_18], edi
0x18000b639  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000b640  call    cs:__imp_PuDbgPrintError
0x18000b646  jmp     loc_18000B6D6
0x18000b64b  lea     rsi, [rbx+7D8h]
0x18000b652  mov     rcx, rsi; lpCriticalSection
0x18000b655  call    cs:__imp_EnterCriticalSection
0x18000b65b  mov     rcx, rbx; this
0x18000b65e  mov     dword ptr [rbx+818h], 5
0x18000b668  mov     dword ptr [rbx+814h], 4
0x18000b672  mov     qword ptr [rbx+81Ch], 0
0x18000b67d  mov     qword ptr [rbx+824h], 0
0x18000b688  call    ?ReportServiceStatus@LOG_SVC_ADMIN@@AEAAJXZ; LOG_SVC_ADMIN::ReportServiceStatus(void)
0x18000b68d  mov     edi, eax
0x18000b68f  test    eax, eax
0x18000b691  jns     short loc_18000B6CD
0x18000b693  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000b69a  jz      short loc_18000B6CD
0x18000b69c  mov     rcx, cs:g_pDebug
0x18000b6a3  lea     rax, aCouldNotUpdate; "Could not update service status\n"
0x18000b6aa  mov     [rsp+38h+var_10], rax
0x18000b6af  lea     r9, aLogSvcAdminFin; "LOG_SVC_ADMIN::FinishStateTransition"
0x18000b6b6  mov     r8d, 686h
0x18000b6bc  mov     [rsp+38h+var_18], edi
0x18000b6c0  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000b6c7  call    cs:__imp_PuDbgPrintError
0x18000b6cd  mov     rcx, rsi; lpCriticalSection
0x18000b6d0  call    cs:__imp_LeaveCriticalSection
0x18000b6d6  mov     rbx, [rsp+38h+arg_0]
0x18000b6db  mov     eax, edi
0x18000b6dd  mov     rsi, [rsp+38h+arg_8]
0x18000b6e2  add     rsp, 30h
0x18000b6e6  pop     rdi
0x18000b6e7  retn
```
