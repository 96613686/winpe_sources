# UpdatePendingServiceStatusCallback(void *,uchar)

- ea: `0x18000d520`
- end: `0x18000d600`
- name: `?UpdatePendingServiceStatusCallback@@YAXPEAXE@Z`
- size: `224`
- prototype: `void __fastcall(PVOID)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000cba8`
- `0x18000d520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d5a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d5a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d53b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d53b`
- `iisutil!PuDbgPrintError` at `0x18000d59b`
- `iisutil!PuDbgPrintError` at `0x18000d5e2`
- `iisutil!PuDbgPrintError` at `0x18000d59b`
- `iisutil!PuDbgPrintError` at `0x18000d5e2`

## string_xrefs

- `0x18000d594`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000d5db`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000d5be`: `Updating pending service status failed\n`
- `0x18000d5ca`: `UpdatePendingServiceStatusCallback`
- `0x18000d577`: `Could not report service status\n`
- `0x18000d583`: `LOG_SVC_ADMIN::UpdatePendingServiceStatus`

## pseudocode

```c
void __fastcall UpdatePendingServiceStatusCallback(PVOID a1)
{
  LOG_SVC_ADMIN *v1; // rbx
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  int v3; // ebx

  v1 = (LOG_SVC_ADMIN *)g_pLogSvcAdmin;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pLogSvcAdmin + 2008);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pLogSvcAdmin + 2008));
  if ( (unsigned int)(*((_DWORD *)v1 + 517) - 2) <= 1 )
  {
    ++*((_DWORD *)v1 + 521);
    v3 = LOG_SVC_ADMIN::ReportServiceStatus(v1);
    if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        1796,
        "LOG_SVC_ADMIN::UpdatePendingServiceStatus",
        v3,
        "Could not report service status\n");
  }
  else
  {
    v3 = 0;
  }
  LeaveCriticalSection(v2);
  if ( v3 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        992,
        "UpdatePendingServiceStatusCallback",
        v3,
        "Updating pending service status failed\n");
    *((_DWORD *)g_pLogSvcAdmin + 530) = v3;
  }
}

```

## disassembly

```asm
0x18000d520  mov     [rsp+arg_0], rbx
0x18000d525  push    rdi
0x18000d526  sub     rsp, 30h
0x18000d52a  mov     rbx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000d531  lea     rdi, [rbx+7D8h]
0x18000d538  mov     rcx, rdi; lpCriticalSection
0x18000d53b  call    cs:__imp_EnterCriticalSection
0x18000d541  mov     eax, [rbx+814h]
0x18000d547  sub     eax, 2
0x18000d54a  cmp     eax, 1
0x18000d54d  jbe     short loc_18000D553
0x18000d54f  xor     ebx, ebx
0x18000d551  jmp     short loc_18000D5A1
0x18000d553  inc     dword ptr [rbx+824h]
0x18000d559  mov     rcx, rbx; this
0x18000d55c  call    ?ReportServiceStatus@LOG_SVC_ADMIN@@AEAAJXZ; LOG_SVC_ADMIN::ReportServiceStatus(void)
0x18000d561  mov     ebx, eax
0x18000d563  test    eax, eax
0x18000d565  jns     short loc_18000D5A1
0x18000d567  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d56e  jz      short loc_18000D5A1
0x18000d570  mov     rcx, cs:g_pDebug
0x18000d577  lea     rax, aCouldNotReport; "Could not report service status\n"
0x18000d57e  mov     [rsp+38h+var_10], rax
0x18000d583  lea     r9, aLogSvcAdminUpd; "LOG_SVC_ADMIN::UpdatePendingServiceStat"...
0x18000d58a  mov     r8d, 704h
0x18000d590  mov     [rsp+38h+var_18], ebx
0x18000d594  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000d59b  call    cs:__imp_PuDbgPrintError
0x18000d5a1  mov     rcx, rdi; lpCriticalSection
0x18000d5a4  call    cs:__imp_LeaveCriticalSection
0x18000d5aa  test    ebx, ebx
0x18000d5ac  jns     short loc_18000D5F5
0x18000d5ae  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d5b5  jz      short loc_18000D5E8
0x18000d5b7  mov     rcx, cs:g_pDebug
0x18000d5be  lea     rax, aUpdatingPendin; "Updating pending service status failed"...
0x18000d5c5  mov     [rsp+38h+var_10], rax
0x18000d5ca  lea     r9, aUpdatependings; "UpdatePendingServiceStatusCallback"
0x18000d5d1  mov     r8d, 3E0h
0x18000d5d7  mov     [rsp+38h+var_18], ebx
0x18000d5db  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000d5e2  call    cs:__imp_PuDbgPrintError
0x18000d5e8  mov     rax, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000d5ef  mov     [rax+848h], ebx
0x18000d5f5  mov     rbx, [rsp+38h+arg_0]
0x18000d5fa  add     rsp, 30h
0x18000d5fe  pop     rdi
0x18000d5ff  retn
```
