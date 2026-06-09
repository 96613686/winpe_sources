# ServiceControlHandler(ulong)

- ea: `0x18000cc70`
- end: `0x18000cdb4`
- name: `?ServiceControlHandler@@YAXK@Z`
- size: `324`
- prototype: `void __fastcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000c3a4`
- `0x18000cba8`
- `0x18000cc70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cd38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cd38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cce7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cce7`
- `iisutil!PuDbgPrint` at `0x18000cccb`
- `iisutil!PuDbgPrint` at `0x18000cccb`
- `iisutil!PuDbgPrintError` at `0x18000cd2f`
- `iisutil!PuDbgPrintError` at `0x18000cd96`
- `iisutil!PuDbgPrintError` at `0x18000cd2f`
- `iisutil!PuDbgPrintError` at `0x18000cd96`

## string_xrefs

- `0x18000ccc4`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000cd28`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000cd8f`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000cca4`: `Service control ignored, OpCode: %lu\n`
- `0x18000ccb2`: `ServiceControlHandler`
- `0x18000cd7e`: `ServiceControlHandler`
- `0x18000cd72`: `Service control operation failed\n`
- `0x18000cd0b`: `Couldn't report the service status\n`
- `0x18000cd17`: `LOG_SVC_ADMIN::InterrogateService`

## pseudocode

```c
void __fastcall ServiceControlHandler(DWORD dwControl)
{
  LOG_SVC_ADMIN *v1; // rbx
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  int v3; // ebx

  if ( dwControl != 1 )
  {
    if ( dwControl == 4 )
    {
      v1 = (LOG_SVC_ADMIN *)g_pLogSvcAdmin;
      v2 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pLogSvcAdmin + 2008);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pLogSvcAdmin + 2008));
      v3 = LOG_SVC_ADMIN::ReportServiceStatus(v1);
      if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
          1327,
          "LOG_SVC_ADMIN::InterrogateService",
          v3,
          "Couldn't report the service status\n");
      LeaveCriticalSection(v2);
      goto LABEL_11;
    }
    if ( dwControl != 5 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
          1044,
          "ServiceControlHandler",
          "Service control ignored, OpCode: %lu\n",
          dwControl);
      return;
    }
  }
  v3 = LOG_SVC_ADMIN::InitiateStopService((LOG_SVC_ADMIN *)g_pLogSvcAdmin);
LABEL_11:
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -2147023835 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        1062,
        "ServiceControlHandler",
        v3,
        "Service control operation failed\n");
    *((_DWORD *)g_pLogSvcAdmin + 530) = v3;
  }
}

```

## disassembly

```asm
0x18000cc70  mov     [rsp+arg_0], rbx
0x18000cc75  push    rdi
0x18000cc76  sub     rsp, 30h
0x18000cc7a  mov     eax, ecx
0x18000cc7c  sub     eax, 1
0x18000cc7f  jz      loc_18000CD40
0x18000cc85  sub     eax, 3
0x18000cc88  jz      short loc_18000CCD6
0x18000cc8a  cmp     eax, 1
0x18000cc8d  jz      loc_18000CD40
0x18000cc93  test    byte ptr cs:g_dwDebugFlags, 3
0x18000cc9a  jz      loc_18000CDA9
0x18000cca0  mov     dword ptr [rsp+38h+var_10], ecx
0x18000cca4  lea     rax, aServiceControl_0; "Service control ignored, OpCode: %lu\n"
0x18000ccab  mov     rcx, cs:g_pDebug
0x18000ccb2  lea     r9, aServicecontrol; "ServiceControlHandler"
0x18000ccb9  mov     r8d, 414h
0x18000ccbf  mov     [rsp+38h+var_18], rax
0x18000ccc4  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000cccb  call    cs:__imp_PuDbgPrint
0x18000ccd1  jmp     loc_18000CDA9
0x18000ccd6  mov     rbx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000ccdd  lea     rdi, [rbx+7D8h]
0x18000cce4  mov     rcx, rdi; lpCriticalSection
0x18000cce7  call    cs:__imp_EnterCriticalSection
0x18000cced  mov     rcx, rbx; this
0x18000ccf0  call    ?ReportServiceStatus@LOG_SVC_ADMIN@@AEAAJXZ; LOG_SVC_ADMIN::ReportServiceStatus(void)
0x18000ccf5  mov     ebx, eax
0x18000ccf7  test    eax, eax
0x18000ccf9  jns     short loc_18000CD35
0x18000ccfb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000cd02  jz      short loc_18000CD35
0x18000cd04  mov     rcx, cs:g_pDebug
0x18000cd0b  lea     rax, aCouldnTReportT; "Couldn't report the service status\n"
0x18000cd12  mov     [rsp+38h+var_10], rax
0x18000cd17  lea     r9, aLogSvcAdminInt; "LOG_SVC_ADMIN::InterrogateService"
0x18000cd1e  mov     r8d, 52Fh
0x18000cd24  mov     dword ptr [rsp+38h+var_18], ebx
0x18000cd28  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000cd2f  call    cs:__imp_PuDbgPrintError
0x18000cd35  mov     rcx, rdi; lpCriticalSection
0x18000cd38  call    cs:__imp_LeaveCriticalSection
0x18000cd3e  jmp     short loc_18000CD4E
0x18000cd40  mov     rcx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; this
0x18000cd47  call    ?InitiateStopService@LOG_SVC_ADMIN@@QEAAJXZ; LOG_SVC_ADMIN::InitiateStopService(void)
0x18000cd4c  mov     ebx, eax
0x18000cd4e  mov     eax, 80000000h
0x18000cd53  lea     ecx, [rbx+rax]
0x18000cd56  test    eax, ecx
0x18000cd58  jnz     short loc_18000CDA9
0x18000cd5a  cmp     ebx, 80070425h
0x18000cd60  jz      short loc_18000CDA9
0x18000cd62  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000cd69  jz      short loc_18000CD9C
0x18000cd6b  mov     rcx, cs:g_pDebug
0x18000cd72  lea     rax, aServiceControl; "Service control operation failed\n"
0x18000cd79  mov     [rsp+38h+var_10], rax
0x18000cd7e  lea     r9, aServicecontrol; "ServiceControlHandler"
0x18000cd85  mov     r8d, 426h
0x18000cd8b  mov     dword ptr [rsp+38h+var_18], ebx
0x18000cd8f  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000cd96  call    cs:__imp_PuDbgPrintError
0x18000cd9c  mov     rax, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000cda3  mov     [rax+848h], ebx
0x18000cda9  mov     rbx, [rsp+38h+arg_0]
0x18000cdae  add     rsp, 30h
0x18000cdb2  pop     rdi
0x18000cdb3  retn
```
