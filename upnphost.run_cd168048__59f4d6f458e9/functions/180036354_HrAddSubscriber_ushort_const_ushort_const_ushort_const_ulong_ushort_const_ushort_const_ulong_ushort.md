# HrAddSubscriber(ushort const *,ushort const *,ushort const *,ulong,ushort const * *,ushort const *,ulong *,ushort * *)

- ea: `0x180036354`
- end: `0x1800369c1`
- name: `?HrAddSubscriber@@YAJPEBG00KPEAPEBG0PEAKPEAPEAG@Z`
- size: `1645`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *Src, struct addrinfoW *, unsigned int, const unsigned __int16 **, STRSAFE_PCNZWCH pszSrc, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180035fd0`

## callees

- `0x1800074dc`
- `0x18000c8e0`
- `0x1800200f4`
- `0x1800209c8`
- `0x180027500`
- `0x180027b60`
- `0x180027ca4`
- `0x1800318ec`
- `0x180036354`
- `0x18003b904`
- `0x18003b96c`
- `0x18003ba9c`
- `0x18003d4b0`
- `0x1800480c0`
- `0x180049258`
- `0x1800492d8`
- `0x180057cac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036964`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036964`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180036400`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003664c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180036400`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003664c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036539`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036539`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036763`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036763`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800367ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036900`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800367ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036900`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003674d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003674d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800366ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800366ee`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180036860`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180036860`
- `WS2_32!GetAddrInfoW` at `0x1800364bf`
- `WS2_32!GetAddrInfoW` at `0x1800364bf`
- `WS2_32!FreeAddrInfoW` at `0x180036518`
- `WS2_32!FreeAddrInfoW` at `0x180036518`

## string_xrefs

- `0x180036583`: `HrAddSubscriber: CreateEvent`
- `0x180036734`: `HrAddSubscriber: CreateThreadpoolWait`
- `0x18003689d`: `HrAddSubscriber: CreateTimerQueueTimer`

## pseudocode

```c
__int64 __fastcall HrAddSubscriber(
        const unsigned __int16 *a1,
        const unsigned __int16 *Src,
        struct addrinfoW *a3,
        unsigned int a4,
        const unsigned __int16 **a5,
        STRSAFE_PCNZWCH pszSrc,
        unsigned int *a7,
        unsigned __int16 **a8)
{
  unsigned int v8; // r15d
  __int64 v9; // r13
  STRSAFE_PCNZWCH v12; // rcx
  unsigned int v13; // ebx
  int v14; // edx
  char *v15; // rax
  char *v16; // rdi
  WCHAR *v17; // rbx
  __int64 v18; // rax
  WCHAR *v19; // rcx
  WCHAR *i; // rdx
  INT AddrInfoW; // eax
  struct addrinfoW *v22; // r15
  HANDLE EventW; // rax
  unsigned int Win32Error; // eax
  STRSAFE_PCNZWCH v25; // rcx
  int v26; // edx
  const char *v27; // r9
  unsigned __int16 *NewSid; // rax
  void *v29; // rax
  unsigned __int16 *v30; // rax
  unsigned __int16 *v31; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax
  struct UPNP_EVENT_SOURCE *EventSource; // rax
  struct UPNP_EVENT_SOURCE *v34; // rbx
  STRSAFE_PCNZWCH v35; // rcx
  __int64 v36; // rdx
  unsigned __int16 *v37; // rax
  unsigned __int16 *v38; // rax
  unsigned int *v39; // rax
  unsigned int v40; // eax
  __int64 v41; // rax
  unsigned __int16 *Block; // [rsp+40h] [rbp-41h]
  ADDRINFOW pHints; // [rsp+48h] [rbp-39h] BYREF
  PADDRINFOW ppResult; // [rsp+E0h] [rbp+5Fh] BYREF

  ppResult = a3;
  v8 = 0;
  v9 = a4;
  if ( !g_fEventApiInitialized )
  {
    v12 = WPP_GLOBAL_Control;
    v13 = -2147467259;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v14 = 56;
LABEL_87:
      WPP_SF_sd(
        *((_QWORD *)v12 + 2),
        v14,
        (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
        (unsigned int)"HrAddSubscriber",
        v13);
      return v13;
    }
    return v13;
  }
  Block = 0;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_SdS(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, (_DWORD)a3, (unsigned int)*a5, a4, (__int64)a1);
  v15 = (char *)malloc(0x118u);
  v16 = v15;
  if ( !v15 )
    goto LABEL_9;
  memset_0(v15, 0, 0x118u);
  v17 = WszAllocateAndCopyWsz(Src);
  if ( v17 )
  {
    ppResult = 0;
    memset(&pHints, 0, sizeof(pHints));
    v18 = -1;
    do
      ++v18;
    while ( v17[v18] );
    v19 = 0;
    for ( i = &v17[(unsigned int)v18]; i != v17; --i )
    {
      if ( *i == 93 )
      {
        if ( v19 )
          *v19 = 0;
        break;
      }
      if ( *i == 58 )
        v19 = i;
    }
    memset(&pHints.ai_socktype, 0, 40);
    *(_QWORD *)&pHints.ai_flags = 4;
    AddrInfoW = GetAddrInfoW(v17, 0, &pHints, &ppResult);
    if ( AddrInfoW )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
          (_DWORD)v17,
          AddrInfoW);
      }
      operator delete(v17);
      v13 = -2147467259;
      goto LABEL_82;
    }
    v22 = ppResult;
    memcpy_0(v16 + 56, ppResult->ai_addr, ppResult->ai_addrlen);
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, v17);
      v22 = ppResult;
    }
    FreeAddrInfoW(v22);
    operator delete(v17);
    v8 = 0;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v16 + 23) = EventW;
  if ( !EventW )
  {
    Win32Error = HrFromLastWin32Error();
    v13 = Win32Error;
    if ( !Win32Error )
      goto LABEL_82;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_82;
    v26 = 60;
    v27 = "HrAddSubscriber: CreateEvent";
    goto LABEL_32;
  }
  NewSid = SzGetNewSid();
  *((_QWORD *)v16 + 5) = NewSid;
  if ( !NewSid )
    goto LABEL_9;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, NewSid);
  Block = WszDupWsz(*((STRSAFE_PCNZWCH *)v16 + 5));
  if ( !Block )
    goto LABEL_9;
  *((_DWORD *)v16 + 4) = 0;
  if ( (unsigned __int64)(8 * v9) > 0xFFFFFFFF )
  {
    v13 = -2147024362;
    goto LABEL_82;
  }
  v29 = malloc((unsigned int)(8 * v9));
  *((_QWORD *)v16 + 1) = v29;
  if ( !v29 )
    goto LABEL_9;
  memset_0(v29, 0, (unsigned int)(8 * v9));
  if ( (_DWORD)v9 )
  {
    do
    {
      *(_QWORD *)(*((_QWORD *)v16 + 1) + 8LL * v8) = WszDupWsz(a5[v8]);
      if ( !*(_QWORD *)(*((_QWORD *)v16 + 1) + 8LL * v8) )
        goto LABEL_9;
      ++*((_DWORD *)v16 + 4);
    }
    while ( ++v8 < (unsigned int)v9 );
  }
  v30 = WszDupWsz(a1);
  *((_QWORD *)v16 + 29) = v30;
  if ( !v30 || (v31 = WszDupWsz(*((STRSAFE_PCNZWCH *)v16 + 5)), (*((_QWORD *)v16 + 30) = v31) == 0) )
  {
LABEL_9:
    v13 = -2147024882;
LABEL_82:
    free(Block);
    FreeSubscriber((struct UPNP_SUBSCRIBER *)v16);
    goto LABEL_83;
  }
  ThreadpoolWait = CreateThreadpoolWait(EventQueueWorker, v16 + 232, &pcbe);
  *((_QWORD *)v16 + 27) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    Win32Error = HrFromLastWin32Error();
    v13 = Win32Error;
    if ( !Win32Error )
      goto LABEL_82;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_82;
    v26 = 62;
    v27 = "HrAddSubscriber: CreateThreadpoolWait";
