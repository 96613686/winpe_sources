# HrInitEventApi(void)

- ea: `0x180036cdc`
- end: `0x180036fc0`
- name: `?HrInitEventApi@@YAJXZ`
- size: `740`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180031c70`

## callees

- `0x1800074dc`
- `0x1800200f4`
- `0x180036cdc`
- `0x1800480c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180036d3c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180036d4f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180036d3c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180036d4f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036e00`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036e13`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036efa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036f0d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036e00`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036e13`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036efa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036f0d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180036ed4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180036ed4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180036f45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180036f45`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180036f24`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180036f24`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180036d94`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180036d94`

## string_xrefs

- `0x180036dd9`: `HrInitEventApi: CreateTimerQueue`

## pseudocode

```c
__int64 HrInitEventApi(void)
{
  int v0; // edi
  HANDLE TimerQueue; // rax
  int Win32Error; // eax
  bool v4; // zf
  struct _TP_POOL *Threadpool; // rax

  v0 = 0;
  if ( g_fEventApiShutDown )
  {
    InitializeCriticalSection(&g_csEventApiLock);
    InitializeCriticalSection(&g_csEventTimerLock);
    qword_180075BD0 = (__int64)&g_DelayedSubscriptionDeletionList;
    g_DelayedSubscriptionDeletionList.Flink = &g_DelayedSubscriptionDeletionList;
    qword_180075BE0 = (__int64)&g_DelayedEventSourceDeletionList;
    g_DelayedEventSourceDeletionList.Flink = &g_DelayedEventSourceDeletionList;
    TimerQueue = CreateTimerQueue();
    g_hTimerQ = TimerQueue;
    if ( TimerQueue )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, TimerQueue);
      }
    }
    else
    {
      Win32Error = HrFromLastWin32Error();
      v0 = Win32Error;
      if ( Win32Error && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
          (unsigned int)"HrInitEventApi: CreateTimerQueue",
          Win32Error);
      DeleteCriticalSection(&g_csEventApiLock);
      DeleteCriticalSection(&g_csEventTimerLock);
    }
    v4 = v0 == 0;
    if ( v0 >= 0 )
    {
      ptpp = 0;
      *(_QWORD *)&pcbe.Version = 3;
      *(_QWORD *)&pcbe.Size = 72;
      *(_OWORD *)&pcbe.Pool = 0;
      pcbe.CleanupGroupCancelCallback = 0;
      pcbe.RaceDll = 0;
      pcbe.ActivationContext = 0;
      pcbe.FinalizationCallback = 0;
      pcbe.u.Flags = 0;
      pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
      Threadpool = CreateThreadpool(0);
      ptpp = Threadpool;
      if ( Threadpool )
      {
        SetThreadpoolThreadMaximum(Threadpool, 0x32u);
        pcbe.Pool = ptpp;
        pcbe.u.Flags |= 1u;
      }
      else
      {
        v0 = HrFromLastWin32Error();
        DeleteCriticalSection(&g_csEventApiLock);
        DeleteCriticalSection(&g_csEventTimerLock);
        DeleteTimerQueueEx(g_hTimerQ, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        g_hTimerQ = 0;
      }
      v4 = v0 == 0;
      if ( v0 >= 0 )
      {
        g_fEventApiShutDown = 0;
        g_fEventApiInitialized = 1;
      }
    }
    if ( !v4 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
        (unsigned int)"HrInitEventApi",
        v0);
    return (unsigned int)v0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
        (unsigned int)"HrInitEventApi",
        5);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180036cdc  mov     [rsp+arg_0], rsi
