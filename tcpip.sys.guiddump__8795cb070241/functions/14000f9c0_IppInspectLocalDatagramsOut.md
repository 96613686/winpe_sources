# IppInspectLocalDatagramsOut

- ea: `0x14000f9c0`
- end: `0x140010ec4`
- name: `IppInspectLocalDatagramsOut`
- size: `5380`
- prototype: `__int64 __fastcall(unsigned int, __int64, int, __int64, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `39`
- tags: `registry_config, installer_update`

## callers

- `0x140045ad0`

## callees

- `0x14000f128`
- `0x14000f9c0`
- `0x140010ecc`
- `0x140011200`
- `0x140011340`
- `0x1400114b0`
- `0x140011568`
- `0x140012f00`
- `0x140015a70`
- `0x1400162f0`
- `0x140016a10`
- `0x14001bb64`
- `0x14001bf2c`
- `0x14001d570`
- `0x14001d598`
- `0x14005f8f0`
- `0x1400602dc`
- `0x1400605b4`
- `0x140060644`
- `0x1400606f8`
- `0x14006c3e0`
- `0x14007a280`
- `0x14007b310`
- `0x14007b378`
- `0x14007b5e4`
- `0x14007b650`
- `0x1400bbc40`
- `0x1400bd6a8`
- `0x1400be9e0`
- `0x1400de9d0`
- `0x1400f5da0`
- `0x1400f5dc8`
- `0x14012f13c`
- `0x14014ff64`
- `0x140150798`
- `0x1401520b4`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x1400107f3`
- `ntoskrnl!KeLowerIrql` at `0x1400107f3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000fabd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140010182`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140010bb3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000fabd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140010182`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140010bb3`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14000faf5`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400101ba`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14000faf5`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400101ba`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000faa1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000faa1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000fc73`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001094e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000fc73`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001094e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000fce9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010a6f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010bdc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010c09`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010c31`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000fce9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010a6f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010bdc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010c09`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010c31`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001081e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001081e`
- `NETIO!KfdIsLayerEmpty` at `0x14000fb57`
- `NETIO!KfdIsLayerEmpty` at `0x14000ff79`
- `NETIO!KfdIsLayerEmpty` at `0x14000ffa3`
- `NETIO!KfdIsLayerEmpty` at `0x140010047`
- `NETIO!KfdIsLayerEmpty` at `0x14001029c`
- `NETIO!KfdIsLayerEmpty` at `0x1400103d8`
- `NETIO!KfdIsLayerEmpty` at `0x140010834`
- `NETIO!KfdIsLayerEmpty` at `0x14000fb57`
- `NETIO!KfdIsLayerEmpty` at `0x14000ff79`
- `NETIO!KfdIsLayerEmpty` at `0x14000ffa3`
- `NETIO!KfdIsLayerEmpty` at `0x140010047`
- `NETIO!KfdIsLayerEmpty` at `0x14001029c`
- `NETIO!KfdIsLayerEmpty` at `0x1400103d8`
- `NETIO!KfdIsLayerEmpty` at `0x140010834`
- `NETIO!KfdAuditEvent` at `0x140010b89`
- `NETIO!KfdAuditEvent` at `0x140010b89`
- `NETIO!KfdDiagnoseEvent` at `0x140010b9c`
- `NETIO!KfdDiagnoseEvent` at `0x140010b9c`
- `NETIO!KfdIsV6OutTransportFastEmpty` at `0x140010718`
- `NETIO!KfdIsV6OutTransportFastEmpty` at `0x140010718`
- `NETIO!KfdIsV4OutTransportFastEmpty` at `0x14001052a`
- `NETIO!KfdIsV4OutTransportFastEmpty` at `0x14001052a`
- `NETIO!KfdClassify2` at `0x1400100f9`
- `NETIO!KfdClassify2` at `0x1400100f9`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14000fbeb`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14000fbeb`
- `fwpkclnt!FwppNetBufferListAssociateContext` at `0x140010def`
- `fwpkclnt!FwppNetBufferListAssociateContext` at `0x1401c2aa3`
- `fwpkclnt!FwppNetBufferListAssociateContext` at `0x1401c2b13`
- `fwpkclnt!FwppNetBufferListAssociateContext` at `0x140010def`
- `fwpkclnt!FwppNetBufferListAssociateContext` at `0x1401c2aa3`
- `fwpkclnt!FwppNetBufferListAssociateContext` at `0x1401c2b13`

## string_xrefs

- `0x14000fd89`: `AleEdgeIFsLookupCachedAction`
- `0x14001068a`: `ProcessAleForTcpFastPath`
- `0x140010a93`: `ProcessAleForTcpFastPath`

## pseudocode

```c
__int64 __fastcall IppInspectLocalDatagramsOut(
        unsigned int a1,
        __int64 a2,
        int a3,
        __int64 a4,
        unsigned __int16 *a5,
        int a6)
{
  unsigned int v7; // r13d
  int v9; // r12d
  unsigned __int16 *v10; // r15
  unsigned __int16 v11; // si
  __int64 v12; // rdi
  unsigned __int16 v13; // r13
  unsigned __int16 v14; // r12
  __int64 v15; // r15
  __int64 v16; // rdi
  int v17; // eax
  int *v18; // rdi
  int v19; // ecx
  __int64 Next_high; // rcx
  int *v21; // rax
  unsigned int v22; // edi
  __int64 *v23; // rsi
  int v24; // eax
  __int64 v25; // rcx
  int v26; // edx
  __int64 v27; // rcx
  unsigned int ProfileIdFromInterface; // r12d
  __int64 v29; // rcx
  PDEVICE_OBJECT v30; // r8
  int v31; // r15d
  bool v32; // dl
  __int64 v33; // rcx
  int v34; // esi
  __int64 v35; // rdi
  char v36; // r12
  __int64 v37; // r15
  __int64 i; // rcx
  __int64 v39; // r8
  void *v40; // rdi
  unsigned int v41; // edi
  bool v42; // di
  char v43; // cl
  int v44; // eax
  int v45; // r15d
  __int64 v46; // rdi
  __int64 v47; // r15
  __int64 v48; // rsi
  int v49; // r12d
  int v50; // edx
  unsigned int v51; // edi
  int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // rsi
  __int64 v57; // rax
  int v58; // eax
  _DWORD *v59; // rbx
  int v60; // eax
  _DWORD *v61; // rcx
  _DWORD *v62; // rbx
  __int64 v64; // r8
  __int64 v65; // rdx
  int v66; // ecx
  __int64 v67; // rcx
  __int64 v68; // r15
  int v69; // esi
  int v70; // ecx
  int v71; // eax
  __int64 v72; // r13
  __int16 v73; // ax
  int v74; // r12d
  unsigned int v75; // eax
  __int64 v76; // rdx
  int v77; // eax
  int v78; // ecx
  unsigned int v79; // edi
  __int64 *v80; // rcx
  int v81; // eax
  __int64 v82; // rdi
  int v83; // eax
  unsigned __int16 v84; // ax
  __int64 v85; // r8
  __int64 v86; // rax
  int v87; // eax
  __int64 v88; // rdx
  __int64 v89; // r9
  __int64 v90; // r8
  __int64 v91; // rcx
  __int64 v92; // rax
  __int64 v93; // r13
  __int64 v94; // r12
  __int64 v95; // rsi
  __int64 v96; // r15
  int v97; // eax
  _DWORD *v98; // rcx
  char updated; // al
  int v100; // eax
  __int64 v101; // rdx
  __int64 v102; // rax
  __int64 v103; // r8
  __int64 v104; // rax
  __int64 inserted; // rax
  char v106; // cl
  bool v107; // zf
  char v108; // r8
  _QWORD *j; // rax
  char v110; // dl
  __int64 v111; // r8
  __int64 v112; // rax
  __int64 v113; // r8
  __int64 v114; // rax
  int v115; // [rsp+38h] [rbp-110h]
  int v116; // [rsp+40h] [rbp-108h]
  int v117; // [rsp+40h] [rbp-108h]
  unsigned __int16 v118; // [rsp+C8h] [rbp-80h]
  __int16 v119; // [rsp+C8h] [rbp-80h]
  unsigned int v121; // [rsp+D0h] [rbp-78h]
  char v122; // [rsp+D4h] [rbp-74h]
  unsigned __int16 v123; // [rsp+D6h] [rbp-72h]
  __int16 v124; // [rsp+D6h] [rbp-72h]
  char v125; // [rsp+D8h] [rbp-70h]
  __int64 v126; // [rsp+E8h] [rbp-60h]
  __int64 v127; // [rsp+E8h] [rbp-60h]
  __int64 v128; // [rsp+E8h] [rbp-60h]
  __int64 v129; // [rsp+E8h] [rbp-60h]
  int v130; // [rsp+F0h] [rbp-58h] BYREF
  __int64 v131; // [rsp+F8h] [rbp-50h] BYREF
  int v132; // [rsp+100h] [rbp-48h]
  int v133; // [rsp+104h] [rbp-44h]
  __int64 v134; // [rsp+108h] [rbp-40h] BYREF
  __int128 v135; // [rsp+118h] [rbp-30h] BYREF
  __int128 v136; // [rsp+128h] [rbp-20h]
  __int128 v137; // [rsp+138h] [rbp-10h]
  _BYTE v138[28]; // [rsp+148h] [rbp+0h] BYREF
  int v139; // [rsp+164h] [rbp+1Ch]
  struct _KLOCK_QUEUE_HANDLE WatchdogInformation; // [rsp+168h] [rbp+20h] BYREF
  __int128 v141; // [rsp+180h] [rbp+38h] BYREF
  __int128 v142; // [rsp+190h] [rbp+48h]
  int v143; // [rsp+1A0h] [rbp+58h]

  v7 = a1;
  v9 = 2;
  v10 = a5;
  v133 = a3;
  v122 = 0;
  if ( a4 )
  {
    if ( (a1 & 0xFFFFFFFB) == 0 )
    {
      v11 = 2;
      goto LABEL_4;
    }
    if ( a1 == 41 )
    {
      v11 = 23;
LABEL_4:
      v12 = *(_QWORD *)(a2 + 8);
      v13 = a5[1];
      v14 = *a5;
      v15 = *(_QWORD *)a2;
      v126 = v12;
      if ( a3 == 6 )
      {
        v16 = a4 + 632;
        *(_DWORD *)((char *)&v135 + 2) = 0;
        WORD3(v135) = 0;
        WORD5(v136) = 0;
        v17 = *(_DWORD *)(a4 + 648);
        memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
        v141 = 0;
        v142 = 0;
        if ( (v17 & 0x80u) == 0 || *(_DWORD *)(a4 + 652) == EQoSPolicyEpoch )
          goto LABEL_7;
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a4 + 632), &WatchdogInformation);
        while ( *(_DWORD *)(v16 + 8) )
          ;
        if ( *(_DWORD *)(v16 + 20) == EQoSPolicyEpoch )
        {
          KeReleaseInStackQueuedSpinLock(&WatchdogInformation);
          goto LABEL_7;
        }
        v87 = *(_DWORD *)(a4 + 48);
        v134 = 0;
        v88 = 0;
        v131 = 0;
        if ( (v87 & 0x200) == 0 )
        {
          InitializeEndpointContextFromParentContext(a4);
          v88 = v131;
        }
        v89 = *(_QWORD *)(a4 + 480) + 8LL;
        v90 = **(_QWORD **)(*(_QWORD *)(*(_QWORD *)(a4 + 488) + 224LL) + 8LL);
        if ( (*(_DWORD *)(v16 + 16) & 0x40000000) != 0 )
          v88 = v16 + 32;
        if ( v15 )
        {
          v91 = *(_QWORD *)(v15 + 8);
          *((_QWORD *)&v135 + 1) = *(_QWORD *)(v91 + 16);
          LODWORD(v136) = *(_DWORD *)(v91 + 56);
        }
        else
        {
          *((_QWORD *)&v135 + 1) = 0;
          LODWORD(v136) = 0;
        }
        *(_QWORD *)&v138[16] = v88;
        LOWORD(v135) = 127;
        *((_QWORD *)&v137 + 1) = v126;
        WORD2(v136) = v11;
        *(_QWORD *)&v137 = v15;
        WORD3(v136) = v14;
        WORD4(v136) = v13;
        HIDWORD(v136) = 6;
        *(_QWORD *)v138 = v89;
        *(_QWORD *)&v138[8] = v90;
        EQoSPolicyFindExactMatch(&v135, &v141);
        v92 = *(_QWORD *)(v16 + 24);
        if ( v92 )
        {
          v93 = *(_QWORD *)(v92 + 8);
          v94 = *(_QWORD *)(v92 + 16);
        }
        else
        {
          v94 = v134;
          v93 = v134;
        }
        v95 = *((_QWORD *)&v141 + 1);
        if ( *((_QWORD *)&v141 + 1) )
        {
          v96 = v142;
          if ( !(unsigned __int8)QimAttachEQoSProfileToQimContext(v16, *((_QWORD *)&v141 + 1), v142) )
          {
            *(_DWORD *)(v16 + 20) = DWORD2(v142);
            KeReleaseInStackQueuedSpinLock(&WatchdogInformation);
            EQoSDereferenceQoSProfile(v95);
            EQoSDereferenceQoSFlow(v96);
            goto LABEL_7;
          }
        }
        else if ( v92 )
        {
          QimClearEQoSProfileFromQimContext(v16);
        }
        *(_DWORD *)(v16 + 20) = DWORD2(v142);
        KeReleaseInStackQueuedSpinLock(&WatchdogInformation);
        if ( v93 )
        {
          EQoSDereferenceQoSProfile(v93);
          if ( v94 )
            EQoSDereferenceQoSFlow(v94);
        }
        goto LABEL_7;
      }
      if ( a3 != 17 )
        goto LABEL_7;
      v64 = a4 + 632;
      if ( (*(_DWORD *)(a4 + 648) & 0x80u) == 0 )
        goto LABEL_7;
      v65 = *(_QWORD *)(a2 + 48);
      v66 = *(_DWORD *)(a4 + 652);
      v131 = v65;
      if ( v66 != EQoSPolicyEpoch )
      {
        QimUpdateUDPEndpointOnPolicyChange(a4, v11, v15, a4);
        v65 = v131;
        v64 = a4 + 632;
      }
      if ( !*(_QWORD *)(v64 + 24) && (*(_DWORD *)(v64 + 16) & 0x10) != 0 )
      {
        v67 = *(_QWORD *)(v65 + 168);
        *(_QWORD *)(v65 + 168) = 0;
        if ( v67 )
          EQoSDereferenceQoSFlow(v67);
        goto LABEL_7;
      }
      RtlAcquireReadLock((PKSPIN_LOCK)v64);
      v80 = *(__int64 **)(a4 + 656);
      if ( !v80 && (*(_DWORD *)(a4 + 648) & 0x10) != 0 )
      {
        v82 = 0;
        goto LABEL_206;
      }
      v81 = *(_DWORD *)(a4 + 648);
      if ( (v81 & 0x10) != 0 )
      {
        v82 = *v80;
      }
      else
      {
        if ( (v81 & 8) == 0 )
        {
          if ( (v81 & 0x20) != 0 )
          {
            if ( v80 )
            {
              v129 = *v80;
              if ( *v80 )
              {
                v100 = EQoSReferenceQoSFlow(*v80);
                v101 = v129;
                if ( v100 < 0 )
                  v101 = 0;
                v129 = v101;
              }
            }
            else
            {
              v129 = 0;
            }
            _InterlockedDecrement((volatile signed __int32 *)(a4 + 640));
            v82 = QimUDPFindExactMatch(a4, v11, v15, v12);
            if ( v129 )
            {
              if ( v82 )
                EQoSDereferenceQoSFlow(v129);
              else
                v82 = v129;
            }
            goto LABEL_207;
          }
          v82 = 0;
LABEL_206:
          _InterlockedDecrement((volatile signed __int32 *)(a4 + 640));
LABEL_207:
          KeLowerIrql(0);
          QimReplaceQoSFlowHandleNBL(v131, v82);
LABEL_7:
          v10 = a5;
          v9 = 2;
          v7 = a1;
          goto LABEL_8;
        }
        v82 = v80[2];
      }
      if ( (int)EQoSReferenceQoSFlow(v82) < 0 )
        v82 = 0;
      goto LABEL_206;
    }
  }
