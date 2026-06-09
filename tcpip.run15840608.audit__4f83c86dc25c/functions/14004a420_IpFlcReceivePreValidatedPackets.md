# IpFlcReceivePreValidatedPackets

- ea: `0x14004a420`
- end: `0x14004bb13`
- name: `IpFlcReceivePreValidatedPackets`
- size: `5875`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400ffc20`
- `0x140127214`
- `0x1401ad960`

## callees

- `0x140031300`
- `0x14004a260`
- `0x14004a2f0`
- `0x14004a420`
- `0x14004c0b0`
- `0x14004e5d0`
- `0x14004f840`
- `0x140050c00`
- `0x14006c050`
- `0x14006d990`
- `0x14006de20`
- `0x14006ef20`
- `0x140071db0`
- `0x1400729b0`
- `0x140072e40`
- `0x14007b590`
- `0x14012b0cc`
- `0x14014eafc`
- `0x1401c1200`
- `0x1401c1aa0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14004a4d6`
- `ntoskrnl!KfRaiseIrql` at `0x14004b14d`
- `ntoskrnl!KfRaiseIrql` at `0x14004b8cb`
- `ntoskrnl!KfRaiseIrql` at `0x14004a4d6`
- `ntoskrnl!KfRaiseIrql` at `0x14004b14d`
- `ntoskrnl!KfRaiseIrql` at `0x14004b8cb`
- `ntoskrnl!KeLowerIrql` at `0x14004ac3d`
- `ntoskrnl!KeLowerIrql` at `0x14004ae67`
- `ntoskrnl!KeLowerIrql` at `0x14004b294`
- `ntoskrnl!KeLowerIrql` at `0x14004b8bd`
- `ntoskrnl!KeLowerIrql` at `0x14004ac3d`
- `ntoskrnl!KeLowerIrql` at `0x14004ae67`
- `ntoskrnl!KeLowerIrql` at `0x14004b294`
- `ntoskrnl!KeLowerIrql` at `0x14004b8bd`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14004b39a`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14004b39a`
- `ntoskrnl!KeShouldYieldProcessor` at `0x14004b896`
- `ntoskrnl!KeShouldYieldProcessor` at `0x14004b896`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14004b001`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14004b001`
- `ntoskrnl!IoQueueWorkItem` at `0x14004ad6e`
- `ntoskrnl!IoQueueWorkItem` at `0x14004ad6e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004a9fc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004ab1b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004b3f5`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004b592`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004a9fc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004ab1b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004b3f5`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004b592`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14004aa27`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14004b433`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14004aa27`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14004b433`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004a4bb`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004abf2`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004a4bb`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004abf2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14004b033`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14004b033`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004b198`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004b198`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004b1b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004b1b0`
- `ntoskrnl!KeTestSpinLock` at `0x14004b179`
- `ntoskrnl!KeTestSpinLock` at `0x14004b179`
- `NETIO!NetioAllocateMdl` at `0x14004b362`
- `NETIO!KfdIsLayerEmpty` at `0x14004a50d`
- `NETIO!KfdIsLayerEmpty` at `0x14004a50d`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14004ab0d`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14004b584`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14004ab0d`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14004b584`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14004addb`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14004b085`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14004addb`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14004b085`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14004b36c`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14004b36c`

## string_xrefs

- `0x14004af63`: `IppFindNextHopInFwdCacheOrRouteTable`
- `0x14004b9c4`: `IppFindNextHopInForwardPathSet`

## pseudocode

