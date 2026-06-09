# LOG_SVC_ADMIN::Terminate(void)

- ea: `0x18000d180`
- end: `0x18000d418`
- name: `?Terminate@LOG_SVC_ADMIN@@AEAAXXZ`
- size: `664`
- prototype: `void __fastcall(LOG_SVC_ADMIN *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d420`

## callees

- `0x180001048`
- `0x1800086a4`
- `0x18000b290`
- `0x18000c670`
- `0x18000cdbc`
- `0x18000d180`
- `0x18000e400`
- `0x18000e760`
- `0x18000e97a`
- `0x180010010`

## import_xrefs

- `ntdll!RtlDeleteTimerQueueEx` at `0x18000d2d3`
- `ntdll!RtlDeleteTimerQueueEx` at `0x18000d2d3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d342`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d342`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d1f6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d22c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d1f6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d22c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d1e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d21f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d1e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d21f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d1da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d210`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d1da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d210`
- `iisutil!TerminateIISUtil` at `0x18000d411`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18000d3a4`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18000d3e9`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18000d3a4`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18000d3e9`
- `iisutil!?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z` at `0x18000d337`
- `iisutil!?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z` at `0x18000d337`
- `iisutil!?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ` at `0x18000d389`
- `iisutil!?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ` at `0x18000d389`
- `iisutil!DestroyRefTraceLog` at `0x18000d3c9`
- `iisutil!DestroyRefTraceLog` at `0x18000d3c9`
- `iisutil!PuDbgPrint` at `0x18000d37c`
- `iisutil!PuDbgPrint` at `0x18000d37c`
- `iisutil!PuDbgPrintError` at `0x18000d2b9`
- `iisutil!PuDbgPrintError` at `0x18000d319`
- `iisutil!PuDbgPrintError` at `0x18000d2b9`
- `iisutil!PuDbgPrintError` at `0x18000d319`

## string_xrefs

- `0x18000d375`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logcontext.cpp`
- `0x18000d2ae`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000d308`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000d28e`: `Could not cancel pending service status timer\n`
- `0x18000d2ea`: `Could not delete timer queue\n`
- `0x18000d2fa`: `LOG_SVC_ADMIN::DeleteTimerQueue`

## pseudocode

