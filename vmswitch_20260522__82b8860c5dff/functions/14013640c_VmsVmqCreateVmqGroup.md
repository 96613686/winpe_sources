# VmsVmqCreateVmqGroup

- ea: `0x14013640c`
- end: `0x140136e6c`
- name: `VmsVmqCreateVmqGroup`
- size: `2656`
- prototype: ``
- caller_count: `4`
- callee_count: `32`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14009f510`
- `0x14009f780`
- `0x14011cf00`
- `0x140137cb8`

## callees

- `0x140027a64`
- `0x14002a2c0`
- `0x14002e0f0`
- `0x14003a450`
- `0x140046e5c`
- `0x14004f5d8`
- `0x1400783d8`
- `0x1400845f8`
- `0x14008497c`
- `0x140084fa0`
- `0x1400867a0`
- `0x14008b3f0`
- `0x1400efbac`
- `0x140117740`
- `0x140117c40`
- `0x140123ebc`
- `0x140132c8c`
- `0x14013640c`
- `0x1401401a8`
- `0x140140368`
- `0x140141328`
- `0x140141380`
- `0x140193094`
- `0x1401ae01c`
- `0x1401aed14`
- `0x1401af070`
- `0x1401af240`
- `0x1401afa7c`
- `0x1401aff3c`
- `0x1401b05d4`
- `0x1401b3004`
- `0x1401b3434`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140136d19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136e13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136e2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136e49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136d19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136e13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136e2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136e49`
- `ntoskrnl!ExAllocatePool2` at `0x140136467`
- `ntoskrnl!ExAllocatePool2` at `0x1401365e5`
- `ntoskrnl!ExAllocatePool2` at `0x140136777`
- `ntoskrnl!ExAllocatePool2` at `0x140136467`
- `ntoskrnl!ExAllocatePool2` at `0x1401365e5`
- `ntoskrnl!ExAllocatePool2` at `0x140136777`
- `NDIS!NdisGetRssProcessorInformation` at `0x1401365b4`
- `NDIS!NdisGetRssProcessorInformation` at `0x1401366b1`
- `NDIS!NdisGetRssProcessorInformation` at `0x1401365b4`
- `NDIS!NdisGetRssProcessorInformation` at `0x1401366b1`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140136ce5`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140136ce5`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x1401364f0`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x1401364f0`

## string_xrefs

- `0x140136a51`: `(Nic->Type == VmsNicProtocol) || (Nic->ConnectState == VmsNicConnectStateConnected)`
- `0x140136bac`: `memberAdapter->ProtocolHandle != NULL`
- `0x140136c7c`: `Disabling VMQ due to RSS misconfiguration`
- `0x140136b27`: `ptNic->GuestRssInfo.IsUpdatePending == FALSE`

## pseudocode

