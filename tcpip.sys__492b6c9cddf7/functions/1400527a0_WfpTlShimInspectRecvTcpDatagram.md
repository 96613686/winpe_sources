# WfpTlShimInspectRecvTcpDatagram

- ea: `0x1400527a0`
- end: `0x140053845`
- name: `WfpTlShimInspectRecvTcpDatagram`
- size: `4261`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140051650`

## callees

- `0x14001b0a0`
- `0x14004c7d0`
- `0x14004d860`
- `0x1400505d0`
- `0x140050740`
- `0x14005079c`
- `0x1400507f8`
- `0x140052390`
- `0x1400525d0`
- `0x1400527a0`
- `0x140053910`
- `0x140054f00`
- `0x140055780`
- `0x14008a370`
- `0x1400abee4`
- `0x1400abf74`
- `0x1400ac028`
- `0x1400d2f60`
- `0x1400ec900`
- `0x1400fff20`
- `0x1401054b4`
- `0x14012529c`
- `0x140134740`
- `0x14014e224`
- `0x140150374`
- `0x1401bf390`
- `0x1401bf5c0`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140053585`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140053585`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140052c1c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140052c1c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140052c92`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400535b1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140052c92`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400535b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052a8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400534b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400536c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052a8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400534b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400536c8`
- `NETIO!KfdIsLayerEmpty` at `0x14005288d`
- `NETIO!KfdIsLayerEmpty` at `0x14005298f`
- `NETIO!KfdIsLayerEmpty` at `0x140052abc`
- `NETIO!KfdIsLayerEmpty` at `0x14005288d`
- `NETIO!KfdIsLayerEmpty` at `0x14005298f`
- `NETIO!KfdIsLayerEmpty` at `0x140052abc`
- `NETIO!KfdAuditEvent` at `0x14005355a`
- `NETIO!KfdAuditEvent` at `0x14005355a`
- `NETIO!KfdDiagnoseEvent` at `0x14005356d`
- `NETIO!KfdDiagnoseEvent` at `0x14005356d`
- `NETIO!KfdReleaseTerminatingFilters` at `0x140053287`
- `NETIO!KfdReleaseTerminatingFilters` at `0x140053287`
- `NETIO!KfdClassify2` at `0x140052a34`
- `NETIO!KfdClassify2` at `0x140052a34`
- `NETIO!KfdReleaseCachedFilters` at `0x140053243`
- `NETIO!KfdReleaseCachedFilters` at `0x140053243`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x140052fe4`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x140052fe4`
- `NETIO!KfdClassify` at `0x140053050`
- `NETIO!KfdClassify` at `0x1400537ff`
- `NETIO!KfdClassify` at `0x140053050`
- `NETIO!KfdClassify` at `0x1400537ff`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x140052fd0`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x140052fd0`
- `NETIO!KfdGetLayerCacheEpoch` at `0x140052b7b`
- `NETIO!KfdGetLayerCacheEpoch` at `0x140053195`
- `NETIO!KfdGetLayerCacheEpoch` at `0x140052b7b`
- `NETIO!KfdGetLayerCacheEpoch` at `0x140053195`

## string_xrefs

- `0x140053660`: `WfpAleCopySecurityRealmIdFromEndpoint`
- `0x14005370f`: `WfpAleCopySecurityRealmIdFromEndpoint`
- `0x140052d49`: `AleEdgeIFsLookupCachedAction`

## pseudocode

