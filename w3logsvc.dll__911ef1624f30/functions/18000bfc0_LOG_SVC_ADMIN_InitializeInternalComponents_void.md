# LOG_SVC_ADMIN::InitializeInternalComponents(void)

- ea: `0x18000bfc0`
- end: `0x18000c1ab`
- name: `?InitializeInternalComponents@LOG_SVC_ADMIN@@AEAAJXZ`
- size: `491`
- prototype: `__int64 __fastcall(LOG_SVC_ADMIN *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000cf98`

## callees

- `0x180008230`
- `0x18000be20`
- `0x18000bfc0`
- `0x18000cdbc`
- `0x18000d860`
- `0x18000da70`
- `0x18000dca0`
- `0x180010010`

## import_xrefs

- `ntdll!RtlCreateTimerQueue` at `0x18000c0b7`
- `ntdll!RtlCreateTimerQueue` at `0x18000c0b7`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x18000c007`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x18000c007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c01d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c04e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c01d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c04e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c0ed`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000bfde`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000bfde`
- `iisutil!InitializeIISUtil` at `0x18000c0e3`
- `iisutil!InitializeIISUtil` at `0x18000c0e3`
- `iisutil!PuDbgPrintError` at `0x18000c09f`
- `iisutil!PuDbgPrintError` at `0x18000c09f`

## string_xrefs

- `0x18000c094`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000c088`: `LOG_SVC_ADMIN::InitializeInternalComponents`
- `0x18000c03f`: `Couldn't register service control handler\n`
- `0x18000c0d4`: `Could not create timer queue\n`

## pseudocode

```c
__int64 __fastcall LOG_SVC_ADMIN::InitializeInternalComponents(LOG_SVC_ADMIN *this)
{
  SERVICE_STATUS_HANDLE v2; // rax
  signed int v3; // eax
  int EtwSession; // ebx
  signed int v5; // eax
  NTSTATUS TimerQueue; // ebx
  signed int LastError; // eax

  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 2008), 0x800003E8) )
  {
    *((_DWORD *)this + 501) = 1;
LABEL_3:
    *((_DWORD *)this + 512) = 1;
    v2 = RegisterServiceCtrlHandlerW(L"w3logsvc", ServiceControlHandler);
    *((_QWORD *)this + 257) = v2;
    if ( v2 )
    {
      g_RegisterServiceCalled = 1;
      TimerQueue = RtlCreateTimerQueue((PHANDLE)this + 264);
      if ( TimerQueue >= 0 )
      {
        if ( (unsigned int)InitializeIISUtil() )
        {
          EtwSession = LOG_SVC_ADMIN::InitializeConfigSystem(this);
          if ( EtwSession >= 0 )
          {
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 8LL))(*((_QWORD *)this + 2));
            EtwSession = HTTP_LOG_SITE_TABLE::Initialize(
                           (LOG_SVC_ADMIN *)((char *)this + 40),
                           *((struct IAppHostAdminManager **)this + 2));
            if ( EtwSession >= 0 )
            {
              EtwSession = HTTP_LOG_EVENT_HANDLER::CreateEtwSession((LOG_SVC_ADMIN *)((char *)this + 1160));
              if ( EtwSession >= 0
                && (EtwSession = HTTP_LOG_EVENT_HANDLER::CreateEtwStatusTimer((char *)this + 1160), EtwSession >= 0)
                && (EtwSession = HTTP_LOG_EVENT_HANDLER::CreateEtwConsumer((LOG_SVC_ADMIN *)((char *)this + 1160)),
                    EtwSession >= 0) )
              {
                return (unsigned int)LOG_SVC_ADMIN::SetConfigChangeHandler(this, 0);
              }
              else
              {
                *((_DWORD *)this + 290) = 0;
              }
            }
          }
        }
        else
        {
          LastError = GetLastError();
          EtwSession = LastError;
          if ( LastError > 0 )
            EtwSession = (unsigned __int16)LastError | 0x80070000;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
              705,
              "LOG_SVC_ADMIN::InitializeInternalComponents",
              EtwSession,
              "Could not initialize iisutil\n");
        }
      }
      else
      {
        EtwSession = TimerQueue | 0x10000000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
            688,
            "LOG_SVC_ADMIN::InitializeInternalComponents",
            EtwSession,
            "Could not create timer queue\n");
      }
    }
    else
    {
      v3 = GetLastError();
      EtwSession = v3;
      if ( v3 > 0 )
        EtwSession = (unsigned __int16)v3 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
          667,
          "LOG_SVC_ADMIN::InitializeInternalComponents",
          EtwSession,
          "Couldn't register service control handler\n");
    }
    return (unsigned int)EtwSession;
  }
  v5 = GetLastError();
  EtwSession = v5;
  if ( v5 > 0 )
    EtwSession = (unsigned __int16)v5 | 0x80070000;
  if ( EtwSession >= 0 )
    goto LABEL_3;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
      643,
      "LOG_SVC_ADMIN::InitializeInternalComponents",
      EtwSession,
      "Lock initialization failed\n");
  return (unsigned int)EtwSession;
}

```