LABEL_8:
  if ( KeGetCurrentIrql() != 2 )
    goto LABEL_13;
  v18 = *(int **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
  v19 = *v18;
  if ( *v18 == 1 )
  {
    memset(&WatchdogInformation, 0, 20);
    KeQueryDpcWatchdogInformation((PKDPC_WATCHDOG_INFORMATION)&WatchdogInformation);
    Next_high = HIDWORD(WatchdogInformation.LockQueue.Next);
    v21 = v18 + 20;
  }
  else if ( v19 )
  {
    v78 = v19 - 2;
    if ( v78 )
    {
      if ( v78 != 1 )
        goto LABEL_12;
      ++v18[26];
      v21 = v18 + 2;
      Next_high = MEMORY[0xFFFFF78000000008];
    }
    else
    {
      Next_high = MEMORY[0xFFFFF78000000008];
      v21 = v18 + 16;
    }
  }
  else
  {
    *v18 = 3;
    v21 = v18 + 2;
    *(_OWORD *)(v18 + 14) = 0;
    *(_OWORD *)(v18 + 18) = 0;
    *(_OWORD *)(v18 + 22) = 0;
    *(_OWORD *)(v18 + 2) = 0;
    *(_OWORD *)(v18 + 6) = 0;
    *(_OWORD *)(v18 + 10) = 0;
    v18[26] = 1;
    Next_high = MEMORY[0xFFFFF78000000008];
  }
  *((_QWORD *)v21 + 2) = Next_high;
LABEL_12:
  v122 = 1;
LABEL_13:
  if ( !*(_BYTE *)(a2 + 84) )
    goto LABEL_68;
  v22 = 0;
  v23 = 0;
  LODWORD(v134) = 0;
  if ( v7 )
    LOWORD(v9) = 23;
  v132 = v9;
  if ( !a4 )
    goto LABEL_137;
  v24 = *(_DWORD *)(a4 + 48);
  if ( v7 )
  {
    v25 = 50;
    if ( (v24 & 0x100000) == 0 )
      v25 = 46;
  }
  else
  {
    v25 = (v24 & 0x100000) != 0 ? 48LL : 44LL;
  }
  if ( (unsigned __int8)KfdIsLayerEmpty(v25) )
  {
LABEL_137:
    v45 = a6;
    goto LABEL_81;
  }
  v123 = v10[1];
  v118 = *v10;
  if ( (*(_DWORD *)(a4 + 48) & 0x40000000) != 0 || (*(_DWORD *)(a4 + 48) & 0x800) != 0 )
    goto LABEL_228;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 48LL) + 12LL) == 131
    && (unsigned int)TlShimDiscoverPhysicalNexthopInterface(a4, (unsigned __int16)v9, 6, a2) == 259 )
  {
    goto LABEL_166;
  }
  v125 = 0;
  if ( (*(_DWORD *)(a4 + 48) & 0x1000) == 0 )
    InitializeEndpointContextFromParentContext(a4);
  v27 = *(_QWORD *)(a2 + 32);
  if ( *(_DWORD *)(*(_QWORD *)(v27 + 48) + 12LL) == 131 )
    ProfileIdFromInterface = WfpGetProfileIdFromInterface(v27, v26, *(_QWORD *)a2, *(_QWORD *)(a2 + 24), 0);
  else
    ProfileIdFromInterface = *(_DWORD *)(v27 + 56);
  v29 = *(unsigned __int16 *)(a4 + 416);
  v121 = ProfileIdFromInterface;
  LODWORD(v134) = ProfileIdFromInterface;
  v130 = 0;
  KfdGetLayerCacheEpoch(v29, &v130);
  v31 = v130;
  v32 = *(_DWORD *)(a4 + 408) != v130;
  v33 = *(_QWORD *)(*(_QWORD *)(a2 + 32) + 16LL);
  v127 = v33;
  if ( (*(_DWORD *)(a4 + 52) & 0x80000) != 0 )
  {
    v22 = 512;
    _InterlockedAnd((volatile signed __int32 *)(a4 + 52), 0xFFF7FFFF);
  }
  v34 = v22 | 1;
  WatchdogInformation.LockQueue = 0;
  if ( !v32 )
    v34 = v22;
  v107 = (*(_BYTE *)(a4 + 328) & 1) == 0;
  *(_QWORD *)&WatchdogInformation.OldIrql = 0;
  if ( v107 )
  {
    v41 = ProfileIdFromInterface;
    v36 = 0;
    goto LABEL_48;
  }
  if ( gCachePerInterfaceProfileCrossing )
  {
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v131 = 0;
    if ( gAleDebugEnabled )
    {
      v86 = WfpPoolAllocNonPaged(28, 1281715265, &v131);
      v35 = v131;
      v37 = v86;
      if ( !v86 )
        WfpStringCchCopyA("AleEdgeIFsIsProfileCrossing", 28, v131);
    }
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a4, &WatchdogInformation);
    while ( *(_DWORD *)(a4 + 8) )
      ;
    v107 = gAleDebugEnabled == 1;
    *(_QWORD *)(a4 + 16) = KeGetCurrentThread();
    if ( v107 && !v37 )
      *(_QWORD *)(a4 + 24) = v35;
    for ( i = a4 + 312; i; i = *(_QWORD *)i )
    {
      if ( *(_QWORD *)(i - 8) == v127 )
      {
        v39 = *(unsigned int *)(i + 12);
        if ( (_DWORD)v39 != v121 )
        {
          *(_BYTE *)(i + 8) = 0;
          v36 = 1;
          *(_BYTE *)(i + 9) = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
          {
            WPP_SF_qIDDd(WPP_GLOBAL_Control->AttachedDevice, 11, v39, a4, *(_QWORD *)(i - 8), v39, v121);
          }
        }
        break;
      }
    }
    v107 = gAleDebugEnabled == 1;
    v40 = 0;
    *(_QWORD *)(a4 + 16) = 0;
    if ( v107 )
    {
      v40 = *(void **)(a4 + 24);
      *(_QWORD *)(a4 + 24) = 0;
    }
    KeReleaseInStackQueuedSpinLock(&WatchdogInformation);
    if ( gAleDebugEnabled == 1 && v40 )
      ExFreePoolWithTag(v40, 0);
    v31 = v130;
  }
  else
  {
    v70 = *(_DWORD *)(a4 + 332);
    if ( ProfileIdFromInterface == v70 )
    {
      v36 = 0;
    }
    else
    {
      v36 = 1;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        v41 = v121;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
          WPP_SF_qIDDd(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_GLOBAL_Control, a4, 0, v70, v121);
        goto LABEL_47;
      }
    }
  }
  v41 = v121;
