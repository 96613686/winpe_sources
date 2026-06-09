# DeInitEventApi(void)

- ea: `0x180048554`
- end: `0x180048787`
- name: `?DeInitEventApi@@YAXXZ`
- size: `563`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003ac54`

## callees

- `0x180031894`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003d4b0`
- `0x1800480c0`
- `0x180048554`
- `0x18004903c`
- `0x1800490e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800485b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800485b8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004875b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004876e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004875b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004876e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800485f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800485f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800486de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800486de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180048736`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180048736`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800486bc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800486bc`
- `WINHTTP!WinHttpCloseHandle` at `0x180048659`
- `WINHTTP!WinHttpCloseHandle` at `0x180048659`

## pseudocode

```c
void DeInitEventApi(void)
{
  struct UPNP_EVENT_SOURCE *v0; // rdi
  struct UPNP_EVENT_SOURCE *v1; // rbx
  void *v2; // rcx
  HANDLE v3; // rax
  DWORD LastError; // eax

  if ( !g_fEventApiShutDown && g_fEventApiInitialized )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
    }
    EnterCriticalSection(&g_csEventApiLock);
    v0 = g_pesList;
    g_fEventApiShutDown = 1;
    g_fEventApiInitialized = 0;
    g_pesList = 0;
    LeaveCriticalSection(&g_csEventApiLock);
    if ( v0 )
    {
      do
      {
        v1 = (struct UPNP_EVENT_SOURCE *)*((_QWORD *)v0 + 3);
        FreeEventSourceBlocking(v0);
        v0 = v1;
      }
      while ( v1 );
    }
    WaitForDelayedSubscriptionDeletion();
    WaitForDelayedEventSourceDeletion();
    v2 = g_hInetSess;
    if ( g_hInetSess )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, g_hInetSess);
        v2 = g_hInetSess;
      }
      WinHttpCloseHandle(v2);
      g_hInetSess = 0;
    }
    v3 = g_hTimerQ;
    if ( g_hTimerQ )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
        v3 = g_hTimerQ;
      }
      g_hTimerQ = 0;
      if ( DeleteTimerQueueEx(v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
        }
      }
      else if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, LastError);
      }
    }
    if ( ptpp )
      CloseThreadpool(ptpp);
    memset_0(&ptpp, 0, 0x50u);
    DeleteCriticalSection(&g_csEventApiLock);
    DeleteCriticalSection(&g_csEventTimerLock);
  }
}

```

## disassembly