LABEL_32:
    WPP_SF_sd(
      *((_QWORD *)v25 + 2),
      v26,
      (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
      (_DWORD)v27,
      Win32Error);
    goto LABEL_82;
  }
  SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)v16 + 23), 0);
  EnterCriticalSection(&g_csEventApiLock);
  EventSource = PesFindEventSource(a1);
  v34 = EventSource;
  if ( !EventSource )
  {
    v13 = -2147024894;
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
    {
      goto LABEL_59;
    }
    v36 = 63;
    goto LABEL_58;
  }
  if ( *((_DWORD *)EventSource + 2) >= 0x7D0u )
  {
    v13 = -2147023604;
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_59;
    v36 = 64;
LABEL_58:
    WPP_SF_S(*((_QWORD *)v35 + 2), v36, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, a1);
LABEL_59:
    LeaveCriticalSection(&g_csEventApiLock);
    goto LABEL_82;
  }
  *((_DWORD *)v16 + 66) = *((_DWORD *)v16 + 12);
  v37 = WszDupWsz(*(STRSAFE_PCNZWCH *)EventSource);
  *((_QWORD *)v16 + 31) = v37;
  if ( !v37 || (v38 = WszDupWsz(*((STRSAFE_PCNZWCH *)v16 + 5)), (*((_QWORD *)v16 + 32) = v38) == 0) )
  {
    v13 = -2147024882;
    goto LABEL_59;
  }
  v39 = a7;
  *a7 = 300;
  *((_DWORD *)v16 + 5) = 300;
  if ( !CreateTimerQueueTimer((PHANDLE)v16 + 28, g_hTimerQ, RenewalCallback, v16 + 248, 1000 * *v39, 0, 0x20u) )
  {
    v40 = HrFromLastWin32Error();
    v13 = v40;
    if ( v40 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
        (unsigned int)"HrAddSubscriber: CreateTimerQueueTimer",
        v40);
    goto LABEL_59;
  }
  *(_QWORD *)v16 = v34;
  v41 = *((_QWORD *)v34 + 2);
  if ( v41 )
    *((_QWORD *)v16 + 34) = v41;
  *((_QWORD *)v34 + 2) = v16;
  ++*((_DWORD *)v34 + 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids, v16);
  LeaveCriticalSection(&g_csEventApiLock);
  *a8 = Block;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      67,
      (unsigned int)WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids,
      (_DWORD)a1,
      (__int64)Block);
  v13 = HrSubmitEventZero(a1, Block, pszSrc);
