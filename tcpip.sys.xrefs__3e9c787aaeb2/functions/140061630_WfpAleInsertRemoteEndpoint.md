# WfpAleInsertRemoteEndpoint

- ea: `0x140061630`
- end: `0x1400623f0`
- name: `WfpAleInsertRemoteEndpoint`
- size: `3520`
- prototype: `__int64 __fastcall(KSPIN_LOCK *SpinLock, unsigned __int16, int, __int64, __int64, __int16, _DWORD *, __int16, char, __int64, unsigned __int16, int, char, __int64, __int64, __int64, unsigned int, int, char, char, __int64, PKSPIN_LOCK *, _BYTE *)`
- caller_count: `3`
- callee_count: `34`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005e2b0`
- `0x14013e520`
- `0x14013fc30`

## callees

- `0x140011340`
- `0x1400114b0`
- `0x140013140`
- `0x140014480`
- `0x140014a90`
- `0x140015a70`
- `0x1400162f0`
- `0x14005fe90`
- `0x14006150c`
- `0x140061630`
- `0x1400623f8`
- `0x140062450`
- `0x140062500`
- `0x140063380`
- `0x140063720`
- `0x1400637b0`
- `0x140063930`
- `0x1400639b4`
- `0x140063b14`
- `0x140063b78`
- `0x140063c60`
- `0x140063d60`
- `0x140071ac0`
- `0x140071af0`
- `0x14009f740`
- `0x1400a0540`
- `0x1400c63f0`
- `0x1400c7fe0`
- `0x1400dff30`
- `0x1401169c8`
- `0x14014ff64`
- `0x140198204`
- `0x1401c0fd0`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140062383`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140062383`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140061e89`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140061e89`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140061c06`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140061c06`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140061db3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140061db3`
- `ntoskrnl!KeReadStateEvent` at `0x1400616f8`
- `ntoskrnl!KeReadStateEvent` at `0x140061d37`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8b72`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8b87`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8b9c`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8bb1`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8c04`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8c19`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8c2e`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8c43`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8c89`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8c9e`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8cb3`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8cc8`
- `ntoskrnl!KeReadStateEvent` at `0x1400616f8`
- `ntoskrnl!KeReadStateEvent` at `0x140061d37`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8b72`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8b87`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8b9c`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8bb1`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8c04`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8c19`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8c2e`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8c43`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8c89`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8c9e`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8cb3`
- `ntoskrnl!KeReadStateEvent` at `0x1401c8cc8`
- `ntoskrnl!KeInitializeSpinLock` at `0x140061b49`
- `ntoskrnl!KeInitializeSpinLock` at `0x140061b49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062017`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062017`
- `NETIO!KfdAleInitializeFlowTable` at `0x140061b0f`
- `NETIO!KfdAleInitializeFlowTable` at `0x140061f05`
- `NETIO!KfdAleInitializeFlowTable` at `0x140061b0f`
- `NETIO!KfdAleInitializeFlowTable` at `0x140061f05`
- `NETIO!KfdAleRemoveFlowContextTable` at `0x140061afb`
- `NETIO!KfdAleRemoveFlowContextTable` at `0x140061afb`
- `NDIS!NdisReleaseRWLock` at `0x140061eba`
- `NDIS!NdisReleaseRWLock` at `0x140061eba`

## pseudocode

