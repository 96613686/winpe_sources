# HrRenewSubscriber(ushort const *,ulong *,ushort const *)

- ea: `0x180031e74`
- end: `0x180032284`
- name: `?HrRenewSubscriber@@YAJPEBGPEAK0@Z`
- size: `1040`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180031da0`

## callees

- `0x18000db4c`
- `0x18000e3ec`
- `0x18001347c`
- `0x180026a60`
- `0x180026b90`
- `0x18002fbac`
- `0x180031e74`
- `0x180038ce4`
- `0x180039388`
- `0x180039a84`
- `0x180046704`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032091`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003209e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032178`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032185`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032091`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003209e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032178`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032185`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031f42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031f83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032032`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031f42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031f83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032032`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031f90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032025`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003223b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031f90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032025`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003223b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180031f1a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800321af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180031f1a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800321af`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18003212a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18003212a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180031fad`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180031fad`

## string_xrefs

- `0x180031fde`: `HrRenewSubscriber: DeleteTimerQueueTimer`
- `0x180032155`: `HrRenewSubscriber: CreateTimerQueueTimer`

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
          GetTickCount();
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids);
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
0x180031e74  push    rbx
0x180031e76  push    rbp
0x180031e77  push    rsi
0x180031e78  push    rdi
0x180031e79  push    r12
0x180031e7b  push    r14
0x180031e7d  push    r15
0x180031e7f  sub     rsp, 40h
0x180031e83  cmp     cs:?g_fEventApiInitialized@@3HA, 0; int g_fEventApiInitialized
0x180031e8a  mov     r15, r8
0x180031e8d  mov     r12, rdx
0x180031e90  mov     r14, rcx
0x180031e93  jnz     short loc_180031ECC
0x180031e95  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e9c  lea     rdi, WPP_GLOBAL_Control
0x180031ea3  mov     ebx, 80004005h
0x180031ea8  cmp     rcx, rdi
0x180031eab  jz      loc_180032273
0x180031eb1  test    byte ptr [rcx+1Ch], 1
0x180031eb5  jz      loc_180032273
0x180031ebb  mov     edx, 45h ; 'E'
0x180031ec0  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180031ec7  jmp     loc_18003225F
0x180031ecc  mov     rax, cs:WPP_GLOBAL_Control
0x180031ed3  lea     rdi, WPP_GLOBAL_Control
0x180031eda  xor     ebx, ebx
0x180031edc  lea     rbp, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180031ee3  mov     esi, 800h
0x180031ee8  cmp     rax, rdi
0x180031eeb  jz      short loc_180031F3B
0x180031eed  test    [rax+1Ch], esi
0x180031ef0  jz      short loc_180031F10
0x180031ef2  mov     rcx, [rax+10h]
0x180031ef6  lea     edx, [rbx+46h]
0x180031ef9  mov     r9, r15
0x180031efc  mov     qword ptr [rsp+78h+DueTime], r14
0x180031f01  mov     r8, rbp
0x180031f04  call    WPP_SF_SS
0x180031f09  mov     rax, cs:WPP_GLOBAL_Control
0x180031f10  cmp     rax, rdi
0x180031f13  jz      short loc_180031F3B
0x180031f15  test    [rax+1Ch], esi
0x180031f18  jz      short loc_180031F3B
0x180031f1a  call    cs:__imp_GetTickCount
0x180031f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180031f27  mov     edx, 47h ; 'G'
0x180031f2c  mov     r9d, eax
0x180031f2f  mov     r8, rbp
0x180031f32  mov     rcx, [rcx+10h]
0x180031f36  call    WPP_SF_d
0x180031f3b  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031f42  call    cs:__imp_EnterCriticalSection
0x180031f48  mov     rcx, r14; unsigned __int16 *
0x180031f4b  call    ?PesFindEventSource@@YAPEAUUPNP_EVENT_SOURCE@@PEBG@Z; PesFindEventSource(ushort const *)
0x180031f50  test    rax, rax
0x180031f53  jz      short loc_180031F89
0x180031f55  mov     rdx, r15; unsigned __int16 *
0x180031f58  mov     rcx, rax; struct UPNP_EVENT_SOURCE *
0x180031f5b  call    ?PsubFindSubscriber@@YAPEAUUPNP_SUBSCRIBER@@PEAUUPNP_EVENT_SOURCE@@PEBG@Z; PsubFindSubscriber(UPNP_EVENT_SOURCE *,ushort const *)
0x180031f60  test    rax, rax
0x180031f63  jz      short loc_180031F89
0x180031f65  mov     rbx, [rax+0E0h]
0x180031f6c  mov     qword ptr [rax+0E0h], 0
0x180031f77  test    rbx, rbx
0x180031f7a  jz      short loc_180031F89
0x180031f7c  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031f83  call    cs:__imp_EnterCriticalSection
0x180031f89  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031f90  call    cs:__imp_LeaveCriticalSection
0x180031f96  test    rbx, rbx
0x180031f99  jz      loc_18003202B
0x180031f9f  mov     rcx, cs:?g_hTimerQ@@3PEAXEA; TimerQueue
0x180031fa6  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180031faa  mov     rdx, rbx; Timer
0x180031fad  call    cs:__imp_DeleteTimerQueueTimer
0x180031fb3  test    eax, eax
0x180031fb5  jnz     short loc_180031FFC
0x180031fb7  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180031fbc  test    eax, eax
0x180031fbe  jz      short loc_18003201E
0x180031fc0  mov     rax, cs:WPP_GLOBAL_Control
0x180031fc7  cmp     rax, rdi
0x180031fca  jz      short loc_18003201E
0x180031fcc  test    byte ptr [rax+1Ch], 1
0x180031fd0  jz      short loc_18003201E
0x180031fd2  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180031fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180031fde  lea     r9, aHrrenewsubscri; "HrRenewSubscriber: DeleteTimerQueueTime"...
0x180031fe5  mov     edx, 48h ; 'H'
0x180031fea  mov     [rsp+78h+DueTime], eax
0x180031fee  mov     r8, rbp
0x180031ff1  mov     rcx, [rcx+10h]
0x180031ff5  call    WPP_SF_sd
0x180031ffa  jmp     short loc_18003201E
0x180031ffc  mov     rcx, cs:WPP_GLOBAL_Control
0x180032003  cmp     rcx, rdi
0x180032006  jz      short loc_18003201E
0x180032008  test    [rcx+1Ch], esi
0x18003200b  jz      short loc_18003201E
0x18003200d  mov     rcx, [rcx+10h]
0x180032011  mov     edx, 49h ; 'I'
0x180032016  mov     r8, rbp
0x180032019  call    WPP_SF_
0x18003201e  lea     rcx, ?g_csEventTimerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180032025  call    cs:__imp_LeaveCriticalSection
0x18003202b  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180032032  call    cs:__imp_EnterCriticalSection
0x180032038  mov     rcx, r14; unsigned __int16 *
0x18003203b  call    ?PesFindEventSource@@YAPEAUUPNP_EVENT_SOURCE@@PEBG@Z; PesFindEventSource(ushort const *)
0x180032040  mov     rbx, rax
0x180032043  test    rax, rax
0x180032046  jz      loc_18003220A
0x18003204c  mov     rdx, r15; unsigned __int16 *
0x18003204f  mov     rcx, rax; struct UPNP_EVENT_SOURCE *
0x180032052  call    ?PsubFindSubscriber@@YAPEAUUPNP_SUBSCRIBER@@PEAUUPNP_EVENT_SOURCE@@PEBG@Z; PsubFindSubscriber(UPNP_EVENT_SOURCE *,ushort const *)
0x180032057  mov     rsi, rax
0x18003205a  test    rax, rax
0x18003205d  jz      loc_1800321D5
0x180032063  lea     r14, [rax+0E0h]
0x18003206a  cmp     qword ptr [r14], 0
0x18003206e  jz      short loc_180032084
0x180032070  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180032077  call    cs:__imp_LeaveCriticalSection
0x18003207d  xor     eax, eax
0x18003207f  jmp     loc_180032275
0x180032084  inc     dword ptr [rax+30h]
0x180032087  lea     r15, [rax+0F8h]
0x18003208e  mov     rcx, [r15]; Block
0x180032091  call    cs:__imp_free
0x180032097  mov     rcx, [rsi+100h]; Block
0x18003209e  call    cs:__imp_free
0x1800320a4  mov     eax, [rsi+30h]
0x1800320a7  mov     [rsi+108h], eax
0x1800320ad  mov     qword ptr [r15], 0
0x1800320b4  mov     qword ptr [rsi+100h], 0
0x1800320bf  mov     rcx, [rbx]; pszSrc
0x1800320c2  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x1800320c7  mov     [r15], rax
0x1800320ca  test    rax, rax
0x1800320cd  jnz     short loc_1800320D9
0x1800320cf  mov     ebx, 8007000Eh
0x1800320d4  jmp     loc_180032175
0x1800320d9  mov     rcx, [rsi+28h]; pszSrc
0x1800320dd  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x1800320e2  mov     [rsi+100h], rax
0x1800320e9  test    rax, rax
0x1800320ec  jz      short loc_1800320CF
0x1800320ee  mov     rdx, cs:?g_hTimerQ@@3PEAXEA; TimerQueue
0x1800320f5  lea     r8, ?RenewalCallback@@YAXPEAXE@Z; Callback
0x1800320fc  mov     eax, 12Ch
0x180032101  mov     [rsp+78h+Flags], 20h ; ' '; Flags
0x180032109  mov     [r12], eax
0x18003210d  mov     r9, r15; Parameter
0x180032110  mov     [rsi+14h], eax
0x180032113  mov     rcx, r14; phNewTimer
0x180032116  imul    eax, [r12], 3E8h
0x18003211e  mov     [rsp+78h+Period], 0; Period
0x180032126  mov     [rsp+78h+DueTime], eax; DueTime
0x18003212a  call    cs:__imp_CreateTimerQueueTimer
0x180032130  test    eax, eax
0x180032132  jnz     short loc_180032190
0x180032134  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180032139  mov     ebx, eax
0x18003213b  test    eax, eax
0x18003213d  jz      short loc_18003216D
0x18003213f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032146  cmp     rcx, rdi
0x180032149  jz      short loc_18003216D
0x18003214b  test    byte ptr [rcx+1Ch], 1
0x18003214f  jz      short loc_18003216D
0x180032151  mov     rcx, [rcx+10h]
0x180032155  lea     r9, aHrrenewsubscri_0; "HrRenewSubscriber: CreateTimerQueueTime"...
0x18003215c  mov     edx, 4Ah ; 'J'
0x180032161  mov     [rsp+78h+DueTime], eax
0x180032165  mov     r8, rbp
0x180032168  call    WPP_SF_sd
0x18003216d  test    ebx, ebx
0x18003216f  jns     loc_180032234
0x180032175  mov     rcx, [r15]; Block
0x180032178  call    cs:__imp_free
0x18003217e  mov     rcx, [rsi+100h]; Block
0x180032185  call    cs:__imp_free
0x18003218b  jmp     loc_180032234
0x180032190  mov     rax, cs:WPP_GLOBAL_Control
0x180032197  xor     ebx, ebx
0x180032199  cmp     rax, rdi
0x18003219c  jz      loc_180032234
0x1800321a2  test    dword ptr [rax+1Ch], 800h
0x1800321a9  jz      loc_180032234
0x1800321af  call    cs:__imp_GetTickCount
0x1800321b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800321bc  lea     edx, [rbx+4Bh]
0x1800321bf  mov     r9d, [r12]
0x1800321c3  mov     r8, rbp
0x1800321c6  mov     [rsp+78h+DueTime], eax
0x1800321ca  mov     rcx, [rcx+10h]
0x1800321ce  call    WPP_SF_dd
0x1800321d3  jmp     short loc_180032234
0x1800321d5  mov     ebx, 80070001h
0x1800321da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800321e1  cmp     rcx, rdi
0x1800321e4  jz      short loc_180032234
0x1800321e6  test    dword ptr [rcx+1Ch], 800h
0x1800321ed  jz      short loc_180032234
0x1800321ef  mov     rcx, [rcx+10h]
0x1800321f3  mov     edx, 4Ch ; 'L'
0x1800321f8  mov     r9, r15
0x1800321fb  mov     qword ptr [rsp+78h+DueTime], r14
0x180032200  mov     r8, rbp
0x180032203  call    WPP_SF_SS
0x180032208  jmp     short loc_180032234
0x18003220a  mov     ebx, 80070002h
0x18003220f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032216  cmp     rcx, rdi
0x180032219  jz      short loc_180032234
0x18003221b  test    [rcx+1Ch], esi
0x18003221e  jz      short loc_180032234
0x180032220  mov     rcx, [rcx+10h]
0x180032224  mov     edx, 4Dh ; 'M'
0x180032229  mov     r9, r14
0x18003222c  mov     r8, rbp
0x18003222f  call    WPP_SF_S
0x180032234  lea     rcx, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003223b  call    cs:__imp_LeaveCriticalSection
0x180032241  test    ebx, ebx
0x180032243  jz      short loc_180032273
0x180032245  mov     rcx, cs:WPP_GLOBAL_Control
0x18003224c  cmp     rcx, rdi
0x18003224f  jz      short loc_180032273
0x180032251  test    byte ptr [rcx+1Ch], 1
0x180032255  jz      short loc_180032273
0x180032257  mov     edx, 4Eh ; 'N'
0x18003225c  mov     r8, rbp
0x18003225f  mov     rcx, [rcx+10h]
0x180032263  lea     r9, aHrrenewsubscri_1; "HrRenewSubscriber"
0x18003226a  mov     [rsp+78h+DueTime], ebx
0x18003226e  call    WPP_SF_sd
0x180032273  mov     eax, ebx
0x180032275  add     rsp, 40h
0x180032279  pop     r15
0x18003227b  pop     r14
0x18003227d  pop     r12
0x18003227f  pop     rdi
0x180032280  pop     rsi
0x180032281  pop     rbp
0x180032282  pop     rbx
0x180032283  retn
```