LABEL_83:
  if ( v13 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v14 = 68;
      goto LABEL_87;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180036354  mov     [rsp-8+ppResult], r8
0x180036359  push    rbp
0x18003635a  push    rbx
0x18003635b  push    rsi
0x18003635c  push    rdi
0x18003635d  push    r12
0x18003635f  push    r13
0x180036361  push    r14
0x180036363  push    r15
0x180036365  lea     rbp, [rsp-7]
0x18003636a  sub     rsp, 88h
0x180036371  xor     r15d, r15d
0x180036374  mov     r13d, r9d
0x180036377  cmp     cs:?g_fEventApiInitialized@@3HA, r15d; int g_fEventApiInitialized
0x18003637e  mov     rbx, rdx
0x180036381  mov     r12, rcx
0x180036384  jnz     short loc_1800363BC
0x180036386  mov     rcx, cs:WPP_GLOBAL_Control
0x18003638d  lea     rsi, WPP_GLOBAL_Control
0x180036394  mov     ebx, 80004005h
0x180036399  cmp     rcx, rsi
0x18003639c  jz      loc_1800369AA
0x1800363a2  test    byte ptr [rcx+1Ch], 1
0x1800363a6  jz      loc_1800369AA
0x1800363ac  lea     edx, [r15+38h]
0x1800363b0  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x1800363b7  jmp     loc_180036996
0x1800363bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800363c3  lea     rsi, WPP_GLOBAL_Control
0x1800363ca  mov     [rbp+3Fh+Block], r15
0x1800363ce  cmp     rcx, rsi
0x1800363d1  jz      short loc_1800363FB
0x1800363d3  test    dword ptr [rcx+1Ch], 800h
0x1800363da  jz      short loc_1800363FB
0x1800363dc  mov     r9, [rbp+3Fh+arg_20]
0x1800363e0  mov     edx, 39h ; '9'
0x1800363e5  mov     rcx, [rcx+10h]
0x1800363e9  mov     qword ptr [rsp+0C0h+Period], r12
0x1800363ee  mov     [rsp+0C0h+DueTime], r13d
0x1800363f3  mov     r9, [r9]
0x1800363f6  call    WPP_SF_SdS
0x1800363fb  mov     ecx, 118h; Size
0x180036400  call    cs:__imp_malloc
0x180036407  nop     dword ptr [rax+rax+00h]
0x18003640c  lea     r14, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x180036413  mov     rdi, rax
0x180036416  test    rax, rax
0x180036419  jnz     short loc_180036425
0x18003641b  mov     ebx, 8007000Eh
0x180036420  jmp     loc_180036960
0x180036425  xor     edx, edx; Val
0x180036427  mov     r8d, 118h; Size
0x18003642d  mov     rcx, rdi; void *
0x180036430  call    memset_0
0x180036435  mov     rcx, rbx; Src
0x180036438  call    ?WszAllocateAndCopyWsz@@YAPEAGPEBG@Z; WszAllocateAndCopyWsz(ushort const *)
0x18003643d  mov     rbx, rax
0x180036440  test    rax, rax
0x180036443  jz      loc_18003652F
0x180036449  xorps   xmm0, xmm0
0x18003644c  mov     [rbp+3Fh+ppResult], r15
0x180036450  movups  xmmword ptr [rbp+3Fh+pHints.ai_flags], xmm0
0x180036454  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036458  movups  xmmword ptr [rbp+3Fh+pHints.ai_addrlen], xmm0
0x18003645c  movups  xmmword ptr [rbp+3Fh+pHints.ai_addr], xmm0
0x180036460  inc     rax
0x180036463  cmp     [rbx+rax*2], r15w
0x180036468  jnz     short loc_180036460
0x18003646a  mov     eax, eax
0x18003646c  mov     rcx, r15
0x18003646f  lea     rdx, [rbx+rax*2]
0x180036473  mov     eax, 3Ah ; ':'
0x180036478  jmp     short loc_18003648B
0x18003647a  cmp     word ptr [rdx], 5Dh ; ']'
0x18003647e  jz      short loc_180036492
0x180036480  cmp     [rdx], ax
0x180036483  cmovz   rcx, rdx
0x180036487  sub     rdx, 2
0x18003648b  cmp     rdx, rbx
0x18003648e  jnz     short loc_18003647A
0x180036490  jmp     short loc_18003649B
0x180036492  test    rcx, rcx
0x180036495  jz      short loc_18003649B
0x180036497  mov     [rcx], r15w
0x18003649b  xorps   xmm0, xmm0
0x18003649e  lea     r9, [rbp+3Fh+ppResult]; ppResult
0x1800364a2  movups  xmmword ptr [rbp+3Fh+pHints.ai_flags], xmm0
0x1800364a6  lea     r8, [rbp+3Fh+pHints]; pHints
0x1800364aa  mov     qword ptr [rbp+3Fh+pHints.ai_flags], 4
0x1800364b2  xor     edx, edx; pServiceName
0x1800364b4  mov     rcx, rbx; pNodeName
0x1800364b7  movups  xmmword ptr [rbp+3Fh+pHints.ai_addrlen], xmm0
0x1800364bb  movups  xmmword ptr [rbp+3Fh+pHints.ai_addr], xmm0
0x1800364bf  call    cs:__imp_GetAddrInfoW
0x1800364c6  nop     dword ptr [rax+rax+00h]
0x1800364cb  test    eax, eax
0x1800364cd  jnz     loc_18003659F
0x1800364d3  mov     r15, [rbp+3Fh+ppResult]
0x1800364d7  lea     rcx, [rdi+38h]; void *
0x1800364db  mov     r8, [r15+10h]; Size
0x1800364df  mov     rdx, [r15+20h]; Src
0x1800364e3  call    memcpy_0
0x1800364e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364ef  cmp     rcx, rsi
0x1800364f2  jz      short loc_180036515
0x1800364f4  test    dword ptr [rcx+1Ch], 800h
0x1800364fb  jz      short loc_180036515
0x1800364fd  mov     rcx, [rcx+10h]
0x180036501  mov     edx, 3Ah ; ':'
0x180036506  mov     r9, rbx
0x180036509  mov     r8, r14
0x18003650c  call    WPP_SF_S
0x180036511  mov     r15, [rbp+3Fh+ppResult]
0x180036515  mov     rcx, r15; pAddrInfo
0x180036518  call    cs:__imp_FreeAddrInfoW
0x18003651f  nop     dword ptr [rax+rax+00h]
0x180036524  mov     rcx, rbx; void *
0x180036527  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003652c  xor     r15d, r15d
0x18003652f  xor     r9d, r9d; lpName
0x180036532  xor     r8d, r8d; bInitialState
0x180036535  xor     edx, edx; bManualReset
0x180036537  xor     ecx, ecx; lpEventAttributes
0x180036539  call    cs:__imp_CreateEventW
0x180036540  nop     dword ptr [rax+rax+00h]
0x180036545  mov     [rdi+0B8h], rax
0x18003654c  test    rax, rax
0x18003654f  jnz     loc_1800365DE
0x180036555  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18003655a  mov     ebx, eax
0x18003655c  test    eax, eax
0x18003655e  jz      loc_180036960
0x180036564  mov     rcx, cs:WPP_GLOBAL_Control
0x18003656b  cmp     rcx, rsi
0x18003656e  jz      loc_180036960
0x180036574  test    byte ptr [rcx+1Ch], 1
0x180036578  jz      loc_180036960
0x18003657e  mov     edx, 3Ch ; '<'
0x180036583  lea     r9, aHraddsubscribe; "HrAddSubscriber: CreateEvent"
0x18003658a  mov     rcx, [rcx+10h]
0x18003658e  mov     r8, r14
0x180036591  mov     [rsp+0C0h+DueTime], eax
0x180036595  call    WPP_SF_sd
0x18003659a  jmp     loc_180036960
0x18003659f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365a6  cmp     rcx, rsi
0x1800365a9  jz      short loc_1800365CC
0x1800365ab  test    dword ptr [rcx+1Ch], 800h
0x1800365b2  jz      short loc_1800365CC
0x1800365b4  mov     rcx, [rcx+10h]
0x1800365b8  mov     edx, 3Bh ; ';'
0x1800365bd  mov     r9, rbx
0x1800365c0  mov     [rsp+0C0h+DueTime], eax
0x1800365c4  mov     r8, r14
0x1800365c7  call    WPP_SF_Sd
0x1800365cc  mov     rcx, rbx; void *
0x1800365cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800365d4  mov     ebx, 80004005h
0x1800365d9  jmp     loc_180036960
0x1800365de  call    ?SzGetNewSid@@YAPEAGXZ; SzGetNewSid(void)
0x1800365e3  mov     [rdi+28h], rax
0x1800365e7  test    rax, rax
0x1800365ea  jz      loc_18003641B
0x1800365f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365f7  cmp     rcx, rsi
0x1800365fa  jz      short loc_180036619
0x1800365fc  test    dword ptr [rcx+1Ch], 800h
0x180036603  jz      short loc_180036619
0x180036605  mov     rcx, [rcx+10h]
0x180036609  mov     edx, 3Dh ; '='
0x18003660e  mov     r9, rax
0x180036611  mov     r8, r14
0x180036614  call    WPP_SF_S
0x180036619  mov     rcx, [rdi+28h]; pszSrc
0x18003661d  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x180036622  mov     [rbp+3Fh+Block], rax
0x180036626  test    rax, rax
0x180036629  jz      loc_18003641B
0x18003662f  mov     rax, r13
0x180036632  mov     [rdi+10h], r15d
0x180036636  shl     rax, 3
0x18003663a  mov     ecx, 0FFFFFFFFh
0x18003663f  cmp     rax, rcx
0x180036642  ja      loc_18003695B
0x180036648  mov     ecx, eax; Size
0x18003664a  mov     ebx, eax
0x18003664c  call    cs:__imp_malloc
0x180036653  nop     dword ptr [rax+rax+00h]
0x180036658  mov     [rdi+8], rax
0x18003665c  test    rax, rax
0x18003665f  jz      loc_18003641B
0x180036665  mov     r8d, ebx; Size
0x180036668  xor     edx, edx; Val
0x18003666a  mov     rcx, rax; void *
0x18003666d  call    memset_0
0x180036672  test    r13d, r13d
0x180036675  jz      short loc_1800366A9
0x180036677  mov     rax, [rbp+3Fh+arg_20]
0x18003667b  mov     ebx, r15d
0x18003667e  mov     rcx, [rax+rbx*8]; pszSrc
0x180036682  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x180036687  mov     rcx, [rdi+8]
0x18003668b  mov     [rcx+rbx*8], rax
0x18003668f  mov     rax, [rdi+8]
0x180036693  cmp     qword ptr [rax+rbx*8], 0
0x180036698  jz      loc_18003641B
0x18003669e  inc     dword ptr [rdi+10h]
0x1800366a1  inc     r15d
0x1800366a4  cmp     r15d, r13d
0x1800366a7  jb      short loc_180036677
0x1800366a9  mov     rcx, r12; pszSrc
0x1800366ac  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x1800366b1  lea     rbx, [rdi+0E8h]
0x1800366b8  mov     [rbx], rax
0x1800366bb  test    rax, rax
0x1800366be  jz      loc_18003641B
0x1800366c4  mov     rcx, [rdi+28h]; pszSrc
0x1800366c8  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x1800366cd  mov     [rdi+0F0h], rax
0x1800366d4  test    rax, rax
0x1800366d7  jz      loc_18003641B
0x1800366dd  lea     r8, pcbe; pcbe
0x1800366e4  mov     rdx, rbx; pv
0x1800366e7  lea     rcx, ?EventQueueWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800366ee  call    cs:__imp_CreateThreadpoolWait
0x1800366f5  nop     dword ptr [rax+rax+00h]
0x1800366fa  mov     [rdi+0D8h], rax
0x180036701  test    rax, rax
0x180036704  jnz     short loc_180036740
0x180036706  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18003670b  mov     ebx, eax
0x18003670d  test    eax, eax
0x18003670f  jz      loc_180036960
0x180036715  mov     rcx, cs:WPP_GLOBAL_Control
0x18003671c  cmp     rcx, rsi
0x18003671f  jz      loc_180036960
0x180036725  test    byte ptr [rcx+1Ch], 1
0x180036729  jz      loc_180036960
0x18003672f  mov     edx, 3Eh ; '>'
0x180036734  lea     r9, aHraddsubscribe_0; "HrAddSubscriber: CreateThreadpoolWait"
0x18003673b  jmp     loc_18003658A
0x180036740  mov     rdx, [rdi+0B8h]; h
0x180036747  xor     r8d, r8d; pftTimeout
0x18003674a  mov     rcx, rax; pwa
0x18003674d  call    cs:__imp_SetThreadpoolWait
0x180036754  nop     dword ptr [rax+rax+00h]
0x180036759  lea     r13, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csEventApiLock
0x180036760  mov     rcx, r13; lpCriticalSection
0x180036763  call    cs:__imp_EnterCriticalSection
0x18003676a  nop     dword ptr [rax+rax+00h]
0x18003676f  mov     rcx, r12; unsigned __int16 *
0x180036772  call    ?PesFindEventSource@@YAPEAUUPNP_EVENT_SOURCE@@PEBG@Z; PesFindEventSource(ushort const *)
0x180036777  mov     rbx, rax
0x18003677a  test    rax, rax
0x18003677d  jnz     short loc_1800367BF
0x18003677f  mov     ebx, 80070002h
0x180036784  mov     rcx, cs:WPP_GLOBAL_Control
0x18003678b  cmp     rcx, rsi
0x18003678e  jz      short loc_1800367AB
0x180036790  test    dword ptr [rcx+1Ch], 800h
0x180036797  jz      short loc_1800367AB
0x180036799  lea     edx, [rax+3Fh]
0x18003679c  mov     rcx, [rcx+10h]
0x1800367a0  mov     r9, r12
0x1800367a3  mov     r8, r14
0x1800367a6  call    WPP_SF_S
0x1800367ab  mov     rcx, r13; lpCriticalSection
0x1800367ae  call    cs:__imp_LeaveCriticalSection
0x1800367b5  nop     dword ptr [rax+rax+00h]
0x1800367ba  jmp     loc_180036960
0x1800367bf  cmp     dword ptr [rax+8], 7D0h
0x1800367c6  jb      short loc_1800367E6
0x1800367c8  mov     ebx, 8007050Ch
0x1800367cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367d4  cmp     rcx, rsi
0x1800367d7  jz      short loc_1800367AB
0x1800367d9  test    byte ptr [rcx+1Ch], 1
0x1800367dd  jz      short loc_1800367AB
0x1800367df  mov     edx, 40h ; '@'
0x1800367e4  jmp     short loc_18003679C
0x1800367e6  mov     eax, [rdi+30h]
0x1800367e9  lea     r15, [rdi+0F8h]
0x1800367f0  mov     [r15+10h], eax
0x1800367f4  mov     rcx, [rbx]; pszSrc
0x1800367f7  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x1800367fc  mov     [r15], rax
0x1800367ff  test    rax, rax
0x180036802  jnz     short loc_18003680B
0x180036804  mov     ebx, 8007000Eh
0x180036809  jmp     short loc_1800367AB
0x18003680b  mov     rcx, [rdi+28h]; pszSrc
0x18003680f  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x180036814  mov     [rdi+100h], rax
0x18003681b  test    rax, rax
0x18003681e  jz      short loc_180036804
0x180036820  mov     rax, [rbp+3Fh+arg_30]
0x180036824  lea     r8, ?RenewalCallback@@YAXPEAXE@Z; Callback
0x18003682b  mov     ecx, 12Ch
0x180036830  mov     [rsp+0C0h+Flags], 20h ; ' '; Flags
0x180036838  mov     [rsp+0C0h+Period], 0; Period
  ... truncated ...
```