```c
__int64 __fastcall WfpAleInsertRemoteEndpoint(
        KSPIN_LOCK *SpinLock,
        unsigned __int16 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int16 a6,
        _DWORD *a7,
        __int16 a8,
        char a9,
        __int64 a10,
        unsigned __int16 a11,
        int a12,
        char a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        unsigned int a17,
        int a18,
        char a19,
        char a20,
        __int64 a21,
        PKSPIN_LOCK *a22,
        _BYTE *a23)
{
  unsigned __int16 v24; // di
  __int64 v26; // rcx
  int v27; // ebx
  __int64 v28; // rsi
  __int64 v29; // r10
  _DWORD *v30; // r8
  _DWORD *v31; // r9
  int v32; // eax
  __int64 v33; // rax
  int v34; // ecx
  char v35; // cl
  unsigned int v36; // eax
  PKSPIN_LOCK v37; // rbx
  char v38; // r12
  char v39; // r13
  char v40; // di
  __int64 v41; // rax
  PKSPIN_LOCK v42; // rcx
  _QWORD *v43; // rax
  __int64 v44; // rdx
  __int128 v45; // xmm0
  KSPIN_LOCK v46; // r13
  __int64 v47; // rcx
  KSPIN_LOCK v48; // r13
  __int64 v49; // rdx
  __int64 v50; // r8
  KSPIN_LOCK v51; // rdi
  int v52; // edx
  int v53; // ecx
  __int64 v54; // r15
  bool v55; // zf
  KSPIN_LOCK v56; // rcx
  _QWORD *v57; // rdx
  int v58; // eax
  __int128 v59; // xmm1
  __int128 v60; // xmm0
  __int128 v61; // xmm1
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  __int128 v64; // xmm0
  void *v65; // rdi
  int v67; // r15d
  int v68; // r9d
  __int64 v69; // rdi
  int ProfileIdFromInterface; // eax
  char v71; // r15
  unsigned __int64 v72; // rbx
  _DWORD *v73; // rdx
  UCHAR v75; // al
  char v76; // dl
  int v77; // ecx
  int v78; // r8d
  __int64 v79; // rax
  KSPIN_LOCK v80; // rdx
  PKSPIN_LOCK *v81; // rcx
  KSPIN_LOCK v82; // rdx
  PKSPIN_LOCK *v83; // rcx
  KSPIN_LOCK v84; // rax
  char v85; // si
  char v86; // di
  char v87; // bl
  LONG v88; // eax
  char StateEvent; // si
  char v90; // di
  char v91; // bl
  LONG v92; // eax
  char v93; // si
  char v94; // di
  char v95; // bl
  LONG v96; // eax
  _DWORD *v97; // rdx
  PVOID v98; // rcx
  char v99; // [rsp+40h] [rbp-C0h]
  char v101; // [rsp+44h] [rbp-BCh]
  KSPIN_LOCK v102; // [rsp+48h] [rbp-B8h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v104; // [rsp+54h] [rbp-ACh]
  _DWORD *v105; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD *v106; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v107; // [rsp+68h] [rbp-98h]
  PKSPIN_LOCK SpinLocka; // [rsp+70h] [rbp-90h] BYREF
  __int64 v109; // [rsp+78h] [rbp-88h]
  __int64 v110; // [rsp+80h] [rbp-80h]
  __int64 v111; // [rsp+88h] [rbp-78h]
  _BYTE *v112; // [rsp+90h] [rbp-70h]
  PKSPIN_LOCK *v113; // [rsp+98h] [rbp-68h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v115[79]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v116[128]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v117[128]; // [rsp+3B0h] [rbp+2B0h] BYREF

  v24 = a2;
  v111 = a14;
  v107 = a5;
  v109 = a21;
  v112 = a23;
  v110 = a4;
  v113 = a22;
  memset(v115, 0, sizeof(v115));
  v105 = 0;
  v106 = 0;
  v102 = 0;
  *a22 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) || KeReadStateEvent(LowNonPagedPoolEvent) )
  {
    if ( WfpSystemHasMemoryAvailable && (BYTE2(WPP_MAIN_CB.Dpc.DeferredContext) & 2) != 0 )
    {
      StateEvent = KeReadStateEvent(LowNonPagedPoolEvent);
      v90 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
      v91 = KeReadStateEvent(HighNonPagedPoolEvent);
      v92 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
      McTemplateK0qqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)LOW_MEMORY,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        v92,
        v91,
        v90,
        StateEvent);
      v24 = a2;
    }
    WfpSystemHasMemoryAvailable = 0;
  }
  else
  {
    if ( !WfpSystemHasMemoryAvailable && (BYTE2(WPP_MAIN_CB.Dpc.DeferredContext) & 4) != 0 )
    {
      v85 = KeReadStateEvent(LowNonPagedPoolEvent);
      v86 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
      v87 = KeReadStateEvent(HighNonPagedPoolEvent);
      v88 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
      McTemplateK0qqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)HIGH_MEMORY,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        v88,
        v87,
        v86,
        v85);
      v24 = a2;
    }
    WfpSystemHasMemoryAvailable = 1;
  }
  if ( !WfpSystemHasMemoryAvailable )
  {
    WfpLruCleanupDpc(0, 0);
    if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredContext) & 4) != 0 )
    {
      v93 = KeReadStateEvent(LowNonPagedPoolEvent);
      v94 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
      v95 = KeReadStateEvent(HighNonPagedPoolEvent);
      v96 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
      McTemplateK0qqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)DPC_LOW_MEMORY,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        v96,
        v95,
        v94,
        v93);
      v24 = a2;
    }
  }
  memset(v115, 0, sizeof(v115));
  v27 = 16;
  if ( v24 == 2 )
  {
    v28 = WfpAllocateFromPerProcessorLookasideList(V4AddressLookasideList, &v105);
    if ( v28 )
      goto LABEL_138;
    v28 = WfpAllocateFromPerProcessorLookasideList(V4AddressLookasideList, &v106);
    if ( v28 )
      goto LABEL_138;
    v29 = v107;
    v30 = v105;
    v31 = v106;
    *v105 = ***(_DWORD ***)(v107 + 16);
    *v31 = *a7;
    LODWORD(v115[61]) = 4;
  }
  else
  {
    if ( v24 != 23 )
    {
      v28 = WfpReportSysErrorAsNtStatus(v26, "WfpAleInsertRemoteEndpoint", 3221225485LL);
LABEL_136:
      if ( v105 )
        PplFreeToLookasideList(V6AddressLookasideList, v105);
      v97 = v106;
      if ( !v106 )
        goto LABEL_86;
      v98 = V6AddressLookasideList;
      goto LABEL_153;
    }
    v28 = WfpAllocateFromPerProcessorLookasideList(V6AddressLookasideList, &v105);
    if ( v28 )
      goto LABEL_136;
    v28 = WfpAllocateFromPerProcessorLookasideList(V6AddressLookasideList, &v106);
    if ( v28 )
      goto LABEL_136;
    v29 = v107;
    v30 = v105;
    v31 = v106;
    *(_OWORD *)v105 = *(_OWORD *)**(_QWORD **)(v107 + 16);
    *(_OWORD *)v31 = *(_OWORD *)a7;
    LODWORD(v115[61]) = 16;
  }
  v32 = LODWORD(v115[6]) | 2;
  v101 = 0;
  BYTE2(v115[77]) = 0;
  LODWORD(v115[6]) |= 2u;
  if ( a13 )
    LODWORD(v115[6]) = v32 | 0x100000;
  if ( a9 )
    _InterlockedOr((volatile signed __int32 *)&v115[6], 0x1000000u);
  if ( (SpinLock[6] & 0x10) != 0 )
    _InterlockedOr((volatile signed __int32 *)&v115[6], 0x10u);
  BYTE5(v115[61]) = a20;
  v33 = *(_QWORD *)(v29 + 8);
  v115[62] = SpinLock;
  WORD2(v115[7]) = a2;
  LODWORD(v115[5]) = a3;
  v115[60] = v30;
  v115[4] = v31;
  BYTE4(v115[61]) = a19;
  LOBYTE(v115[77]) = a13;
  v115[59] = *(_QWORD *)(v33 + 16);
  if ( a2 == 2 )
    v27 = 4;
  LODWORD(v115[61]) = v27;
  if ( a16 )
  {
    v58 = *(_DWORD *)(a16 + 48);
    v59 = *(_OWORD *)(a16 + 184);
    *(_OWORD *)&v115[21] = *(_OWORD *)(a16 + 168);
    v60 = *(_OWORD *)(a16 + 200);
    *(_OWORD *)&v115[23] = v59;
    v61 = *(_OWORD *)(a16 + 216);
    *(_OWORD *)&v115[25] = v60;
    v62 = *(_OWORD *)(a16 + 232);
    *(_OWORD *)&v115[27] = v61;
    v63 = *(_OWORD *)(a16 + 248);
    *(_OWORD *)&v115[29] = v62;
    v64 = *(_OWORD *)(a16 + 264);
    *(_OWORD *)&v115[31] = v63;
    v115[35] = *(_QWORD *)(a16 + 280);
    *(_OWORD *)&v115[33] = v64;
    if ( (v58 & 0x8000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v115[6], 0x8000u);
    if ( (*(_DWORD *)(a16 + 48) & 0x10000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v115[6], 0x10000u);
    if ( (*(_DWORD *)(a16 + 48) & 0x2000000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v115[6], 0x2000000u);
    if ( (*(_DWORD *)(a16 + 48) & 0x4000000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v115[6], 0x4000000u);
    if ( (*(_DWORD *)(a16 + 48) & 0x8000000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v115[6], 0x8000000u);
  }
  v34 = v115[37];
  if ( a18 )
    v34 = a18;
  LODWORD(v115[37]) = v34;
  if ( a2 != 2 )
  {
    if ( a3 == 58 && a2 == 23 )
      goto LABEL_22;
LABEL_24:
    HIWORD(v115[7]) = a6;
    LOWORD(v115[8]) = a8;
    goto LABEL_25;
  }
  if ( a3 != 1 )
    goto LABEL_24;
LABEL_22:
  v35 = *(_BYTE *)(a10 + 4);
  LODWORD(v115[8]) = *(_DWORD *)a10;
  BYTE1(v115[71]) = *(_BYTE *)(a10 + 5);
  LOBYTE(v115[71]) = v35;
  BYTE2(v115[71]) = v35;
LABEL_25:
  WfpAlepHashRemoteEndpoint(v115, &v102);
  v36 = WfpAleGetAndWriteLockPartition(v102, &LockState);
  v104 = v36;
  if ( CurrentLifeTimeThresholdIndex < 3
    && (unsigned int)(*(_DWORD *)(pRemoteEndpointTable + 4) * *(_DWORD *)(pRemoteEndpointTable + 92)) > *((_DWORD *)nFlows + CurrentLifeTimeThresholdIndex) )
  {
    ++CurrentLifeTimeThresholdIndex;
  }
  SpinLocka = (PKSPIN_LOCK)WfpAlepFindRemoteEndpoint(v115, &v102, v36);
  v37 = SpinLocka;
  if ( SpinLocka )
  {
    if ( (v115[6] & 0x8000) != 0 )
    {
      if ( gAleDebugEnabled )
      {
        v84 = SpinLocka[19];
        if ( v84 != 0xBADBADFABADBADFAuLL )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v84 + 16));
          _InterlockedIncrement((volatile signed __int32 *)(v37[19] + 48));
        }
      }
      if ( !(unsigned __int8)WfpAleIncrementWaitRefEx(v37 + 16, 2) )
        goto LABEL_29;
    }
    else if ( !(unsigned __int8)WfpAleReferenceEndpoint_0(SpinLocka, 4) )
    {
      goto LABEL_29;
    }
    v99 = 0;
    if ( (v37[6] & 0x8000) == 0 )
      WfpRefreshRemoteEndpointLruEntry(v37 + 63, 0, a17);
    if ( !v37[31] && v115[31] )
    {
      v37[31] = v115[31];
      *(_QWORD *)(a16 + 248) = 0;
    }
LABEL_80:
    v71 = v99;
    v38 = 0;
    v39 = v99;
    v40 = v99;
    *v113 = v37;
    goto LABEL_81;
  }
LABEL_29:
  v99 = 1;
  *(_QWORD *)(a16 + 248) = 0;
  *(_QWORD *)(a16 + 256) = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = WfpAllocateFromPerProcessorLookasideList(RemoteEndpointLookasideList, &SpinLocka);
  v37 = SpinLocka;
  v28 = v41;
  if ( !v41 )
  {
    memset(SpinLocka, 0, 0x278u);
    v42 = v37;
    v43 = v115;
    v44 = 4;
    do
    {
      v42 += 16;
      v45 = *(_OWORD *)v43;
      v43 += 16;
      *((_OWORD *)v42 - 8) = v45;
      *((_OWORD *)v42 - 7) = *((_OWORD *)v43 - 7);
      *((_OWORD *)v42 - 6) = *((_OWORD *)v43 - 6);
      *((_OWORD *)v42 - 5) = *((_OWORD *)v43 - 5);
      *((_OWORD *)v42 - 4) = *((_OWORD *)v43 - 4);
      *((_OWORD *)v42 - 3) = *((_OWORD *)v43 - 3);
      *((_OWORD *)v42 - 2) = *((_OWORD *)v43 - 2);
      *((_OWORD *)v42 - 1) = *((_OWORD *)v43 - 1);
      --v44;
    }
    while ( v44 );
    v46 = v104;
    *(_OWORD *)v42 = *(_OWORD *)v43;
    *((_OWORD *)v42 + 1) = *((_OWORD *)v43 + 1);
    *((_OWORD *)v42 + 2) = *((_OWORD *)v43 + 2);
    *((_OWORD *)v42 + 3) = *((_OWORD *)v43 + 3);
    *((_OWORD *)v42 + 4) = *((_OWORD *)v43 + 4);
    *((_OWORD *)v42 + 5) = *((_OWORD *)v43 + 5);
    *((_OWORD *)v42 + 6) = *((_OWORD *)v43 + 6);
    v42[14] = v43[14];
    v37[74] = v102;
    v102 = v46;
    v28 = WfpHashtableInsert((v46 << 7) + pRemoteEndpointTable + 72, v37 + 72);
    if ( !v28 )
    {
      v40 = 1;
      if ( !(unsigned __int8)WfpAleReferenceEndpoint_0(SpinLock, 2) )
      {
        v28 = WfpReportSysErrorAsNtStatus(v47, "WfpAleInsertRemoteEndpoint", 3221225473LL);
        v39 = 0;
        v71 = 1;
LABEL_81:
        if ( !v28 )
          goto LABEL_82;
        goto LABEL_131;
      }
      if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredContext) & 1) != 0
        && (memset(v117, 0, sizeof(v117)),
            memset(v116, 0, sizeof(v116)),
            ((void (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int16))INETADDR_SETSOCKADDR)(
              *((unsigned __int16 *)v37 + 30),
              (unsigned int)v117,
              v37[60],
              scopeid_unspecified.0,
              *((_WORD *)v37 + 31)),
            ((void (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int16))INETADDR_SETSOCKADDR)(
              *((unsigned __int16 *)v37 + 30),
              (unsigned int)v116,
              v37[4],
              scopeid_unspecified.0,
              *((_WORD *)v37 + 32)),
            (BYTE2(WPP_MAIN_CB.Dpc.DeferredContext) & 1) != 0) )
      {
        v75 = SOCKADDR_SIZE(*((_WORD *)v37 + 30));
        v48 = v102;
        McTemplateK0qbr0br0xx_EtwWriteTransfer(
          v77,
          (unsigned int)REMOTEENDPOINT_INSERT_V1,
          v78,
          v75,
          (__int64)v117,
          (__int64)v116,
          v102,
          v76);
      }
      else
      {
        v48 = v102;
      }
      v38 = 1;
      WfpAleInitializeEpochContext(
        a2,
        *((_DWORD *)SpinLock + 10),
        (*((_DWORD *)SpinLock + 12) >> 4) & 1,
        a11,
        a12,
        (__int64)(v37 + 45));
      _InterlockedOr((volatile signed __int32 *)v37 + 12, 0x1000u);
      WfpAleInitializeWaitRef(v37 + 16, v49, v50, v37);
      if ( *(_QWORD *)(a16 + 96) )
      {
        KfdAleRemoveFlowContextTable();
        v28 = KfdAleInitializeFlowTable(v37 + 9, *(_QWORD *)(a16 + 96));
        if ( !v28 )
        {
          v51 = 0;
          v37[14] = *(_QWORD *)(a16 + 112);
          *(_QWORD *)(a16 + 112) = 0;
          *(_QWORD *)(a16 + 96) = 0;
LABEL_39:
          WfpAleReferenceEndpointNoLock(v37, 1);
          KeInitializeSpinLock(v37);
          *((_DWORD *)v37 + 2) = 0;
          v28 = 0;
          v37[2] = 0;
          v37[3] = 0;
          if ( (SpinLock[25] & 4) != 0 )
            IPSecSetRequireSecurityOnEndpoint(v37);
          *((_DWORD *)v37 + 50) |= SpinLock[25] & 0x7000884;
          WfpAleCopySecureSocketInfoFromParent(SpinLock, v37);
          if ( v109 )
          {
            v28 = WfpAleProcessPostClassifySocketOptions(v37, v109);
            if ( v28 )
              goto LABEL_140;
          }
          if ( !a13 || a19 != 1 || (v53 = 1, (v37[6] & 0x4000) == 0) )
            v53 = 0;
          if ( (v37[6] & 0x8000) != 0 || v53 )
          {
            *((_DWORD *)v37 + 155) = a17;
          }
          else
          {
            v54 = 0;
            v102 = 0;
            if ( gAleDebugEnabled )
            {
              v79 = WfpPoolAllocNonPaged(27, 1281715265, &v102);
              v51 = v102;
              v54 = v79;
              if ( !v79 )
                WfpStringCchCopyA("WfpAleInsertRemoteEndpoint", 27, v102);
            }
            KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
            while ( *((_DWORD *)SpinLock + 2) )
              ;
            v55 = gAleDebugEnabled == 1;
            SpinLock[2] = (KSPIN_LOCK)KeGetCurrentThread();
            if ( v55 && !v54 )
              SpinLock[3] = v51;
            WfpAlepInsertEntryIntoLruList(v104, v37, a17);
            v56 = 16 * v48 + SpinLock[69];
            v57 = *(_QWORD **)(v56 + 8);
            if ( *v57 != v56 )
LABEL_54:
              __fastfail(3u);
            v101 = 1;
            v37[75] = v56;
            v37[76] = (KSPIN_LOCK)v57;
            *v57 = v37 + 75;
            *(_QWORD *)(v56 + 8) = v37 + 75;
            _InterlockedOr((volatile signed __int32 *)v37 + 12, 0x20000u);
            v55 = gAleDebugEnabled == 1;
            v65 = 0;
            SpinLock[2] = 0;
            if ( v55 )
            {
              v65 = (void *)SpinLock[3];
              SpinLock[3] = 0;
            }
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            if ( gAleDebugEnabled == 1 && v65 )
              ExFreePoolWithTag(v65, 0);
          }
          if ( v110 )
          {
            if ( a13 )
            {
              v68 = v111;
              v67 = 0;
              a15 = 0;
            }
            else
            {
              v67 = 1;
              v68 = 0;
            }
            v69 = *(_QWORD *)(v110 + 16);
            ProfileIdFromInterface = WfpGetProfileIdFromInterface(v110, v52, v107, v68, a15);
            AleEdgeIFsInit((_DWORD)v37 + 304, (_DWORD)v37 + 360, v69, v67, ProfileIdFromInterface);
          }
          WfpAleReferenceEndpointNoLock(v37, 4);
          if ( (v37[6] & 0x8000) != 0 )
            WfpAleReferenceEndpointNoLock(v37, 12);
          if ( v112 )
            *v112 = 1;
          goto LABEL_80;
        }
      }
      else
      {
        v28 = KfdAleInitializeFlowTable(v37 + 9, 0);
        if ( !v28 )
        {
          v51 = 0;
          goto LABEL_39;
        }
      }
    }
    v39 = 0;
  }
LABEL_131:
  v71 = v99;
  if ( v37 && v99 )
  {
    if ( v40 )
      RtlRemoveEntryHashTable(
        (PRTL_DYNAMIC_HASH_TABLE)(pRemoteEndpointTable + 72 + ((unsigned __int64)v104 << 7)),
        (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v37 + 24,
        0);
    if ( v101 )
    {
      v80 = v37[64];
      if ( *(PKSPIN_LOCK *)(v80 + 8) != v37 + 64 )
        goto LABEL_54;
      v81 = (PKSPIN_LOCK *)v37[65];
      if ( *v81 != v37 + 64 )
        goto LABEL_54;
      *v81 = (PKSPIN_LOCK)v80;
      *(_QWORD *)(v80 + 8) = v81;
      WfpAleDereferenceEndpoint(v37, 3);
    }
    if ( (v37[6] & 0x20000) != 0 )
    {
      AleAcquireEndpointLockEx(SpinLock, &LockHandle);
      v82 = v37[75];
      if ( *(PKSPIN_LOCK *)(v82 + 8) != v37 + 75 )
        goto LABEL_54;
      v83 = (PKSPIN_LOCK *)v37[76];
      if ( *v83 != v37 + 75 )
        goto LABEL_54;
      *v83 = (PKSPIN_LOCK)v82;
      *(_QWORD *)(v82 + 8) = v83;
      _InterlockedAnd((volatile signed __int32 *)v37 + 12, 0xFFFDFFFF);
      AleReleaseEndpointLock(SpinLock, &LockHandle);
    }
    if ( v39 )
    {
      WfpAleDisableWaitRef(v37 + 16);
      WfpAleDereferenceEndpoint(v37, 1);
    }
    if ( v38 )
      WfpAleDereferenceEndpoint(SpinLock, 2);
  }
LABEL_82:
  v72 = pRemoteEndpointTable + ((unsigned __int64)v104 << 7);
  if ( gWfpPerProContext )
  {
    v73 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v73 == 4 )
      *v73 = 0;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v72 + 64), &LockState);
  if ( !v71 )
  {
    if ( a2 != 2 )
      goto LABEL_136;
LABEL_138:
    if ( v105 )
      PplFreeToLookasideList(V4AddressLookasideList, v105);
    v97 = v106;
    if ( !v106 )
      goto LABEL_86;
    v98 = V4AddressLookasideList;
LABEL_153:
    PplFreeToLookasideList(v98, v97);
  }
LABEL_86:
  if ( v28 )
LABEL_140:
    WfpReportError(v28, "WfpAleInsertRemoteEndpoint");
  return v28;
}

```