LABEL_47:
  v33 = v127;
LABEL_48:
  if ( (*(_DWORD *)(a4 + 52) & 0x8000) != 0 )
  {
    if ( v41 )
    {
      updated = AleEdgeIFsUpdateOriginalProfileId(a4, v41, v30);
      v33 = v127;
      if ( updated )
        _InterlockedAnd((volatile signed __int32 *)(a4 + 52), 0xFFFF7FFF);
    }
  }
  if ( v36 )
    v34 |= 8u;
  if ( (*(_DWORD *)(a4 + 48) & 0x100000) == 0 && (*(_DWORD *)(a4 + 52) & 0x800) != 0 )
  {
    v34 |= 0x80u;
    _InterlockedAnd((volatile signed __int32 *)(a4 + 52), 0xFFFFF7FF);
  }
  if ( gCachePerInterfaceProfileCrossing && v36 )
    goto LABEL_62;
  v107 = (*(_BYTE *)(a4 + 328) & 1) == 0;
  memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
  if ( v107 )
  {
LABEL_193:
    v34 |= 4u;
LABEL_62:
    v43 = v125;
    goto LABEL_63;
  }
  if ( *(_DWORD *)(a4 + 336) != v31
    || *(_QWORD *)(a4 + 304) != v33
    || !*(_BYTE *)(a4 + 321)
    || (v43 = *(_BYTE *)(a4 + 321), v125 = v43, *(_DWORD *)(a4 + 336) != v31) )
  {
    v42 = 0;
    AleAcquireEndpointLockEx((PKSPIN_LOCK)a4, &WatchdogInformation);
    if ( *(_DWORD *)(a4 + 336) == v31 )
    {
      if ( *(_QWORD *)(a4 + 304) == v127 )
      {
        v106 = *(_BYTE *)(a4 + 321);
        v107 = v106 == 0;
        v108 = v125;
        if ( v106 )
          v108 = *(_BYTE *)(a4 + 321);
LABEL_317:
        v42 = !v107;
        v125 = v108;
      }
      else
      {
        for ( j = *(_QWORD **)(a4 + 312); j; j = (_QWORD *)*j )
        {
          if ( *(j - 1) == v127 )
          {
            v110 = *(_BYTE *)(a4 + 321);
            v107 = v110 == 0;
            v108 = v125;
            if ( v110 )
              v108 = *(_BYTE *)(a4 + 321);
            goto LABEL_317;
          }
        }
      }
    }
    AleReleaseEndpointLock(a4, &WatchdogInformation);
    if ( v42 )
      goto LABEL_62;
    goto LABEL_193;
  }