## disassembly

```asm
0x18000bfc0  mov     [rsp+arg_0], rbx
0x18000bfc5  mov     [rsp+arg_8], rsi
0x18000bfca  push    rdi
0x18000bfcb  sub     rsp, 30h
0x18000bfcf  mov     rdi, rcx
0x18000bfd2  mov     edx, 800003E8h; dwSpinCount
0x18000bfd7  add     rcx, 7D8h; lpCriticalSection
0x18000bfde  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000bfe4  mov     esi, 1
0x18000bfe9  test    eax, eax
0x18000bfeb  jz      short loc_18000C04E
0x18000bfed  mov     [rdi+7D4h], esi
0x18000bff3  lea     rdx, ?ServiceControlHandler@@YAXK@Z; lpHandlerProc
0x18000bffa  mov     [rdi+800h], esi
0x18000c000  lea     rcx, aW3logsvc_1; "w3logsvc"
0x18000c007  call    cs:__imp_RegisterServiceCtrlHandlerW
0x18000c00d  mov     [rdi+808h], rax
0x18000c014  test    rax, rax
0x18000c017  jnz     loc_18000C0AA
0x18000c01d  call    cs:__imp_GetLastError
0x18000c023  mov     ebx, eax
0x18000c025  test    eax, eax
0x18000c027  jle     short loc_18000C032
0x18000c029  movzx   ebx, ax
0x18000c02c  or      ebx, 80070000h
0x18000c032  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000c039  jz      loc_18000C199
0x18000c03f  lea     rax, aCouldnTRegiste; "Couldn't register service control handl"...
0x18000c046  mov     r8d, 29Bh
0x18000c04c  jmp     short loc_18000C081
0x18000c04e  call    cs:__imp_GetLastError
0x18000c054  mov     ebx, eax
0x18000c056  test    eax, eax
0x18000c058  jle     short loc_18000C063
0x18000c05a  movzx   ebx, ax
0x18000c05d  or      ebx, 80070000h
0x18000c063  test    ebx, ebx
0x18000c065  jns     short loc_18000BFF3
0x18000c067  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000c06e  jz      loc_18000C199
0x18000c074  lea     rax, aLockInitializa; "Lock initialization failed\n"
0x18000c07b  mov     r8d, 283h
0x18000c081  mov     rcx, cs:g_pDebug
0x18000c088  lea     r9, aLogSvcAdminIni_0; "LOG_SVC_ADMIN::InitializeInternalCompon"...
0x18000c08f  mov     [rsp+38h+var_10], rax
0x18000c094  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000c09b  mov     [rsp+38h+var_18], ebx
0x18000c09f  call    cs:__imp_PuDbgPrintError
0x18000c0a5  jmp     loc_18000C199
0x18000c0aa  lea     rcx, [rdi+840h]; TimerQueue
0x18000c0b1  mov     cs:?g_RegisterServiceCalled@@3HA, esi; int g_RegisterServiceCalled
0x18000c0b7  call    cs:__imp_RtlCreateTimerQueue
0x18000c0bd  mov     ebx, eax
0x18000c0bf  test    eax, eax
0x18000c0c1  jns     short loc_18000C0E3
0x18000c0c3  bts     ebx, 1Ch
0x18000c0c7  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000c0ce  jz      loc_18000C199
0x18000c0d4  lea     rax, aCouldNotCreate; "Could not create timer queue\n"
0x18000c0db  mov     r8d, 2B0h
0x18000c0e1  jmp     short loc_18000C081
0x18000c0e3  call    cs:__imp_InitializeIISUtil
0x18000c0e9  test    eax, eax
0x18000c0eb  jnz     short loc_18000C121
0x18000c0ed  call    cs:__imp_GetLastError
0x18000c0f3  mov     ebx, eax
0x18000c0f5  test    eax, eax
0x18000c0f7  jle     short loc_18000C102
0x18000c0f9  movzx   ebx, ax
0x18000c0fc  or      ebx, 80070000h
0x18000c102  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000c109  jz      loc_18000C199
0x18000c10f  lea     rax, aCouldNotInitia_0; "Could not initialize iisutil\n"
0x18000c116  mov     r8d, 2C1h
0x18000c11c  jmp     loc_18000C081
0x18000c121  mov     rcx, rdi; this
0x18000c124  call    ?InitializeConfigSystem@LOG_SVC_ADMIN@@AEAAJXZ; LOG_SVC_ADMIN::InitializeConfigSystem(void)
0x18000c129  mov     ebx, eax
0x18000c12b  test    eax, eax
0x18000c12d  js      short loc_18000C199
0x18000c12f  mov     rcx, [rdi+10h]
0x18000c133  mov     rax, [rcx]
0x18000c136  mov     rax, [rax+8]
0x18000c13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c13f  mov     rdx, [rdi+10h]; struct IAppHostAdminManager *
0x18000c143  lea     rcx, [rdi+28h]; this
0x18000c147  call    ?Initialize@HTTP_LOG_SITE_TABLE@@QEAAJPEAUIAppHostAdminManager@@@Z; HTTP_LOG_SITE_TABLE::Initialize(IAppHostAdminManager *)
0x18000c14c  mov     ebx, eax
0x18000c14e  test    eax, eax
0x18000c150  js      short loc_18000C199
0x18000c152  lea     rsi, [rdi+488h]
0x18000c159  mov     rcx, rsi; this
0x18000c15c  call    ?CreateEtwSession@HTTP_LOG_EVENT_HANDLER@@AEAAJXZ; HTTP_LOG_EVENT_HANDLER::CreateEtwSession(void)
0x18000c161  mov     ebx, eax
0x18000c163  test    eax, eax
0x18000c165  js      short loc_18000C183
0x18000c167  mov     rcx, rsi; pv
0x18000c16a  call    ?CreateEtwStatusTimer@HTTP_LOG_EVENT_HANDLER@@AEAAJXZ; HTTP_LOG_EVENT_HANDLER::CreateEtwStatusTimer(void)
0x18000c16f  mov     ebx, eax
0x18000c171  test    eax, eax
0x18000c173  js      short loc_18000C183
0x18000c175  mov     rcx, rsi; this
0x18000c178  call    ?CreateEtwConsumer@HTTP_LOG_EVENT_HANDLER@@AEAAJXZ; HTTP_LOG_EVENT_HANDLER::CreateEtwConsumer(void)
0x18000c17d  mov     ebx, eax
0x18000c17f  test    eax, eax
0x18000c181  jns     short loc_18000C18D
0x18000c183  mov     dword ptr [rsi], 0
0x18000c189  test    ebx, ebx
0x18000c18b  js      short loc_18000C199
0x18000c18d  xor     edx, edx; int
0x18000c18f  mov     rcx, rdi; this
0x18000c192  call    ?SetConfigChangeHandler@LOG_SVC_ADMIN@@AEAAJH@Z; LOG_SVC_ADMIN::SetConfigChangeHandler(int)
0x18000c197  mov     ebx, eax
0x18000c199  mov     rsi, [rsp+38h+arg_8]
0x18000c19e  mov     eax, ebx
0x18000c1a0  mov     rbx, [rsp+38h+arg_0]
0x18000c1a5  add     rsp, 30h
0x18000c1a9  pop     rdi
0x18000c1aa  retn
```