```c
__int64 __fastcall WfpTlShimInspectRecvTcpDatagram(
        PKSPIN_LOCK SpinLock,
        unsigned __int16 a2,
        unsigned __int16 a3,
        unsigned __int16 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        int a8,
        _BYTE *a9,
        char *a10)
{
  PKSPIN_LOCK v10; // rdi
  int v11; // eax
  unsigned __int16 v13; // r13
  int v14; // edx
  unsigned int v15; // r14d
  _QWORD *v16; // rbx
  unsigned int v17; // esi
  _BYTE *v18; // rcx
  _QWORD *v19; // rdx
  unsigned __int16 v20; // r12
  __int64 v21; // rdx
  char v22; // r9
  __int64 v23; // rcx
  unsigned __int16 v24; // r13
  char *v25; // rcx
  unsigned __int16 v26; // r14
  KSPIN_LOCK v27; // rax
  int v28; // eax
  __int64 v30; // rcx
  int v31; // r13d
  __int64 ProfileIdFromInterface; // rax
  __int64 v33; // rcx
  int v34; // ebx
  int v35; // r8d
  bool v36; // zf
  __int64 v37; // rax
  __int64 v38; // rdx
  int v39; // eax
  int v40; // r14d
  __int64 v41; // rbx
  char v42; // r12
  __int64 v43; // r14
  PKSPIN_LOCK i; // rcx
  __int64 v45; // r8
  void *v46; // rbx
  unsigned int v47; // r9d
  char v48; // al
  bool v49; // bl
  int v50; // r12d
  _QWORD *j; // rax
  unsigned __int8 v52; // cl
  unsigned int v53; // eax
  bool v54; // zf
  unsigned int v55; // r8d
  char v56; // r12
  unsigned __int16 v57; // bx
  _DWORD *v58; // r12
  int *v59; // r14
  int v60; // eax
  unsigned __int16 v61; // r13
  int v62; // edx
  int v63; // edx
  __int64 v64; // rax
  KSPIN_LOCK v65; // rax
  __int64 inserted; // rax
  int *v67; // rax
  int v68; // r12d
  __int64 v69; // rax
  __int64 v70; // r14
  char *v71; // r13
  __int64 v72; // r8
  int v73; // eax
  _DWORD *v74; // rcx
  __int64 v75; // rax
  char updated; // al
  __int64 v77; // rax
  __int64 v78; // rbx
  unsigned __int8 v79; // dl
  _DWORD *v80; // rcx
  int v81; // [rsp+20h] [rbp-E0h]
  __int64 v82; // [rsp+28h] [rbp-D8h]
  int v83; // [rsp+38h] [rbp-C8h]
  char v84; // [rsp+60h] [rbp-A0h]
  char v85; // [rsp+61h] [rbp-9Fh]
  unsigned int v87; // [rsp+64h] [rbp-9Ch]
  unsigned int v90; // [rsp+6Ch] [rbp-94h]
  unsigned int v91; // [rsp+70h] [rbp-90h]
  int v92; // [rsp+74h] [rbp-8Ch]
  int v93; // [rsp+78h] [rbp-88h] BYREF
  int v94; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v95; // [rsp+80h] [rbp-80h] BYREF
  __int64 v96; // [rsp+88h] [rbp-78h]
  int v97; // [rsp+90h] [rbp-70h]
  __int64 v98; // [rsp+98h] [rbp-68h] BYREF
  _DWORD *v99; // [rsp+A0h] [rbp-60h] BYREF
  int *v100; // [rsp+A8h] [rbp-58h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v102; // [rsp+C8h] [rbp-38h] BYREF
  void *v103; // [rsp+D0h] [rbp-30h]
  PVOID P[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v105[3]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v106; // [rsp+100h] [rbp+0h] BYREF
  __int128 v107; // [rsp+110h] [rbp+10h]
  __int128 v108; // [rsp+120h] [rbp+20h]
  _BYTE v109[28]; // [rsp+130h] [rbp+30h] BYREF
  int v110; // [rsp+14Ch] [rbp+4Ch]
  char *v111; // [rsp+150h] [rbp+50h]
  _OWORD v112[3]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v113[2]; // [rsp+188h] [rbp+88h] BYREF
  __int128 v114; // [rsp+198h] [rbp+98h]
  __int64 v115; // [rsp+1A8h] [rbp+A8h]
  __int128 v116; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v117; // [rsp+1C0h] [rbp+C0h]
  int v118; // [rsp+1D0h] [rbp+D0h]

  v10 = SpinLock;
  if ( !SpinLock )
    v10 = 0;
  v111 = a10;
  v11 = 12;
  v95 = 0;
  if ( a2 != 2 )
    LOWORD(v11) = 14;
  v91 = 0;
  v97 = v11;
  v13 = a2;
  v85 = 1;
  v102 = 0;
  LODWORD(v103) = 0;
  WORD2(v103) = 0;
  v99 = 0;
  v100 = 0;
  LODWORD(v115) = 0;
  v92 = 0;
  v84 = 0;
  LOBYTE(v87) = 0;
  *(_OWORD *)P = 0;
  memset(v112, 0, sizeof(v112));
  *(_OWORD *)v113 = 0;
  v114 = 0;
  *(_OWORD *)v105 = 0;
  if ( a2 == 2 )
  {
    if ( (unsigned int)KfdIsLayerEmpty(12) )
    {
LABEL_7:
      v15 = 0;
      v16 = (_QWORD *)(a6 + 8);
      v17 = 1;
      v18 = (_BYTE *)(a6 + 16);
      v19 = (_QWORD *)(a6 + 32);
      goto LABEL_8;
    }
  }
  else if ( (unsigned int)KfdIsLayerEmpty(14) )
  {
    goto LABEL_7;
  }
  v30 = *(_QWORD *)(a6 + 56);
  v31 = 0;
  if ( *(_DWORD *)(*(_QWORD *)(v30 + 48) + 12LL) == 131 )
    ProfileIdFromInterface = WfpGetProfileIdFromInterface(v30, v14, *(_QWORD *)(a6 + 32), 0, *(_QWORD *)(a6 + 8));
  else
    ProfileIdFromInterface = *(unsigned int *)(v30 + 56);
  v90 = ProfileIdFromInterface;
  v17 = 2;
  if ( !v10 )
    goto LABEL_104;
  if ( (v10[6] & 0x40000000) != 0 || (v10[6] & 0x800) != 0 )
    return 0;
  if ( a7 )
  {
    InitializeEndpointContextFromParentContext(SpinLock);
    v56 = 1;
    goto LABEL_162;
  }
  if ( (v10[6] & 0x1000) == 0 )
    InitializeEndpointContextFromParentContext(SpinLock);
  if ( a9 )
  {
    if ( *a9 )
      goto LABEL_100;
    if ( a6 == a5 )
    {
      if ( (unsigned __int8)WfpAleCanPermitTcpDatagramGroup(SpinLock) )
        *a9 = 1;
      else
        v84 = 1;
    }
    if ( *a9 )
      goto LABEL_100;
  }
  v33 = *((unsigned __int16 *)v10 + 208);
  v34 = 0;
  v94 = 0;
  KfdGetLayerCacheEpoch(v33, &v94);
  v35 = v94;
  v36 = *((_DWORD *)v10 + 102) == v94;
  v93 = v94;
  v37 = 32;
  if ( a6 )
    v37 = a6 + 56;
  v38 = *(_QWORD *)(*(_QWORD *)v37 + 16LL);
  v39 = *((_DWORD *)v10 + 13);
  v96 = v38;
  if ( (v39 & 0x80000) != 0 )
  {
    v34 = 512;
    _InterlockedAnd((volatile signed __int32 *)v10 + 13, 0xFFF7FFFF);
  }
  v40 = v34 | 1;
  LockHandle.LockQueue = 0;
  if ( v36 )
    v40 = v34;
  v36 = (v10[41] & 1) == 0;
  v94 = v40;
  *(_QWORD *)&LockHandle.OldIrql = 0;
  if ( v36 )
  {
    v47 = v90;
    v42 = 0;
    goto LABEL_72;
  }
  if ( gCachePerInterfaceProfileCrossing )
  {
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v98 = 0;
    if ( gAleDebugEnabled )
    {
      v75 = WfpPoolAllocNonPaged(28, 1281715265, &v98);
      v41 = v98;
      v43 = v75;
      if ( !v75 )
        WfpStringCchCopyA("AleEdgeIFsIsProfileCrossing", 28, v98);
    }
    KeAcquireInStackQueuedSpinLock(v10, &LockHandle);
    while ( *((_DWORD *)v10 + 2) )
      ;
    v36 = gAleDebugEnabled == 1;
    v10[2] = (KSPIN_LOCK)KeGetCurrentThread();
    if ( v36 && !v43 )
      v10[3] = v41;
    for ( i = v10 + 39; i; i = (PKSPIN_LOCK)*i )
    {
      if ( *(i - 1) == v96 )
      {
        v45 = *((unsigned int *)i + 3);
        if ( (_DWORD)v45 != v90 )
        {
          *((_BYTE *)i + 8) = 0;
          v42 = 1;
          *((_BYTE *)i + 9) = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
          {
            WPP_SF_qIDDd(WPP_GLOBAL_Control->AttachedDevice, 11, v45, v10, *(i - 1), v45, v90);
          }
        }
        break;
      }
    }
    v36 = gAleDebugEnabled == 1;
    v46 = 0;
    v10[2] = 0;
    if ( v36 )
    {
      v46 = (void *)v10[3];
      v10[3] = 0;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( gAleDebugEnabled == 1 && v46 )
      ExFreePoolWithTag(v46, 0);
    v40 = v94;
  }
  else
  {
    v72 = *((unsigned int *)v10 + 83);
    v47 = v90;
    if ( v90 == (_DWORD)v72 )
    {
      v42 = 0;
      goto LABEL_71;
    }
    v42 = 1;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 5u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) == 0 )
    {
      goto LABEL_71;
    }
    WPP_SF_qIDDd(WPP_GLOBAL_Control->AttachedDevice, 10, v72, v10, 0, v72, v90);
  }
  v47 = v90;
  v38 = v96;
LABEL_71:
  v35 = v93;
LABEL_72:
  if ( (*((_DWORD *)v10 + 13) & 0x8000) != 0 && v47 )
  {
    updated = AleEdgeIFsUpdateOriginalProfileId(v10, v47);
    v38 = v96;
    if ( updated )
      _InterlockedAnd((volatile signed __int32 *)v10 + 13, 0xFFFF7FFF);
    v35 = v93;
  }
  if ( v42 )
    v40 |= 8u;
  if ( (v10[6] & 0x100000) == 0 && (*((_DWORD *)v10 + 13) & 0x800) != 0 )
  {
    v40 |= 0x80u;
    _InterlockedAnd((volatile signed __int32 *)v10 + 13, 0xFFFFF7FF);
  }
  if ( gCachePerInterfaceProfileCrossing && v42 )
    goto LABEL_131;
  v36 = (v10[41] & 1) == 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( v36 )
  {
    v50 = v93;
LABEL_169:
    v73 = 2;
    if ( !a6 )
      v73 = 4;
    v40 |= v73;
    goto LABEL_97;
  }
  if ( *((_DWORD *)v10 + 84) == v35 && v10[38] == v38 )
  {
    v48 = a6 ? *((_BYTE *)v10 + 320) : *((_BYTE *)v10 + 321);
    if ( v48 )
    {
      LOBYTE(v87) = v48;
      if ( *((_DWORD *)v10 + 84) == v35 )
      {
LABEL_131:
        v50 = v93;
        goto LABEL_97;
      }
    }
  }
  v49 = 0;
  AleAcquireEndpointLockEx(v10, &LockHandle);
  v50 = v93;
  if ( *((_DWORD *)v10 + 84) == v93 )
  {
    if ( v10[38] == v96 )
    {
      if ( a6 )
        v52 = *((_BYTE *)v10 + 320);
      else
        v52 = *((_BYTE *)v10 + 321);
      v53 = v52;
      v54 = v52 == 0;
LABEL_93:
      v49 = !v54;
      v55 = (unsigned __int8)v87;
      if ( !v54 )
        v55 = v53;
      v87 = v55;
    }
    else
    {
      for ( j = (_QWORD *)v10[39]; j; j = (_QWORD *)*j )
      {
        if ( *(j - 1) == v96 )
        {
          if ( a6 )
            v79 = *((_BYTE *)v10 + 320);
          else
            v79 = *((_BYTE *)v10 + 321);
          v53 = v79;
          v54 = v79 == 0;
          goto LABEL_93;
        }
      }
    }
  }
  AleReleaseEndpointLock(v10, &LockHandle);
  if ( !v49 )
    goto LABEL_169;
LABEL_97:
  if ( (*((_DWORD *)v10 + 13) & 0x800000) != 0 )
  {
    v40 |= 0x4000u;
    _InterlockedAnd((volatile signed __int32 *)v10 + 13, 0xFF7FFFFF);
  }
  if ( v40 )
  {
    v92 = v50;
    v56 = 0;
    v91 = v40;
LABEL_162:
    v31 = 256;
    goto LABEL_101;
  }
LABEL_100:
  v56 = 1;
LABEL_101:
  v36 = (v10[25] & 0x4000) == 0;
  P[1] = 0;
  LODWORD(P[0]) = 0;
  if ( !v36 )
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    AleAcquireEndpointLockEx(v10, &LockHandle);
    v77 = WfpBufferCopy((void *)v10[34], *((unsigned int *)v10 + 66));
    LODWORD(P[0]) = *((_DWORD *)v10 + 66);
    v78 = v77;
    AleReleaseEndpointLock(v10, &LockHandle);
    if ( v78 )
    {
      if ( P[1] )
        ExFreePoolWithTag(P[1], 0x52537049u);
      P[1] = 0;
      LODWORD(P[0]) = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpAleCopySecurityRealmIdFromEndpoint",
          v78);
      }
    }
  }
  if ( !v10[43] )
  {
    ProfileIdFromInterface = v91;
    v85 = v56;
LABEL_104:
    v57 = a2;
    goto LABEL_105;
  }
  v98 = TlShimLookupLayerCache(v10);
  v70 = v98;
  if ( !v98 )
  {
    ProfileIdFromInterface = v87;
    v85 = v56;
    goto LABEL_104;
  }
  KfdGetLayerCacheEpoch((unsigned __int16)v97, v10 + 47);
  if ( *((_DWORD *)v10 + 94) != *(_DWORD *)(v70 + 44) )
  {
    TlShimPurgeLayerCache(v10, v70);
    ProfileIdFromInterface = TlShimReleaseLayerCache(&v98);
    v85 = v56;
    goto LABEL_104;
  }
  v57 = a2;
  if ( !TlShimDirectClassify(v10, a2, v70, 6, a3, a4, a6, 0, a8, v56 ^ 1, 0, (int *)&v95) )
  {
    TlShimPurgeLayerCache(v10, v70);
    ProfileIdFromInterface = TlShimReleaseLayerCache(&v98);
    v85 = v56;
LABEL_105:
    LODWORD(ProfileIdFromInterface) = HIDWORD(KeGetPcr()[1].LockArray);
    if ( !*((_BYTE *)gPerProcessorContext + 72 * ProfileIdFromInterface + 32) )
    {
      v58 = (_DWORD *)*((_QWORD *)gPerProcessorContext + 9 * ProfileIdFromInterface + 3);
      v59 = (int *)*((_QWORD *)gPerProcessorContext + 9 * ProfileIdFromInterface + 2);
      *((_BYTE *)gPerProcessorContext + 72 * ProfileIdFromInterface + 32) = 1;
      goto LABEL_107;
    }
    if ( !WfpAllocateFromPerProcessorLookasideList(gIncomingValuesLookasideList, &v99) )
    {
      if ( !WfpAllocateFromPerProcessorLookasideList(gMetadataLookasideList, &v100) )
      {
        v58 = v99;
        v59 = v100;
LABEL_107:
        v99 = v58;
        memset(v58, 0, 0x2A0u);
        memset(v59, 0, 0x2A8u);
        *((_QWORD *)v59 + 79) = v59 + 156;
        *((_QWORD *)v59 + 78) = v59 + 156;
        if ( (*(_BYTE *)(a6 + 16) & 1) != 0 )
          v31 |= 1u;
        v60 = TlShimMarshalInTransportFields(v57, 6, a3, a4, a6, v90, v31, (__int64)P, (__int64)v58);
        v61 = v97;
        HIDWORD(v102) = v60;
        v103 = v58;
        LOWORD(v102) = v97;
        *v59 |= 4u;
        v62 = *v59;
        v59[10] = *(_DWORD *)(a6 + 48) - a8;
        v63 = v62 | 0xC80;
        *v59 = v63;
        v59[11] = a8;
        v64 = *(_QWORD *)(a6 + 32);
        v100 = 0;
        v59[20] = ***(_DWORD ***)(v64 + 8);
        v59[70] = *(_DWORD *)(a6 + 20);
        *((_QWORD *)v59 + 50) = *(_QWORD *)(*(_QWORD *)(a6 + 56) + 16LL);
        if ( v10 )
        {
          if ( *((_DWORD *)v10 + 170) == 1 || (v65 = v10[68]) != 0 && *(_DWORD *)(v65 + 680) == 1 )
            v59[1] |= 0x80000u;
        }
        if ( !v85 || a7 )
          *v59 = v63 | 0x400000;
        if ( v10 )
        {
          inserted = WfpAleQueryOrInsertEndpointHandle(v10);
          if ( inserted )
          {
            *v59 |= 0x8000u;
            *((_QWORD *)v59 + 14) = inserted;
          }
          if ( !KfdAleAcquireFlowHandleForFlow(v10, 0, &v100) )
            KfdAleReleaseFlowHandleForFlow(v10);
        }
        v67 = v100;
        if ( v100 )
        {
          *v59 |= 2u;
          *((_QWORD *)v59 + 4) = v67;
        }
        *(_QWORD *)&v112[0] = v10;
        *((_QWORD *)v59 + 1) = v112;
        v105[1] = (__int64)v105;
        v105[0] = (__int64)v105;
        if ( v10 )
          *((_QWORD *)v59 + 64) = v105;
        v16 = (_QWORD *)(a6 + 8);
        v68 = KfdClassify(v61, &v102, v59, *(_QWORD *)(a6 + 8), 0, v113);
        HIDWORD(v69) = HIDWORD(qword_140227F08);
        if ( qword_140227F08 && (LOWORD(v93) = 0, v95 = 0, v69 = qword_140227F08(*v16, &v93, &v95), (_DWORD)v69) )
        {
          v80 = v99;
          v99[38] = v95;
          *((_WORD *)v80 + 44) = v93;
          *((_QWORD *)v59 + 64) = 0;
          v69 = KfdClassify(v61, &v102, v59, *v16, 0, v113);
          v68 = v69;
        }
        else if ( v10 )
        {
          if ( !v59[134] || (v69 = TlShimCacheMatchedFilterList(v10, (__int64)v105, v82), (int)v69 >= 0) )
          {
LABEL_144:
            if ( v68 )
            {
              HIDWORD(v69) = 0;
              *(_OWORD *)v113 = 0;
              LODWORD(v113[0]) = 4097;
              v114 = 0;
              v115 = 0;
            }
            else if ( LODWORD(v113[0]) != 4097 )
            {
              v17 = 1;
LABEL_147:
              LODWORD(v69) = HIDWORD(KeGetPcr()[1].LockArray);
              v71 = (char *)gPerProcessorContext + 72 * v69;
              KfdReleaseTerminatingFilters(v59 + 156);
              if ( v99 == *((_DWORD **)v71 + 3) )
              {
                v71[32] = 0;
              }
              else
              {
                PplFreeToLookasideList(gMetadataLookasideList);
                PplFreeToLookasideList(gIncomingValuesLookasideList);
              }
              goto LABEL_149;
            }
            if ( (BYTE12(v114) & 1) == 0 )
            {
              *((_QWORD *)v59 + 64) = 0;
              v17 = 0;
              v69 = WfpShimIndicateDiscardGeneral(v61, (unsigned int)&v102, (_DWORD)v59, *v16, 0, (__int64)v113);
            }
            goto LABEL_147;
          }
LABEL_143:
          v69 = KfdReleaseCachedFilters(v105);
          goto LABEL_144;
        }
        if ( !v59[134] )
          goto LABEL_144;
        goto LABEL_143;
      }
      PplFreeToLookasideList(gIncomingValuesLookasideList);
    }
    v17 = 0;
    goto LABEL_32;
  }
  TlShimReleaseLayerCache(&v98);
  v16 = (_QWORD *)(a6 + 8);
  v17 = v95;
  v85 = v56;
LABEL_149:
  v19 = (_QWORD *)(a6 + 32);
  v18 = (_BYTE *)(a6 + 16);
  if ( !v17 )
  {
    v24 = a4;
    v20 = a3;
    v26 = a2;
    if ( (*(_DWORD *)(*v16 + 136LL) & 0x400000) != 0 )
    {
      LOWORD(v82) = a4;
      LOWORD(v81) = a3;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64, int, _DWORD, _QWORD, int))qword_140227F30)(
        a2,
        *v19,
        *(_QWORD *)(a6 + 24),
        6,
        v81,
        v82,
        *v16,
        a8);
    }
    goto LABEL_15;
  }
  if ( v17 != 1 )
  {
    v20 = a3;
    v24 = a4;
    goto LABEL_14;
  }
  v13 = a2;
  v15 = v90;
LABEL_8:
  v20 = a3;
  if ( qword_140227F20 )
  {
    v21 = *v19;
    v22 = *v18 & 1;
    v23 = 0;
    v36 = v13 == 2;
    v24 = a4;
    if ( !v36 )
      v23 = 41;
    LOBYTE(v83) = v22;
    LOWORD(v82) = a4;
    LOWORD(v81) = a3;
    v17 = qword_140227F20(v23, v21, *(_QWORD *)(a6 + 24), 6, v81, v82, v10, v83, *v16);
    if ( v17 != 1 )
      goto LABEL_14;
  }
  else
  {
    v24 = a4;
  }
  v25 = v111;
  *v111 = v85;
  if ( !v85 )
  {
    *((_DWORD *)v25 + 1) = v91;
    *((_DWORD *)v25 + 3) = v92;
    v25[1] = v84;
    *((_DWORD *)v25 + 2) = v15;
    v25[2] = v87;
  }
LABEL_14:
  v26 = a2;
LABEL_15:
  if ( v10 && (v10[6] & 0x100000) != 0 )
  {
    _InterlockedOr((volatile signed __int32 *)v10 + 12, 0x200000u);
    v16 = (_QWORD *)(a6 + 8);
  }
  if ( v17 != 1 )
    goto LABEL_32;
  memset(v109, 0, 26);
  v118 = 0;
  v116 = 0;
  v117 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  if ( !(unsigned int)KfdIsLayerEmpty(78) )
  {
    *((_QWORD *)&v106 + 1) = *v16;
    LOWORD(v106) = 78;
    v17 = 0;
    *(_DWORD *)((char *)&v106 + 2) = 0;
    WORD3(v106) = 0;
    *(_QWORD *)&v108 = 0;
    *(_QWORD *)&v109[4] = 0;
    *(_DWORD *)&v109[12] = 0;
    *(_QWORD *)&v109[20] = 0;
    v110 = 0;
    *(_QWORD *)&v107 = v10;
    *(_DWORD *)&v109[16] = 1;
    *((_QWORD *)&v107 + 1) = a6;
    WORD4(v108) = v26;
    WORD5(v108) = v20;
    HIDWORD(v108) = v24;
    *(_DWORD *)v109 = 6;
    if ( !v10 )
    {
LABEL_27:
      v28 = KfdClassify2(&v106, &v116);
      if ( !v28 )
      {
        if ( (_DWORD)v116 == 4097 )
          v17 = 2 * (BYTE12(v117) & 1);
        else
          v17 = 1;
      }
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( v28 < 0 || (_DWORD)v116 == 4097 )
      {
        WfpAcquireSpinLock(&gWfpAudit, &LockHandle);
        memset(&dword_140227AE8, 0, 0x378u);
        dword_140227AE8 = 1;
        qword_140227C00 = v117 & 0xFFFFFFFFFFFFLL;
        qword_140227BF0 = (unsigned __int16)v106;
        word_140227C40 = 16;
        dword_140227C08 = 5152;
        byte_140227DA8 = 1;
        if ( (unsigned __int16)v106 == 78 )
        {
          MarshalInTransportLayerAuditV2(&v106, &dword_140227AE8);
        }
        else if ( (unsigned __int16)v106 == 79 )
        {
          MarshalOutTransportLayerAuditV2(&v106, &dword_140227AE8);
        }
        KfdAuditEvent(&dword_140227AE8);
        KfdDiagnoseEvent(&dword_140227AE8);
        if ( gWfpPerProContext )
        {
          v74 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
          if ( *v74 == 4 )
            *v74 = 0;
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      goto LABEL_32;
    }
    if ( *((_DWORD *)v10 + 10) == 6 )
    {
      if ( (v10[6] & 0x10) == 0 )
      {
        v27 = v107;
LABEL_24:
        if ( v27 && *(_DWORD *)(v27 + 680) == 1 )
          *(_DWORD *)&v109[16] |= 2u;
        goto LABEL_27;
      }
      v10 = (PKSPIN_LOCK)v107;
    }
    v27 = v10[62];
    goto LABEL_24;
  }
  v17 = 1;
LABEL_32:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x52537049u);
  return v17;
}

```

