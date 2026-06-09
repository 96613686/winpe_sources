# HrInitEventApi(void)

- ea: `0x180034c8c`
- end: `0x180034f33`
- name: `?HrInitEventApi@@YAJXZ`
- size: `679`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180030160`

## callees

- `0x18000db4c`
- `0x18001347c`
- `0x180034c8c`
- `0x1800454d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034cec`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034cf9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034cec`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034cf9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034d9e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034dab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034e86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034e93`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034d9e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034dab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034e86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034e93`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180034e66`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180034e66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180034ebf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180034ebf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180034ea4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180034ea4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180034d38`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180034d38`

## string_xrefs

- `0x180034d77`: `HrInitEventApi: CreateTimerQueue`

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
    qword_180071AE0 = (__int64)&g_DelayedSubscriptionDeletionList;
    g_DelayedSubscriptionDeletionList.Flink = &g_DelayedSubscriptionDeletionList;
    qword_180071AF0 = (__int64)&g_DelayedEventSourceDeletionList;
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
0x180034c8c  mov     [rsp+arg_0], rsi
0x180034c91  push    rdi
0x180034c92  sub     rsp, 30h
0x180034c96  xor     edi, edi
0x180034c98  cmp     cs:?g_fEventApiShutDown@@3HA, edi; int g_fEventApiShutDown
0x180034c9e  jnz     short loc_180034CE5
0x180034ca0  lea     rsi, WPP_GLOBAL_Control
0x180034ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x180034cae  cmp     rcx, rsi
0x180034cb1  jz      short loc_180034CDB
0x180034cb3  test    byte ptr [rcx+1Ch], 1
0x180034cb7  jz      short loc_180034CDB
0x180034cb9  lea     edx, [rdi+0Ah]
0x180034cbc  mov     [rsp+38h+var_18], 80004005h
0x180034cc4  lea     r9, aHriniteventapi_0; "HrInitEventApi"
0x180034ccb  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180034cd2  mov     rcx, [rcx+10h]
0x180034cd6  call    WPP_SF_sd
0x180034cdb  mov     eax, 80004005h
0x180034ce0  jmp     loc_180034F28
0x180034ce5  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180034cec  call    cs:__imp_InitializeCriticalSection
0x180034cf2  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180034cf9  call    cs:__imp_InitializeCriticalSection
0x180034cff  jmp     short loc_180034D06
0x180034d01  mov     edi, 8007000Eh
0x180034d06  lea     rax, ?g_DelayedSubscriptionDeletionList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_DelayedSubscriptionDeletionList
0x180034d0d  mov     cs:qword_180071AE0, rax
0x180034d14  mov     cs:?g_DelayedSubscriptionDeletionList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_DelayedSubscriptionDeletionList
0x180034d1b  lea     rax, ?g_DelayedEventSourceDeletionList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_DelayedEventSourceDeletionList
0x180034d22  mov     cs:qword_180071AF0, rax
0x180034d29  mov     cs:?g_DelayedEventSourceDeletionList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_DelayedEventSourceDeletionList
0x180034d30  test    edi, edi
0x180034d32  js      loc_180034DE9
0x180034d38  call    cs:__imp_CreateTimerQueue
0x180034d3e  mov     cs:?g_hTimerQ@@3PEAXEA, rax; void * g_hTimerQ
0x180034d45  test    rax, rax
0x180034d48  jnz     short loc_180034DB3
0x180034d4a  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180034d4f  mov     edi, eax
0x180034d51  test    eax, eax
0x180034d53  jz      short loc_180034D90
0x180034d55  lea     rsi, WPP_GLOBAL_Control
0x180034d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d63  cmp     rcx, rsi
0x180034d66  jz      short loc_180034D97
0x180034d68  test    byte ptr [rcx+1Ch], 1
0x180034d6c  jz      short loc_180034D97
0x180034d6e  mov     edx, 0Bh
0x180034d73  mov     [rsp+38h+var_18], eax
0x180034d77  lea     r9, aHriniteventapi; "HrInitEventApi: CreateTimerQueue"
0x180034d7e  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180034d85  mov     rcx, [rcx+10h]
0x180034d89  call    WPP_SF_sd
0x180034d8e  jmp     short loc_180034D97
0x180034d90  lea     rsi, WPP_GLOBAL_Control
0x180034d97  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180034d9e  call    cs:__imp_DeleteCriticalSection
0x180034da4  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180034dab  call    cs:__imp_DeleteCriticalSection
0x180034db1  jmp     short loc_180034DF0
0x180034db3  lea     rsi, WPP_GLOBAL_Control
0x180034dba  mov     rcx, cs:WPP_GLOBAL_Control
0x180034dc1  cmp     rcx, rsi
0x180034dc4  jz      short loc_180034DF0
0x180034dc6  test    dword ptr [rcx+1Ch], 800h
0x180034dcd  jz      short loc_180034DF0
0x180034dcf  mov     edx, 0Ch
0x180034dd4  mov     r9, rax
0x180034dd7  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180034dde  mov     rcx, [rcx+10h]
0x180034de2  call    WPP_SF_q
0x180034de7  jmp     short loc_180034DF0
0x180034de9  lea     rsi, WPP_GLOBAL_Control
0x180034df0  test    edi, edi
0x180034df2  js      loc_180034EF2
0x180034df8  mov     cs:ptpp, 0
0x180034e03  mov     qword ptr cs:pcbe.Version, 3
0x180034e0e  mov     qword ptr cs:pcbe.Size, 48h ; 'H'
0x180034e19  xorps   xmm0, xmm0
0x180034e1c  movdqa  xmmword ptr cs:pcbe.Pool, xmm0
0x180034e24  mov     cs:pcbe.CleanupGroupCancelCallback, 0
0x180034e2f  mov     cs:pcbe.RaceDll, 0
0x180034e3a  mov     cs:pcbe.ActivationContext, 0
0x180034e45  mov     cs:pcbe.FinalizationCallback, 0
0x180034e50  mov     dword ptr cs:pcbe.u, 0
0x180034e5a  mov     cs:pcbe.CallbackPriority, 1
0x180034e64  xor     ecx, ecx; reserved
0x180034e66  call    cs:__imp_CreateThreadpool
0x180034e6c  mov     cs:ptpp, rax
0x180034e73  test    rax, rax
0x180034e76  jnz     short loc_180034EB7
0x180034e78  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180034e7d  mov     edi, eax
0x180034e7f  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180034e86  call    cs:__imp_DeleteCriticalSection
0x180034e8c  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180034e93  call    cs:__imp_DeleteCriticalSection
0x180034e99  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180034e9d  mov     rcx, cs:?g_hTimerQ@@3PEAXEA; TimerQueue
0x180034ea4  call    cs:__imp_DeleteTimerQueueEx
0x180034eaa  mov     cs:?g_hTimerQ@@3PEAXEA, 0; void * g_hTimerQ
0x180034eb5  jmp     short loc_180034EDA
0x180034eb7  mov     edx, 32h ; '2'; cthrdMost
0x180034ebc  mov     rcx, rax; ptpp
0x180034ebf  call    cs:__imp_SetThreadpoolThreadMaximum
0x180034ec5  mov     rax, cs:ptpp
0x180034ecc  mov     cs:pcbe.Pool, rax
0x180034ed3  or      dword ptr cs:pcbe.u, 1
0x180034eda  test    edi, edi
0x180034edc  js      short loc_180034EF2
0x180034ede  mov     cs:?g_fEventApiShutDown@@3HA, 0; int g_fEventApiShutDown
0x180034ee8  mov     cs:?g_fEventApiInitialized@@3HA, 1; int g_fEventApiInitialized
0x180034ef2  jz      short loc_180034F26
0x180034ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180034efb  cmp     rcx, rsi
0x180034efe  jz      short loc_180034F26
0x180034f00  test    byte ptr [rcx+1Ch], 1
0x180034f04  jz      short loc_180034F26
0x180034f06  mov     edx, 0Dh
0x180034f0b  mov     [rsp+38h+var_18], edi
0x180034f0f  lea     r9, aHriniteventapi_0; "HrInitEventApi"
0x180034f16  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180034f1d  mov     rcx, [rcx+10h]
0x180034f21  call    WPP_SF_sd
0x180034f26  mov     eax, edi
0x180034f28  mov     rsi, [rsp+38h+arg_0]
0x180034f2d  add     rsp, 30h
0x180034f31  pop     rdi
0x180034f32  retn
0x1800544c8  push    rbp
0x1800544ca  sub     rsp, 30h
0x1800544ce  mov     rbp, rdx
0x1800544d1  mov     rax, [rcx]
0x1800544d4  xor     ecx, ecx
0x1800544d6  cmp     dword ptr [rax], 0C0000017h
0x1800544dc  setz    cl
0x1800544df  mov     eax, ecx
0x1800544e1  add     rsp, 30h
0x1800544e5  pop     rbp
0x1800544e6  retn
```
