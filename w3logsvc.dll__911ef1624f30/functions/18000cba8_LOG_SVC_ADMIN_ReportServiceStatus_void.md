# LOG_SVC_ADMIN::ReportServiceStatus(void)

- ea: `0x18000cba8`
- end: `0x18000cc64`
- name: `?ReportServiceStatus@LOG_SVC_ADMIN@@AEAAJXZ`
- size: `188`
- prototype: `__int64 __fastcall(LOG_SVC_ADMIN *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b154`
- `0x18000b5dc`
- `0x18000cc70`
- `0x18000d520`

## callees

- `0x18000cba8`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000cc03`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000cc03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc0d`
- `iisutil!PuDbgPrint` at `0x18000cbea`
- `iisutil!PuDbgPrint` at `0x18000cbea`
- `iisutil!PuDbgPrintError` at `0x18000cc56`
- `iisutil!PuDbgPrintError` at `0x18000cc56`

## string_xrefs

- `0x18000cbe3`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000cc4f`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000cbca`: `Can't report service status because m_ServiceStatusHandle is null\n`
- `0x18000cbd1`: `LOG_SVC_ADMIN::ReportServiceStatus`
- `0x18000cc3e`: `LOG_SVC_ADMIN::ReportServiceStatus`
- `0x18000cc32`: `Setting service state failed\n`

## pseudocode

```c
__int64 __fastcall LOG_SVC_ADMIN::ReportServiceStatus(LOG_SVC_ADMIN *this)
{
  unsigned int v1; // ebx
  signed int LastError; // eax

  if ( *((_QWORD *)this + 257) )
  {
    v1 = 0;
    if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 257), (LPSERVICE_STATUS)((char *)this + 2064)) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
          1498,
          "LOG_SVC_ADMIN::ReportServiceStatus",
          v1,
          "Setting service state failed\n");
    }
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        1461,
        "LOG_SVC_ADMIN::ReportServiceStatus",
        "Can't report service status because m_ServiceStatusHandle is null\n");
    return (unsigned int)-2147024890;
  }
  return v1;
}

```

## disassembly

```asm
0x18000cba8  push    rbx
0x18000cbaa  sub     rsp, 30h
0x18000cbae  mov     rax, [rcx+808h]
0x18000cbb5  test    rax, rax
0x18000cbb8  jnz     short loc_18000CBF7
0x18000cbba  test    byte ptr cs:g_dwDebugFlags, 3
0x18000cbc1  jz      short loc_18000CBF0
0x18000cbc3  mov     rcx, cs:g_pDebug
0x18000cbca  lea     rax, aCanTReportServ; "Can't report service status because m_S"...
0x18000cbd1  lea     r9, aLogSvcAdminRep; "LOG_SVC_ADMIN::ReportServiceStatus"
0x18000cbd8  mov     [rsp+38h+var_18], rax
0x18000cbdd  mov     r8d, 5B5h
0x18000cbe3  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000cbea  call    cs:__imp_PuDbgPrint
0x18000cbf0  mov     ebx, 80070006h
0x18000cbf5  jmp     short loc_18000CC5C
0x18000cbf7  lea     rdx, [rcx+810h]; lpServiceStatus
0x18000cbfe  xor     ebx, ebx
0x18000cc00  mov     rcx, rax; hServiceStatus
0x18000cc03  call    cs:__imp_SetServiceStatus
0x18000cc09  test    eax, eax
0x18000cc0b  jnz     short loc_18000CC5C
0x18000cc0d  call    cs:__imp_GetLastError
0x18000cc13  mov     ebx, eax
0x18000cc15  test    eax, eax
0x18000cc17  jle     short loc_18000CC22
0x18000cc19  movzx   ebx, ax
0x18000cc1c  or      ebx, 80070000h
0x18000cc22  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000cc29  jz      short loc_18000CC5C
0x18000cc2b  mov     rcx, cs:g_pDebug
0x18000cc32  lea     rax, aSettingService; "Setting service state failed\n"
0x18000cc39  mov     [rsp+38h+var_10], rax
0x18000cc3e  lea     r9, aLogSvcAdminRep; "LOG_SVC_ADMIN::ReportServiceStatus"
0x18000cc45  mov     r8d, 5DAh
0x18000cc4b  mov     dword ptr [rsp+38h+var_18], ebx
0x18000cc4f  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000cc56  call    cs:__imp_PuDbgPrintError
0x18000cc5c  mov     eax, ebx
0x18000cc5e  add     rsp, 30h
0x18000cc62  pop     rbx
0x18000cc63  retn
```
