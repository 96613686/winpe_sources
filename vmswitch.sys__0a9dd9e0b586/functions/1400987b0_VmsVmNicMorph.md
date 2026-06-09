# VmsVmNicMorph

- ea: `0x1400987b0`
- end: `0x1400994ef`
- name: `VmsVmNicMorph`
- size: `3391`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400bf5a8`

## callees

- `0x140027a64`
- `0x14002e0f0`
- `0x14003a450`
- `0x14003e804`
- `0x140046e5c`
- `0x140046f1c`
- `0x140065cc8`
- `0x140065f10`
- `0x14006a330`
- `0x14006a7f8`
- `0x14006b084`
- `0x140070a98`
- `0x14008497c`
- `0x1400867a0`
- `0x140087fbc`
- `0x14008b7e0`
- `0x14008e6ac`
- `0x1400987b0`
- `0x140099618`
- `0x140099770`
- `0x140100de8`
- `0x140194524`
- `0x14019ad0c`
- `0x14019ae2c`
- `0x14019af88`
- `0x1401a1db8`
- `0x1401a2bdc`
- `0x1401a6c8c`
- `0x1401a8a80`
- `0x1401aed84`
- `0x1401af2b0`
- `0x1401affac`
- `0x1401b0644`
- `0x1401bb904`
- `0x1401bbbd4`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtection` at `0x1400992da`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x1400992da`
- `ntoskrnl!KeInitializeEvent` at `0x140098da2`
- `ntoskrnl!KeInitializeEvent` at `0x140098da2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140099363`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14009937e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140099399`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400993b4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140099363`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14009937e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140099399`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400993b4`
- `ntoskrnl!ZwClose` at `0x140098b54`
- `ntoskrnl!ZwClose` at `0x140098b54`
- `ntoskrnl!KeInitializeMutex` at `0x1400991dc`
- `ntoskrnl!KeInitializeMutex` at `0x1400991dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140098b69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140098b69`
- `ntoskrnl!ExAllocatePool2` at `0x1400989b4`
- `ntoskrnl!ExAllocatePool2` at `0x1400989b4`
- `NDIS!NdisFreeNetBufferListPool` at `0x140098a92`
- `NDIS!NdisFreeNetBufferListPool` at `0x140098ab1`
- `NDIS!NdisFreeNetBufferListPool` at `0x140098a92`
- `NDIS!NdisFreeNetBufferListPool` at `0x140098ab1`
- `NDIS!NdisReleaseRWLock` at `0x140098886`
- `NDIS!NdisReleaseRWLock` at `0x140098b3f`
- `NDIS!NdisReleaseRWLock` at `0x140098ba5`
- `NDIS!NdisReleaseRWLock` at `0x1401bca5d`
- `NDIS!NdisReleaseRWLock` at `0x140098886`
- `NDIS!NdisReleaseRWLock` at `0x140098b3f`
- `NDIS!NdisReleaseRWLock` at `0x140098ba5`
- `NDIS!NdisReleaseRWLock` at `0x1401bca5d`
- `vmbkmclr!VmbConvertVmbusHandleToKernelHandle` at `0x1400990a6`
- `vmbkmclr!VmbConvertVmbusHandleToKernelHandle` at `0x1400990a6`
- `vmbkmclr!VmbChannelEnable` at `0x140099270`
- `vmbkmclr!VmbChannelEnable` at `0x140099270`

## pseudocode

```c
__int64 __fastcall VmsVmNicMorph(
        __int64 a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        const UNICODE_STRING *a4,
        char *a5,
        char a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        unsigned int a10,
        char a11,
        unsigned __int8 a12,
        char a13,
        __int64 a14,
        char a15,
        char a16,
        char a17)
{
  int v18; // edx
  int v19; // eax
  int v20; // r8d
  bool v21; // zf
  char v22; // al
  char v23; // r9
  int *v24; // rsi
  char v25; // r11
  int v26; // r9d
  int v27; // ecx
  __int64 Pool2; // rax
  int v29; // edx
  int v30; // r8d
  __int64 v31; // rsi
  int v32; // r15d
  PVOID *v33; // rbx
  PVOID v34; // rcx
  PVOID v35; // rcx
  PVOID v36; // rcx
  int v38; // r15d
  _QWORD *v39; // rax
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rbx
  int v43; // edx
  int WorkItem; // eax
  int v45; // edx
  int v46; // eax
  int v47; // edx
  int v48; // eax
  int v49; // edx
  int v50; // eax
  int v51; // edx
  int v52; // eax
  int v53; // edx
  int v54; // eax
  int v55; // edx
  int v56; // eax
  int v57; // edx
  int v58; // eax
  int v59; // edx
  int v60; // r8d
  int v61; // eax
  int v62; // edx
  unsigned __int32 v63; // ebx
  unsigned __int32 v64; // edx
  __int64 v65; // rcx
  _BYTE v66[32]; // [rsp+0h] [rbp-118h] BYREF
  __int64 v67; // [rsp+20h] [rbp-F8h]
  int v68; // [rsp+58h] [rbp-C0h]
  char v69; // [rsp+C0h] [rbp-58h] BYREF
  char v70; // [rsp+C1h] [rbp-57h]
  struct _LOCK_STATE_EX LockState; // [rsp+C4h] [rbp-54h] BYREF
  int NetBufferListPool; // [rsp+C8h] [rbp-50h]
  PVOID P; // [rsp+D0h] [rbp-48h]
  _BYTE *v74; // [rsp+D8h] [rbp-40h]

  v74 = v66;
  NetBufferListPool = -1073741823;
  v70 = 0;
  P = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v69 = 0;
  VmsOmObjectLockExclusive(a1, &LockState, 0);
  v19 = *(_DWORD *)(a1 + 1872);
  if ( v19 )
  {
    NetBufferListPool = -1073741808;
    LOBYTE(v18) = 2;
    WPP_RECORDER_SF_ld(VmsIfrNicLog, v18, 20, 15, (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids, v19, 16);
    local_unwind_0(v66, &loc_140098A04);
  }
  *(_DWORD *)(a1 + 1872) = 3;
  v70 = 1;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
  *(_QWORD *)(a1 + 3280) = a7;
  if ( !VmsIsHypercopyEnabled || (v21 = (unsigned __int8)HviIsKernelApertureAvailable() == 0, v22 = 0, v21) )
    v22 = 1;
  *(_BYTE *)(a1 + 1877) = v22;
  v23 = *a5;
  if ( (*a5 & 1) != 0 || !*(_DWORD *)a5 && !*((_WORD *)a5 + 2) )
  {
    NetBufferListPool = -1073741811;
    v25 = v23;
    v26 = 16;
    v68 = -1073741811;
    goto LABEL_80;
  }
  *(_DWORD *)(a1 + 3342) = *(_DWORD *)a5;
  *(_WORD *)(a1 + 3346) = *((_WORD *)a5 + 2);
  v24 = (int *)(a1 + 3336);
  LOBYTE(v20) = a6;
  VmsOmNicAssignMacAddress(a1, (_DWORD)a5, v20, a1 + 3336, (__int64)&v69);
  if ( v69 && !a6 )
  {
    NetBufferListPool = -1073741800;
    v25 = *a5;
    v26 = 17;
    v68 = -1073741800;
LABEL_80:
    WPP_RECORDER_SF_DDDDDDd(
      (unsigned __int8)a5[4],
      (unsigned __int8)a5[3],
      (unsigned __int8)a5[2],
      v26,
      v67,
      v25,
      a5[1],
      a5[2],
      a5[3],
      a5[4],
      a5[5],
      v68);
    goto LABEL_14;
  }
  v27 = *v24;
  *v24 = *v24;
  *(_WORD *)(a1 + 3340) = *(_WORD *)(a1 + 3340);
  *(_DWORD *)(a1 + 1838) = v27;
  *(_WORD *)(a1 + 1842) = *(_WORD *)(a1 + 3340);
  *(_DWORD *)(a1 + 2104) = *(_DWORD *)a5;
  *(_WORD *)(a1 + 2108) = *((_WORD *)a5 + 2);
  *(_DWORD *)(a1 + 1832) = *(_DWORD *)a5;
  *(_WORD *)(a1 + 1836) = *((_WORD *)a5 + 2);
  Pool2 = ExAllocatePool2(64, 1856, 1314288470);
  v31 = Pool2;
  P = (PVOID)Pool2;
  if ( Pool2 )
  {
    v38 = 768;
    if ( a10 < 0x300 )
      v38 = a10;
    *(_DWORD *)(Pool2 + 860) = v38;
    *(_DWORD *)(Pool2 + 520) = 0;
    *(_DWORD *)(Pool2 + 524) = 3;
    *(_DWORD *)(Pool2 + 256) = 0;
    *(_DWORD *)(Pool2 + 704) = 28;
    *(_DWORD *)(Pool2 + 600) = 1;
    *(_BYTE *)(Pool2 + 536) = 1;
    v39 = (_QWORD *)(Pool2 + 776);
    v39[1] = v39;
    *v39 = v39;
    memset((void *)(a1 + 3460), 0, 0x60u);
    *(_BYTE *)(v31 + 928) = a11;
    *(_QWORD *)(v31 + 680) = a1;
    *(_QWORD *)(a1 + 3312) = v31;
    *(_QWORD *)(v31 + 1664) = v31 + 1656;
    *(_QWORD *)(v31 + 1656) = v31 + 1656;
    *(_QWORD *)(v31 + 1680) = v31 + 1672;
    *(_QWORD *)(v31 + 1672) = v31 + 1672;
    v40 = NvIoEnvMemAlloc(88, 2017675598);
    v42 = v40;
    if ( v40 )
    {
      *(_QWORD *)(v40 + 56) = a1;
      *(_QWORD *)(v40 + 80) = a1 + 1992;
      *(_DWORD *)v40 = 1;
      *(_QWORD *)(v40 + 8) = 0;
      *(_DWORD *)(v40 + 16) = 0;
      KeInitializeEvent((PRKEVENT)(v40 + 24), SynchronizationEvent, 0);
      LOBYTE(v41) = 0;
    }
    else
    {
      LOBYTE(v41) = 24;
    }
    *(_QWORD *)(v31 + 1616) = v42;
    NetBufferListPool = NvIoEnvConvertToResult(v41);
    if ( NetBufferListPool >= 0 )
    {
      NetBufferListPool = VmsVmNicPvtCreateNetBufferListPool(v31);
      if ( NetBufferListPool >= 0 )
      {
        *(_DWORD *)(v31 + 384) = 0;
        *(_BYTE *)(v31 + 801) = 0;
        *(_QWORD *)(v31 + 808) = 0;
        if ( !*(_QWORD *)(a1 + 2096) )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v43,
            19,
            19,
            (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
            (__int64)"objNic->NvIoWorkerQueue != NULL");
          if ( !*(_QWORD *)(a1 + 2096) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        WorkItem = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2096), 3, v31 + 816);
        NetBufferListPool = WorkItem;
        if ( WorkItem >= 0 )
        {
          *(_QWORD *)(v31 + 824) = 0;
          v46 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2096), 4, v31 + 832);
          NetBufferListPool = v46;
          if ( v46 >= 0 )
          {
            *(_QWORD *)(a1 + 9456) = a1 + 9448;
            *(_QWORD *)(a1 + 9448) = a1 + 9448;
            v48 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2096), 2, v31 + 848);
            NetBufferListPool = v48;
            if ( v48 >= 0 )
            {
              v50 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2096), 11, v31 + 1624);
              NetBufferListPool = v50;
              if ( v50 >= 0 )
              {
                v52 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2096), 12, v31 + 1640);
                NetBufferListPool = v52;
                if ( v52 >= 0 )
                {
                  v54 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2096), 13, v31 + 1688);
                  NetBufferListPool = v54;
                  if ( v54 >= 0 )
                  {
                    v56 = VmbConvertVmbusHandleToKernelHandle(a8, v31 + 8);
                    NetBufferListPool = v56;
                    if ( v56 >= 0 )
                    {
                      v58 = VmsQueueGroupInitialize(a1 + 5696);
                      NetBufferListPool = v58;
                      if ( v58 >= 0 )
                      {
                        VmsScalerInitialize(a1 + 9344, 1, a1);
                        NetBufferListPool = VmsQueueGroupPushScaler(a1 + 5696, a1 + 9344);
                        if ( !NetBufferListPool )
                        {
                          *(_DWORD *)(a1 + 5736) ^= ((unsigned __int8)*(_DWORD *)(a1 + 5736)
                                                   ^ (unsigned __int8)(a15 << 6))
                                                  & 0x40;
                          *(_BYTE *)(a1 + 9464) = a16;
                          LOBYTE(v60) = a13;
                          NetBufferListPool = VmsVmNicChannelAllocatePrimaryChannel(v31, a9, v60, a14, a17);
                          if ( NetBufferListPool >= 0 )
                          {
                            *(_BYTE *)(v31 + 672) = 1;
                            KeInitializeMutex((PRKMUTEX)(v31 + 1464), 0xFFFFu);
                            *(_DWORD *)(v31 + 1456) = 1;
                            if ( !a12
                              || (NetBufferListPool = VmsVmPDInitializeGuestPacketDirect(a1, v31), NetBufferListPool >= 0) )
                            {
                              *(_DWORD *)(v31 + 448) = 7;
                              if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u
                                || LOWORD(WPP_GLOBAL_Control->DeviceType) )
                              {
                                WPP_RECORDER_SF_(
                                  WPP_GLOBAL_Control->DeviceExtension,
                                  0,
                                  10,
                                  28,
                                  (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids);
                              }
                              *(_DWORD *)(v31 + 516) = 1;
                              NetBufferListPool = VmsVmNicPvtCreateRndisDevice(v31);
                              if ( NetBufferListPool >= 0 )
                              {
                                v61 = VmbChannelEnable(*(_QWORD *)(v31 + 16));
                                NetBufferListPool = v61;
                                if ( v61 >= 0 )
                                {
                                  while ( 1 )
                                  {
                                    _m_prefetchw((const void *)(v31 + 128));
                                    v63 = *(_DWORD *)(v31 + 128);
                                    v64 = v63 - 1;
                                    if ( ((v63 - 1) & 0xFFFFFFFB) != 0 )
                                      break;
                                    if ( v63 == _InterlockedCompareExchange(
                                                  (volatile signed __int32 *)(v31 + 128),
                                                  v63 | 2,
                                                  v63) )
                                    {
                                      ExReInitializeRundownProtection((PEX_RUNDOWN_REF)(v31 + 120));
                                      goto LABEL_77;
                                    }
                                  }
                                  LOBYTE(v64) = 2;
                                  WPP_RECORDER_SF_d(
                                    VmsIfrLog,
                                    v64,
                                    20,
                                    12,
                                    (__int64)WPP_7f9c2ac2fa983072b55dd04e2689be0b_Traceguids,
                                    *(_DWORD *)(v31 + 128));
                                  MicrosoftTelemetryAssertTriggeredArgsMsgKM(
                                    v65,
                                    v63,
                                    0,
                                    "VmsVmChannelStateMarkEnabled: unexpected state");
LABEL_77:
                                  NetBufferListPool = RndisDevChannelInit(*(_QWORD *)v31, 0);
                                  if ( NetBufferListPool >= 0 )
                                  {
                                    VmsVmNicPvtCreateControlPacketPool(v31);
                                    *(_DWORD *)(v31 + 240) = 0;
                                    *(_DWORD *)(v31 + 244) = 0;
                                    *(_DWORD *)(v31 + 248) = 0;
                                    RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 616), a2);
                                    RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 1288), a2);
                                    RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 2112), a3);
                                    RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 2640), a4);
                                    *(_QWORD *)(a1 + 3320) = &VmsVmNicPvtContextCleanup;
                                    *(_QWORD *)(a1 + 3328) = VmsVmNicPvtPrepareForDelete;
                                    *(_DWORD *)(a1 + 1872) = 3;
                                    *(_QWORD *)(a1 + 3176) = VmsVmNicPvtPacketForward;
                                    *(_QWORD *)(a1 + 3168) = &VmsVmNicPvtPacketRouted;
                                    *(_QWORD *)(a1 + 3200) = VmsVmNicPvtLinkStateChanged;
                                    *(_QWORD *)(a1 + 3208) = VmsVmNicPvtSendStatus;
                                    *(_QWORD *)(a1 + 3216) = VmsVmNicPvtSendRelearnPacket;
                                    *(_QWORD *)(a1 + 3224) = VmsVmNicPvtEnableOptimizations;
                                    *(_QWORD *)(a1 + 3232) = VmsVmNicPvtDisableOptimizations;
                                    *(_QWORD *)(a1 + 3248) = VmsVmNicPvtSetPortInfo;
                                    *(_QWORD *)(a1 + 3256) = VmsVmNicPvtPacketShortLifetime;
                                    *(_QWORD *)(a1 + 3264) = VmsVmNicPvtDeliverPDBuffers;
                                    *(_QWORD *)(a1 + 3240) = VmsVmNicPvtAllowRef;
                                    VmsOmNicPacketFilterAssign(a1, 0);
                                    *(_DWORD *)(a1 + 68) = 1;
                                    NetBufferListPool = 0;
                                  }
                                }
                                else
                                {
                                  LOBYTE(v62) = 2;
                                  WPP_RECORDER_SF_id(
                                    VmsIfrNicLog,
                                    v62,
                                    20,
                                    29,
                                    (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
                                    *(_QWORD *)(v31 + 16),
                                    v61);
                                }
                              }
                            }
                          }
                        }
                      }
                      else
                      {
                        LOBYTE(v59) = 2;
                        WPP_RECORDER_SF_d(
                          VmsIfrNicLog,
                          v59,
                          20,
                          27,
                          (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
                          v58);
                      }
                    }
                    else
                    {
                      LOBYTE(v57) = 2;
                      WPP_RECORDER_SF_id(
                        VmsIfrNicLog,
                        v57,
                        20,
                        26,
                        (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
                        a8,
                        v56);
                    }
                  }
                  else
                  {
                    LOBYTE(v55) = 2;
                    WPP_RECORDER_SF_d(
                      VmsIfrNicLog,
                      v55,
                      20,
                      25,
                      (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
                      v54);
                  }
                }
                else
                {
                  LOBYTE(v53) = 2;
                  WPP_RECORDER_SF_d(
                    VmsIfrNicLog,
                    v53,
                    20,
                    24,
                    (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
                    v52);
                }
              }
              else
              {
                LOBYTE(v51) = 2;
                WPP_RECORDER_SF_d(
                  VmsIfrNicLog,
                  v51,
                  20,
                  23,
                  (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
                  v50);
              }
            }
            else
            {
              LOBYTE(v49) = 2;
              WPP_RECORDER_SF_d(
                VmsIfrNicLog,
                v49,
                20,
                22,
                (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
                v48);
            }
          }
          else
          {
            LOBYTE(v47) = 2;
            WPP_RECORDER_SF_d(VmsIfrNicLog, v47, 20, 21, (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids, v46);
          }
        }
        else
        {
          LOBYTE(v45) = 2;
          WPP_RECORDER_SF_d(
            VmsIfrNicLog,
            v45,
            20,
            20,
            (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
            WorkItem);
        }
      }
    }
    LOBYTE(a10) = v38;
  }
  else
  {
    NetBufferListPool = -1073741670;
    WPP_RECORDER_SF_Ld(VmsIfrNicLog, v29, v30, 18, (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids, 64, 154);
  }
LABEL_14:
  v32 = NetBufferListPool;
  if ( NetBufferListPool < 0 )
  {
    VmsQueueGroupUninitialize((void *)(a1 + 5696));
    v33 = (PVOID *)P;
    if ( P )
    {
      if ( *((_QWORD *)P + 202) )
      {
        NvIoDeleteContext();
        v33[202] = 0;
      }
      VmsVmbDestroyChannels(v33);
      VmsVmNicPvtPauseHostStack((unsigned int)v33[85]);
      *(_QWORD *)(a1 + 3312) = 0;
      *(_QWORD *)(a1 + 3320) = 0;
      if ( *v33 )
      {
        RndisDevDestroy(*v33);
        *v33 = 0;
      }
      v34 = v33[28];
      if ( v34 )
      {
        NdisFreeNetBufferListPool(v34);
        v33[28] = 0;
      }
      v35 = v33[29];
      if ( v35 )
      {
        NdisFreeNetBufferListPool(v35);
        v33[29] = 0;
      }
      NvIoFreeWorkItem(v33 + 102);
      NvIoFreeWorkItem(v33 + 104);
      NvIoFreeWorkItem(v33 + 106);
      NvIoFreeWorkItem(v33 + 203);
      NvIoFreeWorkItem(v33 + 205);
      NvIoFreeWorkItem(v33 + 211);
      VmsOmObjectLockExclusive(a1, &LockState, 0);
      if ( v33[207] != v33 + 207 )
        VmsVmNicFlushIcmpRequestIrps(v33);
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
      v36 = v33[1];
      if ( v36 )
      {
        ZwClose(v36);
        v33[1] = 0;
      }
      ExFreePoolWithTag(v33, 0);
    }
    if ( v70 )
    {
      VmsOmObjectLockExclusive(a1, &LockState, 0);
      *(_DWORD *)(a1 + 1872) = 0;
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
    }
  }
  if ( v69 )
    v32 = -1073741800;
  if ( v32 < 0 )
    WPP_RECORDER_SF_qZZZDDDDDDdIqqLddd(
      (_DWORD)a2,
      a12,
      (unsigned __int8)a5[5],
      (unsigned __int8)a5[4],
      v67,
      a1,
      (__int64)a2,
      (__int64)a3,
      (__int64)a4,
      *a5,
      a5[1],
      a5[2],
      a5[3],
      a5[4],
      a5[5],
      a6,
      a7,
      a8,
      a9,
      a10,
      a11,
      a12,
      v32);
  return (unsigned int)v32;
}