```c
__int64 __fastcall VmsVmqCreateVmqGroup(__int64 *a1, int a2, __int64 **a3)
{
  __int64 v3; // r13
  _QWORD *v4; // r14
  char *v5; // rsi
  unsigned __int16 v6; // r12
  __int64 *v7; // r15
  int v8; // edx
  int v9; // ebx
  int v10; // edi
  unsigned int v11; // eax
  int v12; // edx
  NDIS_STATUS RssProcessorInformation; // eax
  unsigned int v14; // r15d
  void **v15; // rcx
  void *v16; // rcx
  struct _NDIS_RSS_PROCESSOR_INFO *v17; // rax
  int v18; // edx
  _DWORD *p_Type; // r15
  NDIS_STATUS v20; // eax
  int v21; // edx
  __int64 v22; // rcx
  void **v23; // rcx
  void *v24; // rcx
  struct _NDIS_RSS_PROCESSOR_INFO *v25; // rdx
  unsigned int v26; // r15d
  _QWORD *v27; // rbx
  int v28; // edx
  PVOID v29; // r8
  __int64 v30; // rax
  int v31; // edx
  int NblRefCounters; // eax
  int v33; // edx
  int v34; // edx
  __int64 v35; // rdx
  int v36; // edx
  int v37; // ecx
  int v38; // edx
  __int64 v39; // r15
  int v40; // edx
  int v41; // edx
  __int64 v42; // r8
  _QWORD *v43; // rcx
  __int64 *v44; // rdx
  char *v45; // rax
  __int64 **v46; // rcx
  int v47; // edx
  unsigned int v48; // eax
  int v49; // edx
  __int64 v50; // rdx
  int v51; // edx
  void *v52; // rdi
  void *v53; // rcx
  unsigned int v55; // [rsp+48h] [rbp-49h]
  char v56; // [rsp+78h] [rbp-19h]
  unsigned int v57; // [rsp+7Ch] [rbp-15h] BYREF
  PVOID P; // [rsp+80h] [rbp-11h]
  ULONG_PTR Size; // [rsp+88h] [rbp-9h] BYREF
  void *v60; // [rsp+90h] [rbp-1h]
  PVOID Pool2; // [rsp+98h] [rbp+7h]
  char *v62; // [rsp+A0h] [rbp+Fh] BYREF
  char v66; // [rsp+110h] [rbp+7Fh]

  v3 = *a1;
  v60 = 0;
  v4 = 0;
  P = 0;
  v5 = 0;
  v57 = 0;
  v6 = a2;
  Size = 0;
  v7 = a1;
  v62 = 0;
  VmsOmAssertIoctlMutexIsHeld();
  Pool2 = (PVOID)ExAllocatePool2(64, 2256, 1953919830);
  if ( !Pool2 )
  {
    v9 = -1073741670;
    v10 = 9;
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v8, 20, 35, (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids, 208);
    goto LABEL_105;
  }
  v56 = 0;
  v10 = 0;
  v66 = VmsPtCheckIsEmbeddedTeamingEnabled(v3, 0);
  v11 = VmsPtNicAcquireMemberAdapter(v3, v6, 23, &v62);
  v5 = v62;
  if ( v11 )
  {
    v9 = NdisConvertNdisStatusToNtStatus(v11);
    goto LABEL_50;
  }
  if ( *((_QWORD *)v62 + 241) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v12,
      19,
      36,
      (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids,
      "memberAdapter->MemberNicVmqGroup == NULL");
    if ( *((_QWORD *)v5 + 241) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( *((_BYTE *)v7 + 2401) )
  {
    if ( v66 != 1 )
    {
      RssProcessorInformation = VmsPtPvtProcessPrivateOid(v3, 0, -100597502, a2, 0, 0, 0, 0, 0, 0, (__int64)&v57, 0, 0);
      v14 = v57;
      goto LABEL_16;
    }
    v15 = (void **)(v7 + 14);
    if ( a2 )
      v15 = (void **)v5;
    v16 = *v15;
  }
  else
  {
    v16 = (void *)v7[14];
  }
  RssProcessorInformation = NdisGetRssProcessorInformation(v16, 0, &Size);
  v14 = Size;
LABEL_16:
  v9 = RssProcessorInformation;
  if ( RssProcessorInformation != -1073676266 )
  {
    v10 = 11;
    goto LABEL_50;
  }
  v17 = (struct _NDIS_RSS_PROCESSOR_INFO *)ExAllocatePool2(64, v14, 1953919830);
  P = v17;
  if ( !v17 )
  {
    v9 = -1073741670;
    v10 = 9;
    LOBYTE(v18) = 2;
    WPP_RECORDER_SF_ld(VmsIfrLog, v18, 20, 37, (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids, v14, 154);
    goto LABEL_100;
  }
  if ( *((_BYTE *)a1 + 2401) )
  {
    if ( (unsigned __int8)VmsPtCheckIsEmbeddedTeamingEnabled(v3, 0) != 1 )
    {
      v55 = v14;
      p_Type = P;
      v20 = VmsPtPvtProcessPrivateOid(v3, 0, -100597502, a2, 0, 0, 0, (__int64)P, v55, 0, 0, 0, 0);
      goto LABEL_28;
    }
    v23 = (void **)(a1 + 14);
    if ( a2 )
      v23 = (void **)v5;
    p_Type = P;
    v24 = *v23;
    v25 = (struct _NDIS_RSS_PROCESSOR_INFO *)P;
  }
  else
  {
    v24 = (void *)a1[14];
    p_Type = &v17->Header.Type;
    v25 = v17;
  }
  v20 = NdisGetRssProcessorInformation(v24, v25, &Size);
LABEL_28:
  v9 = v20;
  if ( v20 < 0 )
  {
    v10 = 11;
    goto LABEL_100;
  }
  if ( p_Type[3] > p_Type[6] )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v21,
      19,
      38,
      (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids,
      "(rssProcessorInfo->MaxNumRssProcessors <= rssProcessorInfo->RssProcessorCount)");
    if ( p_Type[3] > p_Type[6] )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v26 = p_Type[3];
  if ( v26 && (*((_BYTE *)a1 + 306) || v26 != 1) )
  {
    v27 = Pool2;
    v28 = a2;
    v7 = a1;
    v29 = P;
    if ( *((_DWORD *)a1 + 375) != 2 )
      v28 = 0;
    *((_DWORD *)Pool2 + 11) = v28;
    v27[4] = v3;
    v62 = (char *)(v27 + 8);
    VmsPlanInitializeDomainForProtocolNic(v27 + 8, v5, v29);
    v30 = ExAllocatePool2(64, 4248, 1953919830);
    v4 = (_QWORD *)v30;
    if ( !v30 )
    {
      v9 = -1073741670;
      v10 = 9;
      WPP_RECORDER_SF_Pd(VmsIfrLog, v31, 20, 40, (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids, 152);
      goto LABEL_100;
    }
    v27[7] = v30;
    v60 = (void *)(v30 + 304);
    *(_QWORD *)(v30 + 32) = v3;
    *(_QWORD *)(v30 + 40) = v3;
    *(_QWORD *)(v30 + 56) = 0;
    *(_QWORD *)(v30 + 248) = v27;
    *(_DWORD *)(v30 + 48) = 1;
    NblRefCounters = VmsVmqAllocateNblRefCounters(v30);
    v9 = NblRefCounters;
    if ( NblRefCounters )
    {
      v10 = 9;
      LOBYTE(v33) = 2;
      WPP_RECORDER_SF_d(
        VmsIfrLog,
        v33,
        20,
        41,
        (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids,
        NblRefCounters);
      goto LABEL_50;
    }
    VmsVmmqTelemetryStartLog(v4);
    v56 = 1;
    v9 = VmsQueueGroupInitialize(v60);
    if ( v9 )
    {
      v10 = 9;
      LOBYTE(v34) = 2;
      WPP_RECORDER_SF_(VmsIfrLog, v34, 20, 42, (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids);
      goto LABEL_50;
    }
    if ( !v5[4285] || (VmsRteConfiguration & 4) == 0 || (v35 = 3, !v5[4287]) )
      v35 = 2;
    VmsScalerInitialize(v4, v35, v3);
    v9 = VmsQueueGroupPushScaler(v60, v4);
    if ( v9 )
    {
      v10 = 27;
      LOBYTE(v36) = 2;
      WPP_RECORDER_SF_(VmsIfrLog, v36, 20, 43, (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids);
LABEL_50:
      if ( v9 >= 0 )
        goto LABEL_102;
      goto LABEL_100;
    }
    v37 = a2;
    if ( v66 )
    {
      if ( a2 )
        goto LABEL_64;
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v36,
        19,
        44,
        (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids,
        "NdisPortNumber != NDIS_DEFAULT_PORT_NUMBER");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    else
    {
      if ( !*((_BYTE *)a1 + 2401) && a2 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v36,
          19,
          45,
          (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids,
          "PtNicExt->IsLbfo || (NdisPortNumber == NDIS_DEFAULT_PORT_NUMBER)");
        if ( !*((_BYTE *)a1 + 2401) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
        v37 = a2;
      }
      if ( v5 == (char *)a1[424] )
        goto LABEL_64;
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v36,
        19,
        47,
        (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids,
        "memberAdapter == PtNicExt->MemberAdapterWrapper");
      if ( v5 != (char *)a1[424] )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v37 = a2;
LABEL_64:
    if ( !*((_BYTE *)a1 + 2401) && *((unsigned __int16 *)v5 + 8) != v37 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v36,
        19,
        48,
        (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids,
        "PtNicExt->IsLbfo || (memberAdapter->MemberIndex == NdisPortNumber)");
      if ( !*((_BYTE *)a1 + 2401) && *((unsigned __int16 *)v5 + 8) != a2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v4[3] = v5;
    if ( (unsigned int)VmsVmmqAllocateOidForVmq(v5, v4) )
    {
      v10 = 9;
      LOBYTE(v38) = 2;
      WPP_RECORDER_SF_(VmsIfrLog, v38, 20, 49, (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids);
LABEL_104:
      v48 = NdisConvertNtStatusToNdisStatus((unsigned int)v9);
      VmsVmmqTelemetryStopAndTraceLog(v4, v48);
      goto LABEL_105;
    }
    if ( v66 )
      *((_QWORD *)v5 + 241) = Pool2;
    v39 = v4[1] + 640LL;
    if ( *(_DWORD *)(v3 + 1872) != 2 && *(_DWORD *)(v3 + 1880) != 1 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v38,
        19,
        195,
        (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
        "(Nic->Type == VmsNicProtocol) || (Nic->ConnectState == VmsNicConnectStateConnected)");
      if ( *(_DWORD *)(v3 + 1872) != 2 && *(_DWORD *)(v3 + 1880) != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    if ( !*(_QWORD *)(v3 + 1984) )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v38,
        19,
        196,
        (__int64)WPP_bda91bcb57e433144f485e69e8239e42_Traceguids,
        "Nic->Port != NULL");
      if ( !*(_QWORD *)(v3 + 1984) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    *(_WORD *)(*(_QWORD *)(v3 + 1984) + 8640LL) &= ~1u;
    VmsPlanConnect(v39);
    if ( *((_BYTE *)a1 + 306) )
    {
      *(_DWORD *)(v39 + 12) = 1;
      VmsPtAdjustNumQueuePairsInUse(v5, 1);
    }
    if ( *(_BYTE *)(v3 + 4931) )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v40,
        19,
        50,
        (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids,
        "ptNic->GuestRssInfo.IsUpdatePending == FALSE");
      if ( *(_BYTE *)(v3 + 4931) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v9 = VmsPlanEvaluate(v39, v5, v62);
    if ( v9 >= 0 )
    {
      if ( !*(_QWORD *)v5 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v41,
          19,
          52,
          (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids,
          "memberAdapter->ProtocolHandle != NULL");
        if ( !*(_QWORD *)v5 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      LOBYTE(v42) = 1;
      VmsPlanAssignCpusStatically(v39, v62, v42);
      VmsQueueGroupSetPrimaryProcessorIfNecessary(v60);
      if ( *(_BYTE *)(v3 + 5496) && v5[4285] && !v5[4286] )
        VmsVmmqApplyHashToDefaultQueue(v5, v4);
      v43 = (_QWORD *)qword_140224C30;
      if ( *(__int64 **)qword_140224C30 != &qword_140224C28 )
        goto LABEL_98;
      v44 = (__int64 *)Pool2;
      v7 = a1;
      v45 = (char *)Pool2 + 16;
      *((_QWORD *)Pool2 + 2) = &qword_140224C28;
      *((_QWORD *)v45 + 1) = v43;
      *v43 = v45;
      qword_140224C30 = (__int64)v45;
      v46 = (__int64 **)a1[186];
      if ( *v46 != a1 + 185 )
LABEL_98:
        __fastfail(3u);
      *v44 = (__int64)(a1 + 185);
      v44[1] = (__int64)v46;
      *v46 = v44;
      a1[186] = (__int64)v44;
      ++VmsPtDynVmqInfo;
      *a3 = v44;
      goto LABEL_104;
    }
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v41,
      19,
      51,
      (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids,
      "!\"Failed to evaluate the plan: most probably not enough queues for Default VPort!\"");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    v10 = 27;
    goto LABEL_100;
  }
  v9 = -1073741670;
  v10 = 23;
  MicrosoftTelemetryAssertTriggeredArgsMsgKM(
    v22,
    v26,
    *((unsigned int *)P + 6),
    "Disabling VMQ due to RSS misconfiguration");
  LOBYTE(v47) = 2;
  WPP_RECORDER_SF_ld(
    VmsIfrLog,
    v47,
    20,
    39,
    (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids,
    v26,
    *((_DWORD *)P + 6));
LABEL_100:
  if ( v5 )
    *((_QWORD *)v5 + 241) = 0;
LABEL_102:
  v7 = a1;
  if ( v56 && v4 )
    goto LABEL_104;
LABEL_105:
  VmsPtNicReleaseMemberAdapter(v3, 23, v5);
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v10 )
  {
    v50 = *(_QWORD *)(v3 + 1888);
    VmsEtwTraceVmqGroupCreateFailure(
      v3 + 616,
      -(int)v50,
      v50 != 0 ? v50 + 72 : 0,
      v3 + 72,
      v3 + 616,
      (v50 + 72) & -(__int64)(v50 != 0),
      (v50 + 616) & -(__int64)(v50 != 0),
      *((_DWORD *)v7 + 375),
      v9,
      v10);
    LOBYTE(v51) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v51, 20, 53, (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids, v10);
  }
  if ( v9 < 0 )
  {
    WPP_RECORDER_SF_qdqd(
      VmsIfrLog,
      v49,
      20,
      54,
      (__int64)WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids,
      (char)v7,
      a2,
      (char)a3,
      v9);
    if ( v4 )
    {
      VmsVmmqUninitializeForVmqQueue(v4);
      v52 = v60;
      if ( v60 )
      {
        VmsQueueGroupPopScaler(v60);
        VmsQueueGroupUninitialize(v52);
      }
      v53 = (void *)v4[27];
      if ( v53 )
      {
        ExFreePoolWithTag(v53, 0);
        v4[27] = 0;
      }
      ExFreePoolWithTag(v4, 0);
    }
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14013640c  mov     rax, rsp
0x14013640f  mov     [rax+18h], r8
0x140136413  mov     [rax+10h], edx
0x140136416  mov     [rax+8], rcx
0x14013641a  push    rbp
0x14013641b  push    rbx
0x14013641c  push    rsi
0x14013641d  push    rdi
0x14013641e  push    r12
0x140136420  push    r13
0x140136422  push    r14
0x140136424  push    r15
0x140136426  lea     rbp, [rax-5Fh]
0x14013642a  sub     rsp, 0A8h
0x140136431  mov     r13, [rcx]
0x140136434  xor     ebx, ebx
0x140136436  mov     [rbp+57h+var_58], rbx
0x14013643a  mov     r14d, ebx
0x14013643d  mov     [rbp+57h+P], rbx
0x140136441  mov     esi, ebx
0x140136443  mov     [rbp+57h+var_6C], ebx
0x140136446  mov     r12d, edx
0x140136449  mov     [rbp+57h+Size], rbx
0x14013644d  mov     r15, rcx
0x140136450  mov     [rbp+57h+var_48], rbx
0x140136454  call    VmsOmAssertIoctlMutexIsHeld
0x140136459  mov     edx, 8D0h
0x14013645e  lea     ecx, [rbx+40h]
0x140136461  mov     r8d, 74767356h
0x140136467  call    cs:__imp_ExAllocatePool2
0x14013646e  nop     dword ptr [rax+rax+00h]
0x140136473  mov     [rbp+57h+var_50], rax
0x140136477  test    rax, rax
0x14013647a  jnz     short loc_1401364B3
0x14013647c  mov     ebx, 0C000009Ah
0x140136481  lea     edi, [rsi+9]
0x140136484  mov     rcx, cs:VmsIfrLog
0x14013648b  lea     r12, WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids
0x140136492  lea     r9d, [rsi+23h]
0x140136496  mov     dword ptr [rsp+0E0h+var_B8], 8D0h
0x14013649e  lea     r8d, [rsi+14h]
0x1401364a2  mov     [rsp+0E0h+var_C0], r12
0x1401364a7  mov     dl, 2
0x1401364a9  call    WPP_RECORDER_SF_d
0x1401364ae  jmp     loc_140136CFB
0x1401364b3  xor     edx, edx
0x1401364b5  mov     [rbp+57h+var_70], bl
0x1401364b8  mov     rcx, r13
0x1401364bb  mov     edi, ebx
0x1401364bd  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x1401364c2  lea     r9, [rbp+57h+var_48]
0x1401364c6  mov     [rbp+57h+arg_18], al
0x1401364c9  mov     r8d, 17h
0x1401364cf  movzx   edx, r12w
0x1401364d3  mov     rcx, r13
0x1401364d6  mov     bl, al
0x1401364d8  call    VmsPtNicAcquireMemberAdapter
0x1401364dd  mov     rsi, [rbp+57h+var_48]
0x1401364e1  lea     r12, WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids
0x1401364e8  xor     ecx, ecx
0x1401364ea  test    eax, eax
0x1401364ec  jz      short loc_140136503
0x1401364ee  mov     ecx, eax
0x1401364f0  call    cs:__imp_NdisConvertNdisStatusToNtStatus
0x1401364f7  nop     dword ptr [rax+rax+00h]
0x1401364fc  mov     ebx, eax
0x1401364fe  jmp     loc_1401368BF
0x140136503  cmp     [rsi+788h], rcx
0x14013650a  jz      short loc_140136545
0x14013650c  mov     rcx, cs:VmsIfrLog
0x140136513  lea     rax, aMemberadapterM_1; "memberAdapter->MemberNicVmqGroup == NUL"...
0x14013651a  mov     r9d, 24h ; '$'
0x140136520  mov     [rsp+0E0h+var_B8], rax
0x140136525  mov     [rsp+0E0h+var_C0], r12
0x14013652a  lea     r8d, [r9-11h]
0x14013652e  call    WPP_RECORDER_SF_s
0x140136533  xor     ecx, ecx
0x140136535  cmp     [rsi+788h], rcx
0x14013653c  jz      short loc_140136545
0x14013653e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "memberAdapter->MemberNicVmqGroup == ((void *)0)")
0x140136543  xor     ecx, ecx
0x140136545  cmp     [r15+961h], cl
0x14013654c  jz      short loc_1401365AA
0x14013654e  cmp     bl, 1
0x140136551  jz      short loc_140136599
0x140136553  mov     r9d, [rbp+57h+arg_8]
0x140136557  lea     rax, [rbp+57h+var_6C]
0x14013655b  mov     [rsp+60h], rcx
0x140136560  xor     edx, edx
0x140136562  mov     [rsp+0E0h+var_88], rcx
0x140136567  mov     r8d, 0FA010102h
0x14013656d  mov     [rsp+0E0h+var_90], rax
0x140136572  mov     dword ptr [rsp+0E0h+var_98], ecx
0x140136576  mov     [rsp+0E0h+var_A0], ecx
0x14013657a  mov     qword ptr [rsp+0E0h+var_A8], rcx
0x14013657f  mov     dword ptr [rsp+0E0h+var_B0], ecx
0x140136583  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x140136587  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x14013658b  mov     rcx, r13
0x14013658e  call    VmsPtPvtProcessPrivateOid
0x140136593  mov     r15d, [rbp+57h+var_6C]
0x140136597  jmp     short loc_1401365C4
0x140136599  cmp     [rbp+57h+arg_8], ecx
0x14013659c  lea     rcx, [r15+70h]
0x1401365a0  jz      short loc_1401365A5
0x1401365a2  mov     rcx, rsi
0x1401365a5  mov     rcx, [rcx]
0x1401365a8  jmp     short loc_1401365AE
0x1401365aa  mov     rcx, [r15+70h]; NdisHandle
0x1401365ae  lea     r8, [rbp+57h+Size]; Size
0x1401365b2  xor     edx, edx; RssProcessorInfo
0x1401365b4  call    cs:__imp_NdisGetRssProcessorInformation
0x1401365bb  nop     dword ptr [rax+rax+00h]
0x1401365c0  mov     r15d, dword ptr [rbp+57h+Size]
0x1401365c4  mov     ebx, eax
0x1401365c6  cmp     eax, 0C0010016h
0x1401365cb  jz      short loc_1401365D7
0x1401365cd  mov     edi, 0Bh
0x1401365d2  jmp     loc_1401368BF
0x1401365d7  mov     edx, r15d
0x1401365da  mov     ecx, 40h ; '@'
0x1401365df  mov     r8d, 74767356h
0x1401365e5  call    cs:__imp_ExAllocatePool2
0x1401365ec  nop     dword ptr [rax+rax+00h]
0x1401365f1  mov     [rbp+57h+P], rax
0x1401365f5  test    rax, rax
0x1401365f8  jnz     short loc_14013662B
0x1401365fa  mov     ebx, 0C000009Ah
0x1401365ff  lea     edi, [rax+9]
0x140136602  mov     rcx, cs:VmsIfrLog
0x140136609  lea     r9d, [rax+25h]
0x14013660d  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x140136611  lea     r8d, [rax+14h]
0x140136615  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x14013661a  mov     dl, 2
0x14013661c  mov     [rsp+0E0h+var_C0], r12
0x140136621  call    WPP_RECORDER_SF_ld
0x140136626  jmp     loc_140136CC4
0x14013662b  mov     rbx, [rbp+57h+arg_0]
0x14013662f  cmp     [rbx+961h], dil
0x140136636  jz      short loc_1401366A3
0x140136638  xor     edx, edx
0x14013663a  mov     rcx, r13
0x14013663d  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x140136642  cmp     al, 1
0x140136644  jz      short loc_14013668B
0x140136646  mov     r9d, [rbp+57h+arg_8]
0x14013664a  xor     eax, eax
0x14013664c  mov     [rsp+60h], rax
0x140136651  xor     edx, edx
0x140136653  mov     [rsp+0E0h+var_88], rax
0x140136658  mov     r8d, 0FA010102h
0x14013665e  mov     [rsp+0E0h+var_90], rax
0x140136663  mov     rcx, r13
0x140136666  mov     dword ptr [rsp+0E0h+var_98], eax
0x14013666a  mov     [rsp+0E0h+var_A0], r15d
0x14013666f  mov     r15, [rbp+57h+P]
0x140136673  mov     qword ptr [rsp+0E0h+var_A8], r15
0x140136678  mov     dword ptr [rsp+0E0h+var_B0], eax
0x14013667c  mov     dword ptr [rsp+0E0h+var_B8], eax
0x140136680  mov     dword ptr [rsp+0E0h+var_C0], eax
0x140136684  call    VmsPtPvtProcessPrivateOid
0x140136689  jmp     short loc_1401366BD
0x14013668b  lea     rcx, [rbx+70h]
0x14013668f  cmp     [rbp+57h+arg_8], edi
0x140136692  jz      short loc_140136697
0x140136694  mov     rcx, rsi
0x140136697  mov     r15, [rbp+57h+P]
0x14013669b  mov     rcx, [rcx]
0x14013669e  mov     rdx, r15
0x1401366a1  jmp     short loc_1401366AD
0x1401366a3  mov     rcx, [rbx+70h]; NdisHandle
0x1401366a7  mov     r15, rax
0x1401366aa  mov     rdx, rax; RssProcessorInfo
0x1401366ad  lea     r8, [rbp+57h+Size]; Size
0x1401366b1  call    cs:__imp_NdisGetRssProcessorInformation
0x1401366b8  nop     dword ptr [rax+rax+00h]
0x1401366bd  mov     ebx, eax
0x1401366bf  test    eax, eax
0x1401366c1  jns     short loc_1401366CD
0x1401366c3  mov     edi, 0Bh
0x1401366c8  jmp     loc_140136CC4
0x1401366cd  mov     eax, [r15+18h]
0x1401366d1  cmp     [r15+0Ch], eax
0x1401366d5  jbe     short loc_14013670D
0x1401366d7  mov     rcx, cs:VmsIfrLog
0x1401366de  lea     rax, aRssprocessorin; "(rssProcessorInfo->MaxNumRssProcessors "...
0x1401366e5  mov     r9d, 26h ; '&'
0x1401366eb  mov     [rsp+0E0h+var_B8], rax
0x1401366f0  mov     [rsp+0E0h+var_C0], r12
0x1401366f5  lea     r8d, [r9-13h]
0x1401366f9  call    WPP_RECORDER_SF_s
0x1401366fe  mov     eax, [r15+18h]
0x140136702  cmp     [r15+0Ch], eax
0x140136706  jbe     short loc_14013670D
0x140136708  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "(rssProcessorInfo->MaxNumRssProcessors <= rssProcessorInfo->RssProcessorCount)")
0x14013670d  mov     r15d, [r15+0Ch]
0x140136711  test    r15d, r15d
0x140136714  jz      loc_140136C78
0x14013671a  mov     rax, [rbp+57h+arg_0]
0x14013671e  cmp     [rax+132h], dil
0x140136725  jnz     short loc_140136731
0x140136727  cmp     r15d, 1
0x14013672b  jz      loc_140136C78
0x140136731  mov     rbx, [rbp+57h+var_50]
0x140136735  xor     eax, eax
0x140136737  mov     edx, [rbp+57h+arg_8]
0x14013673a  mov     r15, [rbp+57h+arg_0]
0x14013673e  mov     r8, [rbp+57h+P]
0x140136742  cmp     dword ptr [r15+5DCh], 2
0x14013674a  cmovnz  edx, eax
0x14013674d  lea     rax, [rbx+40h]
0x140136751  mov     [rbx+2Ch], edx
0x140136754  mov     rcx, rax
0x140136757  mov     rdx, rsi
0x14013675a  mov     [rbx+20h], r13
0x14013675e  mov     [rbp+57h+var_48], rax
0x140136762  call    VmsPlanInitializeDomainForProtocolNic
0x140136767  mov     edx, 1098h
0x14013676c  mov     ecx, 40h ; '@'
0x140136771  mov     r8d, 74767356h
0x140136777  call    cs:__imp_ExAllocatePool2
0x14013677e  nop     dword ptr [rax+rax+00h]
0x140136783  mov     r14, rax
0x140136786  test    rax, rax
0x140136789  jnz     short loc_1401367BA
0x14013678b  mov     ebx, 0C000009Ah
0x140136790  lea     edi, [rax+9]
0x140136793  mov     rcx, cs:VmsIfrLog
0x14013679a  lea     r9d, [rax+28h]
0x14013679e  mov     [rsp+0E0h+var_B8], 1098h
0x1401367a7  lea     r8d, [rax+14h]
0x1401367ab  mov     [rsp+0E0h+var_C0], r12
0x1401367b0  call    WPP_RECORDER_SF_Pd
0x1401367b5  jmp     loc_140136CC4
0x1401367ba  mov     [rbx+38h], r14
0x1401367be  add     rax, 130h
0x1401367c4  mov     rcx, r14
0x1401367c7  mov     [rbp+57h+var_58], rax
0x1401367cb  mov     [r14+20h], r13
0x1401367cf  mov     [r14+28h], r13
0x1401367d3  mov     [r14+38h], rdi
0x1401367d7  mov     [r14+0F8h], rbx
0x1401367de  mov     dword ptr [r14+30h], 1
0x1401367e6  call    VmsVmqAllocateNblRefCounters
0x1401367eb  mov     ebx, eax
0x1401367ed  test    eax, eax
0x1401367ef  jz      short loc_14013681A
0x1401367f1  mov     edi, 9
0x1401367f6  mov     rcx, cs:VmsIfrLog
0x1401367fd  lea     r9d, [rdi+20h]
0x140136801  mov     dword ptr [rsp+0E0h+var_B8], eax
0x140136805  lea     r8d, [rdi+0Bh]
0x140136809  mov     dl, 2
0x14013680b  mov     [rsp+0E0h+var_C0], r12
0x140136810  call    WPP_RECORDER_SF_d
0x140136815  jmp     loc_1401368BF
0x14013681a  mov     rcx, r14
0x14013681d  call    VmsVmmqTelemetryStartLog
0x140136822  mov     rcx, [rbp+57h+var_58]
0x140136826  mov     [rbp+57h+var_70], 1
0x14013682a  call    VmsQueueGroupInitialize
0x14013682f  mov     ebx, eax
0x140136831  test    eax, eax
0x140136833  jz      short loc_140136857
0x140136835  mov     edi, 9
0x14013683a  mov     rcx, cs:VmsIfrLog
0x140136841  lea     r9d, [rdi+21h]
0x140136845  lea     r8d, [rdi+0Bh]
0x140136849  mov     [rsp+0E0h+var_C0], r12
0x14013684e  mov     dl, 2
0x140136850  call    WPP_RECORDER_SF_
0x140136855  jmp     short loc_1401368BF
0x140136857  cmp     [rsi+10BDh], dil
0x14013685e  jz      short loc_140136878
0x140136860  mov     eax, cs:VmsRteConfiguration
0x140136866  test    al, 4
0x140136868  jz      short loc_140136878
0x14013686a  mov     edx, 3
0x14013686f  cmp     [rsi+10BFh], dil
0x140136876  jnz     short loc_14013687D
0x140136878  mov     edx, 2
0x14013687d  movzx   r9d, word ptr [rbp+57h+arg_8]
0x140136882  mov     r8, r13
0x140136885  mov     rcx, r14
0x140136888  call    VmsScalerInitialize
0x14013688d  mov     rcx, [rbp+57h+var_58]
0x140136891  mov     rdx, r14
0x140136894  call    VmsQueueGroupPushScaler
0x140136899  mov     ebx, eax
0x14013689b  test    eax, eax
0x14013689d  jz      short loc_1401368CC
0x14013689f  mov     edi, 1Bh
0x1401368a4  mov     rcx, cs:VmsIfrLog
0x1401368ab  lea     r9d, [rdi+10h]
0x1401368af  lea     r8d, [rdi-7]
0x1401368b3  mov     [rsp+0E0h+var_C0], r12
0x1401368b8  mov     dl, 2
0x1401368ba  call    WPP_RECORDER_SF_
0x1401368bf  test    ebx, ebx
  ... truncated ...
```