LABEL_63:
  if ( (*(_DWORD *)(a4 + 52) & 0x800000) != 0 )
  {
    v34 |= 0x4000u;
    _InterlockedAnd((volatile signed __int32 *)(a4 + 52), 0xFF7FFFFF);
  }
  if ( v34 )
  {
    v44 = 0;
  }
  else
  {
    v31 = 0;
    v44 = 1;
    if ( v43 == 1 )
    {
      v45 = a6;
      goto LABEL_78;
    }
  }
  v117 = v31;
  v45 = a6;
  v52 = AleInspectTcpDatagram(a4, (unsigned __int16)v132, v118, v123, 0, a2, a6, v117, v34, v43, v121, v44);
  if ( v52 != 1 )
  {
    if ( v52 )
    {
      v77 = v52 - 2;
      if ( !v77 )
      {
        v22 = 3;
        goto LABEL_79;
      }
      if ( v77 == 1 )
      {
        v22 = 2;
        goto LABEL_79;
      }
    }
    v22 = 1;
    goto LABEL_79;
  }
LABEL_78:
  v22 = 0;
LABEL_79:
  if ( v22 )
    goto LABEL_109;
  v23 = &v134;
LABEL_81:
  if ( v7 )
    v53 = 71;
  else
    v53 = 70;
  if ( !(unsigned __int8)KfdIsLayerEmpty(v53) )
  {
    v97 = WfpTlShimInspectStreamPacket(a4, (unsigned __int16)v132, *a5, a5[1], 0, a2, v45);
    if ( v97 == 1 )
    {
      v22 = 0;
      goto LABEL_84;
    }
    if ( v97 )
    {
      v71 = v97 - 2;
      if ( !v71 )
      {
LABEL_166:
        v22 = 3;
        goto LABEL_109;
      }
      if ( v71 == 1 )
      {
        v22 = 2;
        goto LABEL_109;
      }
    }
LABEL_228:
    v22 = 1;
    goto LABEL_109;
  }
LABEL_84:
  if ( v7 )
  {
    if ( !(unsigned int)KfdIsLayerEmpty(18) )
      goto LABEL_124;
  }
  else if ( !(unsigned int)KfdIsLayerEmpty(16) )
  {
    goto LABEL_124;
  }
  if ( !*(_BYTE *)(a2 + 44) )
  {
LABEL_87:
    if ( !gWfpIPSecDispatchTable || (int)gWfpIPSecDispatchTable() <= 0 )
    {
      if ( *(_BYTE *)(a2 + 44) )
      {
        if ( a4 )
        {
          v68 = *(_QWORD *)(a2 + 48);
          if ( (*(_DWORD *)(a4 + 48) & 0x200000) == 0 )
          {
            v69 = 0;
            if ( (*(_DWORD *)(a4 + 52) & 0x2000) == 0 )
              goto LABEL_293;
            _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a4 + 448) + 496LL));
            v111 = 16;
            if ( v7 )
              LOWORD(v111) = 18;
            v112 = FwppNetBufferListAssociateContext(
                     1,
                     v68,
                     v111,
                     *(_QWORD *)(a4 + 448),
                     5,
                     0,
                     0,
                     0,
                     &TlShimNblEventNotifyFn,
                     0);
            if ( !v112 || (v69 = v112) == 0 )
            {
LABEL_293:
              if ( (*(_DWORD *)(a4 + 48) & 0x2000000) != 0
                && ((*(_DWORD *)(a4 + 52) & 0x2000) == 0 || *(_DWORD *)(a4 + 40) == 17) )
              {
                inserted = *(_QWORD *)(a4 + 536);
                if ( !inserted )
                  inserted = WfpAleQueryOrInsertEndpointHandle(a4);
                v113 = 16;
                if ( v7 )
                  LOWORD(v113) = 18;
                v114 = FwppNetBufferListAssociateContext(1, v68, v113, inserted, 4, 0, 0, 0, &TlShimNblEventNotifyFn, 0);
                if ( v114 )
                  v69 = v114;
              }
            }
            if ( (*(_DWORD *)(a4 + 56) & 2) != 0 )
            {
              v102 = WfpAleQueryOrInsertEndpointHandle(a4);
              v103 = 16;
              if ( v7 )
                LOWORD(v103) = 18;
              v104 = FwppNetBufferListAssociateContext(1, v68, v103, v102, 9, 0, 0, 0, &TlShimNblEventNotifyFn, 0);
              if ( v104 )
                v69 = v104;
            }
            if ( v69 )
            {
              v22 = 1;
              *(_DWORD *)(*(_QWORD *)(a2 + 48) + 136LL) &= ~0x800000u;
LABEL_108:
              if ( (*(_DWORD *)(a4 + 52) & 0x200000) != 0 && (*(_DWORD *)(a4 + 52) & 0x400000) == 0 )
              {
                v84 = FamilyToLayerIdOutboundTransport((unsigned __int16)v132, v54, *(_QWORD *)(a2 + 48));
                WfpTagAppIdToNblForRio(v84, a4, v85);
                _InterlockedOr((volatile signed __int32 *)(a4 + 52), 0x400000u);
                _InterlockedAnd((volatile signed __int32 *)(a4 + 52), 0xFFDFFFFF);
              }
              goto LABEL_109;
            }
          }
        }
      }