```c
void __fastcall LOG_SVC_ADMIN::Terminate(LOG_SVC_ADMIN *this)
{
  __int64 v2; // r8
  struct _TP_TIMER *v3; // rcx
  int v4; // eax
  void *v5; // rcx
  NTSTATUS v6; // eax
  unsigned int OutstandingAllocationCount; // ebx
  void *v8; // rbx
  void *v9; // rbx

  LOG_SVC_ADMIN::SetConfigChangeHandler(this, 1);
  HTTP_LOG_EVENT_HANDLER::Terminate((LOG_SVC_ADMIN *)((char *)this + 1160));
  MULTI_WORK_QUEUE::Terminate((LOG_SVC_ADMIN *)((char *)this + 1584), 0);
  STTABLE::Iterate(
    (LOG_SVC_ADMIN *)((char *)this + 1400),
    (void (*)(struct STTABLE_ITEM *, unsigned __int64, int *))LOG_SVC_ADMIN::ShutdownPipeIter,
    v2);
  SetThreadpoolTimer(*((PTP_TIMER *)this + 234), 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 234), 1);
  CloseThreadpoolTimer(*((PTP_TIMER *)this + 234));
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 143);
  if ( v3 )
  {
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 143), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 143));
    *((_QWORD *)this + 143) = 0;
  }
  HTTP_LOG_SITE_TABLE::Iterate(
    (RTL_SRWLOCK *)this + 5,
    (int (*)(struct HTTP_LOG_SITE_ENTRY *, struct HTTP_LOG_SITE_TABLE *))HTTP_LOG_SITE_TABLE::DestroyEntry,
    1);
  memset_0((char *)this + 48, 0, 0x418u);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
  *((_QWORD *)this + 2) = 0;
  v4 = LOG_SVC_ADMIN::CancelPendingServiceStatusTimer(this);
  if ( v4 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
      408,
      "LOG_SVC_ADMIN::Terminate",
      v4,
      "Could not cancel pending service status timer\n");
  v5 = (void *)*((_QWORD *)this + 264);
  if ( v5 )
  {
    v6 = RtlDeleteTimerQueueEx(v5, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    if ( v6 >= 0 )
    {
      *((_QWORD *)this + 264) = 0;
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        1569,
        "LOG_SVC_ADMIN::DeleteTimerQueue",
        v6 | 0x10000000,
        "Could not delete timer queue\n");
    }
  }
  while ( 1 )
  {
    OutstandingAllocationCount = ALLOC_CACHE_HANDLER::QueryOutstandingAllocationCount((ALLOC_CACHE_HANDLER *)HTTP_LOG_CONTEXT::sm_pAllocCacheHandler);
    if ( !OutstandingAllocationCount )
      break;
    ALLOC_CACHE_HANDLER::CleanupLookaside((ALLOC_CACHE_HANDLER *)HTTP_LOG_CONTEXT::sm_pAllocCacheHandler, 1);
    Sleep(0x3E8u);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logcontext.cpp",
        110,
        "HTTP_LOG_CONTEXT::Terminate",
        "HTTP_LOG_CONTEXT waiting for %d contexts to drain.\n",
        OutstandingAllocationCount);
  }
  v8 = HTTP_LOG_CONTEXT::sm_pAllocCacheHandler;
  if ( HTTP_LOG_CONTEXT::sm_pAllocCacheHandler )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)HTTP_LOG_CONTEXT::sm_pAllocCacheHandler);
    operator delete(v8);
    HTTP_LOG_CONTEXT::sm_pAllocCacheHandler = 0;
  }
  if ( HTTP_LOG_CONTEXT::sm_pTraceLog )
  {
    DestroyRefTraceLog();
    HTTP_LOG_CONTEXT::sm_pTraceLog = 0;
  }
  v9 = MULTI_WORK_ITEM::sm_pAllocCacheHandler;
  if ( MULTI_WORK_ITEM::sm_pAllocCacheHandler )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)MULTI_WORK_ITEM::sm_pAllocCacheHandler);
    operator delete(v9);
    MULTI_WORK_ITEM::sm_pAllocCacheHandler = 0;
  }
  TerminateIISUtil();
}

```

## disassembly

