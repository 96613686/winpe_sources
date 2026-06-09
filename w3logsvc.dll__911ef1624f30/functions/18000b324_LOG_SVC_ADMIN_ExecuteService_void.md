# LOG_SVC_ADMIN::ExecuteService(void)

- ea: `0x18000b324`
- end: `0x18000b54e`
- name: `?ExecuteService@LOG_SVC_ADMIN@@QEAAXXZ`
- size: `554`
- prototype: `void __fastcall(LOG_SVC_ADMIN *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180001bd0`

## callees

- `0x18000b324`
- `0x18000d420`
- `0x18000e4c4`
- `0x18000e760`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4eb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b4e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b4e1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18000b391`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18000b391`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18000b3a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18000b3a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18000b3b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18000b3b7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000b3bd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000b3bd`
- `iisutil!PuDbgPrintError` at `0x18000b484`
- `iisutil!PuDbgPrintError` at `0x18000b4cd`
- `iisutil!PuDbgPrintError` at `0x18000b534`
- `iisutil!PuDbgPrintError` at `0x18000b484`
- `iisutil!PuDbgPrintError` at `0x18000b4cd`
- `iisutil!PuDbgPrintError` at `0x18000b534`

## string_xrefs

- `0x18000b479`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000b4c6`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000b52d`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000b4b5`: `LOG_SVC_ADMIN::ExecuteService`
- `0x18000b51c`: `LOG_SVC_ADMIN::ExecuteService`
- `0x18000b459`: `Couldn't queue StartLogServiceWorkItem\n`

## pseudocode

```c
void __fastcall LOG_SVC_ADMIN::ExecuteService(LOG_SVC_ADMIN *this)
{
  PVOID v1; // rsi
  char *v2; // rdi
  struct _TP_POOL *Threadpool; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int LastError; // eax
  signed int v6; // ebx
  signed int v7; // eax

  v1 = g_pLogSvcAdmin;
  v2 = (char *)g_pLogSvcAdmin + 1584;
  *((_DWORD *)g_pLogSvcAdmin + 400) = 3;
  *((_QWORD *)v2 + 3) = 0;
  *((_QWORD *)v2 + 4) = 0;
  *((_QWORD *)v2 + 5) = 0;
  *((_QWORD *)v2 + 6) = 0;
  *((_QWORD *)v2 + 7) = 0;
  *((_QWORD *)v2 + 8) = 0;
  *((_DWORD *)v2 + 18) = 0;
  *((_DWORD *)v2 + 19) = 1;
  *((_DWORD *)v2 + 20) = 72;
  *((_DWORD *)v2 + 22) = 1;
  Threadpool = CreateThreadpool(0);
  *((_QWORD *)v2 + 12) = Threadpool;
  if ( Threadpool
    && (SetThreadpoolThreadMaximum(Threadpool, 0x32u),
        SetThreadpoolThreadMinimum(*((PTP_POOL *)v1 + 210), 1u),
        ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup(),
        (*((_QWORD *)v1 + 211) = ThreadpoolCleanupGroup) != 0) )
  {
    *((_QWORD *)v1 + 201) = *((_QWORD *)v1 + 210);
    *((_QWORD *)v1 + 202) = ThreadpoolCleanupGroup;
    *((_QWORD *)v1 + 203) = 0;
  }
  else
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( v6 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
          462,
          "LOG_SVC_ADMIN::StartWorkQueue",
          v6,
          "Couldn't initialize work queue\n");
LABEL_14:
      MULTI_WORK_QUEUE::Terminate((MULTI_WORK_QUEUE *)v2, 1);
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
          304,
          "LOG_SVC_ADMIN::ExecuteService",
          v6,
          "Could not start work queue\n");
      return;
    }
  }
  v6 = MULTI_WORK_QUEUE::GetAndQueueWorkItem((MULTI_WORK_QUEUE *)v2, (struct MULTI_WORK_DISPATCH *)v1, 1u);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        475,
        "LOG_SVC_ADMIN::StartWorkQueue",
        v6,
        "Couldn't queue StartLogServiceWorkItem\n");
    goto LABEL_14;
  }
  if ( WaitForSingleObject(*((HANDLE *)v1 + 236), 0xFFFFFFFF) == -1 )
  {
    v7 = GetLastError();
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        324,
        "LOG_SVC_ADMIN::ExecuteService",
        v6,
        "WaitForSingleObject() failed\n");
  }
  LOG_SVC_ADMIN::TerminateServiceAndReportFinalStatus((LOG_SVC_ADMIN *)v1, v6);
}

```

## disassembly