## disassembly

```asm
0x140061630  push    rbp
0x140061632  push    rbx
0x140061633  push    rsi
0x140061634  push    rdi
0x140061635  push    r12
0x140061637  push    r13
0x140061639  push    r14
0x14006163b  push    r15
0x14006163d  lea     rbp, [rsp-348h]
0x140061645  sub     rsp, 448h
0x14006164c  mov     rax, cs:__security_cookie
0x140061653  xor     rax, rsp
0x140061656  mov     [rbp+380h+var_50], rax
0x14006165d  mov     rax, [rbp+380h+arg_68]
0x140061664  mov     r12d, r8d
0x140061667  mov     rbx, [rbp+380h+arg_A8]
0x14006166e  movzx   edi, dx
0x140061671  mov     r13, [rbp+380h+arg_48]
0x140061678  mov     r14, rcx
0x14006167b  mov     r15, [rbp+380h+arg_78]
0x140061682  lea     rcx, [rbp+380h+var_3C8]; void *
0x140061686  mov     [rbp+380h+var_3F8], rax
0x14006168a  mov     r8d, 278h; Size
0x140061690  mov     rax, [rbp+380h+arg_20]
0x140061697  mov     [rsp+480h+var_418], rax
0x14006169c  mov     rax, [rbp+380h+arg_A0]
0x1400616a3  mov     [rsp+480h+var_408], rax
0x1400616a8  mov     rax, [rbp+380h+arg_B0]
0x1400616af  mov     [rsp+480h+var_43E], dx
0x1400616b4  xor     edx, edx; Val
0x1400616b6  mov     [rbp+380h+var_3F0], rax
0x1400616ba  mov     [rbp+380h+var_400], r9
0x1400616be  mov     [rbp+380h+var_3E8], rbx
0x1400616c2  call    memset
0x1400616c7  xor     ecx, ecx
0x1400616c9  xor     eax, eax
0x1400616cb  mov     [rsp+480h+var_428], rcx
0x1400616d0  xorps   xmm0, xmm0
0x1400616d3  mov     [rsp+480h+var_420], rcx
0x1400616d8  mov     [rsp+480h+var_438], rcx
0x1400616dd  mov     [rbx], rcx
0x1400616e0  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+18h; Event
0x1400616e7  mov     word ptr [rsp+480h+LockState.OldIrql], ax
0x1400616ec  mov     [rsp+480h+LockState.Flags], al
0x1400616f0  movups  xmmword ptr [rbp+380h+LockHandle.LockQueue.Next], xmm0
0x1400616f4  mov     qword ptr [rbp+380h+LockHandle.OldIrql], rax
0x1400616f8  call    cs:__imp_KeReadStateEvent
0x1400616ff  nop     dword ptr [rax+rax+00h]
0x140061704  test    eax, eax
0x140061706  jz      loc_140061D30
0x14006170c  movzx   eax, cs:WfpSystemHasMemoryAvailable
0x140061713  test    al, al
0x140061715  jnz     loc_1401C8BF0
0x14006171b  mov     cs:WfpSystemHasMemoryAvailable, 0
0x140061722  movzx   eax, cs:WfpSystemHasMemoryAvailable
0x140061729  test    al, al
0x14006172b  jz      loc_140062028
0x140061731  xor     edx, edx; Val
0x140061733  lea     rcx, [rbp+380h+var_3C8]; void *
0x140061737  mov     r8d, 278h; Size
0x14006173d  call    memset
0x140061742  mov     ebx, 10h
0x140061747  cmp     di, 2
0x14006174b  jnz     loc_140061F40
0x140061751  mov     rcx, cs:V4AddressLookasideList
0x140061758  lea     rdx, [rsp+480h+var_428]
0x14006175d  call    WfpAllocateFromPerProcessorLookasideList
0x140061762  mov     rsi, rax
0x140061765  test    rax, rax
0x140061768  jnz     loc_1400623BC
0x14006176e  mov     rcx, cs:V4AddressLookasideList
0x140061775  lea     rdx, [rsp+480h+var_420]
0x14006177a  call    WfpAllocateFromPerProcessorLookasideList
0x14006177f  mov     rsi, rax
0x140061782  test    rax, rax
0x140061785  jnz     loc_1400623BC
0x14006178b  mov     r10, [rsp+480h+var_418]
0x140061790  mov     r11d, 4
0x140061796  mov     r8, [rsp+480h+var_428]
0x14006179b  mov     r9, [rsp+480h+var_420]
0x1400617a0  mov     rax, [r10+10h]
0x1400617a4  mov     rcx, [rax]
0x1400617a7  mov     eax, [rcx]
0x1400617a9  mov     [r8], eax
0x1400617ac  mov     rax, [rbp+380h+arg_30]
0x1400617b3  mov     ecx, [rax]
0x1400617b5  mov     [r9], ecx
0x1400617b8  mov     [rbp+380h+var_1E0], r11d
0x1400617bf  mov     eax, [rbp+380h+var_398]
0x1400617c2  movzx   ecx, [rbp+380h+arg_60]
0x1400617c9  or      eax, 2
0x1400617cc  mov     [rsp+480h+var_43C], 0
0x1400617d1  mov     [rbp+380h+var_15E], 0
0x1400617d8  mov     [rbp+380h+var_398], eax
0x1400617db  test    cl, cl
0x1400617dd  jz      short loc_1400617E6
0x1400617df  bts     eax, 14h
0x1400617e3  mov     [rbp+380h+var_398], eax
0x1400617e6  cmp     [rbp+380h+arg_40], 0
0x1400617ed  jz      short loc_1400617F7
0x1400617ef  lock or [rbp+380h+var_398], 1000000h
0x1400617f7  mov     eax, [r14+30h]
0x1400617fb  test    bl, al
0x1400617fd  jnz     loc_140061FC0
0x140061803  movzx   eax, [rbp+380h+arg_98]
0x14006180a  movzx   edx, [rsp+480h+var_43E]
0x14006180f  movzx   edi, [rbp+380h+arg_90]
0x140061816  mov     [rbp+380h+var_1DB], al
0x14006181c  mov     rax, [r10+8]
0x140061820  mov     [rbp+380h+var_1D8], r14
0x140061827  mov     [rbp+380h+var_38C], dx
0x14006182b  mov     [rbp+380h+var_3A0], r12d
0x14006182f  mov     [rbp+380h+var_1E8], r8
0x140061836  mov     [rbp+380h+var_3A8], r9
0x14006183a  mov     [rbp+380h+var_1DC], dil
0x140061841  mov     [rbp+380h+var_160], cl
0x140061847  mov     rcx, [rax+10h]
0x14006184b  mov     eax, 2
0x140061850  cmp     ax, dx
0x140061853  mov     [rbp+380h+var_1F0], rcx
0x14006185a  cmovz   ebx, r11d
0x14006185e  mov     [rbp+380h+var_1E0], ebx
0x140061864  test    r15, r15
0x140061867  jnz     loc_140061C69
0x14006186d  mov     eax, [rbp+380h+arg_88]
0x140061873  test    eax, eax
0x140061875  mov     ecx, [rbp+380h+var_2A0]
0x14006187b  cmovnz  ecx, eax
0x14006187e  mov     [rbp+380h+var_2A0], ecx
0x140061884  cmp     dx, 2
0x140061888  jnz     short loc_1400618B5
0x14006188a  cmp     r12d, 1
0x14006188e  jnz     short loc_1400618BF
0x140061890  mov     eax, [r13+0]
0x140061894  movzx   ecx, byte ptr [r13+4]
0x140061899  mov     [rbp+380h+var_388], eax
0x14006189c  movzx   eax, byte ptr [r13+5]
0x1400618a1  mov     [rbp+380h+var_18F], al
0x1400618a7  mov     [rbp+380h+var_190], cl
0x1400618ad  mov     [rbp+380h+var_18E], cl
0x1400618b3  jmp     short loc_1400618D5
0x1400618b5  cmp     r12d, 3Ah ; ':'
0x1400618b9  jz      loc_140062164
0x1400618bf  movzx   eax, [rbp+380h+arg_28]
0x1400618c6  mov     [rbp+380h+var_38A], ax
0x1400618ca  movzx   eax, [rbp+380h+arg_38]
0x1400618d1  mov     word ptr [rbp+380h+var_388], ax
0x1400618d5  lea     rdx, [rsp+480h+var_438]
0x1400618da  lea     rcx, [rbp+380h+var_3C8]
0x1400618de  call    WfpAlepHashRemoteEndpoint
0x1400618e3  mov     rcx, [rsp+480h+var_438]
0x1400618e8  lea     rdx, [rsp+480h+LockState]
0x1400618ed  call    WfpAleGetAndWriteLockPartition
0x1400618f2  movsxd  r8, cs:CurrentLifeTimeThresholdIndex
0x1400618f9  mov     [rsp+480h+var_42C], eax
0x1400618fd  cmp     r8d, 3
0x140061901  jge     short loc_140061922
0x140061903  mov     rcx, cs:pRemoteEndpointTable
0x14006190a  lea     r9, nFlows
0x140061911  mov     edx, [rcx+5Ch]
0x140061914  imul    edx, [rcx+4]
0x140061918  cmp     edx, [r9+r8*4]
0x14006191c  ja      loc_140062323
0x140061922  mov     r8d, eax
0x140061925  lea     rdx, [rsp+480h+var_438]
0x14006192a  lea     rcx, [rbp+380h+var_3C8]
0x14006192e  call    WfpAlepFindRemoteEndpoint
0x140061933  mov     [rsp+480h+SpinLock], rax
0x140061938  mov     rbx, rax
0x14006193b  test    rax, rax
0x14006193e  jnz     loc_140062173
0x140061944  xor     eax, eax
0x140061946  mov     [rsp+480h+var_440], 1
0x14006194b  mov     [r15+0F8h], rax
0x140061952  lea     rdx, [rsp+480h+SpinLock]
0x140061957  mov     [r15+100h], rax
0x14006195e  xor     r12b, r12b
0x140061961  mov     rcx, cs:RemoteEndpointLookasideList
0x140061968  xor     r13b, r13b
0x14006196b  xor     dil, dil
0x14006196e  call    WfpAllocateFromPerProcessorLookasideList
0x140061973  mov     rbx, [rsp+480h+SpinLock]
0x140061978  mov     rsi, rax
0x14006197b  test    rax, rax
0x14006197e  jnz     loc_140062342
0x140061984  xor     edx, edx; Val
0x140061986  mov     r8d, 278h; Size
0x14006198c  mov     rcx, rbx; void *
0x14006198f  call    memset
0x140061994  mov     rcx, rbx
0x140061997  lea     rax, [rbp+380h+var_3C8]
0x14006199b  mov     edx, 4
0x1400619a0  lea     rcx, [rcx+80h]
0x1400619a7  movups  xmm0, xmmword ptr [rax]
0x1400619aa  lea     rax, [rax+80h]
0x1400619b1  movups  xmmword ptr [rcx-80h], xmm0
0x1400619b5  movups  xmm1, xmmword ptr [rax-70h]
0x1400619b9  movups  xmmword ptr [rcx-70h], xmm1
0x1400619bd  movups  xmm0, xmmword ptr [rax-60h]
0x1400619c1  movups  xmmword ptr [rcx-60h], xmm0
0x1400619c5  movups  xmm1, xmmword ptr [rax-50h]
0x1400619c9  movups  xmmword ptr [rcx-50h], xmm1
0x1400619cd  movups  xmm0, xmmword ptr [rax-40h]
0x1400619d1  movups  xmmword ptr [rcx-40h], xmm0
0x1400619d5  movups  xmm1, xmmword ptr [rax-30h]
0x1400619d9  movups  xmmword ptr [rcx-30h], xmm1
0x1400619dd  movups  xmm0, xmmword ptr [rax-20h]
0x1400619e1  movups  xmmword ptr [rcx-20h], xmm0
0x1400619e5  movups  xmm1, xmmword ptr [rax-10h]
0x1400619e9  movups  xmmword ptr [rcx-10h], xmm1
0x1400619ed  sub     rdx, 1
0x1400619f1  jnz     short loc_1400619A0
0x1400619f3  movups  xmm0, xmmword ptr [rax]
0x1400619f6  mov     r13d, [rsp+480h+var_42C]
0x1400619fb  lea     rdx, [rbx+240h]
0x140061a02  movups  xmmword ptr [rcx], xmm0
0x140061a05  movups  xmm1, xmmword ptr [rax+10h]
0x140061a09  movups  xmmword ptr [rcx+10h], xmm1
0x140061a0d  movups  xmm0, xmmword ptr [rax+20h]
0x140061a11  movups  xmmword ptr [rcx+20h], xmm0
0x140061a15  movups  xmm1, xmmword ptr [rax+30h]
0x140061a19  movups  xmmword ptr [rcx+30h], xmm1
0x140061a1d  movups  xmm0, xmmword ptr [rax+40h]
0x140061a21  movups  xmmword ptr [rcx+40h], xmm0
0x140061a25  movups  xmm1, xmmword ptr [rax+50h]
0x140061a29  movups  xmmword ptr [rcx+50h], xmm1
0x140061a2d  movups  xmm0, xmmword ptr [rax+60h]
0x140061a31  movups  xmmword ptr [rcx+60h], xmm0
0x140061a35  mov     rax, [rax+70h]
0x140061a39  mov     [rcx+70h], rax
0x140061a3d  mov     rax, [rsp+480h+var_438]
0x140061a42  mov     [rbx+250h], rax
0x140061a49  mov     rcx, cs:pRemoteEndpointTable
0x140061a50  add     rcx, 48h ; 'H'
0x140061a54  mov     [rsp+480h+var_438], r13
0x140061a59  shl     r13, 7
0x140061a5d  add     rcx, r13
0x140061a60  call    WfpHashtableInsert
0x140061a65  mov     rsi, rax
0x140061a68  test    rax, rax
0x140061a6b  jnz     loc_14006233F
0x140061a71  mov     edx, 2
0x140061a76  mov     rcx, r14
0x140061a79  mov     dil, 1
0x140061a7c  call    WfpAleReferenceEndpoint_0
0x140061a81  test    al, al
0x140061a83  jz      loc_140061FE8
0x140061a89  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+2, dil
0x140061a90  jnz     loc_140062043
0x140061a96  mov     r13, [rsp+480h+var_438]
0x140061a9b  mov     r8d, [r14+30h]
0x140061a9f  lea     rax, [rbx+168h]
0x140061aa6  movzx   r9d, [rbp+380h+arg_50]
0x140061aae  movzx   r12d, dil
0x140061ab2  mov     edx, [r14+28h]
0x140061ab6  movzx   ecx, [rsp+480h+var_43E]
0x140061abb  mov     [rsp+480h+var_458], rax
0x140061ac0  mov     eax, [rbp+380h+arg_58]
0x140061ac6  shr     r8d, 4
0x140061aca  and     r8d, 1
0x140061ace  mov     dword ptr [rsp+480h+var_460], eax
0x140061ad2  call    WfpAleInitializeEpochContext
0x140061ad7  lock or dword ptr [rbx+30h], 1000h
0x140061adf  lea     rcx, [rbx+80h]
0x140061ae6  mov     r9, rbx
0x140061ae9  call    WfpAleInitializeWaitRef
0x140061aee  mov     rcx, [r15+60h]
0x140061af2  test    rcx, rcx
0x140061af5  jz      loc_140061EFF
0x140061afb  call    cs:__imp_KfdAleRemoveFlowContextTable
0x140061b02  nop     dword ptr [rax+rax+00h]
0x140061b07  mov     rdx, [r15+60h]
0x140061b0b  lea     rcx, [rbx+48h]
0x140061b0f  call    cs:__imp_KfdAleInitializeFlowTable
0x140061b16  nop     dword ptr [rax+rax+00h]
0x140061b1b  mov     rsi, rax
0x140061b1e  test    rax, rax
0x140061b21  jnz     loc_14006233F
0x140061b27  mov     rax, [r15+70h]
0x140061b2b  xor     edi, edi
0x140061b2d  mov     [rbx+70h], rax
0x140061b31  mov     [r15+70h], rdi
0x140061b35  mov     [r15+60h], rdi
0x140061b39  mov     edx, 1
0x140061b3e  mov     rcx, rbx
0x140061b41  call    WfpAleReferenceEndpointNoLock
0x140061b46  mov     rcx, rbx; SpinLock
0x140061b49  call    cs:__imp_KeInitializeSpinLock
0x140061b50  nop     dword ptr [rax+rax+00h]
0x140061b55  mov     [rbx+8], edi
0x140061b58  mov     rsi, rdi
0x140061b5b  mov     [rbx+10h], rdi
0x140061b5f  mov     [rbx+18h], rdi
0x140061b63  mov     eax, [r14+0C8h]
0x140061b6a  test    al, 4
0x140061b6c  jnz     loc_140062332
0x140061b72  mov     eax, [r14+0C8h]
0x140061b79  mov     rdx, rbx
0x140061b7c  and     eax, 7000884h
0x140061b81  mov     rcx, r14
  ... truncated ...
```
