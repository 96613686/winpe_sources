# DeInitEventApi(void)

- ea: `0x1800458fc`
- end: `0x180045afe`
- name: `?DeInitEventApi@@YAXXZ`
- size: `514`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003877c`

## callees

- `0x18002fd78`
- `0x180038ce4`
- `0x180039a84`
- `0x18003ae80`
- `0x1800454d0`
- `0x1800458fc`
- `0x180046364`
- `0x1800463f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045960`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045960`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045adf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045aec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045adf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045aec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045993`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045a6e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180045ac0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180045ac0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180045a52`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180045a52`
- `WINHTTP!WinHttpCloseHandle` at `0x1800459f5`
- `WINHTTP!WinHttpCloseHandle` at `0x1800459f5`

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
0x1800458fc  push    rbx
0x1800458fe  push    rbp
0x1800458ff  push    rdi
0x180045900  push    r14
0x180045902  push    r15
0x180045904  sub     rsp, 20h
0x180045908  cmp     cs:?g_fEventApiShutDown@@3HA, 0; int g_fEventApiShutDown
0x18004590f  jnz     loc_180045AF2
0x180045915  cmp     cs:?g_fEventApiInitialized@@3HA, 0; int g_fEventApiInitialized
0x18004591c  jz      loc_180045AF2
0x180045922  mov     rcx, cs:WPP_GLOBAL_Control
0x180045929  lea     rbp, WPP_GLOBAL_Control
0x180045930  lea     r15, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180045937  mov     r14d, 800h
0x18004593d  cmp     rcx, rbp
0x180045940  jz      short loc_180045959
0x180045942  test    [rcx+1Ch], r14d
0x180045946  jz      short loc_180045959
0x180045948  mov     rcx, [rcx+10h]
0x18004594c  mov     edx, 12h
0x180045951  mov     r8, r15
0x180045954  call    WPP_SF_
0x180045959  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180045960  call    cs:__imp_EnterCriticalSection
0x180045966  mov     rdi, cs:?g_pesList@@3PEAUUPNP_EVENT_SOURCE@@EA; UPNP_EVENT_SOURCE * g_pesList
0x18004596d  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180045974  mov     cs:?g_fEventApiShutDown@@3HA, 1; int g_fEventApiShutDown
0x18004597e  mov     cs:?g_fEventApiInitialized@@3HA, 0; int g_fEventApiInitialized
0x180045988  mov     cs:?g_pesList@@3PEAUUPNP_EVENT_SOURCE@@EA, 0; UPNP_EVENT_SOURCE * g_pesList
0x180045993  call    cs:__imp_LeaveCriticalSection
0x180045999  test    rdi, rdi
0x18004599c  jz      short loc_1800459B2
0x18004599e  mov     rbx, [rdi+18h]
0x1800459a2  mov     rcx, rdi; struct UPNP_EVENT_SOURCE *
0x1800459a5  call    ?FreeEventSourceBlocking@@YAXPEAUUPNP_EVENT_SOURCE@@@Z; FreeEventSourceBlocking(UPNP_EVENT_SOURCE *)
0x1800459aa  mov     rdi, rbx
0x1800459ad  test    rbx, rbx
0x1800459b0  jnz     short loc_18004599E
0x1800459b2  call    ?WaitForDelayedSubscriptionDeletion@@YAXXZ; WaitForDelayedSubscriptionDeletion(void)
0x1800459b7  call    ?WaitForDelayedEventSourceDeletion@@YAXXZ; WaitForDelayedEventSourceDeletion(void)
0x1800459bc  mov     rcx, cs:?g_hInetSess@@3PEAXEA; void * g_hInetSess
0x1800459c3  test    rcx, rcx
0x1800459c6  jz      short loc_180045A06
0x1800459c8  mov     rax, cs:WPP_GLOBAL_Control
0x1800459cf  cmp     rax, rbp
0x1800459d2  jz      short loc_1800459F5
0x1800459d4  test    [rax+1Ch], r14d
0x1800459d8  jz      short loc_1800459F5
0x1800459da  mov     r9, rcx
0x1800459dd  mov     edx, 13h
0x1800459e2  mov     rcx, [rax+10h]
0x1800459e6  mov     r8, r15
0x1800459e9  call    WPP_SF_q
0x1800459ee  mov     rcx, cs:?g_hInetSess@@3PEAXEA; hInternet
0x1800459f5  call    cs:__imp_WinHttpCloseHandle
0x1800459fb  mov     cs:?g_hInetSess@@3PEAXEA, 0; void * g_hInetSess
0x180045a06  mov     rax, cs:?g_hTimerQ@@3PEAXEA; void * g_hTimerQ
0x180045a0d  test    rax, rax
0x180045a10  jz      loc_180045AB4
0x180045a16  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a1d  cmp     rcx, rbp
0x180045a20  jz      short loc_180045A40
0x180045a22  test    [rcx+1Ch], r14d
0x180045a26  jz      short loc_180045A40
0x180045a28  mov     rcx, [rcx+10h]
0x180045a2c  mov     edx, 14h
0x180045a31  mov     r8, r15
0x180045a34  call    WPP_SF_
0x180045a39  mov     rax, cs:?g_hTimerQ@@3PEAXEA; void * g_hTimerQ
0x180045a40  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180045a44  mov     cs:?g_hTimerQ@@3PEAXEA, 0; void * g_hTimerQ
0x180045a4f  mov     rcx, rax; TimerQueue
0x180045a52  call    cs:__imp_DeleteTimerQueueEx
0x180045a58  test    eax, eax
0x180045a5a  jnz     short loc_180045A91
0x180045a5c  mov     rax, cs:WPP_GLOBAL_Control
0x180045a63  cmp     rax, rbp
0x180045a66  jz      short loc_180045AB4
0x180045a68  test    byte ptr [rax+1Ch], 1
0x180045a6c  jz      short loc_180045AB4
0x180045a6e  call    cs:__imp_GetLastError
0x180045a74  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a7b  mov     edx, 15h
0x180045a80  mov     r9d, eax
0x180045a83  mov     r8, r15
0x180045a86  mov     rcx, [rcx+10h]
0x180045a8a  call    WPP_SF_d
0x180045a8f  jmp     short loc_180045AB4
0x180045a91  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a98  cmp     rcx, rbp
0x180045a9b  jz      short loc_180045AB4
0x180045a9d  test    [rcx+1Ch], r14d
0x180045aa1  jz      short loc_180045AB4
0x180045aa3  mov     rcx, [rcx+10h]
0x180045aa7  mov     edx, 16h
0x180045aac  mov     r8, r15
0x180045aaf  call    WPP_SF_
0x180045ab4  mov     rcx, cs:ptpp; ptpp
0x180045abb  test    rcx, rcx
0x180045abe  jz      short loc_180045AC6
0x180045ac0  call    cs:__imp_CloseThreadpool
0x180045ac6  xor     edx, edx; Val
0x180045ac8  lea     rcx, ptpp; void *
0x180045acf  lea     r8d, [rdx+50h]; Size
0x180045ad3  call    memset_0
0x180045ad8  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180045adf  call    cs:__imp_DeleteCriticalSection
0x180045ae5  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180045aec  call    cs:__imp_DeleteCriticalSection
0x180045af2  add     rsp, 20h
0x180045af6  pop     r15
0x180045af8  pop     r14
0x180045afa  pop     rdi
0x180045afb  pop     rbp
0x180045afc  pop     rbx
0x180045afd  retn
```
