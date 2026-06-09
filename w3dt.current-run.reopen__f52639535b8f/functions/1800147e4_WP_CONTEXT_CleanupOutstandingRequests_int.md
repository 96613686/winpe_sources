# WP_CONTEXT::CleanupOutstandingRequests(int)

- ea: `0x1800147e4`
- end: `0x180014950`
- name: `?CleanupOutstandingRequests@WP_CONTEXT@@QEAAJH@Z`
- size: `364`
- prototype: `__int64 __fastcall(WP_CONTEXT *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800159b0`

## callees

- `0x1800147e4`
- `0x180014a90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014821`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001488c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014930`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001488c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014930`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001480e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001480e`
- `iisutil!PuDbgPrint` at `0x180014852`
- `iisutil!PuDbgPrint` at `0x1800148c6`
- `iisutil!PuDbgPrint` at `0x180014925`
- `iisutil!PuDbgPrint` at `0x180014852`
- `iisutil!PuDbgPrint` at `0x1800148c6`
- `iisutil!PuDbgPrint` at `0x180014925`
- `iisutil!?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ` at `0x1800148d3`
- `iisutil!?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ` at `0x1800148d3`
- `iisutil!?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z` at `0x180014881`
- `iisutil!?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z` at `0x180014881`

## string_xrefs

- `0x180014839`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\nativerequest.cxx`
- `0x1800148bf`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\nativerequest.cxx`
- `0x180014840`: `Failed to delete Ping timer (%d)\n`
- `0x18001490c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\disconnectcontext.cxx`

## pseudocode

```c
__int64 __fastcall WP_CONTEXT::CleanupOutstandingRequests(WP_CONTEXT *this, int a2)
{
  WP_CONTEXT *v2; // rsi
  DWORD LastError; // eax
  unsigned int OutstandingAllocationCount; // ebx
  __int64 result; // rax

  v2 = g_pwpContext;
  if ( UL_NATIVE_REQUEST::sm_hPendingRequestsTimer )
  {
    if ( !DeleteTimerQueueTimer(0, UL_NATIVE_REQUEST::sm_hPendingRequestsTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL)
      && (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\nativerequest.cxx",
        2046,
        "UL_NATIVE_REQUEST::StopPendingRequestsMonitor",
        "Failed to delete Ping timer (%d)\n",
        LastError);
    }
    UL_NATIVE_REQUEST::sm_hPendingRequestsTimer = 0;
  }
  if ( a2 )
    UL_APP_POOL::Cleanup((WP_CONTEXT *)((char *)v2 + 760));
  while ( 1 )
  {
    OutstandingAllocationCount = ALLOC_CACHE_HANDLER::QueryOutstandingAllocationCount(UL_NATIVE_REQUEST::sm_pachNativeRequests);
    if ( !OutstandingAllocationCount )
      break;
    ALLOC_CACHE_HANDLER::CleanupLookaside(UL_NATIVE_REQUEST::sm_pachNativeRequests, 1);
    Sleep(0x3E8u);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\nativerequest.cxx",
        1910,
        "UL_NATIVE_REQUEST::ReleaseAllWorkerRequests",
        "UL_NATIVE_REQUEST::ReleaseAllWorkerRequests waiting for %d requests to drain.\n",
        OutstandingAllocationCount);
  }
  if ( !a2 )
    UL_APP_POOL::Cleanup((WP_CONTEXT *)((char *)v2 + 760));
  while ( 1 )
  {
    result = (unsigned int)UL_DISCONNECT_CONTEXT::sm_cOutstanding;
    if ( !UL_DISCONNECT_CONTEXT::sm_cOutstanding )
      break;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\disconnectcontext.cxx",
        168,
        "UL_DISCONNECT_CONTEXT::WaitForOutstandingDisconnects",
        "Waiting for %d disconnect contexts to drain\n",
        UL_DISCONNECT_CONTEXT::sm_cOutstanding);
    Sleep(0x3E8u);
  }
  return result;
}