```c
void __fastcall IpFlcReceivePreValidatedPackets(__int64 a1, _QWORD *a2)
{
  __int64 v2; // r12
  _QWORD *v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // r13
  unsigned __int8 *v7; // rax
  __int16 v8; // r14
  __int64 v9; // rdi
  unsigned __int16 v10; // bx
  ULONG v11; // r14d
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  signed __int32 v16; // eax
  __int64 (__fastcall *v17)(__int64); // rax
  char *v18; // rdi
  int v19; // eax
  int v20; // r15d
  __int64 v21; // rsi
  int v22; // eax
  int v23; // ecx
  unsigned int v24; // eax
  _DWORD *v25; // rbx
  unsigned int v26; // ebx
  int v27; // eax
  unsigned int v28; // r13d
  _DWORD *p_OrderedPointer; // r14
  unsigned int v30; // r13d
  IN6_ADDR **v31; // r12
  __int64 v32; // rsi
  _BYTE *v33; // r11
  _QWORD *v34; // rax
  int v35; // ebx
  __int64 v36; // r9
  IN6_ADDR *v37; // r10
  __int64 v38; // r13
  _QWORD *v39; // rsi
  __int64 v40; // rdi
  int v41; // r15d
  _QWORD *v42; // r8
  __int64 v43; // rcx
  __int64 v44; // rdx
  bool v45; // al
  _QWORD *v46; // rcx
  bool v47; // al
  int v48; // ecx
  int v49; // r15d
  ULONG v50; // edx
  ULONG v51; // r8d
  _BYTE *v52; // rdx
  IN6_ADDR *v53; // rcx
  __int64 v54; // rdi
  char v55; // al
  int v56; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 *v58; // r15
  _QWORD *v59; // r11
  bool v60; // zf
  unsigned __int8 v61; // si
  char v62; // r15
  _QWORD *v63; // rdi
  int *v64; // rbx
  int v65; // eax
  __int64 *v66; // rsi
  __int64 v67; // rcx
  __int64 v68; // rdx
  IN6_ADDR ***v69; // r15
  __int64 v70; // rbx
  _QWORD *v71; // rcx
  _DWORD *v72; // rcx
  __int64 v73; // r9
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  PIO_WORKITEM *v77; // rbx
  int v78; // eax
  IN6_ADDR *v79; // rcx
  __int64 v80; // rdx
  int v81; // eax
  char v82; // al
  IN6_ADDR **v83; // r15
  unsigned int v84; // edi
  _QWORD *i; // rbx
  struct _NET_BUFFER *v86; // rcx
  ULONG v87; // edx
  KSPIN_LOCK *v88; // rax
  unsigned int v89; // r14d
  int NextHopAtDpc; // eax
  struct _NET_BUFFER *v91; // rcx
  unsigned int CurrentMdlOffset; // eax
  struct _RTL_AVL_TABLE *v93; // r13
  __int64 v94; // r9
  struct _RTL_AVL_TABLE *Parent; // rsi
  unsigned __int16 v96; // ax
  TABLE_SEARCH_RESULT v97; // eax
  __int64 v98; // r8
  IN6_ADDR **v99; // rax
  char *v100; // rax
  int *v101; // rcx
  int v102; // eax
  IN6_ADDR *v103; // rax
  __int64 v104; // rcx
  __int64 v105; // rdx
  IN6_ADDR **v106; // r12
  IN6_ADDR ***v107; // r13
  _QWORD *v108; // rax
  __int64 v109; // rcx
  _QWORD *v110; // r9
  _DWORD *v111; // rcx
  unsigned int v112; // edx
  __int64 v113; // rcx
  __int64 v114; // r9
  __int64 v115; // rcx
  _QWORD *v116; // r14
  unsigned int v117; // eax
  _DWORD *NextHopInFwdCacheOrRouteTable; // rax
  int v119; // eax
  __int64 v120; // rax
  char v121; // r8
  IN6_ADDR **v122; // rax
  KIRQL v123; // cl
  _BYTE *v124; // rax
  __int64 v125; // rax
  int v126; // [rsp+28h] [rbp-160h]
  unsigned __int8 v127; // [rsp+60h] [rbp-128h]
  char v128; // [rsp+60h] [rbp-128h]
  unsigned __int8 v129; // [rsp+61h] [rbp-127h]
  char v130; // [rsp+62h] [rbp-126h]
  KIRQL v131; // [rsp+62h] [rbp-126h]
  unsigned int LockArray_high; // [rsp+64h] [rbp-124h]
  char v133; // [rsp+68h] [rbp-120h]
  unsigned __int8 v134; // [rsp+69h] [rbp-11Fh]
  unsigned __int8 v135; // [rsp+6Ah] [rbp-11Eh]
  unsigned __int8 v136; // [rsp+6Bh] [rbp-11Dh]
  unsigned int v137; // [rsp+6Ch] [rbp-11Ch]
  ULONG DataOffsetDelta; // [rsp+70h] [rbp-118h]
  int v139; // [rsp+74h] [rbp-114h]
  unsigned int v140; // [rsp+74h] [rbp-114h]
  IN6_ADDR **v141; // [rsp+78h] [rbp-110h]
  _BYTE *v142; // [rsp+80h] [rbp-108h]
  __int64 v143; // [rsp+88h] [rbp-100h]
  _QWORD *v144; // [rsp+88h] [rbp-100h]
  _QWORD *v145; // [rsp+88h] [rbp-100h]
  unsigned int v146; // [rsp+88h] [rbp-100h]
  char v147; // [rsp+90h] [rbp-F8h]
  unsigned __int16 v148; // [rsp+90h] [rbp-F8h]
  __int16 v149; // [rsp+92h] [rbp-F6h]
  unsigned int v150; // [rsp+94h] [rbp-F4h]
  unsigned int v151; // [rsp+94h] [rbp-F4h]
  IN6_ADDR *v152; // [rsp+98h] [rbp-F0h] BYREF
  PVOID Context; // [rsp+A0h] [rbp-E8h]
  _QWORD *v154; // [rsp+A8h] [rbp-E0h]
  IN6_ADDR **v155; // [rsp+B0h] [rbp-D8h]
  __int64 v156; // [rsp+B8h] [rbp-D0h]
  IN6_ADDR ***v157; // [rsp+C0h] [rbp-C8h]
  KSPIN_LOCK *v158; // [rsp+C8h] [rbp-C0h]
  TABLE_SEARCH_RESULT SearchResult; // [rsp+D0h] [rbp-B8h] BYREF
  int v160; // [rsp+D4h] [rbp-B4h] BYREF
  IN6_ADDR *a; // [rsp+D8h] [rbp-B0h]
  _DWORD *v162; // [rsp+E0h] [rbp-A8h] BYREF
  _QWORD *v163; // [rsp+E8h] [rbp-A0h]
  __int64 v164; // [rsp+F0h] [rbp-98h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+F8h] [rbp-90h] BYREF
  PVOID NodeOrParent; // [rsp+110h] [rbp-78h] BYREF
  __int128 v167; // [rsp+118h] [rbp-70h] BYREF
  _QWORD *v168; // [rsp+128h] [rbp-60h]
  __int64 v169; // [rsp+130h] [rbp-58h]
  __int64 v170; // [rsp+138h] [rbp-50h]
  __int64 v171; // [rsp+140h] [rbp-48h]
  __int64 v172; // [rsp+148h] [rbp-40h]
  _QWORD *v174; // [rsp+198h] [rbp+10h] BYREF
  KIRQL v175; // [rsp+1A0h] [rbp+18h]
  __int64 v176; // [rsp+1A8h] [rbp+20h] BYREF

  v174 = a2;
  v2 = *(_QWORD *)(a1 + 8);
  v4 = a2;
  v154 = a2;
  v133 = 0;
  v171 = v2;
  v5 = *(_QWORD *)(v2 + 96);
  v6 = *(_QWORD *)(*(_QWORD *)v2 + 40LL);
  v7 = *(unsigned __int8 **)(v2 + 48);
  v156 = v6;
  v8 = *(_WORD *)(v6 + 28);
  v9 = *v7;
  v149 = v8;
  if ( v5
    && !*(_BYTE *)(v5 + 40)
    && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v5 + 16), 1u) )
  {
    IppIndicatePrevalidatedPacketsToIpsServiceChain(a1, &v174);
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v2 + 96) + 16LL), 1u);
    v4 = v174;
    v154 = v174;
    if ( !v174 )
      return;
    v133 = 1;
  }
  v141 = 0;
  v10 = v8 & 1;
  v157 = 0;
  v11 = v9;
  DataOffsetDelta = v9;
  if ( KeGetCurrentIrql() >= 2u )
  {
    v175 = 2;
    v129 = 1;
  }
  else
  {
    v129 = 0;
    v175 = KfRaiseIrql(2u);
  }
  LODWORD(v9) = HIDWORD(KeGetPcr()[1].LockArray);
  LockArray_high = v9;
  v12 = 18LL * v10;
  if ( !(unsigned int)KfdIsLayerEmpty(*(unsigned __int16 *)&AddressFamilyInformation[v12 + 8])
    || (v142 = (_BYTE *)*((_QWORD *)qword_140228898 + v9), *v142)
    || *(_DWORD *)(v2 + 416)
    || (*(_BYTE *)(v2 + 392) & 1) != 0 )
  {
LABEL_112:
    v31 = 0;
    v30 = v9;
    v32 = a1;
    goto LABEL_100;
  }
  v13 = v4[14];
  v14 = (unsigned __int8)AddressFamilyInformation[v12 + 7];
  v134 = AddressFamilyInformation[v12 + 2];
  v136 = AddressFamilyInformation[v12 + 6];
  v135 = AddressFamilyInformation[v12 + 5];
  v170 = (unsigned __int8)AddressFamilyInformation[v12 + 4];
  LOBYTE(v176) = *(_BYTE *)(v13 + v170);
  v15 = v6 + 72 * ((unsigned __int8)v176 + 7LL);
  v164 = v15;
  Context = *(PVOID *)(v15 + 56);
  do
  {
    v16 = *(_DWORD *)(v15 + 52);
    if ( (v16 & 1) != 0 )
      goto LABEL_112;
  }
  while ( v16 != _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 52), v16 + 2, v16) );
  v17 = *(__int64 (__fastcall **)(__int64))(v6 + 176);
  v18 = (char *)(v14 + v13);
  v169 = v14;
  v19 = v17(v14 + v13);
  v20 = v19;
  if ( !*(_BYTE *)(v6 + 19729) || ((v19 - 1) & 0xFFFFFFFD) != 0 )
    goto LABEL_13;
  v131 = KfRaiseIrql(2u);
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement((volatile signed __int32 *)(v2 + 384));
  if ( !KeTestSpinLock((PKSPIN_LOCK)(v2 + 376)) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v2 + 384));
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v2 + 376), &LockHandle);
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 384));
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  NodeOrParent = 0;
  p_OrderedPointer = 0;
  SearchResult = TableEmptyTree;
  switch ( v20 )
  {
    case 1:
      v93 = (struct _RTL_AVL_TABLE *)(v2 + 592);
      v94 = 240;
      break;
    case 2:
      v93 = (struct _RTL_AVL_TABLE *)(v2 + 616);
      v94 = 104;
      break;
    case 4:
      v93 = (struct _RTL_AVL_TABLE *)(v2 + 640);
      v94 = 104;
      break;
    default:
      v93 = (struct _RTL_AVL_TABLE *)(v2 + 664);
      v94 = v20 == 3 ? 224LL : 0LL;
      break;
  }
  Parent = (struct _RTL_AVL_TABLE *)v93->BalancedRoot.Parent;
  v143 = v94;
  if ( v93->BalancedRoot.LeftChild )
  {
    v96 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v2 + 40LL) + 16LL) + 6LL);
    v148 = v96;
    while ( Parent != v93 )
    {
      if ( !memcmp((char *)Parent + v94 - 72, v18, v96) )
      {
        v97 = TableFoundNode;
        v93 = Parent;
        goto LABEL_155;
      }
      Parent = (struct _RTL_AVL_TABLE *)Parent->BalancedRoot.Parent;
      v94 = v143;
      v96 = v148;
    }
    Parent = 0;
    v97 = TableInsertAsLeft;
LABEL_155:
    NodeOrParent = v93;
    SearchResult = v97;
  }
  else
  {
    v100 = (char *)RtlLookupElementGenericTableFullAvl(Parent, &v18[-v94 + 104], &NodeOrParent, &SearchResult);
    Parent = (struct _RTL_AVL_TABLE *)(v100 - 32);
    if ( !v100 )
      Parent = 0;
  }
  if ( Parent )
  {
    p_OrderedPointer = &Parent[-1].OrderedPointer;
    v98 = *(_QWORD *)&Parent[-1].DeleteCount;
    if ( (_InterlockedExchangeAdd64(
            (volatile signed __int64 *)(*(_QWORD *)v98
                                      + (unsigned int)(*(_DWORD *)(v98 + 16)
                                                     * (HIDWORD(KeGetPcr()[1].LockArray) % *(_DWORD *)(v98 + 20)))),
            2u)
        & 1) != 0 )
      _InterlockedAdd64((volatile signed __int64 *)(v98 + 24), 2u);
  }
  _InterlockedDecrement((volatile signed __int32 *)(v2 + 384));
  KeLowerIrql(v131);
  if ( !p_OrderedPointer )
  {
LABEL_13:
    v21 = *(_QWORD *)v2;
    v160 = 0;
    v22 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)(v21 + 40) + 168LL))(v18);
    v23 = v22 << 28;
    v24 = v22 & 0xF;
    if ( v24 <= 1 )
    {
      v25 = (_DWORD *)(v2 + 8);
    }
    else if ( v24 >= 0xE )
    {
      v25 = *(_DWORD **)v2;
    }
    else
    {
      _mm_lfence();
      v25 = (_DWORD *)(v2 + 4 * (v24 + 192LL));
    }
    v26 = v23 | *v25 & 0xFFFFFFF;
    if ( (*(_BYTE *)(v2 + 392) & 0x50) != 0 )
      v27 = 0;
    else
      v27 = *(_DWORD *)(v2 + 8);
    v28 = *(_DWORD *)(v2 + 1012);
    v139 = v27;
    if ( v20 == 1 && (p_OrderedPointer = (_DWORD *)IppFindNextHopInForwardPathSet(v21, 0, v18, v26, v28, 0, v27)) != 0 )
    {
      if ( (BYTE5(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x20) != 0 )
      {
        v125 = 0;
        if ( v139 )
          v125 = v2;
        IppLogRouteLookupEvent(
          v21,
          (unsigned int)"IppFindNextHopInForwardPathSet",
          (_DWORD)v18,
          0,
          v125,
          v28,
          (__int64)p_OrderedPointer,
          0,
          0,
          0);
      }
    }
    else
    {
      if ( (*(_BYTE *)(v2 + 392) & 0x50) != 0 && (unsigned int)(v20 - 3) > 1 )
      {
        v88 = 0;
        v128 = 1;
      }
      else
      {
        v88 = (KSPIN_LOCK *)v2;
        v128 = 0;
      }
      v158 = v88;
      v89 = v28 & 0xFFFFFFFE;
      v162 = 0;
      v151 = v28 & 0xFFFFFFFE;
      if ( (v28 & 0xFFFFFFFE) == 0 || (v28 & 1) == 0 )
      {
        v89 = v28;
        v151 = v28;
      }
      NextHopAtDpc = IppFindNextHopAtDpc(
                       v21,
                       (_DWORD)v18,
                       0,
                       (_DWORD)v88,
                       v26,
                       v89,
                       0,
                       0,
                       (__int64)&v162,
                       (__int64)&v160,
                       0);
      if ( (BYTE5(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x20) != 0 )
        IppLogRouteLookupEvent(
          v21,
          (unsigned int)"IppFindNextHopInFwdCacheOrRouteTable",
          (_DWORD)v18,
          0,
          (__int64)v158,
          v89,
          (__int64)v162,
          v128,
          v160,
          NextHopAtDpc);
      p_OrderedPointer = v162;
      if ( !v162 )
        goto LABEL_24;
      if ( v20 == 1 )
      {
        LOBYTE(v126) = 0;
        IppCreateForwardPath(v21, 0, v18, v26, v151, v126, v139, v162);
      }
    }
    if ( *p_OrderedPointer != 1634496585 )
    {
      if ( *p_OrderedPointer == 1701736521 )
        IppDereferenceNeighbor(p_OrderedPointer);
      goto LABEL_24;
    }
    goto LABEL_26;
  }
  if ( v20 == 1 && (int)p_OrderedPointer[26] < 3 )
  {
    IppDereferenceLocalAddress(p_OrderedPointer);
    goto LABEL_13;
  }
LABEL_26:
  if ( ((p_OrderedPointer[6] - 1) & 0xFFFFFFFD) != 0 )
  {
    IppDereferenceLocalAddress(p_OrderedPointer);
LABEL_24:
    IppDereferenceNlClient(Context);
    goto LABEL_25;
  }
  v33 = v142;
  v34 = v154;
  v35 = 0;
  v36 = 0;
  v137 = 0;
  v140 = 0;
  v37 = 0;
  *v142 = 1;
  v150 = 0;
  v158 = 0;
  v152 = 0;
  while ( 1 )
  {
    v38 = v34[14];
    v39 = v34;
    v40 = v34[1];
    v41 = *(_DWORD *)(v40 + 92);
    v42 = (_QWORD *)(v38 + v169);
    v147 = *(_BYTE *)(v135 + v38);
    v43 = v136 + v38;
    v172 = v38;
    a = (IN6_ADDR *)v43;
    v163 = (_QWORD *)(v38 + v169);
    v44 = *(unsigned __int8 *)(v170 + v38);
    v127 = *(_BYTE *)(v170 + v38);
    if ( !v37
      || (v149 == 23
        ? (*(_QWORD *)&v37->u.Word[4] != *(_QWORD *)(v43 + 8) || *(_QWORD *)v37->u.Byte != *(_QWORD *)v43
         ? (v45 = 0)
         : (v45 = 1))
        : (v45 = *(_DWORD *)v37->u.Byte == *(_DWORD *)v43),
          !v45) )
    {
      v35 = 0;
      v152 = *(IN6_ADDR **)(*(_QWORD *)v2 + 40LL);
      v78 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, __int64))&v152[10].u.Word[4])(v43, v44, v42, v36);
      v79 = a;
      v80 = v78;
      if ( v78 != 14 )
      {
        v82 = v152[1].u.Word[6] == 23 ? IN6_IS_ADDR_LOOPBACK(a) : a->u.Byte[0] == 127;
        if ( !v82 )
        {
          if ( (int)v80 <= 1 )
          {
            v35 = *(_DWORD *)(v2 + 8) & 0xFFFFFFF;
          }
          else if ( (int)v80 >= 14 )
          {
            v35 = **(_DWORD **)v2 & 0xFFFFFFF;
          }
          else
          {
            v35 = *(_DWORD *)(v2 + 4 * (v80 + 192)) & 0xFFFFFFF;
          }
        }
      }
      LOBYTE(v44) = v127;
      v42 = v163;
      LODWORD(v36) = v137;
      v33 = v142;
      v152 = v79;
    }
    v46 = (_QWORD *)**((_QWORD **)p_OrderedPointer + 2);
    if ( v149 == 23 )
      v47 = v46[1] == v42[1] && *v46 == *v42;
    else
      v47 = *(_DWORD *)v46 == *(_DWORD *)v42;
    if ( !v47 )
    {
      v130 = 1;
LABEL_180:
      v167 = 0;
      *(_QWORD *)&v33[160 * (unsigned int)(v36 - 1) + 8] = 0;
      v144 = v33 + 8;
      v168 = 0;
      v101 = *(int **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      v152 = (IN6_ADDR *)v101;
      v102 = *v101;
      if ( *v101 )
      {
        if ( v102 == 1 )
        {
          ++v101[32];
        }
        else if ( v102 == 2 )
        {
          ++v101[28];
        }
      }
      else
      {
        v155 = (IN6_ADDR **)(v101 + 2);
        if ( KeQueryDpcWatchdogInformation((PKDPC_WATCHDOG_INFORMATION)(v101 + 2)) )
        {
          *v155 = (IN6_ADDR *)MEMORY[0xFFFFF78000000008];
          v103 = v152;
          *(_DWORD *)v152->u.Byte = 2;
          v103[1] = 0;
          v103[2] = 0;
          v103[3] = 0;
          v103[4] = 0;
          v103[5] = 0;
          v103[6] = 0;
        }
        else
        {
          v103 = v152;
          *(_DWORD *)v152->u.Byte = 1;
          v103[2] = 0;
          v103[3] = 0;
          v103[4] = 0;
          v103[5] = 0;
          v103[6] = 0;
          v103[7] = 0;
          *(_DWORD *)v103[8].u.Byte = 1;
        }
        *(_DWORD *)v103[7].u.Byte = 1;
      }
      v152 = 0;
      v104 = *(_QWORD *)(v164 + 56);
      *(_QWORD *)&v167 = *(_QWORD *)(v104 + 32);
      v168 = v144;
      *((_QWORD *)&v167 + 1) = v158;
      v155 = &v152;
      (*(void (__fastcall **)(__int128 *, _QWORD))(*(_QWORD *)(v104 + 40) + 24LL))(&v167, v137);
      v106 = v155;
      v107 = v157;
      v158 = (KSPIN_LOCK *)*((_QWORD *)&v167 + 1);
      v108 = v144;
      while ( 1 )
      {
        v109 = v108[1];
        v110 = v108;
        v108 = (_QWORD *)*v108;
        v145 = v108;
        v155 = (IN6_ADDR **)v109;
        if ( v109 )
        {
          v105 = *(unsigned int *)(v109 + 140);
          switch ( (_DWORD)v105 )
          {
            case 0xC000023F:
            case 0x40000026:
            case 0xC0220104:
            case 0xC0000022:
LABEL_216:
              *(_QWORD *)(v109 + 112) = 255;
LABEL_217:
              NetioRetreatNetBuffer(*(_QWORD *)(v109 + 8), *((unsigned int *)v110 + 12), 0);
              v122 = v155;
              if ( v107 )
                *v107 = v155;
              else
                v141 = v155;
              v107 = (IN6_ADDR ***)v122;
              v108 = v145;
              goto LABEL_186;
            case 0xC000A014:
              *(_DWORD *)(v109 + 140) = 0;
              goto LABEL_217;
            case 0xC000023E:
              goto LABEL_216;
          }
          *v106 = (IN6_ADDR *)v109;
          v106 = (IN6_ADDR **)v109;
          *(_DWORD *)(v109 + 140) = 0;
        }
LABEL_186:
        if ( !v108 )
        {
          v157 = v107;
          v38 = v172;
          v155 = v106;
          v2 = v171;
          if ( v152 )
          {
            LOBYTE(v105) = 1;
            *v155 = 0;
            NetioDereferenceNetBufferListChain(v152, v105);
          }
          v111 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
          if ( *v111 == 1 )
          {
            v60 = v111[32]-- == 1;
            if ( v60 )
              goto LABEL_191;
          }
          else if ( *v111 == 2 )
          {
            v60 = v111[28]-- == 1;
            if ( v60 )
LABEL_191:
              *v111 = 0;
          }
          v112 = v137;
          if ( v133 )
          {
            v114 = v156;
            v115 = 192LL * LockArray_high;
          }
          else
          {
            v113 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL * LockArray_high);
            *(_QWORD *)(v113 + 48) += v137;
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL * LockArray_high) + 56LL) += v140;
            v114 = v156;
            v115 = 192LL * LockArray_high;
            *(_QWORD *)(*(_QWORD *)(v156 + 20264) + v115) += v137;
            *(_QWORD *)(*(_QWORD *)(v114 + 20264) + v115 + 8) += v140;
            v112 = v137;
          }
          *(_QWORD *)(v115 + *(_QWORD *)(v114 + 20264) + 24) += v137;
          if ( v141 )
          {
            IppDereferenceNlClient(Context);
          }
          else
          {
            if ( !v129 )
            {
              v150 += v112;
              if ( v150 >= 0x20 )
              {
                if ( KeShouldYieldProcessor() )
                {
                  v123 = v175;
                  *v142 = 0;
                  KeLowerIrql(v123);
                  v175 = KfRaiseIrql(2u);
                  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
                  v124 = (_BYTE *)*((_QWORD *)qword_140228898 + LockArray_high);
                  v142 = v124;
                  if ( !*v124 )
                  {
                    v150 = 0;
                    *v124 = 1;
                    goto LABEL_196;
                  }
LABEL_25:
                  v11 = DataOffsetDelta;
                  v30 = LockArray_high;
                  v31 = v141;
                  v32 = a1;
LABEL_100:
                  v83 = (IN6_ADDR **)v154;
                  v84 = 0;
                  for ( i = v154; i; ++v84 )
                  {
                    i[14] = 0;
                    if ( v11 )
                    {
                      v86 = (struct _NET_BUFFER *)i[1];
                      v87 = v11 + v86->CurrentMdlOffset;
                      if ( v87 >= *(_DWORD *)(v86->Link.Region + 40) )
                      {
                        NdisAdvanceNetBufferDataStart(v86, v11, 0, 0);
                      }
                      else
                      {
                        v86->DataOffset += v11;
                        v86->DataLength -= v11;
                        v86->CurrentMdlOffset = v87;
                      }
                    }
                    i = (_QWORD *)*i;
                  }
                  if ( v31 )
                  {
                    v99 = v31;
                    do
                    {
                      v99 = (IN6_ADDR **)*v99;
                      ++v84;
                    }
                    while ( v99 );
                    *v157 = v83;
                    v83 = v31;
                  }
                  if ( TcpipGlobalCounters && v149 == 2 )
                    *((_QWORD *)TcpipGlobalCounters + 40 * v30 + 3) += v84;
                  if ( !v129 )
                    KeLowerIrql(v175);
                  IppReceivePackets(v32, v83, v129, 0);
                  return;
                }
              }
            }
LABEL_196:
            if ( v127 == (_BYTE)v176 )
            {
LABEL_197:
              LODWORD(v36) = 0;
              v152 = 0;
              v140 = 0;
              v137 = 0;
              if ( !v130 )
                goto LABEL_37;
              IppDereferenceLocalAddress(p_OrderedPointer);
              v116 = v163;
              v117 = (*(__int64 (__fastcall **)(_QWORD *))(v156 + 176))(v163);
              v146 = v117;
              if ( *(_BYTE *)(v156 + 19729) && ((v117 - 1) & 0xFFFFFFFD) == 0 )
              {
                p_OrderedPointer = (_DWORD *)IppFindAddressInAddressSet(v2, v116, v117);
                if ( p_OrderedPointer )
                {
LABEL_234:
                  if ( ((p_OrderedPointer[6] - 1) & 0xFFFFFFFD) == 0 )
                  {
                    LODWORD(v36) = 0;
                    goto LABEL_37;
                  }
                  IppDereferenceLocalAddress(p_OrderedPointer);
LABEL_203:
                  IppDereferenceNlClient(Context);
LABEL_213:
                  *v142 = 0;
                  goto LABEL_25;
                }
                v117 = v146;
                LODWORD(v116) = (_DWORD)v163;
              }
              NextHopInFwdCacheOrRouteTable = (_DWORD *)IppFindNextHopInFwdCacheOrRouteTable(
                                                          *(_QWORD *)v2,
                                                          v2,
                                                          0,
                                                          (_DWORD)v116,
                                                          v117);
              p_OrderedPointer = NextHopInFwdCacheOrRouteTable;
              if ( NextHopInFwdCacheOrRouteTable )
              {
                v119 = *NextHopInFwdCacheOrRouteTable;
                if ( v119 == 1634496585 )
                  goto LABEL_234;
                if ( v119 == 1701736521 )
                  IppDereferenceNeighbor(p_OrderedPointer);
              }
              goto LABEL_203;
            }
            IppDereferenceNlClient(Context);
            v120 = v156 + 72 * (v127 + 7LL);
            Context = *(PVOID *)(v120 + 56);
            v164 = v120;
            if ( (unsigned __int8)RoReferenceEx(v120 + 52) )
            {
              LOBYTE(v176) = v121;
              goto LABEL_197;
            }
          }
          IppDereferenceLocalAddress(p_OrderedPointer);
          goto LABEL_213;
        }
      }
    }
    v130 = 0;
    if ( (_BYTE)v44 != (_BYTE)v176 || (_DWORD)v36 == 32 )
      goto LABEL_180;
LABEL_37:
    v48 = *(_DWORD *)(v40 + 24);
    v140 += v48 - DataOffsetDelta;
    v49 = v134 + ((unsigned __int16)v41 >> 10);
    v50 = v49 + DataOffsetDelta;
    if ( v49 + DataOffsetDelta )
    {
      v51 = v50 + *(_DWORD *)(v40 + 16);
      if ( v51 >= *(_DWORD *)(*(_QWORD *)(v40 + 8) + 40LL) )
      {
        NdisAdvanceNetBufferDataStart((PNET_BUFFER)v40, v50, 0, 0);
        LODWORD(v36) = v137;
      }
      else
      {
        *(_DWORD *)(v40 + 40) += v50;
        *(_DWORD *)(v40 + 16) = v51;
        *(_DWORD *)(v40 + 24) = v48 - v50;
      }
    }
    v52 = v142;
    v53 = a;
    v137 = v36 + 1;
    v54 = 160LL * (unsigned int)v36;
    *(_QWORD *)&v142[v54 + 8] = &v142[v54 + 168];
    v55 = v142[v54 + 24];
    *(_QWORD *)&v142[v54 + 16] = v39;
    v142[v54 + 25] = 0;
    v142[v54 + 24] = v55 & 0xF6 | 8;
    *(_DWORD *)&v142[v54 + 28] = v35;
    *(_QWORD *)&v142[v54 + 32] = v53;
    *(_QWORD *)&v142[v54 + 40] = p_OrderedPointer;
    if ( p_OrderedPointer[6] == 1 )
      v56 = p_OrderedPointer[47];
    else
      v56 = 0;
    *(_DWORD *)&v142[v54 + 48] = v56;
    *(_DWORD *)&v142[v54 + 52] = (unsigned __int8)v176;
    *(_DWORD *)&v142[v54 + 56] = v49;
    *(_QWORD *)&v142[v54 + 64] = v2;
    *(_DWORD *)&v142[v54 + 72] = *(_DWORD *)(a1 + 24);
    if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
    {
      IsEnabledDeviceUsageNoInline = Feature_5988_5730__private_featureState & 1;
    }
    else
    {
      IsEnabledDeviceUsageNoInline = Feature_5988_5730__private_IsEnabledDeviceUsageNoInline();
      v53 = a;
      v52 = v142;
    }
    if ( IsEnabledDeviceUsageNoInline )
      *(_QWORD *)&v52[v54 + 80] = v38;
    v58 = v154;
    *(_QWORD *)&v52[v54 + 88] = v39[14] + v134;
    *(_QWORD *)&v52[v54 + 96] = 0;
    v59 = (_QWORD *)*v58;
    v34 = (_QWORD *)*v58;
    *v39 = 0;
    v39[14] = 0;
    *((_DWORD *)v39 + 35) = 261;
    v60 = p_OrderedPointer[6] == 1;
    v154 = v34;
    if ( v60 )
    {
      v61 = *(_BYTE *)(v2 + 451);
      v62 = v147 & 0x1F;
      if ( (unsigned __int8)(v147 & 0x1F) < v61 )
      {
        if ( v62 )
        {
          if ( *p_OrderedPointer != 1634496585
            || !(unsigned __int8)HasPrefix(v53, **((_QWORD **)p_OrderedPointer + 2), (unsigned int)p_OrderedPointer[47])
            || (v62 = 31, v61 > 0x1Fu) )
          {
            *(_BYTE *)(v2 + 451) = v62;
          }
        }
      }
      v52 = v142;
      v34 = v154;
    }
    if ( !v59 )
      break;
    v36 = v137;
    v37 = v152;
    v33 = v142;
  }
  *(_QWORD *)&v52[v54 + 8] = 0;
  v63 = v52 + 8;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v64 = *(int **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
  v65 = *v64;
  if ( *v64 )
  {
    if ( v65 == 1 )
    {
      ++v64[32];
    }
    else if ( v65 == 2 )
    {
      ++v64[28];
    }
  }
  else
  {
    if ( KeQueryDpcWatchdogInformation((PKDPC_WATCHDOG_INFORMATION)(v64 + 2)) )
    {
      *((_QWORD *)v64 + 1) = MEMORY[0xFFFFF78000000008];
      *v64 = 2;
      *((_OWORD *)v64 + 1) = 0;
      *((_OWORD *)v64 + 2) = 0;
      *((_OWORD *)v64 + 3) = 0;
      *((_OWORD *)v64 + 4) = 0;
      *((_OWORD *)v64 + 5) = 0;
      *((_OWORD *)v64 + 6) = 0;
    }
    else
    {
      *v64 = 1;
      *((_OWORD *)v64 + 2) = 0;
      *((_OWORD *)v64 + 3) = 0;
      *((_OWORD *)v64 + 4) = 0;
      *((_OWORD *)v64 + 5) = 0;
      *((_OWORD *)v64 + 6) = 0;
      *((_OWORD *)v64 + 7) = 0;
      v64[32] = 1;
    }
    v64[28] = 1;
  }
  v66 = &v176;
  v176 = 0;
  v67 = *(_QWORD *)(v164 + 56);
  LockHandle.LockQueue.Next = *(struct _KSPIN_LOCK_QUEUE *volatile *)(v67 + 32);
  LockHandle.LockQueue.Lock = v158;
  *(_QWORD *)&LockHandle.OldIrql = v63;
  (*(void (__fastcall **)(struct _KLOCK_QUEUE_HANDLE *, _QWORD))(*(_QWORD *)(v67 + 40) + 24LL))(&LockHandle, v137);
  v69 = v157;
  while ( 2 )
  {
    v70 = v63[1];
    v71 = v63;
    v63 = (_QWORD *)*v63;
    if ( v70 )
    {
      v81 = *(_DWORD *)(v70 + 140);
      if ( v81 != -1073741249 && v81 != 1073741862 && v81 != -1071513340 && v81 != -1073741790 )
      {
        if ( v81 == -1073700844 )
        {
          *(_DWORD *)(v70 + 140) = 0;
          goto LABEL_132;
        }
        if ( v81 != -1073741250 )
        {
          *v66 = v70;
          v66 = (__int64 *)v70;
          *(_DWORD *)(v70 + 140) = 0;
          goto LABEL_60;
        }
      }
      *(_QWORD *)(v70 + 112) = 255;
LABEL_132:
      v68 = *((unsigned int *)v71 + 12);
      v91 = *(struct _NET_BUFFER **)(v70 + 8);
      CurrentMdlOffset = v91->CurrentMdlOffset;
      if ( CurrentMdlOffset < (unsigned int)v68 )
      {
        NdisRetreatNetBufferDataStart(v91, v68, 0, NetioAllocateMdl);
      }
      else
      {
        v91->DataOffset -= v68;
        v91->DataLength += v68;
        v91->CurrentMdlOffset = CurrentMdlOffset - v68;
      }
      if ( v69 )
        *v69 = (IN6_ADDR **)v70;
      else
        v141 = (IN6_ADDR **)v70;
      v69 = (IN6_ADDR ***)v70;
    }
LABEL_60:
    if ( v63 )
      continue;
    break;
  }
  v157 = v69;
  if ( v176 )
  {
    *v66 = 0;
    LOBYTE(v68) = 1;
    NetioDereferenceNetBufferListChain(v176, v68);
  }
  v72 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
  if ( *v72 == 1 )
  {
    v60 = v72[32]-- == 1;
    if ( v60 )
      goto LABEL_65;
  }
  else if ( *v72 == 2 )
  {
    v60 = v72[28]-- == 1;
    if ( v60 )
LABEL_65:
      *v72 = 0;
  }
  v30 = LockArray_high;
  v32 = a1;
  v73 = v156;
  if ( v133 )
  {
    v76 = 192LL * LockArray_high;
  }
  else
  {
    v74 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL * LockArray_high);
    *(_QWORD *)(v74 + 48) += v137;
    v75 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL * LockArray_high);
    *(_QWORD *)(v75 + 56) += v140;
    v76 = 192LL * LockArray_high;
    *(_QWORD *)(*(_QWORD *)(v73 + 20264) + v76) += v137;
    *(_QWORD *)(*(_QWORD *)(v73 + 20264) + v76 + 8) += v140;
  }
  *(_QWORD *)(*(_QWORD *)(v73 + 20264) + v76 + 24) += v137;
  IppDereferenceLocalAddress(p_OrderedPointer);
  v77 = (PIO_WORKITEM *)Context;
  if ( _InterlockedExchangeAdd(
         (volatile signed __int32 *)(*(_QWORD *)Context
                                   + 72LL * *(unsigned __int16 *)(*((_QWORD *)Context + 5) + 4LL)
                                   + 556),
         0xFFFFFFFE) == 3 )
  {
    if ( KeGetCurrentIrql() )
      IoQueueWorkItem(v77[8], IppDetachNlClientCompleteWorkerRoutine, DelayedWorkQueue, v77);
    else
      IppDetachNlClientCompleteWorkerRoutine(IppDeviceObject, v77);
  }
  v31 = v141;
  *v142 = 0;
  if ( v141 )
  {
    v11 = DataOffsetDelta;
    goto LABEL_100;
  }
  if ( !v129 )
    KeLowerIrql(v175);
}

```

