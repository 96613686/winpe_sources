# LOG_SVC_ADMIN::StopServiceWorkItem(void)

- ea: `0x18000d088`
- end: `0x18000d177`
- name: `?StopServiceWorkItem@LOG_SVC_ADMIN@@AEAAXXZ`
- size: `239`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b560`
- `0x18000cf98`

## callees

- `0x18000d088`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d11d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d11d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d127`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d10a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d10a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d09b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d09b`
- `iisutil!PuDbgPrintError` at `0x18000d0fd`
- `iisutil!PuDbgPrintError` at `0x18000d16b`
- `iisutil!PuDbgPrintError` at `0x18000d0fd`
- `iisutil!PuDbgPrintError` at `0x18000d16b`

## string_xrefs

- `0x18000d0f2`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000d160`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000d0d2`: `Error while waiting for start to complete.\n`
- `0x18000d0e4`: `LOG_SVC_ADMIN::StopServiceWorkItem`
- `0x18000d152`: `LOG_SVC_ADMIN::StopServiceWorkItem`

## pseudocode

```c
void __fastcall LOG_SVC_ADMIN::StopServiceWorkItem(HANDLE *this)
{
  signed int LastError; // eax
  signed int v3; // eax

  if ( WaitForSingleObject(this[262], 0xFFFFFFFF) == -1 && (g_dwDebugFlags & 0xF) != 0 )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2147467259;
    }
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
      604,
      "LOG_SVC_ADMIN::StopServiceWorkItem",
      LastError,
      "Error while waiting for start to complete.\n");
  }
  if ( !SetEvent(this[236]) && (g_dwDebugFlags & 0xF) != 0 )
  {
    if ( GetLastError() )
    {
      v3 = GetLastError();
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
      613,
      "LOG_SVC_ADMIN::StopServiceWorkItem",
      v3,
      "Error setting shutdown event.\n");
  }
}

```

## disassembly

```asm
0x18000d088  push    rbx
0x18000d08a  sub     rsp, 30h
0x18000d08e  mov     rbx, rcx
0x18000d091  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d094  mov     rcx, [rcx+830h]; hHandle
0x18000d09b  call    cs:__imp_WaitForSingleObject
0x18000d0a1  cmp     eax, 0FFFFFFFFh
0x18000d0a4  jnz     short loc_18000D103
0x18000d0a6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d0ad  jz      short loc_18000D103
0x18000d0af  call    cs:__imp_GetLastError
0x18000d0b5  test    eax, eax
0x18000d0b7  jz      short loc_18000D0CD
0x18000d0b9  call    cs:__imp_GetLastError
0x18000d0bf  test    eax, eax
0x18000d0c1  jle     short loc_18000D0D2
0x18000d0c3  movzx   eax, ax
0x18000d0c6  or      eax, 80070000h
0x18000d0cb  jmp     short loc_18000D0D2
0x18000d0cd  mov     eax, 80004005h
0x18000d0d2  lea     rcx, aErrorWhileWait; "Error while waiting for start to comple"...
0x18000d0d9  mov     r8d, 25Ch
0x18000d0df  mov     [rsp+38h+var_10], rcx
0x18000d0e4  lea     r9, aLogSvcAdminSto; "LOG_SVC_ADMIN::StopServiceWorkItem"
0x18000d0eb  mov     rcx, cs:g_pDebug
0x18000d0f2  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000d0f9  mov     [rsp+38h+var_18], eax
0x18000d0fd  call    cs:__imp_PuDbgPrintError
0x18000d103  mov     rcx, [rbx+760h]; hEvent
0x18000d10a  call    cs:__imp_SetEvent
0x18000d110  test    eax, eax
0x18000d112  jnz     short loc_18000D171
0x18000d114  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d11b  jz      short loc_18000D171
0x18000d11d  call    cs:__imp_GetLastError
0x18000d123  test    eax, eax
0x18000d125  jz      short loc_18000D13B
0x18000d127  call    cs:__imp_GetLastError
0x18000d12d  test    eax, eax
0x18000d12f  jle     short loc_18000D140
0x18000d131  movzx   eax, ax
0x18000d134  or      eax, 80070000h
0x18000d139  jmp     short loc_18000D140
0x18000d13b  mov     eax, 80004005h
0x18000d140  lea     rcx, aErrorSettingSh; "Error setting shutdown event.\n"
0x18000d147  mov     r8d, 265h
0x18000d14d  mov     [rsp+38h+var_10], rcx
0x18000d152  lea     r9, aLogSvcAdminSto; "LOG_SVC_ADMIN::StopServiceWorkItem"
0x18000d159  mov     rcx, cs:g_pDebug
0x18000d160  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000d167  mov     [rsp+38h+var_18], eax
0x18000d16b  call    cs:__imp_PuDbgPrintError
0x18000d171  add     rsp, 30h
0x18000d175  pop     rbx
0x18000d176  retn
```
