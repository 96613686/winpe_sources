# VmsVmqCreateVmqGroup

- ea: `0x14013647c`
- end: `0x140136edc`
- name: `VmsVmqCreateVmqGroup`
- size: `2656`
- prototype: ``
- caller_count: `4`
- callee_count: `32`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14009f510`
- `0x14009f780`
- `0x14011cf70`
- `0x140137d28`

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
- `0x1400efc1c`
- `0x1401177b0`
- `0x140117cb0`
- `0x140123f2c`
- `0x140132cfc`
- `0x14013647c`
- `0x140140218`
- `0x1401403d8`
- `0x140141398`
- `0x1401413f0`
- `0x140193104`
- `0x1401ae08c`
- `0x1401aed84`
- `0x1401af0e0`
- `0x1401af2b0`
- `0x1401afaec`
- `0x1401affac`
- `0x1401b0644`
- `0x1401b3074`
- `0x1401b34a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140136d89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136e83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136e9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136eb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136d89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136e83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136e9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140136eb9`
- `ntoskrnl!ExAllocatePool2` at `0x1401364d7`
- `ntoskrnl!ExAllocatePool2` at `0x140136655`
- `ntoskrnl!ExAllocatePool2` at `0x1401367e7`
- `ntoskrnl!ExAllocatePool2` at `0x1401364d7`
- `ntoskrnl!ExAllocatePool2` at `0x140136655`
- `ntoskrnl!ExAllocatePool2` at `0x1401367e7`
- `NDIS!NdisGetRssProcessorInformation` at `0x140136624`
- `NDIS!NdisGetRssProcessorInformation` at `0x140136721`
- `NDIS!NdisGetRssProcessorInformation` at `0x140136624`
- `NDIS!NdisGetRssProcessorInformation` at `0x140136721`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140136d55`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140136d55`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x140136560`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x140136560`

## string_xrefs

- `0x140136ac1`: `(Nic->Type == VmsNicProtocol) || (Nic->ConnectState == VmsNicConnectStateConnected)`
- `0x140136c1c`: `memberAdapter->ProtocolHandle != NULL`
- `0x140136cec`: `Disabling VMQ due to RSS misconfiguration`
- `0x140136b97`: `ptNic->GuestRssInfo.IsUpdatePending == FALSE`

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
0x14013647c  mov     rax, rsp
0x14013647f  mov     [rax+18h], r8
0x140136483  mov     [rax+10h], edx
0x140136486  mov     [rax+8], rcx
0x14013648a  push    rbp
0x14013648b  push    rbx
0x14013648c  push    rsi
0x14013648d  push    rdi
0x14013648e  push    r12
0x140136490  push    r13
0x140136492  push    r14
0x140136494  push    r15
0x140136496  lea     rbp, [rax-5Fh]
0x14013649a  sub     rsp, 0A8h
0x1401364a1  mov     r13, [rcx]
0x1401364a4  xor     ebx, ebx
0x1401364a6  mov     [rbp+57h+var_58], rbx
0x1401364aa  mov     r14d, ebx
0x1401364ad  mov     [rbp+57h+P], rbx
0x1401364b1  mov     esi, ebx
0x1401364b3  mov     [rbp+57h+var_6C], ebx
0x1401364b6  mov     r12d, edx
0x1401364b9  mov     [rbp+57h+Size], rbx
0x1401364bd  mov     r15, rcx
0x1401364c0  mov     [rbp+57h+var_48], rbx
0x1401364c4  call    VmsOmAssertIoctlMutexIsHeld
0x1401364c9  mov     edx, 8D0h
0x1401364ce  lea     ecx, [rbx+40h]
0x1401364d1  mov     r8d, 74767356h
0x1401364d7  call    cs:__imp_ExAllocatePool2
0x1401364de  nop     dword ptr [rax+rax+00h]
0x1401364e3  mov     [rbp+57h+var_50], rax
0x1401364e7  test    rax, rax
0x1401364ea  jnz     short loc_140136523
0x1401364ec  mov     ebx, 0C000009Ah
0x1401364f1  lea     edi, [rsi+9]
0x1401364f4  mov     rcx, cs:VmsIfrLog
0x1401364fb  lea     r12, WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids
0x140136502  lea     r9d, [rsi+23h]
0x140136506  mov     dword ptr [rsp+0E0h+var_B8], 8D0h
0x14013650e  lea     r8d, [rsi+14h]
0x140136512  mov     [rsp+0E0h+var_C0], r12
0x140136517  mov     dl, 2
0x140136519  call    WPP_RECORDER_SF_d
0x14013651e  jmp     loc_140136D6B
0x140136523  xor     edx, edx
0x140136525  mov     [rbp+57h+var_70], bl
0x140136528  mov     rcx, r13
0x14013652b  mov     edi, ebx
0x14013652d  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x140136532  lea     r9, [rbp+57h+var_48]
0x140136536  mov     [rbp+57h+arg_18], al
0x140136539  mov     r8d, 17h
0x14013653f  movzx   edx, r12w
0x140136543  mov     rcx, r13
0x140136546  mov     bl, al
0x140136548  call    VmsPtNicAcquireMemberAdapter
0x14013654d  mov     rsi, [rbp+57h+var_48]
0x140136551  lea     r12, WPP_3bf29e89d96837dd89b0e1b2580eb9c6_Traceguids
0x140136558  xor     ecx, ecx
0x14013655a  test    eax, eax
0x14013655c  jz      short loc_140136573
0x14013655e  mov     ecx, eax
0x140136560  call    cs:__imp_NdisConvertNdisStatusToNtStatus
0x140136567  nop     dword ptr [rax+rax+00h]
0x14013656c  mov     ebx, eax
0x14013656e  jmp     loc_14013692F
0x140136573  cmp     [rsi+788h], rcx
0x14013657a  jz      short loc_1401365B5
0x14013657c  mov     rcx, cs:VmsIfrLog
0x140136583  lea     rax, aMemberadapterM_1; "memberAdapter->MemberNicVmqGroup == NUL"...
0x14013658a  mov     r9d, 24h ; '$'
0x140136590  mov     [rsp+0E0h+var_B8], rax
0x140136595  mov     [rsp+0E0h+var_C0], r12
0x14013659a  lea     r8d, [r9-11h]
0x14013659e  call    WPP_RECORDER_SF_s
0x1401365a3  xor     ecx, ecx
0x1401365a5  cmp     [rsi+788h], rcx
0x1401365ac  jz      short loc_1401365B5
0x1401365ae  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "memberAdapter->MemberNicVmqGroup == ((void *)0)")
0x1401365b3  xor     ecx, ecx
0x1401365b5  cmp     [r15+961h], cl
0x1401365bc  jz      short loc_14013661A
0x1401365be  cmp     bl, 1
0x1401365c1  jz      short loc_140136609
0x1401365c3  mov     r9d, [rbp+57h+arg_8]
0x1401365c7  lea     rax, [rbp+57h+var_6C]
0x1401365cb  mov     [rsp+60h], rcx
0x1401365d0  xor     edx, edx
0x1401365d2  mov     [rsp+0E0h+var_88], rcx
0x1401365d7  mov     r8d, 0FA010102h
0x1401365dd  mov     [rsp+0E0h+var_90], rax
0x1401365e2  mov     dword ptr [rsp+0E0h+var_98], ecx
0x1401365e6  mov     [rsp+0E0h+var_A0], ecx
0x1401365ea  mov     qword ptr [rsp+0E0h+var_A8], rcx
0x1401365ef  mov     dword ptr [rsp+0E0h+var_B0], ecx
0x1401365f3  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x1401365f7  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x1401365fb  mov     rcx, r13
0x1401365fe  call    VmsPtPvtProcessPrivateOid
0x140136603  mov     r15d, [rbp+57h+var_6C]
0x140136607  jmp     short loc_140136634
0x140136609  cmp     [rbp+57h+arg_8], ecx
0x14013660c  lea     rcx, [r15+70h]
0x140136610  jz      short loc_140136615
0x140136612  mov     rcx, rsi
0x140136615  mov     rcx, [rcx]
0x140136618  jmp     short loc_14013661E
0x14013661a  mov     rcx, [r15+70h]; NdisHandle
0x14013661e  lea     r8, [rbp+57h+Size]; Size
0x140136622  xor     edx, edx; RssProcessorInfo
0x140136624  call    cs:__imp_NdisGetRssProcessorInformation
0x14013662b  nop     dword ptr [rax+rax+00h]
0x140136630  mov     r15d, dword ptr [rbp+57h+Size]
0x140136634  mov     ebx, eax
0x140136636  cmp     eax, 0C0010016h
0x14013663b  jz      short loc_140136647
0x14013663d  mov     edi, 0Bh
0x140136642  jmp     loc_14013692F
0x140136647  mov     edx, r15d
0x14013664a  mov     ecx, 40h ; '@'
0x14013664f  mov     r8d, 74767356h
0x140136655  call    cs:__imp_ExAllocatePool2
0x14013665c  nop     dword ptr [rax+rax+00h]
0x140136661  mov     [rbp+57h+P], rax
0x140136665  test    rax, rax
0x140136668  jnz     short loc_14013669B
0x14013666a  mov     ebx, 0C000009Ah
0x14013666f  lea     edi, [rax+9]
0x140136672  mov     rcx, cs:VmsIfrLog
0x140136679  lea     r9d, [rax+25h]
0x14013667d  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x140136681  lea     r8d, [rax+14h]
0x140136685  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x14013668a  mov     dl, 2
0x14013668c  mov     [rsp+0E0h+var_C0], r12
0x140136691  call    WPP_RECORDER_SF_ld
0x140136696  jmp     loc_140136D34
0x14013669b  mov     rbx, [rbp+57h+arg_0]
0x14013669f  cmp     [rbx+961h], dil
0x1401366a6  jz      short loc_140136713
0x1401366a8  xor     edx, edx
0x1401366aa  mov     rcx, r13
0x1401366ad  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x1401366b2  cmp     al, 1
0x1401366b4  jz      short loc_1401366FB
0x1401366b6  mov     r9d, [rbp+57h+arg_8]
0x1401366ba  xor     eax, eax
0x1401366bc  mov     [rsp+60h], rax
0x1401366c1  xor     edx, edx
0x1401366c3  mov     [rsp+0E0h+var_88], rax
0x1401366c8  mov     r8d, 0FA010102h
0x1401366ce  mov     [rsp+0E0h+var_90], rax
0x1401366d3  mov     rcx, r13
0x1401366d6  mov     dword ptr [rsp+0E0h+var_98], eax
0x1401366da  mov     [rsp+0E0h+var_A0], r15d
0x1401366df  mov     r15, [rbp+57h+P]
0x1401366e3  mov     qword ptr [rsp+0E0h+var_A8], r15
0x1401366e8  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1401366ec  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1401366f0  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1401366f4  call    VmsPtPvtProcessPrivateOid
0x1401366f9  jmp     short loc_14013672D
0x1401366fb  lea     rcx, [rbx+70h]
0x1401366ff  cmp     [rbp+57h+arg_8], edi
0x140136702  jz      short loc_140136707
0x140136704  mov     rcx, rsi
0x140136707  mov     r15, [rbp+57h+P]
0x14013670b  mov     rcx, [rcx]
0x14013670e  mov     rdx, r15
0x140136711  jmp     short loc_14013671D
0x140136713  mov     rcx, [rbx+70h]; NdisHandle
0x140136717  mov     r15, rax
0x14013671a  mov     rdx, rax; RssProcessorInfo
0x14013671d  lea     r8, [rbp+57h+Size]; Size
0x140136721  call    cs:__imp_NdisGetRssProcessorInformation
0x140136728  nop     dword ptr [rax+rax+00h]
0x14013672d  mov     ebx, eax
0x14013672f  test    eax, eax
0x140136731  jns     short loc_14013673D
0x140136733  mov     edi, 0Bh
0x140136738  jmp     loc_140136D34
0x14013673d  mov     eax, [r15+18h]
0x140136741  cmp     [r15+0Ch], eax
0x140136745  jbe     short loc_14013677D
0x140136747  mov     rcx, cs:VmsIfrLog
0x14013674e  lea     rax, aRssprocessorin; "(rssProcessorInfo->MaxNumRssProcessors "...
0x140136755  mov     r9d, 26h ; '&'
0x14013675b  mov     [rsp+0E0h+var_B8], rax
0x140136760  mov     [rsp+0E0h+var_C0], r12
0x140136765  lea     r8d, [r9-13h]
0x140136769  call    WPP_RECORDER_SF_s
0x14013676e  mov     eax, [r15+18h]
0x140136772  cmp     [r15+0Ch], eax
0x140136776  jbe     short loc_14013677D
0x140136778  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "(rssProcessorInfo->MaxNumRssProcessors <= rssProcessorInfo->RssProcessorCount)")
0x14013677d  mov     r15d, [r15+0Ch]
0x140136781  test    r15d, r15d
0x140136784  jz      loc_140136CE8
0x14013678a  mov     rax, [rbp+57h+arg_0]
0x14013678e  cmp     [rax+132h], dil
0x140136795  jnz     short loc_1401367A1
0x140136797  cmp     r15d, 1
0x14013679b  jz      loc_140136CE8
0x1401367a1  mov     rbx, [rbp+57h+var_50]
0x1401367a5  xor     eax, eax
0x1401367a7  mov     edx, [rbp+57h+arg_8]
0x1401367aa  mov     r15, [rbp+57h+arg_0]
0x1401367ae  mov     r8, [rbp+57h+P]
0x1401367b2  cmp     dword ptr [r15+5DCh], 2
0x1401367ba  cmovnz  edx, eax
0x1401367bd  lea     rax, [rbx+40h]
0x1401367c1  mov     [rbx+2Ch], edx
0x1401367c4  mov     rcx, rax
0x1401367c7  mov     rdx, rsi
0x1401367ca  mov     [rbx+20h], r13
0x1401367ce  mov     [rbp+57h+var_48], rax
0x1401367d2  call    VmsPlanInitializeDomainForProtocolNic
0x1401367d7  mov     edx, 1098h
0x1401367dc  mov     ecx, 40h ; '@'
0x1401367e1  mov     r8d, 74767356h
0x1401367e7  call    cs:__imp_ExAllocatePool2
0x1401367ee  nop     dword ptr [rax+rax+00h]
0x1401367f3  mov     r14, rax
0x1401367f6  test    rax, rax
0x1401367f9  jnz     short loc_14013682A
0x1401367fb  mov     ebx, 0C000009Ah
0x140136800  lea     edi, [rax+9]
0x140136803  mov     rcx, cs:VmsIfrLog
0x14013680a  lea     r9d, [rax+28h]
0x14013680e  mov     [rsp+0E0h+var_B8], 1098h
0x140136817  lea     r8d, [rax+14h]
0x14013681b  mov     [rsp+0E0h+var_C0], r12
0x140136820  call    WPP_RECORDER_SF_Pd
0x140136825  jmp     loc_140136D34
0x14013682a  mov     [rbx+38h], r14
0x14013682e  add     rax, 130h
0x140136834  mov     rcx, r14
0x140136837  mov     [rbp+57h+var_58], rax
0x14013683b  mov     [r14+20h], r13
0x14013683f  mov     [r14+28h], r13
0x140136843  mov     [r14+38h], rdi
0x140136847  mov     [r14+0F8h], rbx
0x14013684e  mov     dword ptr [r14+30h], 1
0x140136856  call    VmsVmqAllocateNblRefCounters
0x14013685b  mov     ebx, eax
0x14013685d  test    eax, eax
0x14013685f  jz      short loc_14013688A
0x140136861  mov     edi, 9
0x140136866  mov     rcx, cs:VmsIfrLog
0x14013686d  lea     r9d, [rdi+20h]
0x140136871  mov     dword ptr [rsp+0E0h+var_B8], eax
0x140136875  lea     r8d, [rdi+0Bh]
0x140136879  mov     dl, 2
0x14013687b  mov     [rsp+0E0h+var_C0], r12
0x140136880  call    WPP_RECORDER_SF_d
0x140136885  jmp     loc_14013692F
0x14013688a  mov     rcx, r14
0x14013688d  call    VmsVmmqTelemetryStartLog
0x140136892  mov     rcx, [rbp+57h+var_58]
0x140136896  mov     [rbp+57h+var_70], 1
0x14013689a  call    VmsQueueGroupInitialize
0x14013689f  mov     ebx, eax
0x1401368a1  test    eax, eax
0x1401368a3  jz      short loc_1401368C7
0x1401368a5  mov     edi, 9
0x1401368aa  mov     rcx, cs:VmsIfrLog
0x1401368b1  lea     r9d, [rdi+21h]
0x1401368b5  lea     r8d, [rdi+0Bh]
0x1401368b9  mov     [rsp+0E0h+var_C0], r12
0x1401368be  mov     dl, 2
0x1401368c0  call    WPP_RECORDER_SF_
0x1401368c5  jmp     short loc_14013692F
0x1401368c7  cmp     [rsi+10BDh], dil
0x1401368ce  jz      short loc_1401368E8
0x1401368d0  mov     eax, cs:VmsRteConfiguration
0x1401368d6  test    al, 4
0x1401368d8  jz      short loc_1401368E8
0x1401368da  mov     edx, 3
0x1401368df  cmp     [rsi+10BFh], dil
0x1401368e6  jnz     short loc_1401368ED
0x1401368e8  mov     edx, 2
0x1401368ed  movzx   r9d, word ptr [rbp+57h+arg_8]
0x1401368f2  mov     r8, r13
0x1401368f5  mov     rcx, r14
0x1401368f8  call    VmsScalerInitialize
0x1401368fd  mov     rcx, [rbp+57h+var_58]
0x140136901  mov     rdx, r14
0x140136904  call    VmsQueueGroupPushScaler
0x140136909  mov     ebx, eax
0x14013690b  test    eax, eax
0x14013690d  jz      short loc_14013693C
0x14013690f  mov     edi, 1Bh
0x140136914  mov     rcx, cs:VmsIfrLog
0x14013691b  lea     r9d, [rdi+10h]
0x14013691f  lea     r8d, [rdi-7]
0x140136923  mov     [rsp+0E0h+var_C0], r12
0x140136928  mov     dl, 2
0x14013692a  call    WPP_RECORDER_SF_
0x14013692f  test    ebx, ebx
  ... truncated ...
```