LABEL_90:
      *(_DWORD *)(*(_QWORD *)(a2 + 48) + 136LL) &= ~0x800000u;
      if ( v22 )
        goto LABEL_107;
      v55 = *(_QWORD *)(*(_QWORD *)(a2 + 32) + 48LL);
      if ( *(_DWORD *)(v55 + 12) == 131 )
      {
        if ( a4 )
        {
          v83 = *(_DWORD *)(v55 + 16);
          if ( v83 == 14 || v83 == 1 )
            _InterlockedOr((volatile signed __int32 *)(a4 + 52), 0x1000u);
        }
      }
      v143 = 0;
      *(_OWORD *)v138 = 0;
      v56 = a4;
      if ( !a4 )
        v56 = 0;
      v141 = 0;
      v142 = 0;
      v135 = 0;
      v136 = 0;
      v137 = 0;
      *(_OWORD *)&v138[10] = 0;
      if ( (unsigned int)KfdIsLayerEmpty(79) )
      {
        v22 = 0;
        goto LABEL_107;
      }
      v22 = 1;
      *((_QWORD *)&v135 + 1) = *(_QWORD *)(a2 + 48);
      LOWORD(v135) = 79;
      *(_DWORD *)((char *)&v137 + 10) = *(_DWORD *)a5;
      *(_DWORD *)((char *)&v135 + 2) = 0;
      WORD3(v135) = 0;
      HIWORD(v137) = 0;
      memset(&v138[4], 0, 24);
      v139 = 0;
      v136 = (unsigned __int64)v56;
      *(_QWORD *)&v137 = a2;
      *(_DWORD *)v138 = v133;
      WORD4(v137) = IpProtoToAddrFamily(v7);
      if ( !v56 )
      {
LABEL_102:
        v58 = KfdClassify2(&v135, &v141);
        if ( !v58 )
        {
          if ( (_DWORD)v141 == 4097 )
            v22 = (2 * (BYTE12(v142) & 1)) | 1;
          else
            v22 = 0;
        }
        v54 = 0;
        memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
        if ( v58 < 0 || (_DWORD)v141 == 4097 )
        {
          WfpAcquireSpinLock(&gWfpAudit, &WatchdogInformation);
          memset(&dword_14022BB08, 0, 0x378u);
          dword_14022BB08 = 1;
          qword_14022BC20 = v142 & 0xFFFFFFFFFFFFLL;
          qword_14022BC10 = (unsigned __int16)v135;
          word_14022BC60 = 16;
          dword_14022BC28 = 5152;
          byte_14022BDC8 = 1;
          if ( (unsigned __int16)v135 == 78 )
          {
            MarshalInTransportLayerAuditV2(&v135, &dword_14022BB08);
          }
          else if ( (unsigned __int16)v135 == 79 )
          {
            MarshalOutTransportLayerAuditV2(&v135, &dword_14022BB08);
          }
          KfdAuditEvent(&dword_14022BB08);
          KfdDiagnoseEvent(&dword_14022BB08);
          if ( gWfpPerProContext )
          {
            v98 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
            if ( *v98 == 4 )
              *v98 = 0;
          }
          KeReleaseInStackQueuedSpinLock(&WatchdogInformation);
        }
LABEL_107:
        if ( !a4 )
          goto LABEL_109;
        goto LABEL_108;
      }
      if ( *(_DWORD *)(v56 + 40) == 6 )
      {
        if ( (*(_DWORD *)(v56 + 48) & 0x10) == 0 )
        {
          v57 = v136;
LABEL_99:
          if ( v57 && *(_DWORD *)(v57 + 680) == 1 )
            *(_DWORD *)&v138[16] |= 2u;
          goto LABEL_102;
        }
        v56 = v136;
      }
      v57 = *(_QWORD *)(v56 + 496);
      goto LABEL_99;
    }
    goto LABEL_124;
  }
  if ( v7 )
  {
    if ( (unsigned int)KfdIsLayerEmpty(67) )
      goto LABEL_87;
  }
  else if ( (unsigned int)KfdIsLayerEmpty(66) )
  {
    goto LABEL_87;
  }
LABEL_124:
  if ( a4 )
  {
    v22 = WfpTlShimInspectSendTcpDatagram((PKSPIN_LOCK)a4, a2, a6, (__int64)v23);
    goto LABEL_90;
  }
LABEL_68:
  v46 = *(_QWORD *)a2;
  v47 = *(_QWORD *)(a2 + 8);
  v48 = *(_QWORD *)(a2 + 32);
  v49 = *(_DWORD *)(a2 + 40);
  if ( a4 && *(_DWORD *)(*(_QWORD *)(v48 + 48) + 12LL) == 131 )
  {
    v76 = 2;
    if ( v7 )
      LOWORD(v76) = 23;
    if ( (unsigned int)TlShimDiscoverPhysicalNexthopInterface(a4, v76, (unsigned int)v133, a2) == 259 )
    {
      v22 = 3;
      goto LABEL_109;
    }
  }
  if ( v133 == 6 && (!a4 || (*(_DWORD *)(a4 + 48) & 0x10) == 0) )
  {
    if ( v7 && v7 != 4 )
    {
      if ( v7 != 41 )
      {
LABEL_150:
        v50 = 0;
        goto LABEL_73;
      }
      LOWORD(v130) = 23;
      if ( (unsigned __int8)KfdIsV6OutTransportFastEmpty() )
      {
LABEL_173:
        v72 = *(_QWORD *)(a2 + 48);
        v73 = a5[1];
        v119 = v73;
        v124 = *a5;
        if ( a4 )
        {
          v128 = *(_QWORD *)(a2 + 24);
          if ( (*(_DWORD *)(a4 + 48) & 0x800) != 0 )
          {
            v74 = 0;
            WfpReportInetAction(0, "ProcessAleForTcpFastPath", 9773);
          }
          else
          {
            v131 = 0;
            WfpGetEpochContext(a4, (unsigned __int16)v130, 6, 0, (__int64)&v131);
            LOWORD(v116) = v119;
            LOWORD(v115) = v124;
            v74 = TlShimOptionalReauthorizeConnection(
                    a4,
                    (unsigned __int16)v130,
                    a4,
                    0,
                    v131,
                    6,
                    v115,
                    v116,
                    0,
                    v46,
                    v47,
                    v128,
                    v72,
                    v48,
                    v49,
                    0,
                    0,
                    a6,
                    0,
                    *(_QWORD *)(a4 + 448));
          }
          v73 = v119;
        }
        else
        {
          v74 = 1;
        }
        v75 = IpSecTlPacketsOutProcessing(a1, v46, v47, 6, v124, v73, v72, v74, a4);
        v51 = v75;
        if ( v72 )
          *(_DWORD *)(v72 + 136) &= ~0x800000u;
        if ( a4 )
        {
          if ( v75 == 1 )
          {
            WfpAleCheckAndMarkTcpFlowEdgeTraversed(v48, a4);
            goto LABEL_74;
          }
        }
        else if ( v75 == 1 )
        {
          goto LABEL_74;
        }
        WfpReportInetAction(v75, "ProcessAleForTcpFastPath", 9861);
        goto LABEL_74;
      }
LABEL_171:
      v50 = 23;
      goto LABEL_73;
    }
    v130 = 2;
    if ( (unsigned __int8)KfdIsV4OutTransportFastEmpty() )
      goto LABEL_173;
  }
  if ( v7 != 4 && v7 )
  {
    if ( v7 != 41 )
      goto LABEL_150;
    goto LABEL_171;
  }
  v50 = 2;
