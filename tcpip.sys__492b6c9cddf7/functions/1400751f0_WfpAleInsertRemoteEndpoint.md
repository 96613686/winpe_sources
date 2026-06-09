# WfpAleInsertRemoteEndpoint

- ea: `0x1400751f0`
- end: `0x140075fb0`
- name: `WfpAleInsertRemoteEndpoint`
- size: `3520`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int64, __int16, __int64, __int16, char, __int64, __int16, int, char, __int64, __int64, __int64, int, int, char, char, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `34`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400974c0`
- `0x140139280`
- `0x14013a990`

## callees

- `0x14001a390`
- `0x14001af00`
- `0x14002f200`
- `0x14002f230`
- `0x1400505d0`
- `0x140050740`
- `0x1400525d0`
- `0x140053910`
- `0x140053f20`
- `0x140054f00`
- `0x140055780`
- `0x140073a00`
- `0x140074df0`
- `0x1400751f0`
- `0x140075fb8`
- `0x140076010`
- `0x1400760c0`
- `0x140076f40`
- `0x1400772e0`
- `0x140077370`
- `0x1400774f0`
- `0x140077574`
- `0x1400776d4`
- `0x140077738`
- `0x140077820`
- `0x140077920`
- `0x1400bcca0`
- `0x1400be890`
- `0x1400d2620`
- `0x14010cde8`
- `0x14014e224`
- `0x140196424`
- `0x1401bf390`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140075f43`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140075f43`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140075a49`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140075a49`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400757c6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400757c6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075973`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075973`
- `ntoskrnl!KeReadStateEvent` at `0x1400752b8`
- `ntoskrnl!KeReadStateEvent` at `0x1400758f7`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6166`
- `ntoskrnl!KeReadStateEvent` at `0x1401c617b`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6190`
- `ntoskrnl!KeReadStateEvent` at `0x1401c61a5`
- `ntoskrnl!KeReadStateEvent` at `0x1401c61f8`
- `ntoskrnl!KeReadStateEvent` at `0x1401c620d`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6222`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6237`
- `ntoskrnl!KeReadStateEvent` at `0x1401c627d`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6292`
- `ntoskrnl!KeReadStateEvent` at `0x1401c62a7`
- `ntoskrnl!KeReadStateEvent` at `0x1401c62bc`
- `ntoskrnl!KeReadStateEvent` at `0x1400752b8`
- `ntoskrnl!KeReadStateEvent` at `0x1400758f7`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6166`
- `ntoskrnl!KeReadStateEvent` at `0x1401c617b`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6190`
- `ntoskrnl!KeReadStateEvent` at `0x1401c61a5`
- `ntoskrnl!KeReadStateEvent` at `0x1401c61f8`
- `ntoskrnl!KeReadStateEvent` at `0x1401c620d`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6222`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6237`
- `ntoskrnl!KeReadStateEvent` at `0x1401c627d`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6292`
- `ntoskrnl!KeReadStateEvent` at `0x1401c62a7`
- `ntoskrnl!KeReadStateEvent` at `0x1401c62bc`
- `ntoskrnl!KeInitializeSpinLock` at `0x140075709`
- `ntoskrnl!KeInitializeSpinLock` at `0x140075709`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075bd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075bd7`
- `NETIO!KfdAleInitializeFlowTable` at `0x1400756cf`
- `NETIO!KfdAleInitializeFlowTable` at `0x140075ac5`
- `NETIO!KfdAleInitializeFlowTable` at `0x1400756cf`
- `NETIO!KfdAleInitializeFlowTable` at `0x140075ac5`
- `NETIO!KfdAleRemoveFlowContextTable` at `0x1400756bb`
- `NETIO!KfdAleRemoveFlowContextTable` at `0x1400756bb`
- `NDIS!NdisReleaseRWLock` at `0x140075a7a`
- `NDIS!NdisReleaseRWLock` at `0x140075a7a`

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
  PVOID v97; // rcx
  char v98; // [rsp+40h] [rbp-C0h]
  char v100; // [rsp+44h] [rbp-BCh]
  KSPIN_LOCK v101; // [rsp+48h] [rbp-B8h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v103; // [rsp+54h] [rbp-ACh]
  _DWORD *v104; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD *v105; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v106; // [rsp+68h] [rbp-98h]
  PKSPIN_LOCK SpinLocka; // [rsp+70h] [rbp-90h] BYREF
  __int64 v108; // [rsp+78h] [rbp-88h]
  __int64 v109; // [rsp+80h] [rbp-80h]
  __int64 v110; // [rsp+88h] [rbp-78h]
  _BYTE *v111; // [rsp+90h] [rbp-70h]
  PKSPIN_LOCK *v112; // [rsp+98h] [rbp-68h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v114[79]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v115[128]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v116[128]; // [rsp+3B0h] [rbp+2B0h] BYREF

  v24 = a2;
  v110 = a14;
  v106 = a5;
  v108 = a21;
  v111 = a23;
  v109 = a4;
  v112 = a22;
  memset(v114, 0, sizeof(v114));
  v104 = 0;
  v105 = 0;
  v101 = 0;
  *a22 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceContext) || KeReadStateEvent(LowNonPagedPoolEvent) )
  {
    if ( WfpSystemHasMemoryAvailable && (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 2) != 0 )
    {
      StateEvent = KeReadStateEvent(LowNonPagedPoolEvent);
      v90 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceContext);
      v91 = KeReadStateEvent(HighNonPagedPoolEvent);
      v92 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredContext);
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
    if ( !WfpSystemHasMemoryAvailable && (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 4) != 0 )
    {
      v85 = KeReadStateEvent(LowNonPagedPoolEvent);
      v86 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceContext);
      v87 = KeReadStateEvent(HighNonPagedPoolEvent);
      v88 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredContext);
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
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 4) != 0 )
    {
      v93 = KeReadStateEvent(LowNonPagedPoolEvent);
      v94 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceContext);
      v95 = KeReadStateEvent(HighNonPagedPoolEvent);
      v96 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredContext);
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
  memset(v114, 0, sizeof(v114));
  v27 = 16;
  if ( v24 == 2 )
  {
    v28 = WfpAllocateFromPerProcessorLookasideList(V4AddressLookasideList, &v104);
    if ( v28 )
      goto LABEL_138;
    v28 = WfpAllocateFromPerProcessorLookasideList(V4AddressLookasideList, &v105);
    if ( v28 )
      goto LABEL_138;
    v29 = v106;
    v30 = v104;
    v31 = v105;
    *v104 = ***(_DWORD ***)(v106 + 16);
    *v31 = *a7;
    LODWORD(v114[61]) = 4;
  }
  else
  {
    if ( v24 != 23 )
    {
      v28 = WfpReportSysErrorAsNtStatus(v26, "WfpAleInsertRemoteEndpoint", 3221225485LL);
LABEL_136:
      if ( v104 )
        PplFreeToLookasideList(V6AddressLookasideList);
      if ( !v105 )
        goto LABEL_86;
      v97 = V6AddressLookasideList;
      goto LABEL_153;
    }
    v28 = WfpAllocateFromPerProcessorLookasideList(V6AddressLookasideList, &v104);
    if ( v28 )
      goto LABEL_136;
    v28 = WfpAllocateFromPerProcessorLookasideList(V6AddressLookasideList, &v105);
    if ( v28 )
      goto LABEL_136;
    v29 = v106;
    v30 = v104;
    v31 = v105;
    *(_OWORD *)v104 = *(_OWORD *)**(_QWORD **)(v106 + 16);
    *(_OWORD *)v31 = *(_OWORD *)a7;
    LODWORD(v114[61]) = 16;
  }
  v32 = LODWORD(v114[6]) | 2;
  v100 = 0;
  BYTE2(v114[77]) = 0;
  LODWORD(v114[6]) |= 2u;
  if ( a13 )
    LODWORD(v114[6]) = v32 | 0x100000;
  if ( a9 )
    _InterlockedOr((volatile signed __int32 *)&v114[6], 0x1000000u);
  if ( (SpinLock[6] & 0x10) != 0 )
    _InterlockedOr((volatile signed __int32 *)&v114[6], 0x10u);
  BYTE5(v114[61]) = a20;
  v33 = *(_QWORD *)(v29 + 8);
  v114[62] = SpinLock;
  WORD2(v114[7]) = a2;
  LODWORD(v114[5]) = a3;
  v114[60] = v30;
  v114[4] = v31;
  BYTE4(v114[61]) = a19;
  LOBYTE(v114[77]) = a13;
  v114[59] = *(_QWORD *)(v33 + 16);
  if ( a2 == 2 )
    v27 = 4;
  LODWORD(v114[61]) = v27;
  if ( a16 )
  {
    v58 = *(_DWORD *)(a16 + 48);
    v59 = *(_OWORD *)(a16 + 184);
    *(_OWORD *)&v114[21] = *(_OWORD *)(a16 + 168);
    v60 = *(_OWORD *)(a16 + 200);
    *(_OWORD *)&v114[23] = v59;
    v61 = *(_OWORD *)(a16 + 216);
    *(_OWORD *)&v114[25] = v60;
    v62 = *(_OWORD *)(a16 + 232);
    *(_OWORD *)&v114[27] = v61;
    v63 = *(_OWORD *)(a16 + 248);
    *(_OWORD *)&v114[29] = v62;
    v64 = *(_OWORD *)(a16 + 264);
    *(_OWORD *)&v114[31] = v63;
    v114[35] = *(_QWORD *)(a16 + 280);
    *(_OWORD *)&v114[33] = v64;
    if ( (v58 & 0x8000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v114[6], 0x8000u);
    if ( (*(_DWORD *)(a16 + 48) & 0x10000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v114[6], 0x10000u);
    if ( (*(_DWORD *)(a16 + 48) & 0x2000000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v114[6], 0x2000000u);
    if ( (*(_DWORD *)(a16 + 48) & 0x4000000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v114[6], 0x4000000u);
    if ( (*(_DWORD *)(a16 + 48) & 0x8000000) != 0 )
      _InterlockedOr((volatile signed __int32 *)&v114[6], 0x8000000u);
  }
  v34 = v114[37];
  if ( a18 )
    v34 = a18;
  LODWORD(v114[37]) = v34;
  if ( a2 != 2 )
  {
    if ( a3 == 58 && a2 == 23 )
      goto LABEL_22;
LABEL_24:
    HIWORD(v114[7]) = a6;
    LOWORD(v114[8]) = a8;
    goto LABEL_25;
  }
  if ( a3 != 1 )
    goto LABEL_24;
LABEL_22:
  v35 = *(_BYTE *)(a10 + 4);
  LODWORD(v114[8]) = *(_DWORD *)a10;
  BYTE1(v114[71]) = *(_BYTE *)(a10 + 5);
  LOBYTE(v114[71]) = v35;
  BYTE2(v114[71]) = v35;
LABEL_25:
  WfpAlepHashRemoteEndpoint(v114, &v101);
  v36 = WfpAleGetAndWriteLockPartition(v101, &LockState);
  v103 = v36;
  if ( CurrentLifeTimeThresholdIndex < 3
    && (unsigned int)(*(_DWORD *)(pRemoteEndpointTable + 4) * *(_DWORD *)(pRemoteEndpointTable + 92)) > *((_DWORD *)nFlows + CurrentLifeTimeThresholdIndex) )
  {
    ++CurrentLifeTimeThresholdIndex;
  }
  SpinLocka = (PKSPIN_LOCK)WfpAlepFindRemoteEndpoint(v114, &v101, v36);
  v37 = SpinLocka;
  if ( SpinLocka )
  {
    if ( (v114[6] & 0x8000) != 0 )
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
    v98 = 0;
    if ( (v37[6] & 0x8000) == 0 )
      WfpRefreshRemoteEndpointLruEntry(v37 + 63, 0, a17);
    if ( !v37[31] && v114[31] )
    {
      v37[31] = v114[31];
      *(_QWORD *)(a16 + 248) = 0;
    }
LABEL_80:
    v71 = v98;
    v38 = 0;
    v39 = v98;
    v40 = v98;
    *v112 = v37;
    goto LABEL_81;
  }
LABEL_29:
  v98 = 1;
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
    v43 = v114;
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
    v46 = v103;
    *(_OWORD *)v42 = *(_OWORD *)v43;
    *((_OWORD *)v42 + 1) = *((_OWORD *)v43 + 1);
    *((_OWORD *)v42 + 2) = *((_OWORD *)v43 + 2);
    *((_OWORD *)v42 + 3) = *((_OWORD *)v43 + 3);
    *((_OWORD *)v42 + 4) = *((_OWORD *)v43 + 4);
    *((_OWORD *)v42 + 5) = *((_OWORD *)v43 + 5);
    *((_OWORD *)v42 + 6) = *((_OWORD *)v43 + 6);
    v42[14] = v43[14];
    v37[74] = v101;
    v101 = v46;
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
      if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 1) != 0
        && (memset(v116, 0, sizeof(v116)),
            memset(v115, 0, sizeof(v115)),
            ((void (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int16))INETADDR_SETSOCKADDR)(
              *((unsigned __int16 *)v37 + 30),
              (unsigned int)v116,
              v37[60],
              scopeid_unspecified.0,
              *((_WORD *)v37 + 31)),
            ((void (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int16))INETADDR_SETSOCKADDR)(
              *((unsigned __int16 *)v37 + 30),
              (unsigned int)v115,
              v37[4],
              scopeid_unspecified.0,
              *((_WORD *)v37 + 32)),
            (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 1) != 0) )
      {
        v75 = SOCKADDR_SIZE(*((_WORD *)v37 + 30));
        v48 = v101;
        McTemplateK0qbr0br0xx_EtwWriteTransfer(
          v77,
          (unsigned int)REMOTEENDPOINT_INSERT_V1,
          v78,
          v75,
          (__int64)v116,
          (__int64)v115,
          v101,
          v76);
      }
      else
      {
        v48 = v101;
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
          if ( v108 )
          {
            v28 = WfpAleProcessPostClassifySocketOptions(v37, v108);
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
            v101 = 0;
            if ( gAleDebugEnabled )
            {
              v79 = WfpPoolAllocNonPaged(27, 1281715265, &v101);
              v51 = v101;
              v54 = v79;
              if ( !v79 )
                WfpStringCchCopyA("WfpAleInsertRemoteEndpoint", 27, v101);
            }
            KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
            while ( *((_DWORD *)SpinLock + 2) )
              ;
            v55 = gAleDebugEnabled == 1;
            SpinLock[2] = (KSPIN_LOCK)KeGetCurrentThread();
            if ( v55 && !v54 )
              SpinLock[3] = v51;
            WfpAlepInsertEntryIntoLruList(v103, v37, a17);
            v56 = 16 * v48 + SpinLock[69];
            v57 = *(_QWORD **)(v56 + 8);
            if ( *v57 != v56 )
LABEL_54:
              __fastfail(3u);
            v100 = 1;
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
          if ( v109 )
          {
            if ( a13 )
            {
              v68 = v110;
              v67 = 0;
              a15 = 0;
            }
            else
            {
              v67 = 1;
              v68 = 0;
            }
            v69 = *(_QWORD *)(v109 + 16);
            ProfileIdFromInterface = WfpGetProfileIdFromInterface(v109, v52, v106, v68, a15);
            AleEdgeIFsInit((_DWORD)v37 + 304, (_DWORD)v37 + 360, v69, v67, ProfileIdFromInterface);
          }
          WfpAleReferenceEndpointNoLock(v37, 4);
          if ( (v37[6] & 0x8000) != 0 )
            WfpAleReferenceEndpointNoLock(v37, 12);
          if ( v111 )
            *v111 = 1;
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
  v71 = v98;
  if ( v37 && v98 )
  {
    if ( v40 )
      RtlRemoveEntryHashTable(
        (PRTL_DYNAMIC_HASH_TABLE)(pRemoteEndpointTable + 72 + ((unsigned __int64)v103 << 7)),
        (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v37 + 24,
        0);
    if ( v100 )
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
  v72 = pRemoteEndpointTable + ((unsigned __int64)v103 << 7);
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
    if ( v104 )
      PplFreeToLookasideList(V4AddressLookasideList);
    if ( !v105 )
      goto LABEL_86;
    v97 = V4AddressLookasideList;
LABEL_153:
    PplFreeToLookasideList(v97);
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
0x1400751f0  push    rbp
0x1400751f2  push    rbx
0x1400751f3  push    rsi
0x1400751f4  push    rdi
0x1400751f5  push    r12
0x1400751f7  push    r13
0x1400751f9  push    r14
0x1400751fb  push    r15
0x1400751fd  lea     rbp, [rsp-348h]
0x140075205  sub     rsp, 448h
0x14007520c  mov     rax, cs:__security_cookie
0x140075213  xor     rax, rsp
0x140075216  mov     [rbp+380h+var_50], rax
0x14007521d  mov     rax, [rbp+380h+arg_68]
0x140075224  mov     r12d, r8d
0x140075227  mov     rbx, [rbp+380h+arg_A8]
0x14007522e  movzx   edi, dx
0x140075231  mov     r13, [rbp+380h+arg_48]
0x140075238  mov     r14, rcx
0x14007523b  mov     r15, [rbp+380h+arg_78]
0x140075242  lea     rcx, [rbp+380h+var_3C8]; void *
0x140075246  mov     [rbp+380h+var_3F8], rax
0x14007524a  mov     r8d, 278h; Size
0x140075250  mov     rax, [rbp+380h+arg_20]
0x140075257  mov     [rsp+480h+var_418], rax
0x14007525c  mov     rax, [rbp+380h+arg_A0]
0x140075263  mov     [rsp+480h+var_408], rax
0x140075268  mov     rax, [rbp+380h+arg_B0]
0x14007526f  mov     [rsp+480h+var_43E], dx
0x140075274  xor     edx, edx; Val
0x140075276  mov     [rbp+380h+var_3F0], rax
0x14007527a  mov     [rbp+380h+var_400], r9
0x14007527e  mov     [rbp+380h+var_3E8], rbx
0x140075282  call    memset
0x140075287  xor     ecx, ecx
0x140075289  xor     eax, eax
0x14007528b  mov     [rsp+480h+var_428], rcx
0x140075290  xorps   xmm0, xmm0
0x140075293  mov     [rsp+480h+var_420], rcx
0x140075298  mov     [rsp+480h+var_438], rcx
0x14007529d  mov     [rbx], rcx
0x1400752a0  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; Event
0x1400752a7  mov     word ptr [rsp+480h+LockState.OldIrql], ax
0x1400752ac  mov     [rsp+480h+LockState.Flags], al
0x1400752b0  movups  xmmword ptr [rbp+380h+LockHandle.LockQueue.Next], xmm0
0x1400752b4  mov     qword ptr [rbp+380h+LockHandle.OldIrql], rax
0x1400752b8  call    cs:__imp_KeReadStateEvent
0x1400752bf  nop     dword ptr [rax+rax+00h]
0x1400752c4  test    eax, eax
0x1400752c6  jz      loc_1400758F0
0x1400752cc  movzx   eax, cs:WfpSystemHasMemoryAvailable
0x1400752d3  test    al, al
0x1400752d5  jnz     loc_1401C61E4
0x1400752db  mov     cs:WfpSystemHasMemoryAvailable, 0
0x1400752e2  movzx   eax, cs:WfpSystemHasMemoryAvailable
0x1400752e9  test    al, al
0x1400752eb  jz      loc_140075BE8
0x1400752f1  xor     edx, edx; Val
0x1400752f3  lea     rcx, [rbp+380h+var_3C8]; void *
0x1400752f7  mov     r8d, 278h; Size
0x1400752fd  call    memset
0x140075302  mov     ebx, 10h
0x140075307  cmp     di, 2
0x14007530b  jnz     loc_140075B00
0x140075311  mov     rcx, cs:V4AddressLookasideList
0x140075318  lea     rdx, [rsp+480h+var_428]
0x14007531d  call    WfpAllocateFromPerProcessorLookasideList
0x140075322  mov     rsi, rax
0x140075325  test    rax, rax
0x140075328  jnz     loc_140075F7C
0x14007532e  mov     rcx, cs:V4AddressLookasideList
0x140075335  lea     rdx, [rsp+480h+var_420]
0x14007533a  call    WfpAllocateFromPerProcessorLookasideList
0x14007533f  mov     rsi, rax
0x140075342  test    rax, rax
0x140075345  jnz     loc_140075F7C
0x14007534b  mov     r10, [rsp+480h+var_418]
0x140075350  mov     r11d, 4
0x140075356  mov     r8, [rsp+480h+var_428]
0x14007535b  mov     r9, [rsp+480h+var_420]
0x140075360  mov     rax, [r10+10h]
0x140075364  mov     rcx, [rax]
0x140075367  mov     eax, [rcx]
0x140075369  mov     [r8], eax
0x14007536c  mov     rax, [rbp+380h+arg_30]
0x140075373  mov     ecx, [rax]
0x140075375  mov     [r9], ecx
0x140075378  mov     [rbp+380h+var_1E0], r11d
0x14007537f  mov     eax, [rbp+380h+var_398]
0x140075382  movzx   ecx, [rbp+380h+arg_60]
0x140075389  or      eax, 2
0x14007538c  mov     [rsp+480h+var_43C], 0
0x140075391  mov     [rbp+380h+var_15E], 0
0x140075398  mov     [rbp+380h+var_398], eax
0x14007539b  test    cl, cl
0x14007539d  jz      short loc_1400753A6
0x14007539f  bts     eax, 14h
0x1400753a3  mov     [rbp+380h+var_398], eax
0x1400753a6  cmp     [rbp+380h+arg_40], 0
0x1400753ad  jz      short loc_1400753B7
0x1400753af  lock or [rbp+380h+var_398], 1000000h
0x1400753b7  mov     eax, [r14+30h]
0x1400753bb  test    bl, al
0x1400753bd  jnz     loc_140075B80
0x1400753c3  movzx   eax, [rbp+380h+arg_98]
0x1400753ca  movzx   edx, [rsp+480h+var_43E]
0x1400753cf  movzx   edi, [rbp+380h+arg_90]
0x1400753d6  mov     [rbp+380h+var_1DB], al
0x1400753dc  mov     rax, [r10+8]
0x1400753e0  mov     [rbp+380h+var_1D8], r14
0x1400753e7  mov     [rbp+380h+var_38C], dx
0x1400753eb  mov     [rbp+380h+var_3A0], r12d
0x1400753ef  mov     [rbp+380h+var_1E8], r8
0x1400753f6  mov     [rbp+380h+var_3A8], r9
0x1400753fa  mov     [rbp+380h+var_1DC], dil
0x140075401  mov     [rbp+380h+var_160], cl
0x140075407  mov     rcx, [rax+10h]
0x14007540b  mov     eax, 2
0x140075410  cmp     ax, dx
0x140075413  mov     [rbp+380h+var_1F0], rcx
0x14007541a  cmovz   ebx, r11d
0x14007541e  mov     [rbp+380h+var_1E0], ebx
0x140075424  test    r15, r15
0x140075427  jnz     loc_140075829
0x14007542d  mov     eax, [rbp+380h+arg_88]
0x140075433  test    eax, eax
0x140075435  mov     ecx, [rbp+380h+var_2A0]
0x14007543b  cmovnz  ecx, eax
0x14007543e  mov     [rbp+380h+var_2A0], ecx
0x140075444  cmp     dx, 2
0x140075448  jnz     short loc_140075475
0x14007544a  cmp     r12d, 1
0x14007544e  jnz     short loc_14007547F
0x140075450  mov     eax, [r13+0]
0x140075454  movzx   ecx, byte ptr [r13+4]
0x140075459  mov     [rbp+380h+var_388], eax
0x14007545c  movzx   eax, byte ptr [r13+5]
0x140075461  mov     [rbp+380h+var_18F], al
0x140075467  mov     [rbp+380h+var_190], cl
0x14007546d  mov     [rbp+380h+var_18E], cl
0x140075473  jmp     short loc_140075495
0x140075475  cmp     r12d, 3Ah ; ':'
0x140075479  jz      loc_140075D24
0x14007547f  movzx   eax, [rbp+380h+arg_28]
0x140075486  mov     [rbp+380h+var_38A], ax
0x14007548a  movzx   eax, [rbp+380h+arg_38]
0x140075491  mov     word ptr [rbp+380h+var_388], ax
0x140075495  lea     rdx, [rsp+480h+var_438]
0x14007549a  lea     rcx, [rbp+380h+var_3C8]
0x14007549e  call    WfpAlepHashRemoteEndpoint
0x1400754a3  mov     rcx, [rsp+480h+var_438]
0x1400754a8  lea     rdx, [rsp+480h+LockState]
0x1400754ad  call    WfpAleGetAndWriteLockPartition
0x1400754b2  movsxd  r8, cs:CurrentLifeTimeThresholdIndex
0x1400754b9  mov     [rsp+480h+var_42C], eax
0x1400754bd  cmp     r8d, 3
0x1400754c1  jge     short loc_1400754E2
0x1400754c3  mov     rcx, cs:pRemoteEndpointTable
0x1400754ca  lea     r9, nFlows
0x1400754d1  mov     edx, [rcx+5Ch]
0x1400754d4  imul    edx, [rcx+4]
0x1400754d8  cmp     edx, [r9+r8*4]
0x1400754dc  ja      loc_140075EE3
0x1400754e2  mov     r8d, eax
0x1400754e5  lea     rdx, [rsp+480h+var_438]
0x1400754ea  lea     rcx, [rbp+380h+var_3C8]
0x1400754ee  call    WfpAlepFindRemoteEndpoint
0x1400754f3  mov     [rsp+480h+SpinLock], rax
0x1400754f8  mov     rbx, rax
0x1400754fb  test    rax, rax
0x1400754fe  jnz     loc_140075D33
0x140075504  xor     eax, eax
0x140075506  mov     [rsp+480h+var_440], 1
0x14007550b  mov     [r15+0F8h], rax
0x140075512  lea     rdx, [rsp+480h+SpinLock]
0x140075517  mov     [r15+100h], rax
0x14007551e  xor     r12b, r12b
0x140075521  mov     rcx, cs:RemoteEndpointLookasideList
0x140075528  xor     r13b, r13b
0x14007552b  xor     dil, dil
0x14007552e  call    WfpAllocateFromPerProcessorLookasideList
0x140075533  mov     rbx, [rsp+480h+SpinLock]
0x140075538  mov     rsi, rax
0x14007553b  test    rax, rax
0x14007553e  jnz     loc_140075F02
0x140075544  xor     edx, edx; Val
0x140075546  mov     r8d, 278h; Size
0x14007554c  mov     rcx, rbx; void *
0x14007554f  call    memset
0x140075554  mov     rcx, rbx
0x140075557  lea     rax, [rbp+380h+var_3C8]
0x14007555b  mov     edx, 4
0x140075560  lea     rcx, [rcx+80h]
0x140075567  movups  xmm0, xmmword ptr [rax]
0x14007556a  lea     rax, [rax+80h]
0x140075571  movups  xmmword ptr [rcx-80h], xmm0
0x140075575  movups  xmm1, xmmword ptr [rax-70h]
0x140075579  movups  xmmword ptr [rcx-70h], xmm1
0x14007557d  movups  xmm0, xmmword ptr [rax-60h]
0x140075581  movups  xmmword ptr [rcx-60h], xmm0
0x140075585  movups  xmm1, xmmword ptr [rax-50h]
0x140075589  movups  xmmword ptr [rcx-50h], xmm1
0x14007558d  movups  xmm0, xmmword ptr [rax-40h]
0x140075591  movups  xmmword ptr [rcx-40h], xmm0
0x140075595  movups  xmm1, xmmword ptr [rax-30h]
0x140075599  movups  xmmword ptr [rcx-30h], xmm1
0x14007559d  movups  xmm0, xmmword ptr [rax-20h]
0x1400755a1  movups  xmmword ptr [rcx-20h], xmm0
0x1400755a5  movups  xmm1, xmmword ptr [rax-10h]
0x1400755a9  movups  xmmword ptr [rcx-10h], xmm1
0x1400755ad  sub     rdx, 1
0x1400755b1  jnz     short loc_140075560
0x1400755b3  movups  xmm0, xmmword ptr [rax]
0x1400755b6  mov     r13d, [rsp+480h+var_42C]
0x1400755bb  lea     rdx, [rbx+240h]
0x1400755c2  movups  xmmword ptr [rcx], xmm0
0x1400755c5  movups  xmm1, xmmword ptr [rax+10h]
0x1400755c9  movups  xmmword ptr [rcx+10h], xmm1
0x1400755cd  movups  xmm0, xmmword ptr [rax+20h]
0x1400755d1  movups  xmmword ptr [rcx+20h], xmm0
0x1400755d5  movups  xmm1, xmmword ptr [rax+30h]
0x1400755d9  movups  xmmword ptr [rcx+30h], xmm1
0x1400755dd  movups  xmm0, xmmword ptr [rax+40h]
0x1400755e1  movups  xmmword ptr [rcx+40h], xmm0
0x1400755e5  movups  xmm1, xmmword ptr [rax+50h]
0x1400755e9  movups  xmmword ptr [rcx+50h], xmm1
0x1400755ed  movups  xmm0, xmmword ptr [rax+60h]
0x1400755f1  movups  xmmword ptr [rcx+60h], xmm0
0x1400755f5  mov     rax, [rax+70h]
0x1400755f9  mov     [rcx+70h], rax
0x1400755fd  mov     rax, [rsp+480h+var_438]
0x140075602  mov     [rbx+250h], rax
0x140075609  mov     rcx, cs:pRemoteEndpointTable
0x140075610  add     rcx, 48h ; 'H'
0x140075614  mov     [rsp+480h+var_438], r13
0x140075619  shl     r13, 7
0x14007561d  add     rcx, r13
0x140075620  call    WfpHashtableInsert
0x140075625  mov     rsi, rax
0x140075628  test    rax, rax
0x14007562b  jnz     loc_140075EFF
0x140075631  mov     edx, 2
0x140075636  mov     rcx, r14
0x140075639  mov     dil, 1
0x14007563c  call    WfpAleReferenceEndpoint_0
0x140075641  test    al, al
0x140075643  jz      loc_140075BA8
0x140075649  test    byte ptr cs:WPP_MAIN_CB+14Ah, dil
0x140075650  jnz     loc_140075C03
0x140075656  mov     r13, [rsp+480h+var_438]
0x14007565b  mov     r8d, [r14+30h]
0x14007565f  lea     rax, [rbx+168h]
0x140075666  movzx   r9d, [rbp+380h+arg_50]
0x14007566e  movzx   r12d, dil
0x140075672  mov     edx, [r14+28h]
0x140075676  movzx   ecx, [rsp+480h+var_43E]
0x14007567b  mov     [rsp+480h+var_458], rax
0x140075680  mov     eax, [rbp+380h+arg_58]
0x140075686  shr     r8d, 4
0x14007568a  and     r8d, 1
0x14007568e  mov     dword ptr [rsp+480h+var_460], eax
0x140075692  call    WfpAleInitializeEpochContext
0x140075697  lock or dword ptr [rbx+30h], 1000h
0x14007569f  lea     rcx, [rbx+80h]
0x1400756a6  mov     r9, rbx
0x1400756a9  call    WfpAleInitializeWaitRef
0x1400756ae  mov     rcx, [r15+60h]
0x1400756b2  test    rcx, rcx
0x1400756b5  jz      loc_140075ABF
0x1400756bb  call    cs:__imp_KfdAleRemoveFlowContextTable
0x1400756c2  nop     dword ptr [rax+rax+00h]
0x1400756c7  mov     rdx, [r15+60h]
0x1400756cb  lea     rcx, [rbx+48h]
0x1400756cf  call    cs:__imp_KfdAleInitializeFlowTable
0x1400756d6  nop     dword ptr [rax+rax+00h]
0x1400756db  mov     rsi, rax
0x1400756de  test    rax, rax
0x1400756e1  jnz     loc_140075EFF
0x1400756e7  mov     rax, [r15+70h]
0x1400756eb  xor     edi, edi
0x1400756ed  mov     [rbx+70h], rax
0x1400756f1  mov     [r15+70h], rdi
0x1400756f5  mov     [r15+60h], rdi
0x1400756f9  mov     edx, 1
0x1400756fe  mov     rcx, rbx
0x140075701  call    WfpAleReferenceEndpointNoLock
0x140075706  mov     rcx, rbx; SpinLock
0x140075709  call    cs:__imp_KeInitializeSpinLock
0x140075710  nop     dword ptr [rax+rax+00h]
0x140075715  mov     [rbx+8], edi
0x140075718  mov     rsi, rdi
0x14007571b  mov     [rbx+10h], rdi
0x14007571f  mov     [rbx+18h], rdi
0x140075723  mov     eax, [r14+0C8h]
0x14007572a  test    al, 4
0x14007572c  jnz     loc_140075EF2
0x140075732  mov     eax, [r14+0C8h]
0x140075739  mov     rdx, rbx
0x14007573c  and     eax, 7000884h
0x140075741  mov     rcx, r14
  ... truncated ...
```