```asm
0x180048554  push    rbx
0x180048556  push    rbp
0x180048557  push    rdi
0x180048558  push    r14
0x18004855a  push    r15
0x18004855c  sub     rsp, 20h
0x180048560  cmp     cs:?g_fEventApiShutDown@@3HA, 0; int g_fEventApiShutDown
0x180048567  jnz     loc_18004877A
0x18004856d  cmp     cs:?g_fEventApiInitialized@@3HA, 0; int g_fEventApiInitialized
0x180048574  jz      loc_18004877A
0x18004857a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048581  lea     rbp, WPP_GLOBAL_Control
0x180048588  lea     r15, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x18004858f  mov     r14d, 800h
0x180048595  cmp     rcx, rbp
0x180048598  jz      short loc_1800485B1
0x18004859a  test    [rcx+1Ch], r14d
0x18004859e  jz      short loc_1800485B1
0x1800485a0  mov     rcx, [rcx+10h]
0x1800485a4  mov     edx, 12h
0x1800485a9  mov     r8, r15
0x1800485ac  call    WPP_SF_
0x1800485b1  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800485b8  call    cs:__imp_EnterCriticalSection
0x1800485bf  nop     dword ptr [rax+rax+00h]
0x1800485c4  mov     rdi, cs:?g_pesList@@3PEAUUPNP_EVENT_SOURCE@@EA; UPNP_EVENT_SOURCE * g_pesList
0x1800485cb  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800485d2  mov     cs:?g_fEventApiShutDown@@3HA, 1; int g_fEventApiShutDown
0x1800485dc  mov     cs:?g_fEventApiInitialized@@3HA, 0; int g_fEventApiInitialized
0x1800485e6  mov     cs:?g_pesList@@3PEAUUPNP_EVENT_SOURCE@@EA, 0; UPNP_EVENT_SOURCE * g_pesList
0x1800485f1  call    cs:__imp_LeaveCriticalSection
0x1800485f8  nop     dword ptr [rax+rax+00h]
0x1800485fd  test    rdi, rdi
0x180048600  jz      short loc_180048616
0x180048602  mov     rbx, [rdi+18h]
0x180048606  mov     rcx, rdi; struct UPNP_EVENT_SOURCE *
0x180048609  call    ?FreeEventSourceBlocking@@YAXPEAUUPNP_EVENT_SOURCE@@@Z; FreeEventSourceBlocking(UPNP_EVENT_SOURCE *)
0x18004860e  mov     rdi, rbx
0x180048611  test    rbx, rbx
0x180048614  jnz     short loc_180048602
0x180048616  call    ?WaitForDelayedSubscriptionDeletion@@YAXXZ; WaitForDelayedSubscriptionDeletion(void)
0x18004861b  call    ?WaitForDelayedEventSourceDeletion@@YAXXZ; WaitForDelayedEventSourceDeletion(void)
0x180048620  mov     rcx, cs:?g_hInetSess@@3PEAXEA; void * g_hInetSess
0x180048627  test    rcx, rcx
0x18004862a  jz      short loc_180048670
0x18004862c  mov     rax, cs:WPP_GLOBAL_Control
0x180048633  cmp     rax, rbp
0x180048636  jz      short loc_180048659
0x180048638  test    [rax+1Ch], r14d
0x18004863c  jz      short loc_180048659
0x18004863e  mov     r9, rcx
0x180048641  mov     edx, 13h
0x180048646  mov     rcx, [rax+10h]
0x18004864a  mov     r8, r15
0x18004864d  call    WPP_SF_q
0x180048652  mov     rcx, cs:?g_hInetSess@@3PEAXEA; hInternet
0x180048659  call    cs:__imp_WinHttpCloseHandle
0x180048660  nop     dword ptr [rax+rax+00h]
0x180048665  mov     cs:?g_hInetSess@@3PEAXEA, 0; void * g_hInetSess
0x180048670  mov     rax, cs:?g_hTimerQ@@3PEAXEA; void * g_hTimerQ
0x180048677  test    rax, rax
0x18004867a  jz      loc_18004872A
0x180048680  mov     rcx, cs:WPP_GLOBAL_Control
0x180048687  cmp     rcx, rbp
0x18004868a  jz      short loc_1800486AA
0x18004868c  test    [rcx+1Ch], r14d
0x180048690  jz      short loc_1800486AA
0x180048692  mov     rcx, [rcx+10h]
0x180048696  mov     edx, 14h
0x18004869b  mov     r8, r15
0x18004869e  call    WPP_SF_
0x1800486a3  mov     rax, cs:?g_hTimerQ@@3PEAXEA; void * g_hTimerQ
0x1800486aa  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800486ae  mov     cs:?g_hTimerQ@@3PEAXEA, 0; void * g_hTimerQ
0x1800486b9  mov     rcx, rax; TimerQueue
0x1800486bc  call    cs:__imp_DeleteTimerQueueEx
0x1800486c3  nop     dword ptr [rax+rax+00h]
0x1800486c8  test    eax, eax
0x1800486ca  jnz     short loc_180048707
0x1800486cc  mov     rax, cs:WPP_GLOBAL_Control
0x1800486d3  cmp     rax, rbp
0x1800486d6  jz      short loc_18004872A
0x1800486d8  test    byte ptr [rax+1Ch], 1
0x1800486dc  jz      short loc_18004872A
0x1800486de  call    cs:__imp_GetLastError
0x1800486e5  nop     dword ptr [rax+rax+00h]
0x1800486ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800486f1  mov     edx, 15h
0x1800486f6  mov     r9d, eax
0x1800486f9  mov     r8, r15
0x1800486fc  mov     rcx, [rcx+10h]
0x180048700  call    WPP_SF_d
0x180048705  jmp     short loc_18004872A
0x180048707  mov     rcx, cs:WPP_GLOBAL_Control
0x18004870e  cmp     rcx, rbp
0x180048711  jz      short loc_18004872A
0x180048713  test    [rcx+1Ch], r14d
0x180048717  jz      short loc_18004872A
0x180048719  mov     rcx, [rcx+10h]
0x18004871d  mov     edx, 16h
0x180048722  mov     r8, r15
0x180048725  call    WPP_SF_
0x18004872a  mov     rcx, cs:ptpp; ptpp
0x180048731  test    rcx, rcx
0x180048734  jz      short loc_180048742
0x180048736  call    cs:__imp_CloseThreadpool
0x18004873d  nop     dword ptr [rax+rax+00h]
0x180048742  xor     edx, edx; Val
0x180048744  lea     rcx, ptpp; void *
0x18004874b  lea     r8d, [rdx+50h]; Size
0x18004874f  call    memset_0
0x180048754  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004875b  call    cs:__imp_DeleteCriticalSection
0x180048762  nop     dword ptr [rax+rax+00h]
0x180048767  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004876e  call    cs:__imp_DeleteCriticalSection
0x180048775  nop     dword ptr [rax+rax+00h]
0x18004877a  add     rsp, 20h
0x18004877e  pop     r15
0x180048780  pop     r14
0x180048782  pop     rdi
0x180048783  pop     rbp
0x180048784  pop     rbx
0x180048785  retn
```