LABEL_73:
  v51 = WfpProcessOutTransportStackIndication(
          v133,
          v50,
          *a5,
          a5[1],
          a2,
          v46,
          v47,
          *(_BYTE *)(a2 + 16),
          v48,
          v49,
          *(_BYTE *)(a2 + 44),
          *(_QWORD *)(a2 + 24),
          *(NET_BUFFER_LIST **)(a2 + 48),
          (__int64)a5,
          a6,
          (PKSPIN_LOCK)a4,
          *(_QWORD *)(a2 + 56),
          *(_DWORD *)(a2 + 64),
          *(_QWORD *)(a2 + 72),
          *(_DWORD *)(a2 + 80),
          *(_QWORD *)(a2 + 88),
          *(_DWORD *)(a2 + 96),
          0);
LABEL_74:
  if ( v51 == 1 )
  {
    v22 = 0;
    *(_DWORD *)(*(_QWORD *)(a2 + 48) + 136LL) &= ~0x800000u;
    goto LABEL_109;
  }
  if ( !v51 )
    goto LABEL_254;
  v79 = v51 - 2;
  if ( !v79 )
  {
    v22 = 3;
    *(_DWORD *)(*(_QWORD *)(a2 + 48) + 136LL) &= ~0x800000u;
    goto LABEL_109;
  }
  if ( v79 == 1 )
  {
    v22 = 2;
    *(_DWORD *)(*(_QWORD *)(a2 + 48) + 136LL) &= ~0x800000u;
  }
  else
  {
LABEL_254:
    v22 = 1;
    *(_DWORD *)(*(_QWORD *)(a2 + 48) + 136LL) &= ~0x800000u;
  }
LABEL_109:
  if ( v122 )
  {
    v59 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    switch ( *v59 )
    {
      case 1:
        memset(&WatchdogInformation, 0, 20);
        KeQueryDpcWatchdogInformation((PKDPC_WATCHDOG_INFORMATION)&WatchdogInformation);
        v60 = HIDWORD(WatchdogInformation.LockQueue.Next);
        v61 = v59 + 26;
        v62 = v59 + 24;
        break;
      case 2:
        v61 = v59 + 22;
        v62 = v59 + 20;
        v60 = MEMORY[0xFFFFF78000000008];
        break;
      case 3:
        --v59[26];
        v60 = MEMORY[0xFFFFF78000000008];
        if ( !v59[26] )
          *v59 = 0;
        v61 = v59 + 8;
        v62 = v59 + 6;
        break;
      default:
        return v22;
    }
    *v61 += v60 - *v62;
  }
  return v22;
}