```

## disassembly

```asm
0x1400987b0  mov     r11, rsp
0x1400987b3  mov     [r11+20h], r9
0x1400987b7  mov     [r11+18h], r8
0x1400987bb  mov     [r11+10h], rdx
0x1400987bf  mov     [r11+8], rcx
0x1400987c3  push    rbx
0x1400987c4  push    rsi
0x1400987c5  push    rdi
0x1400987c6  push    r12
0x1400987c8  push    r13
0x1400987ca  push    r14
0x1400987cc  push    r15
0x1400987ce  sub     rsp, 0E0h
0x1400987d5  mov     [rsp+118h+var_40], rsp
0x1400987dd  mov     r14, rcx
0x1400987e0  mov     dword ptr [r11-50h], 0C0000001h
0x1400987e8  xor     edi, edi
0x1400987ea  mov     [r11-57h], dil
0x1400987ee  mov     [rsp+118h+P], rdi
0x1400987f6  xor     eax, eax
0x1400987f8  mov     [r11-54h], ax
0x1400987fd  mov     [r11-52h], al
0x140098801  mov     [r11-58h], dil
0x140098805  xor     r8d, r8d
0x140098808  lea     rdx, [r11-54h]
0x14009880c  call    VmsOmObjectLockExclusive
0x140098811  mov     eax, [r14+750h]
0x140098818  test    eax, eax
0x14009881a  jz      short loc_140098861
0x14009881c  mov     ecx, 0C0000010h
0x140098821  mov     [rsp+118h+var_50], ecx
0x140098828  lea     r9d, [rdi+0Fh]
0x14009882c  mov     dword ptr [rsp+118h+var_E8], ecx
0x140098830  mov     dword ptr [rsp+118h+var_F0], eax
0x140098834  lea     r12, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x14009883b  mov     [rsp+118h+var_F8], r12
0x140098840  lea     r8d, [rdi+14h]
0x140098844  mov     dl, 2
0x140098846  mov     rcx, cs:VmsIfrNicLog
0x14009884d  call    WPP_RECORDER_SF_ld
0x140098852  lea     rdx, loc_140098A04
0x140098859  mov     rcx, rsp
0x14009885c  call    _local_unwind_0
0x140098861  mov     dword ptr [r14+750h], 3
0x14009886c  mov     r13d, 1
0x140098872  mov     [rsp+118h+var_57], r13b
0x14009887a  lea     rdx, [rsp+118h+LockState]; LockState
0x140098882  mov     rcx, [r14+38h]; Lock
0x140098886  call    cs:__imp_NdisReleaseRWLock
0x14009888d  nop     dword ptr [rax+rax+00h]
0x140098892  mov     rax, [rsp+118h+arg_30]
0x14009889a  mov     [r14+0CD0h], rax
0x1400988a1  cmp     cs:VmsIsHypercopyEnabled, 0
0x1400988a8  jz      short loc_1400988B6
0x1400988aa  call    HviIsKernelApertureAvailable
0x1400988af  test    al, al
0x1400988b1  mov     al, dil
0x1400988b4  jnz     short loc_1400988B9
0x1400988b6  mov     al, r13b
0x1400988b9  mov     rbx, [rsp+118h+arg_20]
0x1400988c1  mov     [r14+755h], al
0x1400988c8  movzx   r9d, byte ptr [rbx]
0x1400988cc  test    r13b, r9b
0x1400988cf  jnz     loc_14009949B
0x1400988d5  mov     eax, [rbx]
0x1400988d7  test    eax, eax
0x1400988d9  jnz     short loc_1400988E5
0x1400988db  cmp     [rbx+4], di
0x1400988df  jz      loc_14009949B
0x1400988e5  mov     [r14+0D0Eh], eax
0x1400988ec  movzx   eax, word ptr [rbx+4]
0x1400988f0  mov     [r14+0D12h], ax
0x1400988f8  lea     rsi, [r14+0D08h]
0x1400988ff  lea     rax, [rsp+118h+var_58]
0x140098907  mov     [rsp+118h+var_F8], rax
0x14009890c  mov     r9, rsi
0x14009890f  mov     r8b, [rsp+118h+arg_28]
0x140098917  mov     rdx, rbx
0x14009891a  mov     rcx, r14
0x14009891d  call    VmsOmNicAssignMacAddress
0x140098922  cmp     [rsp+118h+var_58], dil
0x14009892a  jz      short loc_140098955
0x14009892c  cmp     [rsp+118h+arg_28], dil
0x140098934  jnz     short loc_140098955
0x140098936  mov     esi, 0C0000018h
0x14009893b  mov     [rsp+118h+var_50], esi
0x140098942  movzx   r11d, byte ptr [rbx]
0x140098946  mov     r9d, 11h
0x14009894c  mov     [rsp+118h+var_C0], esi
0x140098950  jmp     loc_1400994B4
0x140098955  mov     ecx, [rsi]
0x140098957  mov     [rsi], ecx
0x140098959  movzx   eax, word ptr [rsi+4]
0x14009895d  mov     [r14+0D0Ch], ax
0x140098965  mov     [r14+72Eh], ecx
0x14009896c  movzx   eax, word ptr [rsi+4]
0x140098970  mov     [r14+732h], ax
0x140098978  mov     eax, [rbx]
0x14009897a  mov     [r14+838h], eax
0x140098981  movzx   eax, word ptr [rbx+4]
0x140098985  mov     [r14+83Ch], ax
0x14009898d  mov     eax, [rbx]
0x14009898f  mov     [r14+728h], eax
0x140098996  movzx   eax, word ptr [rbx+4]
0x14009899a  mov     [r14+72Ch], ax
0x1400989a2  mov     ebx, 740h
0x1400989a7  mov     r8d, 4E567356h
0x1400989ad  mov     edx, ebx
0x1400989af  mov     ecx, 40h ; '@'
0x1400989b4  call    cs:__imp_ExAllocatePool2
0x1400989bb  nop     dword ptr [rax+rax+00h]
0x1400989c0  mov     rsi, rax
0x1400989c3  mov     [rsp+118h+P], rax
0x1400989cb  test    rax, rax
0x1400989ce  jnz     loc_140098CC2
0x1400989d4  mov     eax, 0C000009Ah
0x1400989d9  mov     [rsp+118h+var_50], eax
0x1400989e0  lea     r9d, [rsi+12h]
0x1400989e4  mov     dword ptr [rsp+118h+var_E8], eax
0x1400989e8  mov     dword ptr [rsp+118h+var_F0], ebx
0x1400989ec  lea     r12, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x1400989f3  mov     [rsp+118h+var_F8], r12
0x1400989f8  mov     rcx, cs:VmsIfrNicLog
0x1400989ff  call    WPP_RECORDER_SF_Ld
0x140098a04  mov     r15d, [rsp+118h+var_50]
0x140098a0c  xor     edi, edi
0x140098a0e  mov     r14, [rsp+118h+arg_0]
0x140098a16  test    r15d, r15d
0x140098a19  jns     loc_140098BB1
0x140098a1f  lea     rcx, [r14+1640h]; void *
0x140098a26  call    VmsQueueGroupUninitialize
0x140098a2b  mov     rbx, [rsp+118h+P]
0x140098a33  test    rbx, rbx
0x140098a36  jz      loc_140098B75
0x140098a3c  mov     rcx, [rbx+650h]
0x140098a43  test    rcx, rcx
0x140098a46  jz      short loc_140098A54
0x140098a48  call    NvIoDeleteContext
0x140098a4d  mov     [rbx+650h], rdi
0x140098a54  mov     rcx, rbx
0x140098a57  call    VmsVmbDestroyChannels
0x140098a5c  mov     rcx, [rbx+2A8h]
0x140098a63  call    VmsVmNicPvtPauseHostStack
0x140098a68  mov     [r14+0CF0h], rdi
0x140098a6f  mov     [r14+0CF8h], rdi
0x140098a76  mov     rcx, [rbx]; P
0x140098a79  test    rcx, rcx
0x140098a7c  jz      short loc_140098A86
0x140098a7e  call    RndisDevDestroy
0x140098a83  mov     [rbx], rdi
0x140098a86  mov     rcx, [rbx+0E0h]; PoolHandle
0x140098a8d  test    rcx, rcx
0x140098a90  jz      short loc_140098AA5
0x140098a92  call    cs:__imp_NdisFreeNetBufferListPool
0x140098a99  nop     dword ptr [rax+rax+00h]
0x140098a9e  mov     [rbx+0E0h], rdi
0x140098aa5  mov     rcx, [rbx+0E8h]; PoolHandle
0x140098aac  test    rcx, rcx
0x140098aaf  jz      short loc_140098AC4
0x140098ab1  call    cs:__imp_NdisFreeNetBufferListPool
0x140098ab8  nop     dword ptr [rax+rax+00h]
0x140098abd  mov     [rbx+0E8h], rdi
0x140098ac4  lea     rcx, [rbx+330h]
0x140098acb  call    NvIoFreeWorkItem
0x140098ad0  lea     rcx, [rbx+340h]
0x140098ad7  call    NvIoFreeWorkItem
0x140098adc  lea     rcx, [rbx+350h]
0x140098ae3  call    NvIoFreeWorkItem
0x140098ae8  lea     rcx, [rbx+658h]
0x140098aef  call    NvIoFreeWorkItem
0x140098af4  lea     rcx, [rbx+668h]
0x140098afb  call    NvIoFreeWorkItem
0x140098b00  lea     rcx, [rbx+698h]
0x140098b07  call    NvIoFreeWorkItem
0x140098b0c  xor     r8d, r8d
0x140098b0f  lea     rdx, [rsp+118h+LockState]
0x140098b17  mov     rcx, r14
0x140098b1a  call    VmsOmObjectLockExclusive
0x140098b1f  lea     rax, [rbx+678h]
0x140098b26  cmp     [rax], rax
0x140098b29  jz      short loc_140098B33
0x140098b2b  mov     rcx, rbx
0x140098b2e  call    VmsVmNicFlushIcmpRequestIrps
0x140098b33  lea     rdx, [rsp+118h+LockState]; LockState
0x140098b3b  mov     rcx, [r14+38h]; Lock
0x140098b3f  call    cs:__imp_NdisReleaseRWLock
0x140098b46  nop     dword ptr [rax+rax+00h]
0x140098b4b  mov     rcx, [rbx+8]; Handle
0x140098b4f  test    rcx, rcx
0x140098b52  jz      short loc_140098B64
0x140098b54  call    cs:__imp_ZwClose
0x140098b5b  nop     dword ptr [rax+rax+00h]
0x140098b60  mov     [rbx+8], rdi
0x140098b64  xor     edx, edx; Tag
0x140098b66  mov     rcx, rbx; P
0x140098b69  call    cs:__imp_ExFreePoolWithTag
0x140098b70  nop     dword ptr [rax+rax+00h]
0x140098b75  cmp     [rsp+118h+var_57], dil
0x140098b7d  jz      short loc_140098BB1
0x140098b7f  xor     r8d, r8d
0x140098b82  lea     rdx, [rsp+118h+LockState]
0x140098b8a  mov     rcx, r14
0x140098b8d  call    VmsOmObjectLockExclusive
0x140098b92  mov     [r14+750h], edi
0x140098b99  lea     rdx, [rsp+118h+LockState]; LockState
0x140098ba1  mov     rcx, [r14+38h]; Lock
0x140098ba5  call    cs:__imp_NdisReleaseRWLock
0x140098bac  nop     dword ptr [rax+rax+00h]
0x140098bb1  mov     esi, 0C0000018h
0x140098bb6  cmp     [rsp+118h+var_58], dil
0x140098bbe  cmovnz  r15d, esi
0x140098bc2  test    r15d, r15d
0x140098bc5  jns     loc_140098CAB
0x140098bcb  movzx   edx, [rsp+118h+arg_58]
0x140098bd3  movzx   ecx, [rsp+118h+arg_50]
0x140098bdb  movzx   esi, [rsp+118h+arg_28]
0x140098be3  mov     rax, [rsp+118h+arg_20]
0x140098beb  movzx   r8d, byte ptr [rax+5]
0x140098bf0  movzx   r9d, byte ptr [rax+4]
0x140098bf5  movzx   r10d, byte ptr [rax+3]
0x140098bfa  movzx   r11d, byte ptr [rax+2]
0x140098bff  movzx   ebx, byte ptr [rax+1]
0x140098c03  movzx   edi, byte ptr [rax]
0x140098c06  mov     [rsp+118h+var_68], r15d
0x140098c0e  mov     [rsp+118h+var_70], edx
0x140098c15  mov     [rsp+118h+var_78], ecx
0x140098c1c  mov     eax, [rsp+118h+arg_48]
0x140098c23  mov     [rsp+118h+var_80], eax
0x140098c2a  mov     rax, [rsp+118h+arg_40]
0x140098c32  mov     [rsp+118h+var_88], rax
0x140098c3a  mov     rax, [rsp+118h+arg_38]
0x140098c42  mov     [rsp+118h+var_90], rax
0x140098c4a  mov     rax, [rsp+118h+arg_30]
0x140098c52  mov     [rsp+118h+var_98], rax
0x140098c5a  mov     [rsp+118h+var_A0], esi
0x140098c5e  mov     [rsp+118h+var_A8], r8d
0x140098c63  mov     [rsp+118h+var_B0], r9d
0x140098c68  mov     [rsp+118h+var_B8], r10d
0x140098c6d  mov     [rsp+118h+var_C0], r11d
0x140098c72  mov     [rsp+118h+var_C8], ebx
0x140098c76  mov     [rsp+118h+var_D0], edi
0x140098c7a  mov     rcx, [rsp+118h+arg_18]
0x140098c82  mov     [rsp+118h+var_D8], rcx
0x140098c87  mov     rcx, [rsp+118h+arg_10]
0x140098c8f  mov     [rsp+118h+var_E0], rcx
0x140098c94  mov     rcx, [rsp+118h+SourceString]
0x140098c9c  mov     [rsp+118h+var_E8], rcx
0x140098ca1  mov     [rsp+118h+var_F0], r14
0x140098ca6  call    WPP_RECORDER_SF_qZZZDDDDDDdIqqLddd
0x140098cab  mov     eax, r15d
0x140098cae  add     rsp, 0E0h
0x140098cb5  pop     r15
0x140098cb7  pop     r14
0x140098cb9  pop     r13
0x140098cbb  pop     r12
0x140098cbd  pop     rdi
0x140098cbe  pop     rsi
0x140098cbf  pop     rbx
0x140098cc0  retn
0x140098cc2  mov     r15d, 300h
0x140098cc8  cmp     [rsp+118h+arg_48], r15d
0x140098cd0  cmovb   r15d, [rsp+118h+arg_48]
0x140098cd9  mov     [rax+35Ch], r15d
0x140098ce0  mov     [rax+208h], edi
0x140098ce6  mov     dword ptr [rax+20Ch], 3
0x140098cf0  mov     [rax+100h], edi
0x140098cf6  mov     dword ptr [rax+2C0h], 1Ch
0x140098d00  mov     [rax+258h], r13d
0x140098d07  mov     [rax+218h], r13b
0x140098d0e  add     rax, 308h
0x140098d14  mov     [rax+8], rax
0x140098d18  mov     [rax], rax
0x140098d1b  lea     rcx, [r14+0D84h]; void *
0x140098d22  xor     edx, edx; Val
0x140098d24  lea     r8d, [rdx+60h]; Size
0x140098d28  call    memset
0x140098d2d  mov     al, [rsp+118h+arg_50]
0x140098d34  mov     [rsi+3A0h], al
0x140098d3a  mov     [rsi+2A8h], r14
0x140098d41  mov     [r14+0CF0h], rsi
0x140098d48  lea     rax, [rsi+678h]
0x140098d4f  mov     [rax+8], rax
0x140098d53  mov     [rax], rax
0x140098d56  lea     rax, [rsi+688h]
0x140098d5d  mov     [rax+8], rax
0x140098d61  mov     [rax], rax
0x140098d64  mov     edx, 7843494Eh
0x140098d69  mov     ecx, 58h ; 'X'
0x140098d6e  call    NvIoEnvMemAlloc
0x140098d73  mov     rbx, rax
0x140098d76  test    rax, rax
0x140098d79  jnz     short loc_140098D7F
0x140098d7b  mov     cl, 18h
0x140098d7d  jmp     short loc_140098DB1
0x140098d7f  mov     [rax+38h], r14
0x140098d83  lea     rax, [r14+7C8h]
0x140098d8a  mov     [rbx+50h], rax
0x140098d8e  mov     [rbx], r13d
0x140098d91  mov     [rbx+8], rdi
0x140098d95  mov     [rbx+10h], edi
  ... truncated ...
```