## disassembly

```asm
0x14004a420  mov     [rsp+arg_8], rdx
0x14004a425  mov     [rsp+arg_0], rcx
0x14004a42a  push    rbx
0x14004a42b  push    rsi
0x14004a42c  push    rdi
0x14004a42d  push    r12
0x14004a42f  push    r13
0x14004a431  push    r14
0x14004a433  sub     rsp, 158h
0x14004a43a  mov     r12, [rcx+8]
0x14004a43e  mov     rbx, rcx
0x14004a441  mov     rsi, rdx
0x14004a444  mov     [rsp+188h+var_E0], rdx
0x14004a44c  mov     [rsp+188h+var_120], 0
0x14004a451  mov     [rsp+188h+var_48], r12
0x14004a459  mov     rax, [r12]
0x14004a45d  mov     rcx, [r12+60h]
0x14004a462  mov     r13, [rax+28h]
0x14004a466  mov     rax, [r12+30h]
0x14004a46b  mov     [rsp+188h+var_D0], r13
0x14004a473  movzx   r14d, word ptr [r13+1Ch]
0x14004a478  movzx   edi, byte ptr [rax]
0x14004a47b  mov     [rsp+188h+var_F6], r14w
0x14004a484  test    rcx, rcx
0x14004a487  jz      short loc_14004A495
0x14004a489  movzx   eax, byte ptr [rcx+28h]
0x14004a48d  test    al, al
0x14004a48f  jz      loc_14004AFF8
0x14004a495  xor     eax, eax
0x14004a497  mov     [rsp+188h+var_38], r15
0x14004a49f  movzx   ebx, r14w
0x14004a4a3  mov     [rsp+188h+var_110], rax
0x14004a4a8  and     bx, 1
0x14004a4ac  mov     [rsp+188h+var_C8], rax
0x14004a4b4  mov     r14d, edi
0x14004a4b7  mov     [rsp+188h+DataOffsetDelta], edi
0x14004a4bb  call    cs:__imp_KeGetCurrentIrql
0x14004a4c2  nop     dword ptr [rax+rax+00h]
0x14004a4c7  cmp     al, 2
0x14004a4c9  jnb     loc_14004B325
0x14004a4cf  mov     cl, 2; NewIrql
0x14004a4d1  mov     [rsp+188h+var_127], 0
0x14004a4d6  call    cs:__imp_KfRaiseIrql
0x14004a4dd  nop     dword ptr [rax+rax+00h]
0x14004a4e2  mov     [rsp+188h+arg_10], al
0x14004a4e9  mov     edi, gs:1A4h
0x14004a4f1  lea     r15, AddressFamilyInformation
0x14004a4f8  movzx   ecx, bx
0x14004a4fb  mov     [rsp+188h+var_124], edi
0x14004a4ff  lea     rdx, [rcx+rcx*8]
0x14004a503  lea     rbx, [rdx+rdx]
0x14004a507  movzx   ecx, word ptr [rbx+r15+8]
0x14004a50d  call    cs:__imp_KfdIsLayerEmpty
0x14004a514  nop     dword ptr [rax+rax+00h]
0x14004a519  test    eax, eax
0x14004a51b  jz      loc_14004AEA9
0x14004a521  mov     rax, cs:qword_140228898
0x14004a528  mov     rax, [rax+rdi*8]
0x14004a52c  mov     [rsp+188h+var_108], rax
0x14004a534  cmp     byte ptr [rax], 0
0x14004a537  jnz     loc_14004AEA9
0x14004a53d  cmp     dword ptr [r12+1A0h], 0
0x14004a546  ja      loc_14004AEA9
0x14004a54c  test    byte ptr [r12+188h], 1
0x14004a555  jnz     loc_14004AEA9
0x14004a55b  movzx   eax, byte ptr [rbx+r15+2]
0x14004a561  mov     rdx, [rsi+70h]
0x14004a565  movzx   r8d, byte ptr [rbx+r15+7]
0x14004a56b  mov     [rsp+188h+var_11F], al
0x14004a56f  movzx   eax, byte ptr [rbx+r15+6]
0x14004a575  mov     [rsp+188h+var_11D], al
0x14004a579  movzx   eax, byte ptr [rbx+r15+5]
0x14004a57f  mov     [rsp+188h+var_11E], al
0x14004a583  movzx   eax, byte ptr [rbx+r15+4]
0x14004a589  mov     [rsp+188h+var_50], rax
0x14004a591  movzx   eax, byte ptr [rdx+rax]
0x14004a595  mov     byte ptr [rsp+188h+arg_18], al
0x14004a59c  add     rax, 7
0x14004a5a0  lea     rax, [rax+rax*8]
0x14004a5a4  lea     r9, ds:0[rax*8]
0x14004a5ac  add     r9, r13
0x14004a5af  mov     [rsp+188h+var_98], r9
0x14004a5b7  mov     rax, [r9+38h]
0x14004a5bb  mov     [rsp+188h+Context], rax
0x14004a5c3  mov     eax, [r9+34h]
0x14004a5c7  test    al, 1
0x14004a5c9  jnz     loc_14004AEA9
0x14004a5cf  lea     ecx, [rax+2]
0x14004a5d2  lock cmpxchg [r9+34h], ecx
0x14004a5d8  jnz     short loc_14004A5C3
0x14004a5da  mov     rax, [r13+0B0h]
0x14004a5e1  lea     rdi, [r8+rdx]
0x14004a5e5  mov     rcx, rdi
0x14004a5e8  mov     [rsp+188h+var_58], r8
0x14004a5f0  call    _guard_dispatch_icall
0x14004a5f5  cmp     byte ptr [r13+4D11h], 0
0x14004a5fd  mov     r15d, eax
0x14004a600  jnz     loc_14004B134
0x14004a606  mov     rsi, [r12]
0x14004a60a  mov     rcx, rdi
0x14004a60d  mov     [rsp+188h+var_B4], 0
0x14004a618  mov     rax, [rsi+28h]
0x14004a61c  mov     rax, [rax+0A8h]
0x14004a623  call    _guard_dispatch_icall
0x14004a628  mov     ecx, eax
0x14004a62a  shl     ecx, 1Ch
0x14004a62d  mov     eax, ecx
0x14004a62f  shr     eax, 1Ch
0x14004a632  cmp     eax, 1
0x14004a635  jbe     loc_14004B0A0
0x14004a63b  cmp     eax, 0Eh
0x14004a63e  jnb     loc_14004B062
0x14004a644  lfence
0x14004a647  mov     ebx, eax
0x14004a649  add     rbx, 0C0h
0x14004a650  lea     rbx, [r12+rbx*4]
0x14004a654  mov     ebx, [rbx]
0x14004a656  and     ebx, 0FFFFFFFh
0x14004a65c  or      ebx, ecx
0x14004a65e  test    byte ptr [r12+188h], 50h
0x14004a667  jnz     loc_14004B0FD
0x14004a66d  mov     eax, [r12+8]
0x14004a672  mov     r13d, [r12+3F4h]
0x14004a67a  mov     [rsp+188h+var_114], eax
0x14004a67e  cmp     r15d, 1
0x14004a682  jnz     loc_14004AEBE
0x14004a688  mov     dword ptr [rsp+188h+var_158], eax
0x14004a68c  mov     r9d, ebx
0x14004a68f  mov     byte ptr [rsp+188h+var_160], 0
0x14004a694  mov     r8, rdi
0x14004a697  xor     edx, edx
0x14004a699  mov     dword ptr [rsp+188h+var_168], r13d
0x14004a69e  mov     rcx, rsi
0x14004a6a1  call    IppFindNextHopInForwardPathSet
0x14004a6a6  mov     r14, rax
0x14004a6a9  test    rax, rax
0x14004a6ac  jz      loc_14004AEBE
0x14004a6b2  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+5, 20h
0x14004a6b9  jnz     loc_14004B99E
0x14004a6bf  mov     eax, [r14]
0x14004a6c2  cmp     eax, 616C7049h
0x14004a6c7  jz      short loc_14004A70A
0x14004a6c9  cmp     eax, 656E7049h
0x14004a6ce  jnz     short loc_14004A6D8
0x14004a6d0  mov     rcx, r14; P
0x14004a6d3  call    IppDereferenceNeighbor
0x14004a6d8  mov     rcx, [rsp+188h+Context]; Context
0x14004a6e0  call    IppDereferenceNlClient
0x14004a6e5  mov     r14d, [rsp+188h+DataOffsetDelta]
0x14004a6ea  mov     r13d, [rsp+188h+var_124]
0x14004a6ef  mov     r12, [rsp+188h+var_110]
0x14004a6f4  mov     rsi, [rsp+188h+arg_0]
0x14004a6fc  jmp     loc_14004ADF6
0x14004a701  test    r14, r14
0x14004a704  jz      loc_14004A606
0x14004a70a  mov     eax, [r14+18h]
0x14004a70e  dec     eax
0x14004a710  test    eax, 0FFFFFFFDh
0x14004a715  jnz     loc_14004B96F
0x14004a71b  mov     r11, [rsp+188h+var_108]
0x14004a723  xor     ecx, ecx
0x14004a725  mov     rax, [rsp+188h+var_E0]
0x14004a72d  mov     ebx, ecx
0x14004a72f  mov     r9d, ecx
0x14004a732  mov     [rsp+188h+var_11C], ecx
0x14004a736  mov     [rsp+188h+var_114], ecx
0x14004a73a  mov     r10d, ecx
0x14004a73d  mov     byte ptr [r11], 1
0x14004a741  mov     [rsp+188h+var_F4], ecx
0x14004a748  mov     [rsp+188h+var_C0], rcx
0x14004a750  mov     [rsp+188h+var_F0], rcx
0x14004a758  mov     r13, [rax+70h]
0x14004a75c  mov     rsi, rax
0x14004a75f  mov     rdi, [rax+8]
0x14004a763  movzx   ecx, [rsp+188h+var_11E]
0x14004a768  movzx   edx, [rsp+188h+var_11D]
0x14004a76d  mov     r8, [rsp+188h+var_58]
0x14004a775  mov     r15d, [rdi+5Ch]
0x14004a779  add     r8, r13
0x14004a77c  movzx   eax, byte ptr [rcx+r13]
0x14004a781  mov     byte ptr [rsp+188h+var_F8], al
0x14004a788  lea     rcx, [rdx+r13]
0x14004a78c  mov     rax, [rsp+188h+var_50]
0x14004a794  mov     [rsp+188h+var_40], r13
0x14004a79c  mov     [rsp+188h+a], rcx
0x14004a7a4  mov     [rsp+188h+var_A0], r8
0x14004a7ac  movzx   edx, byte ptr [rax+r13]
0x14004a7b1  mov     [rsp+188h+var_128], dl
0x14004a7b5  test    r10, r10
0x14004a7b8  jz      loc_14004AC63
0x14004a7be  cmp     [rsp+188h+var_F6], 17h
0x14004a7c7  jz      loc_14004ACBC
0x14004a7cd  mov     eax, [rcx]
0x14004a7cf  cmp     [r10], eax
0x14004a7d2  setz    al
0x14004a7d5  test    al, al
0x14004a7d7  jz      loc_14004AC63
0x14004a7dd  cmp     [rsp+188h+var_F6], 17h
0x14004a7e6  mov     rax, [r14+10h]
0x14004a7ea  mov     rcx, [rax]
0x14004a7ed  jz      loc_14004A9BB
0x14004a7f3  mov     eax, [r8]
0x14004a7f6  cmp     [rcx], eax
0x14004a7f8  setz    al
0x14004a7fb  test    al, al
0x14004a7fd  jz      loc_14004B3B8
0x14004a803  mov     [rsp+188h+var_126], 0
0x14004a808  cmp     dl, byte ptr [rsp+188h+arg_18]
0x14004a80f  jnz     loc_14004B3BD
0x14004a815  cmp     r9d, 20h ; ' '
0x14004a819  jz      loc_14004B3BD
0x14004a81f  mov     edx, [rsp+188h+DataOffsetDelta]
0x14004a823  mov     ecx, [rdi+18h]
0x14004a826  mov     eax, ecx
0x14004a828  sub     eax, edx
0x14004a82a  shr     r15d, 0Ah
0x14004a82e  add     [rsp+188h+var_114], eax
0x14004a832  and     r15d, 3Fh
0x14004a836  movzx   eax, [rsp+188h+var_11F]
0x14004a83b  add     r15d, eax
0x14004a83e  add     edx, r15d; DataOffsetDelta
0x14004a841  jz      short loc_14004A864
0x14004a843  mov     rax, [rdi+8]
0x14004a847  mov     r8d, [rdi+10h]
0x14004a84b  add     r8d, edx
0x14004a84e  cmp     r8d, [rax+28h]
0x14004a852  jnb     loc_14004ADD2
0x14004a858  add     [rdi+28h], edx
0x14004a85b  sub     ecx, edx
0x14004a85d  mov     [rdi+10h], r8d
0x14004a861  mov     [rdi+18h], ecx
0x14004a864  mov     rdx, [rsp+188h+var_108]
0x14004a86c  mov     rcx, [rsp+188h+a]
0x14004a874  mov     eax, r9d
0x14004a877  inc     r9d
0x14004a87a  mov     [rsp+188h+var_11C], r9d
0x14004a87f  lea     rdi, [rax+rax*4]
0x14004a883  shl     rdi, 5
0x14004a887  lea     rax, [rdx+0A8h]
0x14004a88e  add     rax, rdi
0x14004a891  mov     [rdi+rdx+8], rax
0x14004a896  movzx   eax, byte ptr [rdi+rdx+18h]
0x14004a89b  and     al, 0FEh
0x14004a89d  mov     [rdi+rdx+10h], rsi
0x14004a8a2  or      al, 8
0x14004a8a4  mov     byte ptr [rdi+rdx+19h], 0
0x14004a8a9  mov     [rdi+rdx+18h], al
0x14004a8ad  mov     [rdi+rdx+1Ch], ebx
0x14004a8b1  mov     [rdi+rdx+20h], rcx
0x14004a8b6  mov     [rdi+rdx+28h], r14
0x14004a8bb  cmp     dword ptr [r14+18h], 1
0x14004a8c0  jnz     loc_14004B12D
0x14004a8c6  mov     eax, [r14+0BCh]
0x14004a8cd  mov     [rdi+rdx+30h], eax
0x14004a8d1  movzx   eax, byte ptr [rsp+188h+arg_18]
0x14004a8d9  mov     [rdi+rdx+34h], eax
0x14004a8dd  mov     rax, [rsp+188h+arg_0]
0x14004a8e5  mov     [rdi+rdx+38h], r15d
0x14004a8ea  mov     [rdi+rdx+40h], r12
0x14004a8ef  mov     eax, [rax+18h]
0x14004a8f2  mov     [rdi+rdx+48h], eax
0x14004a8f6  mov     eax, cs:Feature_5988_5730__private_featureState
0x14004a8fc  test    al, 10h
0x14004a8fe  jnz     loc_14004AD7F
0x14004a904  call    Feature_5988_5730__private_IsEnabledDeviceUsageNoInline
0x14004a909  mov     rcx, [rsp+188h+a]
0x14004a911  mov     rdx, [rsp+188h+var_108]
0x14004a919  test    eax, eax
0x14004a91b  jz      short loc_14004A922
0x14004a91d  mov     [rdi+rdx+50h], r13
0x14004a922  mov     r15, [rsp+188h+var_E0]
0x14004a92a  xor     r13d, r13d
0x14004a92d  movzx   eax, [rsp+188h+var_11F]
0x14004a932  add     rax, [rsi+70h]
0x14004a936  mov     [rdi+rdx+58h], rax
0x14004a93b  mov     [rdi+rdx+60h], r13
0x14004a940  mov     r11, [r15]
0x14004a943  mov     rax, r11
0x14004a946  mov     [rsi], r13
0x14004a949  mov     [rsi+70h], r13
0x14004a94d  mov     dword ptr [rsi+8Ch], 105h
0x14004a957  cmp     dword ptr [r14+18h], 1
0x14004a95c  mov     [rsp+188h+var_E0], rax
0x14004a964  jnz     short loc_14004A99C
0x14004a966  mov     rax, [r14+10h]
0x14004a96a  movzx   r15d, byte ptr [rsp+188h+var_F8]
0x14004a973  movzx   esi, byte ptr [r12+1C3h]
0x14004a97c  and     r15b, 1Fh
0x14004a980  mov     rdx, [rax]
0x14004a983  cmp     r15b, sil
0x14004a986  jb      loc_14004ACDD
0x14004a98c  mov     rdx, [rsp+188h+var_108]
0x14004a994  mov     rax, [rsp+188h+var_E0]
0x14004a99c  test    r11, r11
0x14004a99f  jz      short loc_14004A9DC
0x14004a9a1  mov     r9d, [rsp+188h+var_11C]
0x14004a9a6  mov     r10, [rsp+188h+var_F0]
0x14004a9ae  mov     r11, [rsp+188h+var_108]
0x14004a9b6  jmp     loc_14004A758
0x14004a9bb  mov     rax, [r8+8]
  ... truncated ...
```