```

## disassembly

```asm
0x14000f9c0  mov     r11, rsp
0x14000f9c3  push    rbp
0x14000f9c4  push    rbx
0x14000f9c5  push    rdi
0x14000f9c6  lea     rbp, [r11-0B8h]
0x14000f9cd  sub     rsp, 1E0h
0x14000f9d4  mov     rax, cs:__security_cookie
0x14000f9db  xor     rax, rsp
0x14000f9de  mov     [rbp+0B0h+var_50], rax
0x14000f9e2  mov     [r11-20h], rsi
0x14000f9e6  mov     eax, r8d
0x14000f9e9  mov     [r11-28h], r12
0x14000f9ed  mov     rbx, r9
0x14000f9f0  mov     [r11-30h], r13
0x14000f9f4  mov     r13d, ecx
0x14000f9f7  mov     [r11-38h], r14
0x14000f9fb  mov     r14, rdx
0x14000f9fe  mov     [r11-40h], r15
0x14000fa02  mov     r12d, 2
0x14000fa08  mov     r15, [rbp+0B0h+arg_20]
0x14000fa0f  mov     [rbp+0B0h+var_12C], ecx
0x14000fa12  mov     ecx, 17h
0x14000fa17  mov     [rbp+0B0h+var_118], r15
0x14000fa1b  mov     [rbp+0B0h+var_F4], eax
0x14000fa1e  mov     [rbp+0B0h+var_124], 0
0x14000fa22  test    r9, r9
0x14000fa25  jz      short loc_14000FAA1
0x14000fa27  test    r13d, 0FFFFFFFBh
0x14000fa2e  jnz     loc_14001036F
0x14000fa34  mov     esi, r12d
0x14000fa37  mov     rdi, [rdx+8]
0x14000fa3b  movzx   r13d, word ptr [r15+2]
0x14000fa40  movzx   r12d, word ptr [r15]
0x14000fa44  mov     r15, [rdx]
0x14000fa47  mov     [rbp+0B0h+var_110], rdi
0x14000fa4b  cmp     eax, 6
0x14000fa4e  jnz     loc_1400101EF
0x14000fa54  xor     eax, eax
0x14000fa56  lea     rdi, [r9+278h]
0x14000fa5d  xorps   xmm0, xmm0
0x14000fa60  mov     qword ptr [rbp+0B0h+WatchdogInformation+10h], rax
0x14000fa64  mov     [rbp+0B0h+var_DE], eax
0x14000fa67  mov     [rbp+0B0h+var_DA], ax
0x14000fa6b  mov     [rbp+0B0h+var_C6], ax
0x14000fa6f  mov     eax, [rdi+10h]
0x14000fa72  movups  xmmword ptr [rbp+0B0h+WatchdogInformation], xmm0
0x14000fa76  movups  [rbp+0B0h+var_78], xmm0
0x14000fa7a  movups  [rbp+0B0h+var_68], xmm0
0x14000fa7e  test    al, al
0x14000fa80  jns     short loc_14000FA93
0x14000fa82  mov     ecx, [rdi+14h]
0x14000fa85  mov     eax, cs:EQoSPolicyEpoch
0x14000fa8b  cmp     ecx, eax
0x14000fa8d  jnz     loc_140010947
0x14000fa93  mov     r15, [rbp+0B0h+var_118]
0x14000fa97  mov     r12d, 2
0x14000fa9d  mov     r13d, [rbp+0B0h+var_12C]
0x14000faa1  call    cs:__imp_KeGetCurrentIrql
0x14000faa8  nop     dword ptr [rax+rax+00h]
0x14000faad  mov     rsi, 0FFFFF78000000008h
0x14000fab7  cmp     al, 2
0x14000fab9  jnz     short loc_14000FB10
0x14000fabb  xor     ecx, ecx; ProcNumber
0x14000fabd  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000fac4  nop     dword ptr [rax+rax+00h]
0x14000fac9  lea     ecx, [rax+rax*8]
0x14000facc  mov     rax, cs:gWfpPerProContext
0x14000fad3  shl     ecx, 3
0x14000fad6  mov     rdi, [rcx+rax]
0x14000fada  mov     ecx, [rdi]
0x14000fadc  cmp     ecx, 1
0x14000fadf  jnz     loc_140010321
0x14000fae5  xorps   xmm0, xmm0
0x14000fae8  lea     rcx, [rbp+0B0h+WatchdogInformation]; WatchdogInformation
0x14000faec  xor     eax, eax
0x14000faee  movups  xmmword ptr [rbp+0B0h+WatchdogInformation], xmm0
0x14000faf2  mov     dword ptr [rbp+0B0h+WatchdogInformation+10h], eax
0x14000faf5  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14000fafc  nop     dword ptr [rax+rax+00h]
0x14000fb01  mov     ecx, dword ptr [rbp+0B0h+WatchdogInformation+4]
0x14000fb04  lea     rax, [rdi+50h]
0x14000fb08  mov     [rax+10h], rcx
0x14000fb0c  mov     [rbp+0B0h+var_124], 1
0x14000fb10  cmp     byte ptr [r14+54h], 0
0x14000fb15  jz      loc_14000FDF7
0x14000fb1b  xor     edi, edi
0x14000fb1d  xor     esi, esi
0x14000fb1f  test    r13d, r13d
0x14000fb22  mov     dword ptr [rbp+0B0h+var_F0], edi
0x14000fb25  mov     eax, 17h
0x14000fb2a  cmovnz  r12w, ax
0x14000fb2f  mov     [rbp+0B0h+var_F8], r12d
0x14000fb33  test    rbx, rbx
0x14000fb36  jz      loc_140010381
0x14000fb3c  mov     eax, [rbx+30h]
0x14000fb3f  test    r13d, r13d
0x14000fb42  jnz     loc_1400103A7
0x14000fb48  bt      eax, 14h
0x14000fb4c  jnb     loc_14001028D
0x14000fb52  mov     ecx, 30h ; '0'
0x14000fb57  call    cs:__imp_KfdIsLayerEmpty
0x14000fb5e  nop     dword ptr [rax+rax+00h]
0x14000fb63  test    al, al
0x14000fb65  jnz     loc_140010381
0x14000fb6b  movzx   eax, word ptr [r15+2]
0x14000fb70  mov     [rbp+0B0h+var_122], ax
0x14000fb74  movzx   eax, word ptr [r15]
0x14000fb78  mov     [rbp+0B0h+var_130], ax
0x14000fb7c  mov     eax, [rbx+30h]
0x14000fb7f  bt      eax, 1Eh
0x14000fb83  jb      loc_14001093D
0x14000fb89  mov     eax, [rbx+30h]
0x14000fb8c  bt      eax, 0Bh
0x14000fb90  jb      loc_14001093D
0x14000fb96  mov     rax, [r14+20h]
0x14000fb9a  mov     rcx, [rax+30h]
0x14000fb9e  cmp     dword ptr [rcx+0Ch], 83h
0x14000fba5  jz      loc_14001041E
0x14000fbab  mov     eax, [rbx+30h]
0x14000fbae  mov     [rbp+0B0h+var_120], sil
0x14000fbb2  bt      eax, 0Ch
0x14000fbb6  jnb     loc_140010280
0x14000fbbc  mov     rcx, [r14+20h]
0x14000fbc0  mov     rax, [rcx+30h]
0x14000fbc4  cmp     dword ptr [rax+0Ch], 83h
0x14000fbcb  jz      loc_140010794
0x14000fbd1  mov     r12d, [rcx+38h]
0x14000fbd5  movzx   ecx, word ptr [rbx+1A0h]
0x14000fbdc  lea     rdx, [rbp+0B0h+var_108]
0x14000fbe0  mov     [rbp+0B0h+var_128], r12d
0x14000fbe4  mov     dword ptr [rbp+0B0h+var_F0], r12d
0x14000fbe8  mov     [rbp+0B0h+var_108], esi
0x14000fbeb  call    cs:__imp_KfdGetLayerCacheEpoch
0x14000fbf2  nop     dword ptr [rax+rax+00h]
0x14000fbf7  mov     ecx, [rbx+198h]
0x14000fbfd  mov     r15d, [rbp+0B0h+var_108]
0x14000fc01  cmp     ecx, r15d
0x14000fc04  mov     rcx, [r14+20h]
0x14000fc08  mov     eax, [rbx+34h]
0x14000fc0b  setnz   dl
0x14000fc0e  mov     [rbp+0B0h+var_108], r15d
0x14000fc12  mov     rcx, [rcx+10h]
0x14000fc16  mov     [rbp+0B0h+var_110], rcx
0x14000fc1a  bt      eax, 13h
0x14000fc1e  jb      loc_140010E57
0x14000fc24  mov     esi, edi
0x14000fc26  xorps   xmm0, xmm0
0x14000fc29  or      esi, 1
0x14000fc2c  test    dl, dl
0x14000fc2e  movups  xmmword ptr [rbp+0B0h+WatchdogInformation], xmm0
0x14000fc32  cmovz   esi, edi
0x14000fc35  xor     eax, eax
0x14000fc37  test    byte ptr [rbx+148h], 1
0x14000fc3e  mov     qword ptr [rbp+0B0h+WatchdogInformation+10h], rax
0x14000fc42  jz      loc_140010E69
0x14000fc48  cmp     cs:gCachePerInterfaceProfileCrossing, eax
0x14000fc4e  jz      loc_1400104B3
0x14000fc54  xor     edi, edi
0x14000fc56  xor     r12b, r12b
0x14000fc59  xor     r15d, r15d
0x14000fc5c  mov     [rbp+0B0h+var_100], rdi
0x14000fc60  cmp     cs:gAleDebugEnabled, al
0x14000fc66  jnz     loc_1400108EF
0x14000fc6c  lea     rdx, [rbp+0B0h+WatchdogInformation]; LockHandle
0x14000fc70  mov     rcx, rbx; SpinLock
0x14000fc73  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000fc7a  nop     dword ptr [rax+rax+00h]
0x14000fc7f  nop
0x14000fc80  mov     eax, [rbx+8]
0x14000fc83  test    eax, eax
0x14000fc85  jnz     short loc_14000FC80
0x14000fc87  mov     rax, gs:188h
0x14000fc90  cmp     cs:gAleDebugEnabled, 1
0x14000fc97  mov     [rbx+10h], rax
0x14000fc9b  jz      loc_14001092B
0x14000fca1  mov     rdx, [rbp+0B0h+var_110]
0x14000fca5  lea     rcx, [rbx+138h]
0x14000fcac  test    rcx, rcx
0x14000fcaf  jz      short loc_14000FCCC
0x14000fcb1  cmp     [rcx-8], rdx
0x14000fcb5  jnz     loc_140010E74
0x14000fcbb  mov     r8d, [rcx+0Ch]
0x14000fcbf  mov     r9d, [rbp+0B0h+var_128]
0x14000fcc3  cmp     r8d, r9d
0x14000fcc6  jnz     loc_1401C29B0
0x14000fccc  xor     eax, eax
0x14000fcce  cmp     cs:gAleDebugEnabled, 1
0x14000fcd5  mov     edi, eax
0x14000fcd7  mov     [rbx+10h], rax
0x14000fcdb  jnz     short loc_14000FCE5
0x14000fcdd  mov     rdi, [rbx+18h]
0x14000fce1  mov     [rbx+18h], rax
0x14000fce5  lea     rcx, [rbp+0B0h+WatchdogInformation]; LockHandle
0x14000fce9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000fcf0  nop     dword ptr [rax+rax+00h]
0x14000fcf5  cmp     cs:gAleDebugEnabled, 1
0x14000fcfc  jz      loc_140010810
0x14000fd02  mov     r15d, [rbp+0B0h+var_108]
0x14000fd06  mov     edi, [rbp+0B0h+var_128]
0x14000fd09  mov     rcx, [rbp+0B0h+var_110]
0x14000fd0d  mov     eax, [rbx+34h]
0x14000fd10  bt      eax, 0Fh
0x14000fd14  jb      loc_140010C99
0x14000fd1a  mov     eax, esi
0x14000fd1c  or      eax, 8
0x14000fd1f  test    r12b, r12b
0x14000fd22  cmovnz  esi, eax
0x14000fd25  mov     eax, [rbx+30h]
0x14000fd28  bt      eax, 14h
0x14000fd2c  jb      short loc_14000FD3B
0x14000fd2e  mov     eax, [rbx+34h]
0x14000fd31  bt      eax, 0Bh
0x14000fd35  jb      loc_1400106FE
0x14000fd3b  cmp     cs:gCachePerInterfaceProfileCrossing, 0
0x14000fd42  jz      short loc_14000FD49
0x14000fd44  test    r12b, r12b
0x14000fd47  jnz     short loc_14000FDC3
0x14000fd49  xor     eax, eax
0x14000fd4b  xorps   xmm0, xmm0
0x14000fd4e  test    byte ptr [rbx+148h], 1
0x14000fd55  movups  xmmword ptr [rbp+0B0h+WatchdogInformation], xmm0
0x14000fd59  mov     qword ptr [rbp+0B0h+WatchdogInformation+10h], rax
0x14000fd5d  jz      loc_140010731
0x14000fd63  mov     eax, [rbx+150h]
0x14000fd69  cmp     eax, r15d
0x14000fd6c  jnz     short loc_14000FD89
0x14000fd6e  mov     rax, [rbx+130h]
0x14000fd75  cmp     rax, rcx
0x14000fd78  jnz     short loc_14000FD89
0x14000fd7a  movzx   eax, byte ptr [rbx+141h]
0x14000fd81  test    al, al
0x14000fd83  jnz     loc_14001038D
0x14000fd89  lea     r8, aAleedgeifslook; "AleEdgeIFsLookupCachedAction"
0x14000fd90  mov     rcx, rbx; SpinLock
0x14000fd93  lea     rdx, [rbp+0B0h+WatchdogInformation]; LockHandle
0x14000fd97  xor     dil, dil
0x14000fd9a  call    AleAcquireEndpointLockEx
0x14000fd9f  mov     eax, [rbx+150h]
0x14000fda5  cmp     eax, r15d
0x14000fda8  jz      loc_140010E7C
0x14000fdae  lea     rdx, [rbp+0B0h+WatchdogInformation]
0x14000fdb2  mov     rcx, rbx
0x14000fdb5  call    AleReleaseEndpointLock
0x14000fdba  test    dil, dil
0x14000fdbd  jz      loc_140010731
0x14000fdc3  mov     ecx, dword ptr [rbp+0B0h+var_120]
0x14000fdc6  mov     eax, [rbx+34h]
0x14000fdc9  bt      eax, 17h
0x14000fdcd  jb      loc_140010EAA
0x14000fdd3  test    esi, esi
0x14000fdd5  jnz     loc_14000FF08
0x14000fddb  xor     r15d, r15d
0x14000fdde  mov     eax, 1
0x14000fde3  cmp     cl, al
0x14000fde5  jnz     loc_14000FF0A
0x14000fdeb  mov     r15d, [rbp+0B0h+arg_28]
0x14000fdf2  jmp     loc_14000FF5D
0x14000fdf7  mov     rdi, [r14]
0x14000fdfa  mov     r15, [r14+8]
0x14000fdfe  mov     rsi, [r14+20h]
0x14000fe02  mov     r12d, [r14+28h]
0x14000fe06  test    rbx, rbx
0x14000fe09  jz      short loc_14000FE1C
0x14000fe0b  mov     rax, [rsi+30h]
0x14000fe0f  cmp     dword ptr [rax+0Ch], 83h
0x14000fe16  jz      loc_14001069D
0x14000fe1c  cmp     [rbp+0B0h+var_F4], 6
0x14000fe20  jz      loc_1400103F1
0x14000fe26  cmp     r13d, 4
0x14000fe2a  jnz     loc_140010506
0x14000fe30  mov     edx, 2; int
0x14000fe35  mov     r8, [rbp+0B0h+var_118]
0x14000fe39  mov     eax, [r14+60h]
0x14000fe3d  mov     ecx, [rbp+0B0h+var_F4]; int
0x14000fe40  mov     byte ptr [rsp+0B0h], 0; char
0x14000fe48  movzx   r9d, word ptr [r8+2]; int
0x14000fe4d  mov     [rsp+1F0h+var_148], eax; int
0x14000fe54  mov     rax, [r14+58h]
0x14000fe58  mov     [rsp+1F0h+var_150], rax; __int64
0x14000fe60  mov     eax, [r14+50h]
0x14000fe64  mov     [rsp+1F0h+var_158], eax; int
0x14000fe6b  mov     rax, [r14+48h]
0x14000fe6f  mov     [rsp+1F0h+var_160], rax; __int64
0x14000fe77  mov     eax, [r14+40h]
0x14000fe7b  mov     [rsp+1F0h+var_168], eax; int
0x14000fe82  mov     rax, [r14+38h]
0x14000fe86  mov     [rsp+1F0h+var_170], rax; __int64
0x14000fe8e  mov     eax, [rbp+0B0h+arg_28]
0x14000fe94  mov     [rsp+1F0h+SpinLock], rbx; SpinLock
0x14000fe99  mov     [rsp+1F0h+var_180], eax; int
0x14000fe9d  mov     rax, [r14+30h]
0x14000fea1  mov     [rsp+1F0h+var_188], r8; __int64
0x14000fea6  movzx   r8d, word ptr [r8]; int
0x14000feaa  mov     [rsp+1F0h+netBufferList], rax; netBufferList
0x14000feaf  mov     rax, [r14+18h]
0x14000feb3  mov     [rsp+1F0h+var_198], rax; __int64
0x14000feb8  movzx   eax, byte ptr [r14+2Ch]
0x14000febd  mov     [rsp+1F0h+var_1A0], al; char
0x14000fec1  movzx   eax, byte ptr [r14+10h]
0x14000fec6  mov     [rsp+1F0h+var_1A8], r12d; int
  ... truncated ...
```
