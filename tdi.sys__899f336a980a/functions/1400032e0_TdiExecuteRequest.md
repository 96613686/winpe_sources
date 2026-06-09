# TdiExecuteRequest

- ea: `0x1400032e0`
- end: `0x1400039bc`
- name: `TdiExecuteRequest`
- size: `1756`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140002860`
- `0x140002f50`

## callees

- `0x140001540`
- `0x140001df0`
- `0x140002240`
- `0x140002590`
- `0x1400032e0`
- `0x140005530`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400033a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000363e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000399b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400033a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000363e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000399b`
- `ntoskrnl!KeSetEvent` at `0x14000352b`
- `ntoskrnl!KeSetEvent` at `0x14000352b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400035cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000368f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400036a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400036b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003773`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000378a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400037b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003880`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000389e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400038bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400035cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000368f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400036a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400036b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003773`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000378a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400037b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003880`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000389e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400038bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000331a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000353e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000331a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000353e`
- `ntoskrnl!ExQueueWorkItem` at `0x140003968`
- `ntoskrnl!ExQueueWorkItem` at `0x140003968`

## pseudocode

```c
__int64 __fastcall TdiExecuteRequest(PVOID P, char a2)
{
  unsigned int v4; // r12d
  KIRQL v5; // r8
  int v6; // edx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rax
  _QWORD *v11; // rdx
  __int64 v12; // rcx
  _QWORD *v13; // r14
  __int64 v14; // rdi
  _QWORD *v15; // rbx
  char v16; // al
  void (__fastcall *v17)(_QWORD *); // rax
  _QWORD *k; // rbx
  KIRQL v19; // bp
  int v20; // edx
  __int64 v21; // rcx
  PVOID *v22; // rbx
  int v23; // eax
  PVOID *v24; // rdi
  _QWORD *v25; // rax
  void ***v26; // rbx
  void **v27; // rax
  void **v28; // rcx
  __int64 v29; // rdi
  void *v30; // rcx
  void *v31; // rcx
  __int64 v32; // rcx
  _QWORD *v33; // rdx
  _QWORD *v34; // rax
  void **v35; // rax
  void **v36; // rcx
  void **v37; // rcx
  void **v38; // rcx
  __int64 v39; // rbx
  _QWORD *v40; // rcx
  _QWORD *i; // rax
  __int64 v42; // rcx
  __int64 v43; // rax
  _QWORD *v44; // rcx
  void (__fastcall *v45)(_QWORD, _QWORD); // rax
  void *v46; // rcx
  void *v47; // rcx
  void *v48; // rcx
  __int64 **v49; // rdi
  __int64 v50; // rbp
  __int64 *j; // rbx
  void (__fastcall *v52)(__int64 *, __int64 *, __int64); // rax
  __int64 v54; // [rsp+20h] [rbp-58h]

  while ( 2 )
  {
    v4 = 0;
    v5 = KeAcquireSpinLockRaiseToDpc(&TDIListLock);
    if ( *((_QWORD *)P + 10) )
      **((_QWORD **)P + 12) = KeGetCurrentThread();
    v7 = 4LL * NextExec++;
    v6 = NextExec;
    TrackExecs[v7] = (__int64)P;
    LODWORD(TrackExecs[v7 + 1]) = *((_DWORD *)P + 18);
    TrackExecs[v7 + 2] = *((_QWORD *)P + 8);
    TrackExecs[v7 + 3] = *((_QWORD *)P + 12);
    if ( v6 == 8 )
      NextExec = 0;
    qword_140008348 = (__int64)KeGetCurrentThread();
    KeReleaseSpinLock(&TDIListLock, v5);
    switch ( *((_DWORD *)P + 18) )
    {
      case 8:
        v10 = *((_QWORD *)P + 3);
        v11 = *(_QWORD **)(v10 + 8);
        if ( *v11 != v10 )
          goto LABEL_94;
        v12 = *((_QWORD *)P + 8);
        *(_QWORD *)v12 = v10;
        *(_QWORD *)(v12 + 8) = v11;
        *v11 = v12;
        *(_QWORD *)(v10 + 8) = v12;
        TdipGetMultiSZList(
          (_QWORD *)(v12 + 88),
          (__int64)v11,
          (const UNICODE_STRING *)(v12 + 32),
          v9,
          v54,
          (unsigned int *)(v12 + 96));
        v13 = (_QWORD *)*((_QWORD *)P + 4);
        v14 = *((_QWORD *)P + 8);
        v15 = (_QWORD *)*v13;
        if ( (_QWORD *)*v13 == v13 )
          goto LABEL_20;
        break;
      case 9:
        v26 = (void ***)*((_QWORD *)P + 8);
        v27 = *v26;
        if ( (*v26)[1] != v26 )
          goto LABEL_94;
        v28 = v26[1];
        if ( *v28 != v26 )
          goto LABEL_94;
        *v28 = v27;
        v27[1] = v28;
        v26[1] = (void **)4025479151LL;
        *v26 = (void **)2880154539LL;
        v29 = *((_QWORD *)P + 8);
        v30 = *(void **)(v29 + 40);
        if ( v30 )
          ExFreePoolWithTag(v30, 0);
        v31 = *(void **)(v29 + 88);
        if ( v31 )
          ExFreePoolWithTag(v31, 0);
        goto LABEL_50;
      case 0xA:
        v39 = *((_QWORD *)P + 8);
        *(_DWORD *)(v39 + 96) = 1;
        v40 = (_QWORD *)*((_QWORD *)P + 3);
        for ( i = (_QWORD *)*v40; i != v40; v40 = (_QWORD *)*((_QWORD *)P + 3) )
        {
          if ( i[10] )
            ++*(_DWORD *)(v39 + 96);
          i = (_QWORD *)*i;
        }
        v4 = TdiNotifyPnpClientList(v40, *((_QWORD *)P + 8), 0);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v39 + 96), 0xFFFFFFFF) == 1 )
        {
          v42 = *(_QWORD *)(v39 + 40);
          v4 = *(_DWORD *)(v39 + 56);
          v43 = *(_QWORD *)(v42 + 88);
          if ( *(_QWORD *)(v43 + 104) )
          {
            do
            {
              v44 = (_QWORD *)(v43 + 104);
              v43 = *(_QWORD *)(v43 + 104);
            }
            while ( *(_QWORD *)(v43 + 104) );
            *v44 = 0;
          }
          else
          {
            *(_OWORD *)(v42 + 88) = 0;
            *(_OWORD *)(v42 + 104) = 0;
          }
          if ( *((_BYTE *)P + 88) )
          {
            v45 = *(void (__fastcall **)(_QWORD, _QWORD))(v39 + 48);
            if ( v45 )
            {
              v45(*(_QWORD *)(v39 + 40), *(unsigned int *)(v39 + 56));
              v46 = *(void **)(v39 + 128);
              if ( v46 )
              {
                ExFreePoolWithTag(v46, 0);
                *(_QWORD *)(v39 + 128) = 0;
              }
              v47 = *(void **)(v39 + 80);
              if ( v47 )
              {
                ExFreePoolWithTag(v47, 0);
                *(_QWORD *)(v39 + 80) = 0;
              }
              v48 = *(void **)(v39 + 88);
              if ( v48 )
              {
                ExFreePoolWithTag(v48, 0);
                *(_QWORD *)(v39 + 88) = 0;
              }
            }
          }
        }
        goto LABEL_29;
      case 0xB:
      case 0xD:
        goto LABEL_52;
      case 0xC:
      case 0xE:
        goto LABEL_56;
      case 0xF:
        TdiHandlePnpOperation(*((const UNICODE_STRING ***)P + 3), *((_QWORD *)P + 8), *((_QWORD *)P + 16));
        goto LABEL_29;
      case 0x10:
        v49 = (__int64 **)*((_QWORD *)P + 4);
        v50 = *((_QWORD *)P + 8);
        for ( j = *v49; j != (__int64 *)v49; j = (__int64 *)*j )
        {
          if ( *((_BYTE *)j + 16) == 1 )
          {
            v52 = *(void (__fastcall **)(__int64 *, __int64 *, __int64))(v50 + 64);
            if ( v52 )
              v52(j + 15, j + 8, j[11]);
          }
        }
        goto LABEL_29;
      case 0x11:
        _InterlockedIncrement(&ProvidersRegistered);
LABEL_52:
        v32 = *((_QWORD *)P + 4);
        v33 = *(_QWORD **)(v32 + 8);
        if ( *v33 != v32 )
          goto LABEL_94;
        v34 = (_QWORD *)*((_QWORD *)P + 8);
        *v34 = v32;
        v34[1] = v33;
        *v33 = v34;
        *(_QWORD *)(v32 + 8) = v34;
LABEL_54:
        LOBYTE(v8) = 1;
        TdiNotifyPnpClientList(*((_QWORD *)P + 3), *((_QWORD *)P + 8), v8);
        goto LABEL_29;
      case 0x12:
        _InterlockedDecrement(&ProvidersRegistered);
LABEL_56:
        v26 = (void ***)*((_QWORD *)P + 8);
        v35 = *v26;
        if ( (*v26)[1] != v26 )
          goto LABEL_94;
        v36 = v26[1];
        if ( *v36 != v26 )
          goto LABEL_94;
        *v36 = v35;
        v35[1] = v36;
        v26[1] = (void **)4025479151LL;
        *v26 = (void **)2880154539LL;
        if ( *((_DWORD *)P + 18) == 18 )
        {
          if ( *((_DWORD *)v26 + 25) )
            _InterlockedDecrement(&ProvidersReady);
        }
        else
        {
          TdiNotifyPnpClientList(*((_QWORD *)P + 3), *((_QWORD *)P + 8), 0);
        }
        if ( *((_DWORD *)P + 18) == 14 )
          ExFreePoolWithTag(v26[16], 0);
        v37 = v26[9];
        if ( v37 )
        {
          ExFreePoolWithTag(v37, 0);
          v26[9] = 0;
          *((_DWORD *)v26 + 16) = 0;
        }
        v38 = v26[11];
        if ( v38 )
        {
          ExFreePoolWithTag(v38, 0);
          v26[11] = 0;
        }
LABEL_50:
        ExFreePoolWithTag(v26, 0);
        goto LABEL_29;
      case 0x13:
        _InterlockedIncrement(&ProvidersReady);
        *(_DWORD *)(*((_QWORD *)P + 8) + 100LL) = 1;
        goto LABEL_54;
      default:
        goto LABEL_29;
    }
    do
    {
      v16 = *((_BYTE *)v15 + 16);
      if ( !v16 )
      {
        v17 = *(void (__fastcall **)(_QWORD *))(v14 + 48);
        if ( *(_WORD *)(v14 + 24) != 1 )
        {
          if ( v17 && (unsigned __int8)TdipMultiSzStrStr(*(_QWORD *)(v14 + 88), v15 + 15) )
            (*(void (__fastcall **)(__int64, _QWORD *, __int64))(v14 + 48))(
              1,
              v15 + 15,
              *(_QWORD *)(v14 + 88) + 8LL * *(unsigned int *)(v14 + 96));
          goto LABEL_19;
        }
LABEL_15:
        if ( v17 )
          v17(v15 + 15);
        goto LABEL_19;
      }
      if ( v16 != 1 )
        goto LABEL_19;
      v17 = *(void (__fastcall **)(_QWORD *))(v14 + 64);
      if ( *(_WORD *)(v14 + 24) == 1 )
        goto LABEL_15;
      if ( v17 )
        ((void (__fastcall *)(_QWORD *, _QWORD *, _QWORD))v17)(v15 + 15, v15 + 8, v15[11]);
LABEL_19:
      v15 = (_QWORD *)*v15;
    }
    while ( v15 != v13 );
LABEL_20:
    if ( *(_QWORD *)(v14 + 48) && *(_WORD *)(v14 + 24) != 1 )
    {
      for ( k = (_QWORD *)*v13; k != v13; k = (_QWORD *)*k )
      {
        if ( *((_BYTE *)k + 16) == 3 && *((_DWORD *)k + 25) )
          (*(void (__fastcall **)(__int64, _QWORD *, _QWORD))(v14 + 48))(4, k + 15, 0);
      }
      if ( ProvidersReady == ProvidersRegistered )
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(v14 + 48))(5, 0, 0);
    }
LABEL_29:
    if ( *((_QWORD *)P + 10) )
    {
      **((_QWORD **)P + 12) = 0;
      KeSetEvent(*((PRKEVENT *)P + 10), 0, 0);
    }
    v19 = KeAcquireSpinLockRaiseToDpc(&TDIListLock);
    v21 = 4LL * NextExecComplete++;
    v20 = NextExecComplete;
    TrackExecCompletes[v21] = (__int64)P;
    LODWORD(TrackExecCompletes[v21 + 1]) = *((_DWORD *)P + 18);
    TrackExecCompletes[v21 + 2] = *((_QWORD *)P + 8);
    TrackExecCompletes[v21 + 3] = *((_QWORD *)P + 12);
    if ( v20 == 8 )
      NextExecComplete = 0;
    --PnpRequestsExecuting;
    --PnpRequestsInQueue;
    qword_140008348 = 0;
    v22 = (PVOID *)*((_QWORD *)P + 5);
    v23 = *((_DWORD *)P + 18);
    v24 = (PVOID *)*v22;
    if ( v23 != 10 && v23 != 15 )
      --PnpExclusiveRequestsInQueue;
    ExFreePoolWithTag(P, 0);
    if ( v24 == v22 || PnpRequestsExecuting )
    {
      if ( a2 )
        PnpWorkerThreadActive = 0;
    }
    else if ( a2 || !PnpWorkerThreadActive )
    {
      P = *v22;
      PnpRequestsExecuting = 1;
      if ( *((PVOID **)P + 1) != v22 || (v25 = *(_QWORD **)P, *(PVOID *)(*(_QWORD *)P + 8LL) != P) )
LABEL_94:
        __fastfail(3u);
      *v22 = v25;
      v25[1] = v22;
      if ( a2 )
      {
        KeReleaseSpinLock(&TDIListLock, v19);
        continue;
      }
      PnpTdiWorkItem.Parameter = P;
      PnpTdiWorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)TdiExecuteRequestWrapper;
      PnpTdiWorkItem.List.Flink = 0;
      ExQueueWorkItem(&PnpTdiWorkItem, DelayedWorkQueue);
      PnpWorkerThreadActive = 1;
    }
    break;
  }
  KeReleaseSpinLock(&TDIListLock, v19);
  return v4;
}

```