```

## disassembly

```asm
0x1800147e4  mov     [rsp+arg_0], rbx
0x1800147e9  mov     [rsp+arg_8], rsi
0x1800147ee  push    rdi
0x1800147ef  sub     rsp, 30h
0x1800147f3  mov     rsi, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x1800147fa  mov     edi, edx
0x1800147fc  mov     rdx, cs:?sm_hPendingRequestsTimer@UL_NATIVE_REQUEST@@0PEAXEA; Timer
0x180014803  test    rdx, rdx
0x180014806  jz      short loc_180014863
0x180014808  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001480c  xor     ecx, ecx; TimerQueue
0x18001480e  call    cs:__imp_DeleteTimerQueueTimer
0x180014814  test    eax, eax
0x180014816  jnz     short loc_180014858
0x180014818  test    byte ptr cs:g_dwDebugFlags, 3
0x18001481f  jz      short loc_180014858
0x180014821  call    cs:__imp_GetLastError
0x180014827  mov     rcx, cs:g_pDebug
0x18001482e  lea     r9, aUlNativeReques_1; "UL_NATIVE_REQUEST::StopPendingRequestsM"...
0x180014835  mov     [rsp+38h+var_10], eax
0x180014839  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180014840  lea     rax, aFailedToDelete; "Failed to delete Ping timer (%d)\n"
0x180014847  mov     r8d, 7FEh
0x18001484d  mov     [rsp+38h+var_18], rax
0x180014852  call    cs:__imp_PuDbgPrint
0x180014858  mov     cs:?sm_hPendingRequestsTimer@UL_NATIVE_REQUEST@@0PEAXEA, 0; void * UL_NATIVE_REQUEST::sm_hPendingRequestsTimer
0x180014863  test    edi, edi
0x180014865  jz      short loc_1800148CC
0x180014867  lea     rcx, [rsi+2F8h]; this
0x18001486e  call    ?Cleanup@UL_APP_POOL@@QEAAJXZ; UL_APP_POOL::Cleanup(void)
0x180014873  jmp     short loc_1800148CC
0x180014875  mov     rcx, cs:?sm_pachNativeRequests@UL_NATIVE_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * UL_NATIVE_REQUEST::sm_pachNativeRequests
0x18001487c  mov     edx, 1
0x180014881  call    cs:__imp_?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z; ALLOC_CACHE_HANDLER::CleanupLookaside(int)
0x180014887  mov     ecx, 3E8h; dwMilliseconds
0x18001488c  call    cs:__imp_Sleep
0x180014892  test    byte ptr cs:g_dwDebugFlags, 3
0x180014899  jz      short loc_1800148CC
0x18001489b  mov     rcx, cs:g_pDebug
0x1800148a2  lea     rax, aUlNativeReques_0; "UL_NATIVE_REQUEST::ReleaseAllWorkerRequ"...
0x1800148a9  mov     [rsp+38h+var_10], ebx
0x1800148ad  lea     r9, aUlNativeReques_3; "UL_NATIVE_REQUEST::ReleaseAllWorkerRequ"...
0x1800148b4  mov     r8d, 776h
0x1800148ba  mov     [rsp+38h+var_18], rax
0x1800148bf  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800148c6  call    cs:__imp_PuDbgPrint
0x1800148cc  mov     rcx, cs:?sm_pachNativeRequests@UL_NATIVE_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * UL_NATIVE_REQUEST::sm_pachNativeRequests
0x1800148d3  call    cs:__imp_?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ; ALLOC_CACHE_HANDLER::QueryOutstandingAllocationCount(void)
0x1800148d9  mov     ebx, eax
0x1800148db  test    eax, eax
0x1800148dd  jnz     short loc_180014875
0x1800148df  test    edi, edi
0x1800148e1  jnz     short loc_180014936
0x1800148e3  lea     rcx, [rsi+2F8h]; this
0x1800148ea  call    ?Cleanup@UL_APP_POOL@@QEAAJXZ; UL_APP_POOL::Cleanup(void)
0x1800148ef  jmp     short loc_180014936
0x1800148f1  test    byte ptr cs:g_dwDebugFlags, 3
0x1800148f8  jz      short loc_18001492B
0x1800148fa  mov     rcx, cs:g_pDebug
0x180014901  lea     r9, aUlDisconnectCo; "UL_DISCONNECT_CONTEXT::WaitForOutstandi"...
0x180014908  mov     [rsp+38h+var_10], eax
0x18001490c  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180014913  lea     rax, aWaitingForDDis; "Waiting for %d disconnect contexts to d"...
0x18001491a  mov     r8d, 0A8h
0x180014920  mov     [rsp+38h+var_18], rax
0x180014925  call    cs:__imp_PuDbgPrint
0x18001492b  mov     ecx, 3E8h; dwMilliseconds
0x180014930  call    cs:__imp_Sleep
0x180014936  mov     eax, cs:?sm_cOutstanding@UL_DISCONNECT_CONTEXT@@0JA; long UL_DISCONNECT_CONTEXT::sm_cOutstanding
0x18001493c  test    eax, eax
0x18001493e  jnz     short loc_1800148F1
0x180014940  mov     rbx, [rsp+38h+arg_0]
0x180014945  mov     rsi, [rsp+38h+arg_8]
0x18001494a  add     rsp, 30h
0x18001494e  pop     rdi
0x18001494f  retn
```
