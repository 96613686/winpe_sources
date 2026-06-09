# HrRenewSubscriber(ushort const *,ulong *,ushort const *)

- ea: `0x180033c24`
- end: `0x18003408f`
- name: `?HrRenewSubscriber@@YAJPEBGPEAK0@Z`
- size: `1131`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180033b50`

## callees

- `0x1800074dc`
- `0x1800200f4`
- `0x1800209c8`
- `0x180027b60`
- `0x180027ca4`
- `0x180027fc8`
- `0x180033c24`
- `0x18003b1cc`
- `0x18003b904`
- `0x18003c018`
- `0x180049430`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033e71`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033e84`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033f6a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033f7d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033e71`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033e84`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033f6a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033f7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033cf8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033d3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033e06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033cf8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033d3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033e06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033d52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033df3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033e51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003403f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033d52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033df3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033e51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003403f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033cca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033fad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033cca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033fad`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180033f16`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180033f16`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180033d75`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180033d75`

## string_xrefs

- `0x180033dac`: `HrRenewSubscriber: DeleteTimerQueueTimer`
- `0x180033f47`: `HrRenewSubscriber: CreateTimerQueueTimer`

## pseudocode

```c
__int64 __fastcall HrRenewSubscriber(const unsigned __int16 *a1, unsigned int *a2, const unsigned __int16 *a3)
{
  STRSAFE_PCNZWCH v6; // rcx
  unsigned int v7; // ebx
  int v8; // edx
  STRSAFE_PCNZWCH v9; // rax
  void *v10; // rbx
  DWORD TickCount; // eax
  struct UPNP_EVENT_SOURCE *EventSource; // rax
  struct UPNP_SUBSCRIBER *Subscriber; // rax
  char Win32Error; // al
  struct UPNP_EVENT_SOURCE *v15; // rax
  STRSAFE_PCNZWCH *v16; // rbx
  struct UPNP_SUBSCRIBER *v17; // rax
  struct UPNP_SUBSCRIBER *v18; // rsi
  void **v19; // r14
  unsigned __int16 **v21; // r15
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // rax
  HANDLE v24; // rdx
  unsigned int v25; // eax
  DWORD v26; // eax

  if ( g_fEventApiInitialized )
  {
    v9 = WPP_GLOBAL_Control;
    v10 = 0;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
          (_DWORD)a3,
          (__int64)a1);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 )
      {
        TickCount = GetTickCount();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, TickCount);
      }
    }
    EnterCriticalSection(&g_csEventApiLock);
    EventSource = PesFindEventSource(a1);
    if ( EventSource )
    {
      Subscriber = PsubFindSubscriber(EventSource, a3);
      if ( Subscriber )
      {
        v10 = (void *)*((_QWORD *)Subscriber + 28);
        *((_QWORD *)Subscriber + 28) = 0;
        if ( v10 )
          EnterCriticalSection(&g_csEventTimerLock);
      }
    }
    LeaveCriticalSection(&g_csEventApiLock);
    if ( v10 )
    {
      if ( DeleteTimerQueueTimer(g_hTimerQ, v10, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
        }
      }
      else if ( (unsigned int)HrFromLastWin32Error()
             && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
             && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        Win32Error = HrFromLastWin32Error();
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
          (unsigned int)"HrRenewSubscriber: DeleteTimerQueueTimer",
          Win32Error);
      }
      LeaveCriticalSection(&g_csEventTimerLock);
    }
    EnterCriticalSection(&g_csEventApiLock);
    v15 = PesFindEventSource(a1);
    v16 = (STRSAFE_PCNZWCH *)v15;
    if ( !v15 )
    {
      v7 = -2147024894;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, a1);
      }
      goto LABEL_48;
    }
    v17 = PsubFindSubscriber(v15, a3);
    v18 = v17;
    if ( !v17 )
    {
      v7 = -2147024895;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          76,
          (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
          (_DWORD)a3,
          (__int64)a1);
      }
      goto LABEL_48;
    }
    v19 = (void **)((char *)v17 + 224);
    if ( *((_QWORD *)v17 + 28) )
    {
      LeaveCriticalSection(&g_csEventApiLock);
      return 0;
    }
    ++*((_DWORD *)v17 + 12);
    v21 = (unsigned __int16 **)((char *)v17 + 248);
    free(*((void **)v17 + 31));
    free(*((void **)v18 + 32));
    *((_DWORD *)v18 + 66) = *((_DWORD *)v18 + 12);
    *v21 = 0;
    *((_QWORD *)v18 + 32) = 0;
    v22 = WszDupWsz(*v16);
    *v21 = v22;
    if ( v22 && (v23 = WszDupWsz(*((STRSAFE_PCNZWCH *)v18 + 5)), (*((_QWORD *)v18 + 32) = v23) != 0) )
    {
      v24 = g_hTimerQ;
      *a2 = 300;
      *((_DWORD *)v18 + 5) = 300;
      if ( CreateTimerQueueTimer(v19, v24, RenewalCallback, v21, 1000 * *a2, 0, 0x20u) )
      {
        v7 = 0;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          v26 = GetTickCount();
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, *a2, v26);
        }
        goto LABEL_48;
      }
      v25 = HrFromLastWin32Error();
      v7 = v25;
      if ( v25 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          74,
          (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
          (unsigned int)"HrRenewSubscriber: CreateTimerQueueTimer",
          v25);
      if ( (v7 & 0x80000000) == 0 )
      {
LABEL_48:
        LeaveCriticalSection(&g_csEventApiLock);
        if ( !v7 )
          return v7;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          return v7;
        v8 = 78;
        goto LABEL_52;
      }
    }
    else
    {
      v7 = -2147024882;
    }
    free(*v21);
    free(*((void **)v18 + 32));
    goto LABEL_48;
  }
  v6 = WPP_GLOBAL_Control;
  v7 = -2147467259;
  if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
    return v7;
  v8 = 69;
LABEL_52:
  WPP_SF_sd(
    *((_QWORD *)v6 + 2),
    v8,
    (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
    (unsigned int)"HrRenewSubscriber",
    v7);
  return v7;
}

```