```asm
0x18000d180  mov     [rsp+arg_0], rbx
0x18000d185  mov     [rsp+arg_8], rbp
0x18000d18a  push    rdi
0x18000d18b  sub     rsp, 30h
0x18000d18f  mov     ebp, 1
0x18000d194  mov     rbx, rcx
0x18000d197  mov     edx, ebp; int
0x18000d199  call    ?SetConfigChangeHandler@LOG_SVC_ADMIN@@AEAAJH@Z; LOG_SVC_ADMIN::SetConfigChangeHandler(int)
0x18000d19e  lea     rcx, [rbx+488h]; this
0x18000d1a5  call    ?Terminate@HTTP_LOG_EVENT_HANDLER@@QEAAJXZ; HTTP_LOG_EVENT_HANDLER::Terminate(void)
0x18000d1aa  lea     rcx, [rbx+630h]; this
0x18000d1b1  xor     edx, edx; int
0x18000d1b3  call    ?Terminate@MULTI_WORK_QUEUE@@QEAAXH@Z; MULTI_WORK_QUEUE::Terminate(int)
0x18000d1b8  lea     rcx, [rbx+578h]; this
0x18000d1bf  lea     rdx, ?ShutdownPipeIter@LOG_SVC_ADMIN@@CAXPEAVSTTABLE_ITEM@@_KPEAH@Z; void (*)(struct STTABLE_ITEM *, unsigned __int64, int *)
0x18000d1c6  call    ?Iterate@STTABLE@@QEAAXP6AXPEAVSTTABLE_ITEM@@_KPEAH@Z1@Z; STTABLE::Iterate(void (*)(STTABLE_ITEM *,unsigned __int64,int *),unsigned __int64)
0x18000d1cb  mov     rcx, [rbx+750h]; pti
0x18000d1d2  xor     r9d, r9d; msWindowLength
0x18000d1d5  xor     r8d, r8d; msPeriod
0x18000d1d8  xor     edx, edx; pftDueTime
0x18000d1da  call    cs:__imp_SetThreadpoolTimer
0x18000d1e0  mov     rcx, [rbx+750h]; pti
0x18000d1e7  mov     edx, ebp; fCancelPendingCallbacks
0x18000d1e9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d1ef  mov     rcx, [rbx+750h]; pti
0x18000d1f6  call    cs:__imp_CloseThreadpoolTimer
0x18000d1fc  mov     rcx, [rbx+478h]; pti
0x18000d203  test    rcx, rcx
0x18000d206  jz      short loc_18000D23D
0x18000d208  xor     r9d, r9d; msWindowLength
0x18000d20b  xor     r8d, r8d; msPeriod
0x18000d20e  xor     edx, edx; pftDueTime
0x18000d210  call    cs:__imp_SetThreadpoolTimer
0x18000d216  mov     rcx, [rbx+478h]; pti
0x18000d21d  mov     edx, ebp; fCancelPendingCallbacks
0x18000d21f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d225  mov     rcx, [rbx+478h]; pti
0x18000d22c  call    cs:__imp_CloseThreadpoolTimer
0x18000d232  mov     qword ptr [rbx+478h], 0
0x18000d23d  mov     r8d, ebp; int
0x18000d240  lea     rdx, ?DestroyEntry@HTTP_LOG_SITE_TABLE@@CAJPEAVHTTP_LOG_SITE_ENTRY@@PEAV1@@Z; int (*)(struct HTTP_LOG_SITE_ENTRY *, struct HTTP_LOG_SITE_TABLE *)
0x18000d247  lea     rcx, [rbx+28h]; this
0x18000d24b  call    ?Iterate@HTTP_LOG_SITE_TABLE@@AEAAJP6AJPEAVHTTP_LOG_SITE_ENTRY@@PEAV1@@ZH@Z; HTTP_LOG_SITE_TABLE::Iterate(long (*)(HTTP_LOG_SITE_ENTRY *,HTTP_LOG_SITE_TABLE *),int)
0x18000d250  lea     rcx, [rbx+30h]; void *
0x18000d254  xor     edx, edx; Val
0x18000d256  mov     r8d, 418h; Size
0x18000d25c  call    memset_0
0x18000d261  mov     rcx, [rbx+10h]
0x18000d265  mov     rax, [rcx]
0x18000d268  mov     rax, [rax+10h]
0x18000d26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d271  mov     rcx, rbx; this
0x18000d274  mov     qword ptr [rbx+10h], 0
0x18000d27c  call    ?CancelPendingServiceStatusTimer@LOG_SVC_ADMIN@@AEAAJXZ; LOG_SVC_ADMIN::CancelPendingServiceStatusTimer(void)
0x18000d281  test    eax, eax
0x18000d283  jns     short loc_18000D2BF
0x18000d285  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d28c  jz      short loc_18000D2BF
0x18000d28e  lea     rcx, aCouldNotCancel; "Could not cancel pending service status"...
0x18000d295  mov     r8d, 198h
0x18000d29b  mov     [rsp+38h+var_10], rcx
0x18000d2a0  lea     r9, aLogSvcAdminTer_0; "LOG_SVC_ADMIN::Terminate"
0x18000d2a7  mov     rcx, cs:g_pDebug
0x18000d2ae  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000d2b5  mov     dword ptr [rsp+38h+var_18], eax
0x18000d2b9  call    cs:__imp_PuDbgPrintError
0x18000d2bf  mov     rcx, [rbx+840h]; TimerQueue
0x18000d2c6  test    rcx, rcx
0x18000d2c9  jz      loc_18000D382
0x18000d2cf  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000d2d3  call    cs:__imp_RtlDeleteTimerQueueEx
0x18000d2d9  test    eax, eax
0x18000d2db  jns     short loc_18000D321
0x18000d2dd  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000d2e4  jz      loc_18000D382
0x18000d2ea  lea     rcx, aCouldNotDelete; "Could not delete timer queue\n"
0x18000d2f1  bts     eax, 1Ch
0x18000d2f5  mov     [rsp+38h+var_10], rcx
0x18000d2fa  lea     r9, aLogSvcAdminDel; "LOG_SVC_ADMIN::DeleteTimerQueue"
0x18000d301  mov     rcx, cs:g_pDebug
0x18000d308  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000d30f  mov     r8d, 621h
0x18000d315  mov     dword ptr [rsp+38h+var_18], eax
0x18000d319  call    cs:__imp_PuDbgPrintError
0x18000d31f  jmp     short loc_18000D382
0x18000d321  mov     qword ptr [rbx+840h], 0
0x18000d32c  jmp     short loc_18000D382
0x18000d32e  mov     rcx, cs:?sm_pAllocCacheHandler@HTTP_LOG_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * HTTP_LOG_CONTEXT::sm_pAllocCacheHandler
0x18000d335  mov     edx, ebp
0x18000d337  call    cs:__imp_?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z; ALLOC_CACHE_HANDLER::CleanupLookaside(int)
0x18000d33d  mov     ecx, 3E8h; dwMilliseconds
0x18000d342  call    cs:__imp_Sleep
0x18000d348  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d34f  jz      short loc_18000D382
0x18000d351  mov     rcx, cs:g_pDebug
0x18000d358  lea     rax, aHttpLogContext_0; "HTTP_LOG_CONTEXT waiting for %d context"...
0x18000d35f  mov     dword ptr [rsp+38h+var_10], ebx
0x18000d363  lea     r9, aHttpLogContext_3; "HTTP_LOG_CONTEXT::Terminate"
0x18000d36a  mov     r8d, 6Eh ; 'n'
0x18000d370  mov     [rsp+38h+var_18], rax
0x18000d375  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000d37c  call    cs:__imp_PuDbgPrint
0x18000d382  mov     rcx, cs:?sm_pAllocCacheHandler@HTTP_LOG_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * HTTP_LOG_CONTEXT::sm_pAllocCacheHandler
0x18000d389  call    cs:__imp_?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ; ALLOC_CACHE_HANDLER::QueryOutstandingAllocationCount(void)
0x18000d38f  mov     ebx, eax
0x18000d391  test    eax, eax
0x18000d393  jnz     short loc_18000D32E
0x18000d395  mov     rbx, cs:?sm_pAllocCacheHandler@HTTP_LOG_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * HTTP_LOG_CONTEXT::sm_pAllocCacheHandler
0x18000d39c  test    rbx, rbx
0x18000d39f  jz      short loc_18000D3BD
0x18000d3a1  mov     rcx, rbx
0x18000d3a4  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x18000d3aa  mov     rcx, rbx; Block
0x18000d3ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d3b2  mov     cs:?sm_pAllocCacheHandler@HTTP_LOG_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * HTTP_LOG_CONTEXT::sm_pAllocCacheHandler
0x18000d3bd  mov     rcx, cs:?sm_pTraceLog@HTTP_LOG_CONTEXT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * HTTP_LOG_CONTEXT::sm_pTraceLog
0x18000d3c4  test    rcx, rcx
0x18000d3c7  jz      short loc_18000D3DA
0x18000d3c9  call    cs:__imp_DestroyRefTraceLog
0x18000d3cf  mov     cs:?sm_pTraceLog@HTTP_LOG_CONTEXT@@0PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * HTTP_LOG_CONTEXT::sm_pTraceLog
0x18000d3da  mov     rbx, cs:?sm_pAllocCacheHandler@MULTI_WORK_ITEM@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * MULTI_WORK_ITEM::sm_pAllocCacheHandler
0x18000d3e1  test    rbx, rbx
0x18000d3e4  jz      short loc_18000D402
0x18000d3e6  mov     rcx, rbx
0x18000d3e9  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x18000d3ef  mov     rcx, rbx; Block
0x18000d3f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d3f7  mov     cs:?sm_pAllocCacheHandler@MULTI_WORK_ITEM@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * MULTI_WORK_ITEM::sm_pAllocCacheHandler
0x18000d402  mov     rbx, [rsp+38h+arg_0]
0x18000d407  mov     rbp, [rsp+38h+arg_8]
0x18000d40c  add     rsp, 30h
0x18000d410  pop     rdi
0x18000d411  jmp     cs:__imp_TerminateIISUtil
```