## disassembly

```asm
0x1400032e0  push    rbx
0x1400032e2  push    rbp
0x1400032e3  push    rsi
0x1400032e4  push    rdi
0x1400032e5  push    r12
0x1400032e7  push    r13
0x1400032e9  push    r14
0x1400032eb  push    r15
0x1400032ed  sub     rsp, 38h
0x1400032f1  movzx   r13d, dl
0x1400032f5  mov     rsi, rcx
0x1400032f8  xor     r14d, r14d
0x1400032fb  mov     edi, 0ABABABABh
0x140003300  lea     rbx, cs:140000000h
0x140003307  mov     ebp, 1
0x14000330c  nop     dword ptr [rax+00h]
0x140003310  lea     rcx, TDIListLock; SpinLock
0x140003317  mov     r12d, r14d
0x14000331a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003321  nop     dword ptr [rax+rax+00h]
0x140003326  cmp     qword ptr [rsi+50h], 0
0x14000332b  movzx   r8d, al
0x14000332f  jz      short loc_140003341
0x140003331  mov     rcx, gs:188h
0x14000333a  mov     rax, [rsi+60h]
0x14000333e  mov     [rax], rcx
0x140003341  movsxd  rdx, cs:NextExec
0x140003348  mov     rcx, rdx
0x14000334b  inc     edx
0x14000334d  shl     rcx, 5
0x140003351  mov     cs:NextExec, edx
0x140003357  mov     [rcx+rbx+8240h], rsi
0x14000335f  mov     eax, [rsi+48h]
0x140003362  mov     [rcx+rbx+8248h], eax
0x140003369  mov     rax, [rsi+40h]
0x14000336d  mov     [rcx+rbx+8250h], rax
0x140003375  mov     rax, [rsi+60h]
0x140003379  mov     [rcx+rbx+8258h], rax
0x140003381  cmp     edx, 8
0x140003384  jnz     short loc_14000338D
0x140003386  mov     cs:NextExec, r14d
0x14000338d  mov     rax, gs:188h
0x140003396  lea     rcx, TDIListLock; SpinLock
0x14000339d  movzx   edx, r8b; NewIrql
0x1400033a1  mov     cs:qword_140008348, rax
0x1400033a8  call    cs:__imp_KeReleaseSpinLock
0x1400033af  nop     dword ptr [rax+rax+00h]
0x1400033b4  mov     eax, [rsi+48h]
0x1400033b7  add     eax, 0FFFFFFF8h; switch 12 cases
0x1400033ba  cmp     eax, 0Bh
0x1400033bd  ja      def_1400033CD; jumptable 00000001400033CD default case
0x1400033c3  mov     eax, ds:(jpt_1400033CD - 140000000h)[rbx+rax*4]
0x1400033ca  add     rax, rbx
0x1400033cd  jmp     rax; switch jump
0x1400033d3  mov     rax, [rsi+18h]; jumptable 00000001400033CD case 8
0x1400033d7  mov     rdx, [rax+8]
0x1400033db  cmp     [rdx], rax
0x1400033de  jnz     loc_14000397D
0x1400033e4  mov     rcx, [rsi+40h]
0x1400033e8  mov     [rcx], rax
0x1400033eb  lea     r8, [rcx+20h]
0x1400033ef  mov     [rcx+8], rdx
0x1400033f3  mov     [rdx], rcx
0x1400033f6  mov     [rax+8], rcx
0x1400033fa  lea     rax, [rcx+60h]
0x1400033fe  add     rcx, 58h ; 'X'
0x140003402  mov     [rsp+78h+var_50], rax
0x140003407  call    TdipGetMultiSZList
0x14000340c  mov     r14, [rsi+20h]
0x140003410  mov     rdi, [rsi+40h]
0x140003414  mov     rbx, [r14]
0x140003417  cmp     rbx, r14
0x14000341a  jz      loc_1400034A9
0x140003420  movzx   eax, byte ptr [rbx+10h]
0x140003424  test    al, al
0x140003426  jnz     short loc_140003469
0x140003428  mov     rax, [rdi+30h]
0x14000342c  cmp     bp, [rdi+18h]
0x140003430  jz      short loc_140003477
0x140003432  test    rax, rax
0x140003435  jz      short loc_14000349D
0x140003437  mov     rcx, [rdi+58h]
0x14000343b  lea     rdx, [rbx+78h]
0x14000343f  call    TdipMultiSzStrStr
0x140003444  mov     ebp, 1
0x140003449  test    al, al
0x14000344b  jz      short loc_14000349D
0x14000344d  mov     ecx, [rdi+60h]
0x140003450  lea     rdx, [rbx+78h]
0x140003454  mov     rax, [rdi+58h]
0x140003458  lea     r8, [rax+rcx*8]
0x14000345c  mov     rax, [rdi+30h]
0x140003460  mov     ecx, ebp
0x140003462  call    _guard_dispatch_icall
0x140003467  jmp     short loc_14000349D
0x140003469  cmp     al, 1
0x14000346b  jnz     short loc_14000349D
0x14000346d  mov     rax, [rdi+40h]
0x140003471  cmp     bp, [rdi+18h]
0x140003475  jnz     short loc_140003487
0x140003477  test    rax, rax
0x14000347a  jz      short loc_14000349D
0x14000347c  lea     rcx, [rbx+78h]
0x140003480  call    _guard_dispatch_icall
0x140003485  jmp     short loc_14000349D
0x140003487  test    rax, rax
0x14000348a  jz      short loc_14000349D
0x14000348c  mov     r8, [rbx+58h]
0x140003490  lea     rdx, [rbx+40h]
0x140003494  lea     rcx, [rbx+78h]
0x140003498  call    _guard_dispatch_icall
0x14000349d  mov     rbx, [rbx]
0x1400034a0  cmp     rbx, r14
0x1400034a3  jnz     loc_140003420
0x1400034a9  cmp     qword ptr [rdi+30h], 0
0x1400034ae  jz      short loc_14000350A
0x1400034b0  cmp     bp, [rdi+18h]
0x1400034b4  jz      short loc_14000350A
0x1400034b6  mov     rbx, [r14]
0x1400034b9  cmp     rbx, r14
0x1400034bc  jz      short loc_1400034E9
0x1400034be  xchg    ax, ax
0x1400034c0  cmp     byte ptr [rbx+10h], 3
0x1400034c4  jnz     short loc_1400034E1
0x1400034c6  cmp     dword ptr [rbx+64h], 0
0x1400034ca  jz      short loc_1400034E1
0x1400034cc  mov     rax, [rdi+30h]
0x1400034d0  lea     rdx, [rbx+78h]
0x1400034d4  xor     r8d, r8d
0x1400034d7  mov     ecx, 4
0x1400034dc  call    _guard_dispatch_icall
0x1400034e1  mov     rbx, [rbx]
0x1400034e4  cmp     rbx, r14
0x1400034e7  jnz     short loc_1400034C0
0x1400034e9  mov     eax, cs:ProvidersRegistered
0x1400034ef  cmp     cs:ProvidersReady, eax
0x1400034f5  jnz     short loc_14000350A
0x1400034f7  mov     rax, [rdi+30h]
0x1400034fb  xor     r8d, r8d
0x1400034fe  xor     edx, edx
0x140003500  mov     ecx, 5
0x140003505  call    _guard_dispatch_icall
0x14000350a  xor     r14d, r14d
0x14000350d  lea     rbx, cs:140000000h
0x140003514  cmp     qword ptr [rsi+50h], 0; jumptable 00000001400033CD default case
0x140003519  jz      short loc_140003537
0x14000351b  mov     rax, [rsi+60h]
0x14000351f  xor     r8d, r8d; Wait
0x140003522  xor     edx, edx; Increment
0x140003524  mov     [rax], r14
0x140003527  mov     rcx, [rsi+50h]; Event
0x14000352b  call    cs:__imp_KeSetEvent
0x140003532  nop     dword ptr [rax+rax+00h]
0x140003537  lea     rcx, TDIListLock; SpinLock
0x14000353e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003545  nop     dword ptr [rax+rax+00h]
0x14000354a  movsxd  rdx, cs:NextExecComplete
0x140003551  movzx   ebp, al
0x140003554  mov     rcx, rdx
0x140003557  inc     edx
0x140003559  shl     rcx, 5
0x14000355d  mov     cs:NextExecComplete, edx
0x140003563  mov     [rcx+rbx+8140h], rsi
0x14000356b  mov     eax, [rsi+48h]
0x14000356e  mov     [rcx+rbx+8148h], eax
0x140003575  mov     rax, [rsi+40h]
0x140003579  mov     [rcx+rbx+8150h], rax
0x140003581  mov     rax, [rsi+60h]
0x140003585  mov     [rcx+rbx+8158h], rax
0x14000358d  cmp     edx, 8
0x140003590  jnz     short loc_140003599
0x140003592  mov     cs:NextExecComplete, r14d
0x140003599  dec     cs:PnpRequestsExecuting
0x14000359f  dec     cs:PnpRequestsInQueue
0x1400035a5  mov     cs:qword_140008348, r14
0x1400035ac  mov     rbx, [rsi+28h]
0x1400035b0  mov     eax, [rsi+48h]
0x1400035b3  mov     rdi, [rbx]
0x1400035b6  cmp     eax, 0Ah
0x1400035b9  jz      short loc_1400035C6
0x1400035bb  cmp     eax, 0Fh
0x1400035be  jz      short loc_1400035C6
0x1400035c0  dec     cs:PnpExclusiveRequestsInQueue
0x1400035c6  xor     edx, edx; Tag
0x1400035c8  mov     rcx, rsi; P
0x1400035cb  call    cs:__imp_ExFreePoolWithTag
0x1400035d2  nop     dword ptr [rax+rax+00h]
0x1400035d7  cmp     rdi, rbx
0x1400035da  jz      loc_140003984
0x1400035e0  cmp     cs:PnpRequestsExecuting, 0
0x1400035e7  jnz     loc_140003984
0x1400035ed  test    r13b, r13b
0x1400035f0  jnz     short loc_1400035FF
0x1400035f2  cmp     cs:PnpWorkerThreadActive, r13b
0x1400035f9  jnz     loc_140003990
0x1400035ff  mov     rsi, [rbx]
0x140003602  mov     cs:PnpRequestsExecuting, 1
0x14000360c  cmp     [rsi+8], rbx
0x140003610  jnz     loc_14000397D
0x140003616  mov     rax, [rsi]
0x140003619  cmp     [rax+8], rsi
0x14000361d  jnz     loc_14000397D
0x140003623  mov     [rbx], rax
0x140003626  mov     [rax+8], rbx
0x14000362a  test    r13b, r13b
0x14000362d  jz      loc_140003940
0x140003633  movzx   edx, bpl; NewIrql
0x140003637  lea     rcx, TDIListLock; SpinLock
0x14000363e  call    cs:__imp_KeReleaseSpinLock
0x140003645  nop     dword ptr [rax+rax+00h]
0x14000364a  jmp     loc_1400032FB
0x14000364f  mov     rbx, [rsi+40h]; jumptable 00000001400033CD case 9
0x140003653  mov     rax, [rbx]
0x140003656  cmp     [rax+8], rbx
0x14000365a  jnz     loc_14000397D
0x140003660  mov     rcx, [rbx+8]
0x140003664  cmp     [rcx], rbx
0x140003667  jnz     loc_14000397D
0x14000366d  mov     [rcx], rax
0x140003670  mov     [rax+8], rcx
0x140003674  mov     eax, 0EFEFEFEFh
0x140003679  mov     [rbx+8], rax
0x14000367d  mov     [rbx], rdi
0x140003680  mov     rdi, [rsi+40h]
0x140003684  mov     rcx, [rdi+28h]; P
0x140003688  test    rcx, rcx
0x14000368b  jz      short loc_14000369B
0x14000368d  xor     edx, edx; Tag
0x14000368f  call    cs:__imp_ExFreePoolWithTag
0x140003696  nop     dword ptr [rax+rax+00h]
0x14000369b  mov     rcx, [rdi+58h]; P
0x14000369f  test    rcx, rcx
0x1400036a2  jz      short loc_1400036B2
0x1400036a4  xor     edx, edx; Tag
0x1400036a6  call    cs:__imp_ExFreePoolWithTag
0x1400036ad  nop     dword ptr [rax+rax+00h]
0x1400036b2  xor     edx, edx; Tag
0x1400036b4  mov     rcx, rbx; P
0x1400036b7  call    cs:__imp_ExFreePoolWithTag
0x1400036be  nop     dword ptr [rax+rax+00h]
0x1400036c3  jmp     loc_14000350D
0x1400036c8  lock inc cs:ProvidersRegistered; jumptable 00000001400033CD case 17
0x1400036cf  mov     rcx, [rsi+20h]; jumptable 00000001400033CD cases 11,13
0x1400036d3  mov     rdx, [rcx+8]
0x1400036d7  cmp     [rdx], rcx
0x1400036da  jnz     loc_14000397D
0x1400036e0  mov     rax, [rsi+40h]
0x1400036e4  mov     [rax], rcx
0x1400036e7  mov     [rax+8], rdx
0x1400036eb  mov     [rdx], rax
0x1400036ee  mov     [rcx+8], rax
0x1400036f2  mov     rdx, [rsi+40h]
0x1400036f6  mov     r8b, 1
0x1400036f9  mov     rcx, [rsi+18h]
0x1400036fd  call    TdiNotifyPnpClientList
0x140003702  jmp     def_1400033CD; jumptable 00000001400033CD default case
0x140003707  lock dec cs:ProvidersRegistered; jumptable 00000001400033CD case 18
0x14000370e  mov     rbx, [rsi+40h]; jumptable 00000001400033CD cases 12,14
0x140003712  mov     rax, [rbx]
0x140003715  cmp     [rax+8], rbx
0x140003719  jnz     loc_14000397D
0x14000371f  mov     rcx, [rbx+8]
0x140003723  cmp     [rcx], rbx
0x140003726  jnz     loc_14000397D
0x14000372c  mov     [rcx], rax
0x14000372f  mov     [rax+8], rcx
0x140003733  mov     eax, 0EFEFEFEFh
0x140003738  mov     [rbx+8], rax
0x14000373c  mov     [rbx], rdi
0x14000373f  cmp     dword ptr [rsi+48h], 12h
0x140003743  jnz     short loc_140003754
0x140003745  cmp     dword ptr [rbx+64h], 0
0x140003749  jz      short loc_140003764
0x14000374b  lock dec cs:ProvidersReady
0x140003752  jmp     short loc_140003764
0x140003754  mov     rdx, [rsi+40h]
0x140003758  xor     r8d, r8d
0x14000375b  mov     rcx, [rsi+18h]
0x14000375f  call    TdiNotifyPnpClientList
0x140003764  cmp     dword ptr [rsi+48h], 0Eh
0x140003768  jnz     short loc_14000377F
0x14000376a  mov     rcx, [rbx+80h]; P
0x140003771  xor     edx, edx; Tag
0x140003773  call    cs:__imp_ExFreePoolWithTag
0x14000377a  nop     dword ptr [rax+rax+00h]
0x14000377f  mov     rcx, [rbx+48h]; P
0x140003783  test    rcx, rcx
0x140003786  jz      short loc_1400037A1
0x140003788  xor     edx, edx; Tag
0x14000378a  call    cs:__imp_ExFreePoolWithTag
0x140003791  nop     dword ptr [rax+rax+00h]
0x140003796  mov     [rbx+48h], r14
0x14000379a  mov     dword ptr [rbx+40h], 0
0x1400037a1  mov     rcx, [rbx+58h]; P
0x1400037a5  test    rcx, rcx
0x1400037a8  jz      loc_1400036B2
0x1400037ae  xor     edx, edx; Tag
0x1400037b0  call    cs:__imp_ExFreePoolWithTag
0x1400037b7  nop     dword ptr [rax+rax+00h]
0x1400037bc  mov     [rbx+58h], r14
  ... truncated ...
```