## disassembly

```asm
0x180033c24  push    rbx
0x180033c26  push    rbp
0x180033c27  push    rsi
0x180033c28  push    rdi
0x180033c29  push    r12
0x180033c2b  push    r14
0x180033c2d  push    r15
0x180033c2f  sub     rsp, 40h
0x180033c33  cmp     cs:?g_fEventApiInitialized@@3HA, 0; int g_fEventApiInitialized
0x180033c3a  mov     r15, r8
0x180033c3d  mov     r12, rdx
0x180033c40  mov     r14, rcx
0x180033c43  jnz     short loc_180033C7C
0x180033c45  mov     rcx, cs:WPP_GLOBAL_Control
0x180033c4c  lea     rdi, WPP_GLOBAL_Control
0x180033c53  mov     ebx, 80004005h
0x180033c58  cmp     rcx, rdi
0x180033c5b  jz      loc_18003407D
0x180033c61  test    byte ptr [rcx+1Ch], 1
0x180033c65  jz      loc_18003407D
0x180033c6b  mov     edx, 45h ; 'E'
0x180033c70  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180033c77  jmp     loc_180034069
0x180033c7c  mov     rax, cs:WPP_GLOBAL_Control
0x180033c83  lea     rdi, WPP_GLOBAL_Control
0x180033c8a  xor     ebx, ebx
0x180033c8c  lea     rbp, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180033c93  mov     esi, 800h
0x180033c98  cmp     rax, rdi
0x180033c9b  jz      short loc_180033CF1
0x180033c9d  test    [rax+1Ch], esi
0x180033ca0  jz      short loc_180033CC0
0x180033ca2  mov     rcx, [rax+10h]
0x180033ca6  lea     edx, [rbx+46h]
0x180033ca9  mov     r9, r15
0x180033cac  mov     qword ptr [rsp+78h+DueTime], r14
0x180033cb1  mov     r8, rbp
0x180033cb4  call    WPP_SF_SS
0x180033cb9  mov     rax, cs:WPP_GLOBAL_Control
0x180033cc0  cmp     rax, rdi
0x180033cc3  jz      short loc_180033CF1
0x180033cc5  test    [rax+1Ch], esi
0x180033cc8  jz      short loc_180033CF1
0x180033cca  call    cs:__imp_GetTickCount
0x180033cd1  nop     dword ptr [rax+rax+00h]
0x180033cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180033cdd  mov     edx, 47h ; 'G'
0x180033ce2  mov     r9d, eax
0x180033ce5  mov     r8, rbp
0x180033ce8  mov     rcx, [rcx+10h]
0x180033cec  call    WPP_SF_d
0x180033cf1  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180033cf8  call    cs:__imp_EnterCriticalSection
0x180033cff  nop     dword ptr [rax+rax+00h]
0x180033d04  mov     rcx, r14; unsigned __int16 *
0x180033d07  call    ?PesFindEventSource@@YAPEAUUPNP_EVENT_SOURCE@@PEBG@Z; PesFindEventSource(ushort const *)
0x180033d0c  test    rax, rax
0x180033d0f  jz      short loc_180033D4B
0x180033d11  mov     rdx, r15; unsigned __int16 *
0x180033d14  mov     rcx, rax; struct UPNP_EVENT_SOURCE *
0x180033d17  call    ?PsubFindSubscriber@@YAPEAUUPNP_SUBSCRIBER@@PEAUUPNP_EVENT_SOURCE@@PEBG@Z; PsubFindSubscriber(UPNP_EVENT_SOURCE *,ushort const *)
0x180033d1c  test    rax, rax
0x180033d1f  jz      short loc_180033D4B
0x180033d21  mov     rbx, [rax+0E0h]
0x180033d28  mov     qword ptr [rax+0E0h], 0
0x180033d33  test    rbx, rbx
0x180033d36  jz      short loc_180033D4B
0x180033d38  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180033d3f  call    cs:__imp_EnterCriticalSection
0x180033d46  nop     dword ptr [rax+rax+00h]
0x180033d4b  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180033d52  call    cs:__imp_LeaveCriticalSection
0x180033d59  nop     dword ptr [rax+rax+00h]
0x180033d5e  test    rbx, rbx
0x180033d61  jz      loc_180033DFF
0x180033d67  mov     rcx, cs:?g_hTimerQ@@3PEAXEA; TimerQueue
0x180033d6e  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180033d72  mov     rdx, rbx; Timer
0x180033d75  call    cs:__imp_DeleteTimerQueueTimer
0x180033d7c  nop     dword ptr [rax+rax+00h]
0x180033d81  test    eax, eax
0x180033d83  jnz     short loc_180033DCA
0x180033d85  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180033d8a  test    eax, eax
0x180033d8c  jz      short loc_180033DEC
0x180033d8e  mov     rax, cs:WPP_GLOBAL_Control
0x180033d95  cmp     rax, rdi
0x180033d98  jz      short loc_180033DEC
0x180033d9a  test    byte ptr [rax+1Ch], 1
0x180033d9e  jz      short loc_180033DEC
0x180033da0  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180033da5  mov     rcx, cs:WPP_GLOBAL_Control
0x180033dac  lea     r9, aHrrenewsubscri; "HrRenewSubscriber: DeleteTimerQueueTime"...
0x180033db3  mov     edx, 48h ; 'H'
0x180033db8  mov     [rsp+78h+DueTime], eax
0x180033dbc  mov     r8, rbp
0x180033dbf  mov     rcx, [rcx+10h]
0x180033dc3  call    WPP_SF_sd
0x180033dc8  jmp     short loc_180033DEC
0x180033dca  mov     rcx, cs:WPP_GLOBAL_Control
0x180033dd1  cmp     rcx, rdi
0x180033dd4  jz      short loc_180033DEC
0x180033dd6  test    [rcx+1Ch], esi
0x180033dd9  jz      short loc_180033DEC
0x180033ddb  mov     rcx, [rcx+10h]
0x180033ddf  mov     edx, 49h ; 'I'
0x180033de4  mov     r8, rbp
0x180033de7  call    WPP_SF_
0x180033dec  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180033df3  call    cs:__imp_LeaveCriticalSection
0x180033dfa  nop     dword ptr [rax+rax+00h]
0x180033dff  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180033e06  call    cs:__imp_EnterCriticalSection
0x180033e0d  nop     dword ptr [rax+rax+00h]
0x180033e12  mov     rcx, r14; unsigned __int16 *
0x180033e15  call    ?PesFindEventSource@@YAPEAUUPNP_EVENT_SOURCE@@PEBG@Z; PesFindEventSource(ushort const *)
0x180033e1a  mov     rbx, rax
0x180033e1d  test    rax, rax
0x180033e20  jz      loc_18003400E
0x180033e26  mov     rdx, r15; unsigned __int16 *
0x180033e29  mov     rcx, rax; struct UPNP_EVENT_SOURCE *
0x180033e2c  call    ?PsubFindSubscriber@@YAPEAUUPNP_SUBSCRIBER@@PEAUUPNP_EVENT_SOURCE@@PEBG@Z; PsubFindSubscriber(UPNP_EVENT_SOURCE *,ushort const *)
0x180033e31  mov     rsi, rax
0x180033e34  test    rax, rax
0x180033e37  jz      loc_180033FD9
0x180033e3d  lea     r14, [rax+0E0h]
0x180033e44  cmp     qword ptr [r14], 0
0x180033e48  jz      short loc_180033E64
0x180033e4a  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180033e51  call    cs:__imp_LeaveCriticalSection
0x180033e58  nop     dword ptr [rax+rax+00h]
0x180033e5d  xor     eax, eax
0x180033e5f  jmp     loc_18003407F
0x180033e64  inc     dword ptr [rax+30h]
0x180033e67  lea     r15, [rax+0F8h]
0x180033e6e  mov     rcx, [r15]; Block
0x180033e71  call    cs:__imp_free
0x180033e78  nop     dword ptr [rax+rax+00h]
0x180033e7d  mov     rcx, [rsi+100h]; Block
0x180033e84  call    cs:__imp_free
0x180033e8b  nop     dword ptr [rax+rax+00h]
0x180033e90  mov     eax, [rsi+30h]
0x180033e93  mov     [rsi+108h], eax
0x180033e99  mov     qword ptr [r15], 0
0x180033ea0  mov     qword ptr [rsi+100h], 0
0x180033eab  mov     rcx, [rbx]; pszSrc
0x180033eae  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x180033eb3  mov     [r15], rax
0x180033eb6  test    rax, rax
0x180033eb9  jnz     short loc_180033EC5
0x180033ebb  mov     ebx, 8007000Eh
0x180033ec0  jmp     loc_180033F67
0x180033ec5  mov     rcx, [rsi+28h]; pszSrc
0x180033ec9  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x180033ece  mov     [rsi+100h], rax
0x180033ed5  test    rax, rax
0x180033ed8  jz      short loc_180033EBB
0x180033eda  mov     rdx, cs:?g_hTimerQ@@3PEAXEA; TimerQueue
0x180033ee1  lea     r8, ?RenewalCallback@@YAXPEAXE@Z; Callback
0x180033ee8  mov     eax, 12Ch
0x180033eed  mov     [rsp+78h+Flags], 20h ; ' '; Flags
0x180033ef5  mov     [r12], eax
0x180033ef9  mov     r9, r15; Parameter
0x180033efc  mov     [rsi+14h], eax
0x180033eff  mov     rcx, r14; phNewTimer
0x180033f02  imul    eax, [r12], 3E8h
0x180033f0a  mov     [rsp+78h+Period], 0; Period
0x180033f12  mov     [rsp+78h+DueTime], eax; DueTime
0x180033f16  call    cs:__imp_CreateTimerQueueTimer
0x180033f1d  nop     dword ptr [rax+rax+00h]
0x180033f22  test    eax, eax
0x180033f24  jnz     short loc_180033F8E
0x180033f26  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180033f2b  mov     ebx, eax
0x180033f2d  test    eax, eax
0x180033f2f  jz      short loc_180033F5F
0x180033f31  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f38  cmp     rcx, rdi
0x180033f3b  jz      short loc_180033F5F
0x180033f3d  test    byte ptr [rcx+1Ch], 1
0x180033f41  jz      short loc_180033F5F
0x180033f43  mov     rcx, [rcx+10h]
0x180033f47  lea     r9, aHrrenewsubscri_0; "HrRenewSubscriber: CreateTimerQueueTime"...
0x180033f4e  mov     edx, 4Ah ; 'J'
0x180033f53  mov     [rsp+78h+DueTime], eax
0x180033f57  mov     r8, rbp
0x180033f5a  call    WPP_SF_sd
0x180033f5f  test    ebx, ebx
0x180033f61  jns     loc_180034038
0x180033f67  mov     rcx, [r15]; Block
0x180033f6a  call    cs:__imp_free
0x180033f71  nop     dword ptr [rax+rax+00h]
0x180033f76  mov     rcx, [rsi+100h]; Block
0x180033f7d  call    cs:__imp_free
0x180033f84  nop     dword ptr [rax+rax+00h]
0x180033f89  jmp     loc_180034038
0x180033f8e  mov     rax, cs:WPP_GLOBAL_Control
0x180033f95  xor     ebx, ebx
0x180033f97  cmp     rax, rdi
0x180033f9a  jz      loc_180034038
0x180033fa0  test    dword ptr [rax+1Ch], 800h
0x180033fa7  jz      loc_180034038
0x180033fad  call    cs:__imp_GetTickCount
0x180033fb4  nop     dword ptr [rax+rax+00h]
0x180033fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180033fc0  lea     edx, [rbx+4Bh]
0x180033fc3  mov     r9d, [r12]
0x180033fc7  mov     r8, rbp
0x180033fca  mov     [rsp+78h+DueTime], eax
0x180033fce  mov     rcx, [rcx+10h]
0x180033fd2  call    WPP_SF_dd
0x180033fd7  jmp     short loc_180034038
0x180033fd9  mov     ebx, 80070001h
0x180033fde  mov     rcx, cs:WPP_GLOBAL_Control
0x180033fe5  cmp     rcx, rdi
0x180033fe8  jz      short loc_180034038
0x180033fea  test    dword ptr [rcx+1Ch], 800h
0x180033ff1  jz      short loc_180034038
0x180033ff3  mov     rcx, [rcx+10h]
0x180033ff7  mov     edx, 4Ch ; 'L'
0x180033ffc  mov     r9, r15
0x180033fff  mov     qword ptr [rsp+78h+DueTime], r14
0x180034004  mov     r8, rbp
0x180034007  call    WPP_SF_SS
0x18003400c  jmp     short loc_180034038
0x18003400e  mov     ebx, 80070002h
0x180034013  mov     rcx, cs:WPP_GLOBAL_Control
0x18003401a  cmp     rcx, rdi
0x18003401d  jz      short loc_180034038
0x18003401f  test    [rcx+1Ch], esi
0x180034022  jz      short loc_180034038
0x180034024  mov     rcx, [rcx+10h]
0x180034028  mov     edx, 4Dh ; 'M'
0x18003402d  mov     r9, r14
0x180034030  mov     r8, rbp
0x180034033  call    WPP_SF_S
0x180034038  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003403f  call    cs:__imp_LeaveCriticalSection
0x180034046  nop     dword ptr [rax+rax+00h]
0x18003404b  test    ebx, ebx
0x18003404d  jz      short loc_18003407D
0x18003404f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034056  cmp     rcx, rdi
0x180034059  jz      short loc_18003407D
0x18003405b  test    byte ptr [rcx+1Ch], 1
0x18003405f  jz      short loc_18003407D
0x180034061  mov     edx, 4Eh ; 'N'
0x180034066  mov     r8, rbp
0x180034069  mov     rcx, [rcx+10h]
0x18003406d  lea     r9, aHrrenewsubscri_1; "HrRenewSubscriber"
0x180034074  mov     [rsp+78h+DueTime], ebx
0x180034078  call    WPP_SF_sd
0x18003407d  mov     eax, ebx
0x18003407f  add     rsp, 40h
0x180034083  pop     r15
0x180034085  pop     r14
0x180034087  pop     r12
0x180034089  pop     rdi
0x18003408a  pop     rsi
0x18003408b  pop     rbp
0x18003408c  pop     rbx
0x18003408d  retn
```