## disassembly

```asm
0x1400527a0  push    rbp
0x1400527a2  push    rbx
0x1400527a3  push    rsi
0x1400527a4  push    rdi
0x1400527a5  push    r12
0x1400527a7  push    r13
0x1400527a9  push    r14
0x1400527ab  push    r15
0x1400527ad  lea     rbp, [rsp-0E8h]
0x1400527b5  sub     rsp, 1E8h
0x1400527bc  mov     rax, cs:__security_cookie
0x1400527c3  xor     rax, rsp
0x1400527c6  mov     [rbp+120h+var_48], rax
0x1400527cd  mov     rax, [rbp+120h+arg_48]
0x1400527d4  xor     esi, esi
0x1400527d6  mov     r15, [rbp+120h+arg_28]
0x1400527dd  xorps   xmm0, xmm0
0x1400527e0  mov     r14, [rbp+120h+arg_40]
0x1400527e7  test    rcx, rcx
0x1400527ea  mov     r12, [rbp+120h+arg_20]
0x1400527f1  mov     rdi, rcx
0x1400527f4  cmovz   rdi, rsi
0x1400527f8  mov     [rbp+120h+var_D0], rax
0x1400527fc  mov     eax, 0Ch
0x140052801  mov     [rsp+220h+var_1B6], r9w
0x140052807  cmp     dx, 2
0x14005280b  mov     [rsp+220h+var_1B8], r8w
0x140052811  mov     rbx, rcx
0x140052814  mov     [rsp+220h+var_1BE], dx
0x140052819  mov     ecx, 0Eh
0x14005281e  mov     [rbp+120h+var_1A0], esi
0x140052821  cmovnz  ax, cx
0x140052825  mov     [rsp+220h+var_1B0], esi
0x140052829  mov     [rbp+120h+var_190], eax
0x14005282c  movzx   r13d, dx
0x140052830  xor     eax, eax
0x140052832  mov     [rsp+220h+var_1BF], 1
0x140052837  mov     [rbp+120h+var_158], rax
0x14005283b  mov     dword ptr [rbp+120h+var_150], eax
0x14005283e  mov     word ptr [rbp+120h+var_150+4], ax
0x140052842  mov     [rbp+120h+var_180], rsi
0x140052846  mov     [rbp+120h+var_178], rsi
0x14005284a  mov     dword ptr [rbp+120h+var_78], eax
0x140052850  mov     [rsp+220h+var_1AC], esi
0x140052854  mov     [rsp+220h+var_1C0], al
0x140052858  mov     byte ptr [rsp+220h+var_1BC], al
0x14005285c  movups  xmmword ptr [rbp+120h+P], xmm0
0x140052860  movups  [rbp+120h+var_C8], xmm0
0x140052864  movups  [rbp+120h+var_B8], xmm0
0x140052868  movups  [rbp+120h+var_A8], xmm0
0x14005286c  movups  xmmword ptr [rbp+120h+var_98], xmm0
0x140052873  movups  [rbp+120h+var_88], xmm0
0x14005287a  movups  xmmword ptr [rbp+120h+var_138], xmm0
0x14005287e  cmp     dx, 2
0x140052882  jnz     loc_140052ABC
0x140052888  mov     ecx, 0Ch
0x14005288d  call    cs:__imp_KfdIsLayerEmpty
0x140052894  nop     dword ptr [rax+rax+00h]
0x140052899  test    eax, eax
0x14005289b  jz      loc_140052AD0
0x1400528a1  mov     r14d, esi
0x1400528a4  lea     rbx, [r15+8]
0x1400528a8  mov     esi, 1
0x1400528ad  lea     rcx, [r15+10h]
0x1400528b1  lea     rdx, [r15+20h]
0x1400528b5  mov     rax, cs:qword_140227F20
0x1400528bc  movzx   r12d, [rsp+220h+var_1B8]
0x1400528c2  test    rax, rax
0x1400528c5  jz      loc_1400535C2
0x1400528cb  movzx   r9d, byte ptr [rcx]
0x1400528cf  mov     r8d, 29h ; ')'
0x1400528d5  mov     rdx, [rdx]
0x1400528d8  and     r9b, 1
0x1400528dc  xor     ecx, ecx
0x1400528de  cmp     r13w, 2
0x1400528e3  movzx   r13d, [rsp+220h+var_1B6]
0x1400528e9  cmovnz  ecx, r8d
0x1400528ed  mov     r8, [rbx]
0x1400528f0  mov     [rsp+220h+var_1E0], r8
0x1400528f5  mov     r8, [r15+18h]
0x1400528f9  mov     byte ptr [rsp+220h+var_1E8], r9b
0x1400528fe  mov     r9d, 6
0x140052904  mov     [rsp+220h+var_1F0], rdi
0x140052909  mov     word ptr [rsp+220h+var_1F8], r13w
0x14005290f  mov     word ptr [rsp+220h+var_200], r12w
0x140052915  call    _guard_dispatch_icall
0x14005291a  mov     esi, eax
0x14005291c  cmp     eax, 1
0x14005291f  jnz     short loc_140052934
0x140052921  movzx   eax, [rsp+220h+var_1BF]
0x140052926  mov     rcx, [rbp+120h+var_D0]
0x14005292a  mov     [rcx], al
0x14005292c  test    al, al
0x14005292e  jz      loc_140053114
0x140052934  movzx   r14d, [rsp+220h+var_1BE]
0x14005293a  test    rdi, rdi
0x14005293d  jz      short loc_140052954
0x14005293f  mov     eax, [rdi+30h]
0x140052942  bt      eax, 14h
0x140052946  jnb     short loc_140052954
0x140052948  lock or dword ptr [rdi+30h], 200000h
0x140052950  lea     rbx, [r15+8]
0x140052954  cmp     esi, 1
0x140052957  jnz     loc_140052A7C
0x14005295d  xorps   xmm0, xmm0
0x140052960  xor     eax, eax
0x140052962  movups  [rbp+120h+var_F0], xmm0
0x140052966  mov     ecx, 4Eh ; 'N'
0x14005296b  mov     [rbp+120h+var_50], eax
0x140052971  movups  [rbp+120h+var_F0+0Ah], xmm0
0x140052975  movups  [rbp+120h+var_70], xmm0
0x14005297c  movups  [rbp+120h+var_60], xmm0
0x140052983  movups  [rbp+120h+var_120], xmm0
0x140052987  movups  [rbp+120h+var_110], xmm0
0x14005298b  movups  [rbp+120h+var_100], xmm0
0x14005298f  call    cs:__imp_KfdIsLayerEmpty
0x140052996  nop     dword ptr [rax+rax+00h]
0x14005299b  test    eax, eax
0x14005299d  jnz     loc_140053156
0x1400529a3  mov     rax, [rbx]
0x1400529a6  xor     ecx, ecx
0x1400529a8  mov     qword ptr [rbp+120h+var_120+8], rax
0x1400529ac  mov     eax, 4Eh ; 'N'
0x1400529b1  mov     word ptr [rbp+120h+var_120], ax
0x1400529b5  mov     esi, ecx
0x1400529b7  mov     dword ptr [rbp+120h+var_120+2], ecx
0x1400529ba  mov     word ptr [rbp+120h+var_120+6], cx
0x1400529be  mov     qword ptr [rbp+120h+var_100], rcx
0x1400529c2  mov     word ptr [rbp+120h+var_100+0Eh], cx
0x1400529c6  mov     qword ptr [rbp+120h+var_F0+4], rcx
0x1400529ca  mov     dword ptr [rbp+120h+var_F0+0Ch], ecx
0x1400529cd  mov     [rbp+120h+var_DC], rcx
0x1400529d1  mov     [rbp+120h+var_D4], ecx
0x1400529d4  mov     qword ptr [rbp+120h+var_110], rdi
0x1400529d8  mov     [rbp+120h+var_E0], 1
0x1400529df  mov     qword ptr [rbp+120h+var_110+8], r15
0x1400529e3  mov     word ptr [rbp+120h+var_100+8], r14w
0x1400529e8  mov     word ptr [rbp+120h+var_100+0Ah], r12w
0x1400529ed  mov     word ptr [rbp+120h+var_100+0Ch], r13w
0x1400529f2  mov     dword ptr [rbp+120h+var_F0], 6
0x1400529f9  test    rdi, rdi
0x1400529fc  jz      short loc_140052A29
0x1400529fe  cmp     dword ptr [rdi+28h], 6
0x140052a02  jnz     loc_140052D92
0x140052a08  mov     eax, [rdi+30h]
0x140052a0b  test    al, 10h
0x140052a0d  jnz     loc_140052D8E
0x140052a13  mov     rax, qword ptr [rbp+120h+var_110]
0x140052a17  test    rax, rax
0x140052a1a  jz      short loc_140052A29
0x140052a1c  cmp     dword ptr [rax+2A8h], 1
0x140052a23  jz      loc_14005383C
0x140052a29  lea     rdx, [rbp+120h+var_70]
0x140052a30  lea     rcx, [rbp+120h+var_120]
0x140052a34  call    cs:__imp_KfdClassify2
0x140052a3b  nop     dword ptr [rax+rax+00h]
0x140052a40  mov     ecx, dword ptr [rbp+120h+var_70]
0x140052a46  test    eax, eax
0x140052a48  jnz     short loc_140052A5B
0x140052a4a  cmp     ecx, 1001h
0x140052a50  jz      loc_140053103
0x140052a56  mov     esi, 1
0x140052a5b  xor     edx, edx
0x140052a5d  xorps   xmm0, xmm0
0x140052a60  mov     qword ptr [rbp+120h+LockHandle.OldIrql], rdx
0x140052a64  movups  xmmword ptr [rbp+120h+LockHandle.LockQueue.Next], xmm0
0x140052a68  test    eax, eax
0x140052a6a  js      loc_1400534C2
0x140052a70  cmp     ecx, 1001h
0x140052a76  jz      loc_1400534C2
0x140052a7c  mov     rcx, [rbp+120h+P+8]; P
0x140052a80  test    rcx, rcx
0x140052a83  jz      short loc_140052A96
0x140052a85  mov     edx, 52537049h; Tag
0x140052a8a  call    cs:__imp_ExFreePoolWithTag
0x140052a91  nop     dword ptr [rax+rax+00h]
0x140052a96  mov     eax, esi
0x140052a98  mov     rcx, [rbp+120h+var_48]
0x140052a9f  xor     rcx, rsp; StackCookie
0x140052aa2  call    __security_check_cookie
0x140052aa7  add     rsp, 1E8h
0x140052aae  pop     r15
0x140052ab0  pop     r14
0x140052ab2  pop     r13
0x140052ab4  pop     r12
0x140052ab6  pop     rdi
0x140052ab7  pop     rsi
0x140052ab8  pop     rbx
0x140052ab9  pop     rbp
0x140052aba  retn
0x140052abc  call    cs:__imp_KfdIsLayerEmpty
0x140052ac3  nop     dword ptr [rax+rax+00h]
0x140052ac8  test    eax, eax
0x140052aca  jnz     loc_1400528A1
0x140052ad0  mov     rcx, [r15+38h]
0x140052ad4  mov     r13d, esi
0x140052ad7  mov     rax, [rcx+30h]
0x140052adb  cmp     dword ptr [rax+0Ch], 83h
0x140052ae2  jz      loc_14005313C
0x140052ae8  mov     eax, [rcx+38h]
0x140052aeb  mov     [rsp+220h+var_1B4], eax
0x140052aef  mov     esi, 2
0x140052af4  test    rdi, rdi
0x140052af7  jz      loc_140052E54
0x140052afd  mov     ecx, [rdi+30h]
0x140052b00  bt      ecx, 1Eh
0x140052b04  jb      loc_1400530FC
0x140052b0a  mov     eax, [rdi+30h]
0x140052b0d  bt      eax, 0Bh
0x140052b11  jb      loc_1400530FC
0x140052b17  cmp     [rbp+120h+arg_30], r13b
0x140052b1e  jnz     loc_1400533BB
0x140052b24  mov     eax, [rdi+30h]
0x140052b27  bt      eax, 0Ch
0x140052b2b  jb      short loc_140052B35
0x140052b2d  mov     rcx, rbx
0x140052b30  call    InitializeEndpointContextFromParentContext
0x140052b35  test    r14, r14
0x140052b38  jz      short loc_140052B69
0x140052b3a  cmp     [r14], r13b
0x140052b3d  jnz     loc_140052DE9
0x140052b43  cmp     r15, r12
0x140052b46  jnz     short loc_140052B60
0x140052b48  mov     r8, r12
0x140052b4b  mov     rcx, rbx; SpinLock
0x140052b4e  call    WfpAleCanPermitTcpDatagramGroup
0x140052b53  test    al, al
0x140052b55  jnz     loc_140053160
0x140052b5b  mov     [rsp+220h+var_1C0], 1
0x140052b60  cmp     [r14], r13b
0x140052b63  jnz     loc_140052DE9
0x140052b69  movzx   ecx, word ptr [rdi+1A0h]
0x140052b70  lea     rdx, [rsp+220h+var_1A4]
0x140052b75  xor     ebx, ebx
0x140052b77  mov     [rsp+220h+var_1A4], ebx
0x140052b7b  call    cs:__imp_KfdGetLayerCacheEpoch
0x140052b82  nop     dword ptr [rax+rax+00h]
0x140052b87  mov     eax, [rdi+198h]
0x140052b8d  lea     rdx, [r15+38h]
0x140052b91  mov     r8d, [rsp+220h+var_1A4]
0x140052b96  cmp     eax, r8d
0x140052b99  mov     [rsp+220h+var_1A8], r8d
0x140052b9e  mov     eax, 20h ; ' '
0x140052ba3  setnz   cl
0x140052ba6  test    r15, r15
0x140052ba9  cmovnz  rax, rdx
0x140052bad  mov     rax, [rax]
0x140052bb0  mov     rdx, [rax+10h]
0x140052bb4  mov     eax, [rdi+34h]
0x140052bb7  mov     [rbp+120h+var_198], rdx
0x140052bbb  bt      eax, 13h
0x140052bbf  jb      loc_140053764
0x140052bc5  mov     r14d, ebx
0x140052bc8  xorps   xmm0, xmm0
0x140052bcb  or      r14d, 1
0x140052bcf  test    cl, cl
0x140052bd1  movups  xmmword ptr [rbp+120h+LockHandle.LockQueue.Next], xmm0
0x140052bd5  cmovz   r14d, ebx
0x140052bd9  xor     eax, eax
0x140052bdb  test    byte ptr [rdi+148h], 1
0x140052be2  mov     [rsp+220h+var_1A4], r14d
0x140052be7  mov     qword ptr [rbp+120h+LockHandle.OldIrql], rax
0x140052beb  jz      loc_140053776
0x140052bf1  cmp     cs:gCachePerInterfaceProfileCrossing, eax
0x140052bf7  jz      loc_140053318
0x140052bfd  xor     ebx, ebx
0x140052bff  xor     r12b, r12b
0x140052c02  xor     r14d, r14d
0x140052c05  mov     [rbp+120h+var_188], rbx
0x140052c09  cmp     cs:gAleDebugEnabled, al
0x140052c0f  jnz     loc_1400535E2
0x140052c15  lea     rdx, [rbp+120h+LockHandle]; LockHandle
0x140052c19  mov     rcx, rdi; SpinLock
0x140052c1c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140052c23  nop     dword ptr [rax+rax+00h]
0x140052c28  mov     eax, [rdi+8]
0x140052c2b  test    eax, eax
0x140052c2d  jnz     short loc_140052C28
0x140052c2f  mov     rax, gs:188h
0x140052c38  cmp     cs:gAleDebugEnabled, 1
0x140052c3f  mov     [rdi+10h], rax
0x140052c43  jz      loc_14005361E
0x140052c49  mov     rdx, [rbp+120h+var_198]
0x140052c4d  lea     rcx, [rdi+138h]
0x140052c54  test    rcx, rcx
0x140052c57  jz      short loc_140052C75
0x140052c59  cmp     [rcx-8], rdx
0x140052c5d  jnz     loc_140053783
0x140052c63  mov     r8d, [rcx+0Ch]
0x140052c67  mov     r9d, [rsp+220h+var_1B4]
0x140052c6c  cmp     r8d, r9d
0x140052c6f  jnz     loc_1401C42F7
0x140052c75  xor     eax, eax
0x140052c77  cmp     cs:gAleDebugEnabled, 1
0x140052c7e  mov     ebx, eax
0x140052c80  mov     [rdi+10h], rax
0x140052c84  jnz     short loc_140052C8E
0x140052c86  mov     rbx, [rdi+18h]
0x140052c8a  mov     [rdi+18h], rax
0x140052c8e  lea     rcx, [rbp+120h+LockHandle]; LockHandle
  ... truncated ...
```
