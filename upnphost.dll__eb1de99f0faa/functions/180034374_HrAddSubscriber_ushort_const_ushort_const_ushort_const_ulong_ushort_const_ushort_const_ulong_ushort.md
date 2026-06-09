# HrAddSubscriber(ushort const *,ushort const *,ushort const *,ulong,ushort const * *,ushort const *,ulong *,ushort * *)

- ea: `0x180034374`
- end: `0x180034998`
- name: `?HrAddSubscriber@@YAJPEBG00KPEAPEBG0PEAKPEAPEAG@Z`
- size: `1572`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *Src, struct addrinfoW *, unsigned int, const unsigned __int16 **, STRSAFE_PCNZWCH pszSrc, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180034030`

## callees

- `0x18000db4c`
- `0x18000e3ec`
- `0x18001347c`
- `0x180018738`
- `0x18002643c`
- `0x180026a60`
- `0x180026b90`
- `0x18002fdc8`
- `0x180034374`
- `0x180039388`
- `0x180039410`
- `0x1800394f8`
- `0x18003ae80`
- `0x1800454d0`
- `0x180046540`
- `0x1800465b8`
- `0x18005430c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034942`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034942`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034420`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034654`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034420`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034654`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180034547`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180034547`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034759`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034759`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003479e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800348e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003479e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800348e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180034749`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180034749`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800346f0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800346f0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18003484a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18003484a`
- `WS2_32!GetAddrInfoW` at `0x1800344d9`
- `WS2_32!GetAddrInfoW` at `0x1800344d9`
- `WS2_32!FreeAddrInfoW` at `0x18003452c`
- `WS2_32!FreeAddrInfoW` at `0x18003452c`

## string_xrefs

- `0x18003458b`: `HrAddSubscriber: CreateEvent`
- `0x180034730`: `HrAddSubscriber: CreateThreadpoolWait`
- `0x180034881`: `HrAddSubscriber: CreateTimerQueueTimer`

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
0x180034374  mov     [rsp-8+ppResult], r8
0x180034379  push    rbp
0x18003437a  push    rbx
0x18003437b  push    rsi
0x18003437c  push    rdi
0x18003437d  push    r12
0x18003437f  push    r13
0x180034381  push    r14
0x180034383  push    r15
0x180034385  lea     rbp, [rsp-7]
0x18003438a  sub     rsp, 88h
0x180034391  xor     r15d, r15d
0x180034394  mov     r13d, r9d
0x180034397  cmp     cs:?g_fEventApiInitialized@@3HA, r15d; int g_fEventApiInitialized
0x18003439e  mov     rbx, rdx
0x1800343a1  mov     r12, rcx
0x1800343a4  jnz     short loc_1800343DC
0x1800343a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800343ad  lea     rsi, WPP_GLOBAL_Control
0x1800343b4  mov     ebx, 80004005h
0x1800343b9  cmp     rcx, rsi
0x1800343bc  jz      loc_180034982
0x1800343c2  test    byte ptr [rcx+1Ch], 1
0x1800343c6  jz      loc_180034982
0x1800343cc  lea     edx, [r15+38h]
0x1800343d0  lea     r8, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x1800343d7  jmp     loc_18003496E
0x1800343dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800343e3  lea     rsi, WPP_GLOBAL_Control
0x1800343ea  mov     [rbp+3Fh+Block], r15
0x1800343ee  cmp     rcx, rsi
0x1800343f1  jz      short loc_18003441B
0x1800343f3  test    dword ptr [rcx+1Ch], 800h
0x1800343fa  jz      short loc_18003441B
0x1800343fc  mov     r9, [rbp+3Fh+arg_20]
0x180034400  mov     edx, 39h ; '9'
0x180034405  mov     rcx, [rcx+10h]
0x180034409  mov     qword ptr [rsp+0C0h+Period], r12
0x18003440e  mov     [rsp+0C0h+DueTime], r13d
0x180034413  mov     r9, [r9]
0x180034416  call    WPP_SF_SdS
0x18003441b  mov     ecx, 118h; Size
0x180034420  call    cs:__imp_malloc
0x180034426  lea     r14, WPP_2e07143474063d9a59b5fe4ea0113338_Traceguids
0x18003442d  mov     rdi, rax
0x180034430  test    rax, rax
0x180034433  jnz     short loc_18003443F
0x180034435  mov     ebx, 8007000Eh
0x18003443a  jmp     loc_18003493E
0x18003443f  xor     edx, edx; Val
0x180034441  mov     r8d, 118h; Size
0x180034447  mov     rcx, rdi; void *
0x18003444a  call    memset_0
0x18003444f  mov     rcx, rbx; Src
0x180034452  call    ?WszAllocateAndCopyWsz@@YAPEAGPEBG@Z; WszAllocateAndCopyWsz(ushort const *)
0x180034457  mov     rbx, rax
0x18003445a  test    rax, rax
0x18003445d  jz      loc_18003453D
0x180034463  xorps   xmm0, xmm0
0x180034466  mov     [rbp+3Fh+ppResult], r15
0x18003446a  movups  xmmword ptr [rbp+3Fh+pHints.ai_flags], xmm0
0x18003446e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034472  movups  xmmword ptr [rbp+3Fh+pHints.ai_addrlen], xmm0
0x180034476  movups  xmmword ptr [rbp+3Fh+pHints.ai_addr], xmm0
0x18003447a  inc     rax
0x18003447d  cmp     [rbx+rax*2], r15w
0x180034482  jnz     short loc_18003447A
0x180034484  mov     eax, eax
0x180034486  mov     rcx, r15
0x180034489  lea     rdx, [rbx+rax*2]
0x18003448d  mov     eax, 3Ah ; ':'
0x180034492  jmp     short loc_1800344A5
0x180034494  cmp     word ptr [rdx], 5Dh ; ']'
0x180034498  jz      short loc_1800344AC
0x18003449a  cmp     [rdx], ax
0x18003449d  cmovz   rcx, rdx
0x1800344a1  sub     rdx, 2
0x1800344a5  cmp     rdx, rbx
0x1800344a8  jnz     short loc_180034494
0x1800344aa  jmp     short loc_1800344B5
0x1800344ac  test    rcx, rcx
0x1800344af  jz      short loc_1800344B5
0x1800344b1  mov     [rcx], r15w
0x1800344b5  xorps   xmm0, xmm0
0x1800344b8  lea     r9, [rbp+3Fh+ppResult]; ppResult
0x1800344bc  movups  xmmword ptr [rbp+3Fh+pHints.ai_flags], xmm0
0x1800344c0  lea     r8, [rbp+3Fh+pHints]; pHints
0x1800344c4  mov     qword ptr [rbp+3Fh+pHints.ai_flags], 4
0x1800344cc  xor     edx, edx; pServiceName
0x1800344ce  mov     rcx, rbx; pNodeName
0x1800344d1  movups  xmmword ptr [rbp+3Fh+pHints.ai_addrlen], xmm0
0x1800344d5  movups  xmmword ptr [rbp+3Fh+pHints.ai_addr], xmm0
0x1800344d9  call    cs:__imp_GetAddrInfoW
0x1800344df  test    eax, eax
0x1800344e1  jnz     loc_1800345A7
0x1800344e7  mov     r15, [rbp+3Fh+ppResult]
0x1800344eb  lea     rcx, [rdi+38h]; void *
0x1800344ef  mov     r8, [r15+10h]; Size
0x1800344f3  mov     rdx, [r15+20h]; Src
0x1800344f7  call    memcpy_0
0x1800344fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180034503  cmp     rcx, rsi
0x180034506  jz      short loc_180034529
0x180034508  test    dword ptr [rcx+1Ch], 800h
0x18003450f  jz      short loc_180034529
0x180034511  mov     rcx, [rcx+10h]
0x180034515  mov     edx, 3Ah ; ':'
0x18003451a  mov     r9, rbx
0x18003451d  mov     r8, r14
0x180034520  call    WPP_SF_S
0x180034525  mov     r15, [rbp+3Fh+ppResult]
0x180034529  mov     rcx, r15; pAddrInfo
0x18003452c  call    cs:__imp_FreeAddrInfoW
0x180034532  mov     rcx, rbx; void *
0x180034535  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003453a  xor     r15d, r15d
0x18003453d  xor     r9d, r9d; lpName
0x180034540  xor     r8d, r8d; bInitialState
0x180034543  xor     edx, edx; bManualReset
0x180034545  xor     ecx, ecx; lpEventAttributes
0x180034547  call    cs:__imp_CreateEventW
0x18003454d  mov     [rdi+0B8h], rax
0x180034554  test    rax, rax
0x180034557  jnz     loc_1800345E6
0x18003455d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180034562  mov     ebx, eax
0x180034564  test    eax, eax
0x180034566  jz      loc_18003493E
0x18003456c  mov     rcx, cs:WPP_GLOBAL_Control
0x180034573  cmp     rcx, rsi
0x180034576  jz      loc_18003493E
0x18003457c  test    byte ptr [rcx+1Ch], 1
0x180034580  jz      loc_18003493E
0x180034586  mov     edx, 3Ch ; '<'
0x18003458b  lea     r9, aHraddsubscribe; "HrAddSubscriber: CreateEvent"
0x180034592  mov     rcx, [rcx+10h]
0x180034596  mov     r8, r14
0x180034599  mov     [rsp+0C0h+DueTime], eax
0x18003459d  call    WPP_SF_sd
0x1800345a2  jmp     loc_18003493E
0x1800345a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800345ae  cmp     rcx, rsi
0x1800345b1  jz      short loc_1800345D4
0x1800345b3  test    dword ptr [rcx+1Ch], 800h
0x1800345ba  jz      short loc_1800345D4
0x1800345bc  mov     rcx, [rcx+10h]
0x1800345c0  mov     edx, 3Bh ; ';'
0x1800345c5  mov     r9, rbx
0x1800345c8  mov     [rsp+0C0h+DueTime], eax
0x1800345cc  mov     r8, r14
0x1800345cf  call    WPP_SF_Sd
0x1800345d4  mov     rcx, rbx; void *
0x1800345d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800345dc  mov     ebx, 80004005h
0x1800345e1  jmp     loc_18003493E
0x1800345e6  call    ?SzGetNewSid@@YAPEAGXZ; SzGetNewSid(void)
0x1800345eb  mov     [rdi+28h], rax
0x1800345ef  test    rax, rax
0x1800345f2  jz      loc_180034435
0x1800345f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800345ff  cmp     rcx, rsi
0x180034602  jz      short loc_180034621
0x180034604  test    dword ptr [rcx+1Ch], 800h
0x18003460b  jz      short loc_180034621
0x18003460d  mov     rcx, [rcx+10h]
0x180034611  mov     edx, 3Dh ; '='
0x180034616  mov     r9, rax
0x180034619  mov     r8, r14
0x18003461c  call    WPP_SF_S
0x180034621  mov     rcx, [rdi+28h]; pszSrc
0x180034625  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x18003462a  mov     [rbp+3Fh+Block], rax
0x18003462e  test    rax, rax
0x180034631  jz      loc_180034435
0x180034637  mov     rax, r13
0x18003463a  mov     [rdi+10h], r15d
0x18003463e  shl     rax, 3
0x180034642  mov     ecx, 0FFFFFFFFh
0x180034647  cmp     rax, rcx
0x18003464a  ja      loc_180034939
0x180034650  mov     ecx, eax; Size
0x180034652  mov     ebx, eax
0x180034654  call    cs:__imp_malloc
0x18003465a  mov     [rdi+8], rax
0x18003465e  test    rax, rax
0x180034661  jz      loc_180034435
0x180034667  mov     r8d, ebx; Size
0x18003466a  xor     edx, edx; Val
0x18003466c  mov     rcx, rax; void *
0x18003466f  call    memset_0
0x180034674  test    r13d, r13d
0x180034677  jz      short loc_1800346AB
0x180034679  mov     rax, [rbp+3Fh+arg_20]
0x18003467d  mov     ebx, r15d
0x180034680  mov     rcx, [rax+rbx*8]; pszSrc
0x180034684  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x180034689  mov     rcx, [rdi+8]
0x18003468d  mov     [rcx+rbx*8], rax
0x180034691  mov     rax, [rdi+8]
0x180034695  cmp     qword ptr [rax+rbx*8], 0
0x18003469a  jz      loc_180034435
0x1800346a0  inc     dword ptr [rdi+10h]
0x1800346a3  inc     r15d
0x1800346a6  cmp     r15d, r13d
0x1800346a9  jb      short loc_180034679
0x1800346ab  mov     rcx, r12; pszSrc
0x1800346ae  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x1800346b3  lea     rbx, [rdi+0E8h]
0x1800346ba  mov     [rbx], rax
0x1800346bd  test    rax, rax
0x1800346c0  jz      loc_180034435
0x1800346c6  mov     rcx, [rdi+28h]; pszSrc
0x1800346ca  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x1800346cf  mov     [rdi+0F0h], rax
0x1800346d6  test    rax, rax
0x1800346d9  jz      loc_180034435
0x1800346df  lea     r8, pcbe; pcbe
0x1800346e6  mov     rdx, rbx; pv
0x1800346e9  lea     rcx, ?EventQueueWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800346f0  call    cs:__imp_CreateThreadpoolWait
0x1800346f6  mov     [rdi+0D8h], rax
0x1800346fd  test    rax, rax
0x180034700  jnz     short loc_18003473C
0x180034702  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180034707  mov     ebx, eax
0x180034709  test    eax, eax
0x18003470b  jz      loc_18003493E
0x180034711  mov     rcx, cs:WPP_GLOBAL_Control
0x180034718  cmp     rcx, rsi
0x18003471b  jz      loc_18003493E
0x180034721  test    byte ptr [rcx+1Ch], 1
0x180034725  jz      loc_18003493E
0x18003472b  mov     edx, 3Eh ; '>'
0x180034730  lea     r9, aHraddsubscribe_0; "HrAddSubscriber: CreateThreadpoolWait"
0x180034737  jmp     loc_180034592
0x18003473c  mov     rdx, [rdi+0B8h]; h
0x180034743  xor     r8d, r8d; pftTimeout
0x180034746  mov     rcx, rax; pwa
0x180034749  call    cs:__imp_SetThreadpoolWait
0x18003474f  lea     r13, ?g_csEventApiLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csEventApiLock
0x180034756  mov     rcx, r13; lpCriticalSection
0x180034759  call    cs:__imp_EnterCriticalSection
0x18003475f  mov     rcx, r12; unsigned __int16 *
0x180034762  call    ?PesFindEventSource@@YAPEAUUPNP_EVENT_SOURCE@@PEBG@Z; PesFindEventSource(ushort const *)
0x180034767  mov     rbx, rax
0x18003476a  test    rax, rax
0x18003476d  jnz     short loc_1800347A9
0x18003476f  mov     ebx, 80070002h
0x180034774  mov     rcx, cs:WPP_GLOBAL_Control
0x18003477b  cmp     rcx, rsi
0x18003477e  jz      short loc_18003479B
0x180034780  test    dword ptr [rcx+1Ch], 800h
0x180034787  jz      short loc_18003479B
0x180034789  lea     edx, [rax+3Fh]
0x18003478c  mov     rcx, [rcx+10h]
0x180034790  mov     r9, r12
0x180034793  mov     r8, r14
0x180034796  call    WPP_SF_S
0x18003479b  mov     rcx, r13; lpCriticalSection
0x18003479e  call    cs:__imp_LeaveCriticalSection
0x1800347a4  jmp     loc_18003493E
0x1800347a9  cmp     dword ptr [rax+8], 7D0h
0x1800347b0  jb      short loc_1800347D0
0x1800347b2  mov     ebx, 8007050Ch
0x1800347b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800347be  cmp     rcx, rsi
0x1800347c1  jz      short loc_18003479B
0x1800347c3  test    byte ptr [rcx+1Ch], 1
0x1800347c7  jz      short loc_18003479B
0x1800347c9  mov     edx, 40h ; '@'
0x1800347ce  jmp     short loc_18003478C
0x1800347d0  mov     eax, [rdi+30h]
0x1800347d3  lea     r15, [rdi+0F8h]
0x1800347da  mov     [r15+10h], eax
0x1800347de  mov     rcx, [rbx]; pszSrc
0x1800347e1  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x1800347e6  mov     [r15], rax
0x1800347e9  test    rax, rax
0x1800347ec  jnz     short loc_1800347F5
0x1800347ee  mov     ebx, 8007000Eh
0x1800347f3  jmp     short loc_18003479B
0x1800347f5  mov     rcx, [rdi+28h]; pszSrc
0x1800347f9  call    ?WszDupWsz@@YAPEAGPEBG@Z; WszDupWsz(ushort const *)
0x1800347fe  mov     [rdi+100h], rax
0x180034805  test    rax, rax
0x180034808  jz      short loc_1800347EE
0x18003480a  mov     rax, [rbp+3Fh+arg_30]
0x18003480e  lea     r8, ?RenewalCallback@@YAXPEAXE@Z; Callback
0x180034815  mov     ecx, 12Ch
0x18003481a  mov     [rsp+0C0h+Flags], 20h ; ' '; Flags
0x180034822  mov     [rsp+0C0h+Period], 0; Period
0x18003482a  mov     r9, r15; Parameter
0x18003482d  mov     [rax], ecx
0x18003482f  mov     [rdi+14h], ecx
0x180034832  lea     rcx, [rdi+0E0h]; phNewTimer
0x180034839  imul    edx, [rax], 3E8h
0x18003483f  mov     [rsp+0C0h+DueTime], edx; DueTime
0x180034843  mov     rdx, cs:?g_hTimerQ@@3PEAXEA; TimerQueue
0x18003484a  call    cs:__imp_CreateTimerQueueTimer
0x180034850  test    eax, eax
  ... truncated ...
```