0x180036ce1  push    rdi
0x180036ce2  sub     rsp, 30h
0x180036ce6  xor     edi, edi
0x180036ce8  cmp     cs:?g_fEventApiShutDown@@3HA, edi; int g_fEventApiShutDown
0x180036cee  jnz     short loc_180036D35
0x180036cf0  lea     rsi, WPP_GLOBAL_Control
0x180036cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cfe  cmp     rcx, rsi
0x180036d01  jz      short loc_180036D2B
0x180036d03  test    byte ptr [rcx+1Ch], 1
0x180036d07  jz      short loc_180036D2B
0x180036d09  lea     edx, [rdi+0Ah]
0x180036d0c  mov     [rsp+38h+var_18], 80004005h
0x180036d14  lea     r9, aHriniteventapi_0; "HrInitEventApi"
0x180036d1b  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180036d22  mov     rcx, [rcx+10h]
0x180036d26  call    WPP_SF_sd
0x180036d2b  mov     eax, 80004005h
0x180036d30  jmp     loc_180036FB4
0x180036d35  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036d3c  call    cs:__imp_InitializeCriticalSection
0x180036d43  nop     dword ptr [rax+rax+00h]
0x180036d48  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036d4f  call    cs:__imp_InitializeCriticalSection
0x180036d56  nop     dword ptr [rax+rax+00h]
0x180036d5b  jmp     short loc_180036D62
0x180036d5d  mov     edi, 8007000Eh
0x180036d62  lea     rax, ?g_DelayedSubscriptionDeletionList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_DelayedSubscriptionDeletionList
0x180036d69  mov     cs:qword_180075BD0, rax
0x180036d70  mov     cs:?g_DelayedSubscriptionDeletionList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_DelayedSubscriptionDeletionList
0x180036d77  lea     rax, ?g_DelayedEventSourceDeletionList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_DelayedEventSourceDeletionList
0x180036d7e  mov     cs:qword_180075BE0, rax
0x180036d85  mov     cs:?g_DelayedEventSourceDeletionList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_DelayedEventSourceDeletionList
0x180036d8c  test    edi, edi
0x180036d8e  js      loc_180036E57
0x180036d94  call    cs:__imp_CreateTimerQueue
0x180036d9b  nop     dword ptr [rax+rax+00h]
0x180036da0  mov     cs:?g_hTimerQ@@3PEAXEA, rax; void * g_hTimerQ
0x180036da7  test    rax, rax
0x180036daa  jnz     short loc_180036E21
0x180036dac  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180036db1  mov     edi, eax
0x180036db3  test    eax, eax
0x180036db5  jz      short loc_180036DF2
0x180036db7  lea     rsi, WPP_GLOBAL_Control
0x180036dbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180036dc5  cmp     rcx, rsi
0x180036dc8  jz      short loc_180036DF9
0x180036dca  test    byte ptr [rcx+1Ch], 1
0x180036dce  jz      short loc_180036DF9
0x180036dd0  mov     edx, 0Bh
0x180036dd5  mov     [rsp+38h+var_18], eax
0x180036dd9  lea     r9, aHriniteventapi; "HrInitEventApi: CreateTimerQueue"
0x180036de0  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180036de7  mov     rcx, [rcx+10h]
0x180036deb  call    WPP_SF_sd
0x180036df0  jmp     short loc_180036DF9
0x180036df2  lea     rsi, WPP_GLOBAL_Control
0x180036df9  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036e00  call    cs:__imp_DeleteCriticalSection
0x180036e07  nop     dword ptr [rax+rax+00h]
0x180036e0c  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036e13  call    cs:__imp_DeleteCriticalSection
0x180036e1a  nop     dword ptr [rax+rax+00h]
0x180036e1f  jmp     short loc_180036E5E
0x180036e21  lea     rsi, WPP_GLOBAL_Control
0x180036e28  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e2f  cmp     rcx, rsi
0x180036e32  jz      short loc_180036E5E
0x180036e34  test    dword ptr [rcx+1Ch], 800h
0x180036e3b  jz      short loc_180036E5E
0x180036e3d  mov     edx, 0Ch
0x180036e42  mov     r9, rax
0x180036e45  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180036e4c  mov     rcx, [rcx+10h]
0x180036e50  call    WPP_SF_q
0x180036e55  jmp     short loc_180036E5E
0x180036e57  lea     rsi, WPP_GLOBAL_Control
0x180036e5e  test    edi, edi
0x180036e60  js      loc_180036F7E
0x180036e66  mov     cs:ptpp, 0
0x180036e71  mov     qword ptr cs:pcbe.Version, 3
0x180036e7c  mov     qword ptr cs:pcbe.Size, 48h ; 'H'
0x180036e87  xorps   xmm0, xmm0
0x180036e8a  movdqa  xmmword ptr cs:pcbe.Pool, xmm0
0x180036e92  mov     cs:pcbe.CleanupGroupCancelCallback, 0
0x180036e9d  mov     cs:pcbe.RaceDll, 0
0x180036ea8  mov     cs:pcbe.ActivationContext, 0
0x180036eb3  mov     cs:pcbe.FinalizationCallback, 0
0x180036ebe  mov     dword ptr cs:pcbe.u, 0
0x180036ec8  mov     cs:pcbe.CallbackPriority, 1
0x180036ed2  xor     ecx, ecx; reserved
0x180036ed4  call    cs:__imp_CreateThreadpool
0x180036edb  nop     dword ptr [rax+rax+00h]
0x180036ee0  mov     cs:ptpp, rax
0x180036ee7  test    rax, rax
0x180036eea  jnz     short loc_180036F3D
0x180036eec  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180036ef1  mov     edi, eax
0x180036ef3  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036efa  call    cs:__imp_DeleteCriticalSection
0x180036f01  nop     dword ptr [rax+rax+00h]
0x180036f06  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036f0d  call    cs:__imp_DeleteCriticalSection
0x180036f14  nop     dword ptr [rax+rax+00h]
0x180036f19  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180036f1d  mov     rcx, cs:?g_hTimerQ@@3PEAXEA; TimerQueue
0x180036f24  call    cs:__imp_DeleteTimerQueueEx
0x180036f2b  nop     dword ptr [rax+rax+00h]
0x180036f30  mov     cs:?g_hTimerQ@@3PEAXEA, 0; void * g_hTimerQ
0x180036f3b  jmp     short loc_180036F66
0x180036f3d  mov     edx, 32h ; '2'; cthrdMost
0x180036f42  mov     rcx, rax; ptpp
0x180036f45  call    cs:__imp_SetThreadpoolThreadMaximum
0x180036f4c  nop     dword ptr [rax+rax+00h]
0x180036f51  mov     rax, cs:ptpp
0x180036f58  mov     cs:pcbe.Pool, rax
0x180036f5f  or      dword ptr cs:pcbe.u, 1
0x180036f66  test    edi, edi
0x180036f68  js      short loc_180036F7E
0x180036f6a  mov     cs:?g_fEventApiShutDown@@3HA, 0; int g_fEventApiShutDown
0x180036f74  mov     cs:?g_fEventApiInitialized@@3HA, 1; int g_fEventApiInitialized
0x180036f7e  jz      short loc_180036FB2
0x180036f80  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f87  cmp     rcx, rsi
0x180036f8a  jz      short loc_180036FB2
0x180036f8c  test    byte ptr [rcx+1Ch], 1
0x180036f90  jz      short loc_180036FB2
0x180036f92  mov     edx, 0Dh
0x180036f97  mov     [rsp+38h+var_18], edi
0x180036f9b  lea     r9, aHriniteventapi_0; "HrInitEventApi"
0x180036fa2  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180036fa9  mov     rcx, [rcx+10h]
0x180036fad  call    WPP_SF_sd
0x180036fb2  mov     eax, edi
0x180036fb4  mov     rsi, [rsp+38h+arg_0]
0x180036fb9  add     rsp, 30h
0x180036fbd  pop     rdi
0x180036fbe  retn
0x180057e77  push    rbp
0x180057e79  sub     rsp, 30h
0x180057e7d  mov     rbp, rdx
0x180057e80  mov     rax, [rcx]
0x180057e83  xor     ecx, ecx
0x180057e85  cmp     dword ptr [rax], 0C0000017h
0x180057e8b  setz    cl
0x180057e8e  mov     eax, ecx
0x180057e90  add     rsp, 30h
0x180057e94  pop     rbp
0x180057e95  retn
```