```asm
0x18000b324  push    rbx
0x18000b326  push    rsi
0x18000b327  push    rdi
0x18000b328  push    r14
0x18000b32a  sub     rsp, 38h
0x18000b32e  mov     rsi, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000b335  mov     r14d, 1
0x18000b33b  xor     ecx, ecx; reserved
0x18000b33d  lea     rdi, [rsi+630h]
0x18000b344  mov     dword ptr [rdi+10h], 3
0x18000b34b  mov     qword ptr [rdi+18h], 0
0x18000b353  mov     qword ptr [rdi+20h], 0
0x18000b35b  mov     qword ptr [rdi+28h], 0
0x18000b363  mov     qword ptr [rdi+30h], 0
0x18000b36b  mov     qword ptr [rdi+38h], 0
0x18000b373  mov     qword ptr [rdi+40h], 0
0x18000b37b  mov     dword ptr [rdi+48h], 0
0x18000b382  mov     [rdi+4Ch], r14d
0x18000b386  mov     dword ptr [rdi+50h], 48h ; 'H'
0x18000b38d  mov     [rdi+58h], r14d
0x18000b391  call    cs:__imp_CreateThreadpool
0x18000b397  mov     [rdi+60h], rax
0x18000b39b  test    rax, rax
0x18000b39e  jz      short loc_18000B3D2
0x18000b3a0  lea     edx, [r14+31h]; cthrdMost
0x18000b3a4  mov     rcx, rax; ptpp
0x18000b3a7  call    cs:__imp_SetThreadpoolThreadMaximum
0x18000b3ad  mov     rcx, [rsi+690h]; ptpp
0x18000b3b4  mov     edx, r14d; cthrdMic
0x18000b3b7  call    cs:__imp_SetThreadpoolThreadMinimum
0x18000b3bd  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18000b3c3  mov     [rsi+698h], rax
0x18000b3ca  mov     rcx, rax
0x18000b3cd  test    rax, rax
0x18000b3d0  jnz     short loc_18000B418
0x18000b3d2  call    cs:__imp_GetLastError
0x18000b3d8  test    eax, eax
0x18000b3da  jz      short loc_18000B3F3
0x18000b3dc  call    cs:__imp_GetLastError
0x18000b3e2  mov     ebx, eax
0x18000b3e4  test    eax, eax
0x18000b3e6  jle     short loc_18000B3F8
0x18000b3e8  movzx   ebx, ax
0x18000b3eb  or      ebx, 80070000h
0x18000b3f1  jmp     short loc_18000B3F8
0x18000b3f3  mov     ebx, 80004005h
0x18000b3f8  test    ebx, ebx
0x18000b3fa  jns     short loc_18000B438
0x18000b3fc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000b403  jz      loc_18000B48A
0x18000b409  lea     rax, aCouldnTInitial; "Couldn't initialize work queue\n"
0x18000b410  mov     r8d, 1CEh
0x18000b416  jmp     short loc_18000B466
0x18000b418  mov     rax, [rsi+690h]
0x18000b41f  mov     [rsi+648h], rax
0x18000b426  mov     [rsi+650h], rcx
0x18000b42d  mov     qword ptr [rsi+658h], 0
0x18000b438  mov     r8, r14; unsigned __int64
0x18000b43b  mov     rdx, rsi; struct MULTI_WORK_DISPATCH *
0x18000b43e  mov     rcx, rdi; this
0x18000b441  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x18000b446  mov     ebx, eax
0x18000b448  test    eax, eax
0x18000b44a  jns     loc_18000B4D5
0x18000b450  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000b457  jz      short loc_18000B48A
0x18000b459  lea     rax, aCouldnTQueueSt_0; "Couldn't queue StartLogServiceWorkItem"...
0x18000b460  mov     r8d, 1DBh
0x18000b466  mov     rcx, cs:g_pDebug
0x18000b46d  lea     r9, aLogSvcAdminSta_0; "LOG_SVC_ADMIN::StartWorkQueue"
0x18000b474  mov     [rsp+58h+var_30], rax
0x18000b479  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000b480  mov     [rsp+58h+var_38], ebx
0x18000b484  call    cs:__imp_PuDbgPrintError
0x18000b48a  mov     edx, r14d; int
0x18000b48d  mov     rcx, rdi; this
0x18000b490  call    ?Terminate@MULTI_WORK_QUEUE@@QEAAXH@Z; MULTI_WORK_QUEUE::Terminate(int)
0x18000b495  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000b49c  jz      loc_18000B544
0x18000b4a2  mov     rcx, cs:g_pDebug
0x18000b4a9  lea     rax, aCouldNotStartW; "Could not start work queue\n"
0x18000b4b0  mov     [rsp+58h+var_30], rax
0x18000b4b5  lea     r9, aLogSvcAdminExe; "LOG_SVC_ADMIN::ExecuteService"
0x18000b4bc  mov     r8d, 130h
0x18000b4c2  mov     [rsp+58h+var_38], ebx
0x18000b4c6  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000b4cd  call    cs:__imp_PuDbgPrintError
0x18000b4d3  jmp     short loc_18000B544
0x18000b4d5  mov     rcx, [rsi+760h]; hHandle
0x18000b4dc  or      edi, 0FFFFFFFFh
0x18000b4df  mov     edx, edi; dwMilliseconds
0x18000b4e1  call    cs:__imp_WaitForSingleObject
0x18000b4e7  cmp     eax, edi
0x18000b4e9  jnz     short loc_18000B53A
0x18000b4eb  call    cs:__imp_GetLastError
0x18000b4f1  mov     ebx, eax
0x18000b4f3  test    eax, eax
0x18000b4f5  jle     short loc_18000B500
0x18000b4f7  movzx   ebx, ax
0x18000b4fa  or      ebx, 80070000h
0x18000b500  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000b507  jz      short loc_18000B53A
0x18000b509  mov     rcx, cs:g_pDebug
0x18000b510  lea     rax, aWaitforsingleo; "WaitForSingleObject() failed\n"
0x18000b517  mov     [rsp+58h+var_30], rax
0x18000b51c  lea     r9, aLogSvcAdminExe; "LOG_SVC_ADMIN::ExecuteService"
0x18000b523  mov     r8d, 144h
0x18000b529  mov     [rsp+58h+var_38], ebx
0x18000b52d  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000b534  call    cs:__imp_PuDbgPrintError
0x18000b53a  mov     edx, ebx; int
0x18000b53c  mov     rcx, rsi; this
0x18000b53f  call    ?TerminateServiceAndReportFinalStatus@LOG_SVC_ADMIN@@AEAAXJ@Z; LOG_SVC_ADMIN::TerminateServiceAndReportFinalStatus(long)
0x18000b544  add     rsp, 38h
0x18000b548  pop     r14
0x18000b54a  pop     rdi
0x18000b54b  pop     rsi
0x18000b54c  pop     rbx
0x18000b54d  retn
```
