# VmsIovAllocateVF

- ea: `0x14012edb0`
- end: `0x14012fd26`
- name: `VmsIovAllocateVF`
- size: `3958`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400b8f68`

## callees

- `0x14000accc`
- `0x14000b440`
- `0x140014988`
- `0x140027a64`
- `0x14002e0f0`
- `0x14002e45c`
- `0x1400313cc`
- `0x140035438`
- `0x14003a450`
- `0x14003e804`
- `0x14004d37c`
- `0x14004f5d8`
- `0x140050da4`
- `0x14006b084`
- `0x1400721d8`
- `0x140074bb8`
- `0x14007a890`
- `0x1400845f8`
- `0x14008497c`
- `0x14008b3f0`
- `0x14008c624`
- `0x140094d5c`
- `0x14010c5e0`
- `0x140117cb0`
- `0x14011ee94`
- `0x14012edb0`
- `0x140130a2c`
- `0x1401311bc`
- `0x1401317dc`
- `0x1401321d8`
- `0x140132610`
- `0x14015c020`
- `0x14015dce8`
- `0x1401a1358`
- `0x1401bbcb0`
- `0x1401bc040`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14012fcaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012fce3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012fcaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012fce3`
- `ntoskrnl!ExAllocatePool2` at `0x14012f253`
- `ntoskrnl!ExAllocatePool2` at `0x14012f2b0`
- `ntoskrnl!ExAllocatePool2` at `0x14012f253`
- `ntoskrnl!ExAllocatePool2` at `0x14012f2b0`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x14012fcf2`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x14012fcf2`
- `NDIS!NdisReleaseRWLock` at `0x14012f20a`
- `NDIS!NdisReleaseRWLock` at `0x14012f8f5`
- `NDIS!NdisReleaseRWLock` at `0x14012f20a`
- `NDIS!NdisReleaseRWLock` at `0x14012f8f5`

## string_xrefs

- `0x14012fb99`: `tempStatus == NDIS_STATUS_SUCCESS`
- `0x14012fc1c`: `tempStatus == NDIS_STATUS_SUCCESS`
- `0x14012fc74`: `tempStatus == NDIS_STATUS_SUCCESS`
- `0x14012f08b`: `port->ParentSwitch->ProtocolNic`

## pseudocode

```c
__int64 __fastcall VmsIovAllocateVF(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v3; // rbx
  __int64 v5; // r13
  __int64 v6; // r15
  char *Pool2; // r14
  _DWORD *v8; // rsi
  __int64 v9; // r12
  int v10; // r9d
  int v11; // ecx
  _QWORD *v12; // rdx
  int v13; // ebx
  _DWORD *v14; // rax
  char v15; // r9
  int v16; // edx
  int v17; // r8d
  char IsIovConflictingPoliciesPresent; // al
  int v19; // edx
  char *v20; // rax
  __int64 v21; // rsi
  __int64 VmqExt; // rax
  int v23; // edx
  __int64 v24; // rax
  int v25; // edx
  unsigned __int16 v26; // ax
  unsigned __int16 v27; // ax
  unsigned __int16 v28; // ax
  __int64 v29; // r8
  int v30; // eax
  int v31; // edx
  char v32; // cl
  __int64 v33; // r9
  int v34; // r8d
  _DWORD *v35; // r15
  int NumQueuePairsInUse; // eax
  unsigned int v37; // edx
  unsigned int v38; // eax
  __int64 v39; // rdx
  _DWORD *v40; // r15
  int v41; // eax
  int v42; // edx
  int v43; // edx
  __int64 v44; // r15
  _QWORD *v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rdx
  _DWORD *v49; // rcx
  __int64 v50; // rsi
  __int64 v51; // rax
  unsigned int v52; // ecx
  int v53; // edx
  int v54; // edx
  int v55; // edx
  __int64 v56; // r8
  int v57; // edx
  int MappedNicIndexByObjNic; // [rsp+60h] [rbp-59h]
  char v60; // [rsp+64h] [rbp-55h]
  unsigned __int16 v61[2]; // [rsp+68h] [rbp-51h] BYREF
  char v62; // [rsp+6Ch] [rbp-4Dh]
  char v63; // [rsp+6Dh] [rbp-4Ch]
  char v64; // [rsp+6Eh] [rbp-4Bh]
  __int64 v65; // [rsp+70h] [rbp-49h]
  _DWORD *v66; // [rsp+78h] [rbp-41h]
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp-39h] BYREF
  struct _LOCK_STATE_EX v68; // [rsp+84h] [rbp-35h] BYREF
  int v69; // [rsp+88h] [rbp-31h] BYREF
  __int64 v70; // [rsp+90h] [rbp-29h]
  __int64 v71; // [rsp+98h] [rbp-21h] BYREF
  _DWORD *v72; // [rsp+A0h] [rbp-19h]
  __int64 v73; // [rsp+A8h] [rbp-11h]
  __int64 v74; // [rsp+B0h] [rbp-9h]
  PCEVENT_DESCRIPTOR EventDescriptor; // [rsp+B8h] [rbp-1h]
  _QWORD v76[2]; // [rsp+C0h] [rbp+7h] BYREF

  v3 = 0;
  v72 = a3;
  v70 = a2;
  *(_WORD *)&v68.OldIrql = 0;
  v68.Flags = 0;
  v5 = 0;
  v6 = 0;
  v74 = *(_QWORD *)(a1 + 3312);
  Pool2 = 0;
  EventDescriptor = &VM_NIC_ALLOCATE_VF_FAILED;
  v8 = 0;
  v69 = 0;
  v9 = 0;
  v63 = 0;
  v62 = 0;
  v64 = 0;
  v61[0] = 0;
  v66 = 0;
  v65 = 0;
  v71 = 0;
  VmsOmAssertIoctlMutexIsHeld();
  v11 = *(_DWORD *)(a1 + 1880);
  v12 = (_QWORD *)(v74 + 792);
  v76[0] = v74 + 792;
  if ( v11 != 1 || *v12 )
  {
    v13 = 5;
    MappedNicIndexByObjNic = -1073741436;
    WPP_RECORDER_SF_Lqd(v11, (_DWORD)v12, -1073741436, v10);
    goto LABEL_104;
  }
  if ( *(_DWORD *)(v74 + 580) == 3 )
  {
    if ( *(_DWORD *)(v74 + 596) < 0x40000u )
    {
      v13 = 12;
      MappedNicIndexByObjNic = -1073741637;
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_ddd(
        VmsIfrNicLog,
        (_DWORD)v12,
        20,
        52,
        (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
        *(_DWORD *)(v74 + 596),
        0,
        187);
      goto LABEL_104;
    }
    if ( (*(_BYTE *)(v74 + 564) & 4) == 0 )
    {
      v13 = 15;
      MappedNicIndexByObjNic = -1073741637;
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_d(
        VmsIfrNicLog,
        (_DWORD)v12,
        20,
        53,
        (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
        187);
      goto LABEL_104;
    }
    v6 = *(_QWORD *)(a1 + 1984);
    v73 = v6;
    v14 = *(_DWORD **)(v6 + 1240);
    if ( !v14[2142] )
    {
      v13 = 20;
      MappedNicIndexByObjNic = -1073741808;
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_d(VmsIfrNicLog, (_DWORD)v12, 20, 54, (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids, 16);
      goto LABEL_104;
    }
    if ( !v14[2143] )
    {
      v13 = 25;
      MappedNicIndexByObjNic = -1073741436;
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_d(
        VmsIfrNicLog,
        (_DWORD)v12,
        20,
        55,
        (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
        132);
      goto LABEL_104;
    }
    v15 = *(_BYTE *)(a1 + 1884);
    if ( (unsigned int)(v14[1068] - 2) > 1 || v15 )
    {
      v13 = 30;
      MappedNicIndexByObjNic = -1073741436;
      v52 = *(_DWORD *)(*(_QWORD *)(v6 + 1240) + 4272LL) - 2;
      WPP_RECORDER_SF_DDd(
        VmsIfrNicLog,
        v52 <= 1,
        20,
        56,
        (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
        v52 <= 1,
        v15,
        132);
      goto LABEL_104;
    }
    if ( !*(_DWORD *)(v6 + 6316) )
    {
      v13 = 35;
      MappedNicIndexByObjNic = -1073741811;
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_d(VmsIfrNicLog, (_DWORD)v12, 20, 57, (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids, 13);
      goto LABEL_104;
    }
    if ( (unsigned __int8)VmsOmPortIsIovConflictingPoliciesPresent(v6) )
    {
      v13 = 40;
      MappedNicIndexByObjNic = -1073741637;
      IsIovConflictingPoliciesPresent = VmsOmPortIsIovConflictingPoliciesPresent(v6);
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_ld(
        VmsIfrNicLog,
        v19,
        20,
        58,
        (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
        IsIovConflictingPoliciesPresent,
        187);
      goto LABEL_104;
    }
    if ( !*(_QWORD *)(*(_QWORD *)(v6 + 1240) + 4264LL) )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v16,
        19,
        59,
        (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
        "port->ParentSwitch->ProtocolNic");
      if ( !*(_QWORD *)(*(_QWORD *)(v6 + 1240) + 4264LL) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v5 = *(_QWORD *)(*(_QWORD *)(v6 + 1240) + 4264LL);
    v20 = (char *)(v5 + 4024);
    if ( *(_BYTE *)(v5 + 4025) || *v20 )
    {
      v13 = 45;
      MappedNicIndexByObjNic = -1073741436;
      WPP_RECORDER_SF_DDd(
        VmsIfrNicLog,
        v16,
        20,
        60,
        (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
        *(_BYTE *)(v5 + 4025),
        *v20,
        132);
      goto LABEL_104;
    }
    v21 = *(_QWORD *)(v5 + 3312);
    if ( !*(_BYTE *)(v21 + 305) )
    {
      v13 = 50;
      MappedNicIndexByObjNic = -1073740759;
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_d(VmsIfrNicLog, v16, 20, 61, (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids, 41);
LABEL_26:
      v8 = 0;
      goto LABEL_104;
    }
    if ( !*(_BYTE *)(v21 + 307) )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v16,
        19,
        62,
        (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
        "ptNicExt->VmqInfo.IovUsage");
      if ( !*(_BYTE *)(v21 + 307) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    if ( *(_DWORD *)(v21 + 1348) == *(_DWORD *)(v21 + 1452) )
    {
      v13 = 55;
      MappedNicIndexByObjNic = -1073741670;
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_LLd(
        VmsIfrNicLog,
        v16,
        v17,
        63,
        (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
        *(_DWORD *)(v21 + 1348),
        *(_DWORD *)(v21 + 1452),
        154);
      goto LABEL_26;
    }
    *(_WORD *)&LockState.OldIrql = 0;
    LockState.Flags = 0;
    VmsOmAssertIoctlMutexIsHeld();
    VmsOmObjectLockShared(a1, &LockState, 0);
    VmqExt = VmsMpCommonGetVmqExt(a1);
    if ( VmqExt )
      v3 = *(_QWORD *)(VmqExt + 16);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
    if ( v3 )
    {
      LODWORD(v3) = 0;
      MappedNicIndexByObjNic = VmsVmqDoVmqOperation(a1, v5, 2);
      if ( MappedNicIndexByObjNic < 0 )
      {
        v13 = 60;
        goto LABEL_26;
      }
      v64 = 1;
    }
    Pool2 = (char *)ExAllocatePool2(64, 360, 1953919830);
    if ( !Pool2 )
    {
      MappedNicIndexByObjNic = -1073741801;
      v13 = 65;
      LOBYTE(v23) = 2;
      WPP_RECORDER_SF_d(VmsIfrNicLog, v23, 20, 64, (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids, 104);
      goto LABEL_26;
    }
    v24 = ExAllocatePool2(64, 1632, 1953919830);
    v9 = v24;
    if ( !v24 )
    {
      MappedNicIndexByObjNic = -1073741801;
      v13 = 70;
      LOBYTE(v25) = 2;
      WPP_RECORDER_SF_d(VmsIfrNicLog, v25, 20, 65, (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids, 96);
LABEL_42:
      v8 = v66;
      goto LABEL_104;
    }
    *((_QWORD *)Pool2 + 1) = Pool2;
    *(_QWORD *)Pool2 = Pool2;
    *((_DWORD *)Pool2 + 8) = v3;
    *((_QWORD *)Pool2 + 2) = v5;
    *((_QWORD *)Pool2 + 3) = a1;
    *((_QWORD *)Pool2 + 12) = v5;
    *((_QWORD *)Pool2 + 13) = a1;
    *((_QWORD *)Pool2 + 34) = Pool2 + 264;
    *((_QWORD *)Pool2 + 33) = Pool2 + 264;
    *((_DWORD *)Pool2 + 30) = v3;
    *(_QWORD *)v24 = 106955136;
    *(_DWORD *)(v24 + 8) = v3;
    v26 = *(_WORD *)(a1 + 2112);
    v66 = Pool2 + 64;
    if ( v26 >= 0x200u )
      v26 = 512;
    *(_WORD *)(v9 + 528) = v26;
    memmove((void *)(v9 + 530), *(const void **)(a1 + 2120), v26);
    v27 = *(_WORD *)(a1 + 2640);
    if ( v27 >= 0x200u )
      v27 = 512;
    *(_WORD *)(v9 + 12) = v27;
    memmove((void *)(v9 + 14), *(const void **)(a1 + 2648), v27);
    v28 = *(_WORD *)(a1 + 72);
    if ( v28 >= 0x200u )
      v28 = 512;
    *(_WORD *)(v9 + 1044) = v28;
    memmove((void *)(v9 + 1046), *(const void **)(a1 + 80), v28);
    *(_WORD *)(v9 + 1560) = 6;
    *(_DWORD *)(v9 + 1562) = *(_DWORD *)(a1 + 2104);
    *(_WORD *)(v9 + 1566) = *(_WORD *)(a1 + 2108);
    *(_DWORD *)(v9 + 1594) = *(_DWORD *)(a1 + 3336);
    *(_WORD *)(v9 + 1598) = *(_WORD *)(a1 + 3340);
    *(_WORD *)(v9 + 1626) = -1;
    *(_DWORD *)(v9 + 1628) = -1;
    v61[0] = v3;
    v60 = VmsPtCheckIsEmbeddedTeamingEnabled(v5, 0);
    if ( v60 )
    {
      MappedNicIndexByObjNic = VmsTmGetMappedNicIndexByObjNic(a1, 1, v61);
      if ( MappedNicIndexByObjNic )
      {
        v13 = 75;
        goto LABEL_42;
      }
    }
    MappedNicIndexByObjNic = VmsPtNicAcquireMemberAdapter(v5, v61[0], 27, &v71);
    if ( MappedNicIndexByObjNic )
    {
      v13 = 105;
LABEL_54:
      v29 = v71;
      v8 = v66;
      goto LABEL_105;
    }
    v30 = VmsPtNicProcessPublicOid(a1, v5, 12, 66117, v61[0], v3, v3, v3, v9, 1632, 1632);
    v32 = v60;
    MappedNicIndexByObjNic = v30;
    if ( v60 )
    {
      VmsTmUpdateStubAllocationMaskByObjNic(a1, 1);
      v30 = MappedNicIndexByObjNic;
      v32 = v60;
    }
    if ( v30 )
    {
      v13 = 80;
      goto LABEL_54;
    }
    v33 = v70;
    *((_WORD *)Pool2 + 20) = *(_WORD *)(v9 + 1626);
    *((_DWORD *)Pool2 + 8) = 1;
    v63 = 1;
    if ( !*(_DWORD *)(v33 + 256) )
    {
      v13 = 85;
      MappedNicIndexByObjNic = -1073741811;
      LOBYTE(v31) = 2;
      WPP_RECORDER_SF_d(VmsIfrNicLog, v31, 20, 66, (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids, 13);
      goto LABEL_54;
    }
    v65 = v71;
    if ( v32 )
    {
      v34 = *(_DWORD *)(v71 + 640);
      v35 = (_DWORD *)(v71 + 376);
    }
    else
    {
      v35 = (_DWORD *)(v21 + 504);
      NumQueuePairsInUse = VmsPtGetNumQueuePairsInUse(v21);
      v33 = v70;
      v34 = NumQueuePairsInUse;
    }
    if ( (v35[8] & 4) != 0 )
    {
      v38 = v35[17];
      if ( *(_DWORD *)(v33 + 256) <= v38 )
        v38 = *(_DWORD *)(v33 + 256);
      else
        *(_DWORD *)(v33 + 256) = v38;
      v37 = v35[13] - v34;
      if ( v38 <= v37 )
      {
        v37 = v38;
      }
      else
      {
        *(_DWORD *)(v33 + 256) = v37;
        if ( !v37 )
        {
          v13 = 95;
          MappedNicIndexByObjNic = -1073741670;
          WPP_RECORDER_SF_LLLd(
            VmsIfrNicLog,
            0,
            20,
            68,
            (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
            0,
            v35[13],
            v34,
            154);
          goto LABEL_67;
        }
      }
    }
    else
    {
      v37 = *(_DWORD *)(v21 + 572);
      *(_DWORD *)(v33 + 256) = v37;
      if ( v37 > v35[13] - v34 )
      {
        v13 = 90;
        MappedNicIndexByObjNic = -1073741670;
        WPP_RECORDER_SF_LLLd(
          VmsIfrNicLog,
          v37,
          20,
          67,
          (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
          v37,
          v35[13],
          v34,
          154);
LABEL_67:
        v6 = v73;
        goto LABEL_42;
      }
    }
    MappedNicIndexByObjNic = VmsIovPvtIssueOidToCreateVPort(
                               v5,
                               a1,
                               0,
                               0,
                               v37,
                               *((_WORD *)Pool2 + 20),
                               *(_DWORD *)(v33 + 260));
    if ( !MappedNicIndexByObjNic )
    {
      v39 = v70;
      v40 = v66;
      v72[4] = *(_DWORD *)(v70 + 256);
      v40[12] = 1;
      v40[15] = *(_DWORD *)(a1 + 4188);
      v40[13] = 34;
      *((_QWORD *)Pool2 + 6) = v40;
      *((_DWORD *)Pool2 + 8) = 3;
      *((_DWORD *)Pool2 + 11) = *(_DWORD *)(v39 + 264);
      *((_DWORD *)Pool2 + 14) = *(_DWORD *)(v39 + 256);
      v41 = VmsVmNicSendVFAssociationMesg(a1, 1, *(unsigned int *)(v39 + 264));
      MappedNicIndexByObjNic = v41;
      if ( v41 )
      {
        LOBYTE(v42) = 2;
        WPP_RECORDER_SF_qqdd(
          VmsIfrNicLog,
          v42,
          20,
          69,
          (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
          a1,
          v70,
          *(_DWORD *)(v70 + 264),
          v41);
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v43,
          19,
          70,
          (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
          "!\"Investigate why VmsVmNicSendVFAssociationMesg() failed\"");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
        MappedNicIndexByObjNic = 0;
      }
      *((_DWORD *)Pool2 + 8) = 4;
      if ( v40[15] > *(_DWORD *)(v21 + 1420) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v42,
          19,
          71,
          (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
          "vmqBlock->VPortId <= ptNicExt->VmqInfo.VmqArrayCount");
        if ( v40[15] > *(_DWORD *)(v21 + 1420) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      if ( v60 )
      {
        MappedNicIndexByObjNic = VmsPtNicMUXGetAggregateVMQId(v61[0], (unsigned int)v40[15], &v69);
        if ( MappedNicIndexByObjNic )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v42,
            19,
            72,
            (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
            "status == NDIS_STATUS_SUCCESS");
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
      }
      else
      {
        v69 = v40[15];
      }
      v44 = (unsigned int)(v69 - 1);
      if ( *(_QWORD *)(*(_QWORD *)(v21 + 1424) + 8 * v44) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v42,
          19,
          73,
          (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
          "ptNicExt->VmqInfo.AllocatedVmqArray[vmqArrayIndex] == NULL");
        if ( *(_QWORD *)(*(_QWORD *)(v21 + 1424) + 8 * v44) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      *(_QWORD *)(*(_QWORD *)(v21 + 1424) + 8 * v44) = v66;
      v45 = (_QWORD *)(v21 + 1464);
      ++*(_DWORD *)(v21 + 1452);
      ++*(_DWORD *)(v21 + 1456);
      v46 = *(_QWORD *)(v21 + 1464);
      if ( *(_QWORD *)(v46 + 8) != v21 + 1464 )
        __fastfail(3u);
      *(_QWORD *)Pool2 = v46;
      *((_QWORD *)Pool2 + 1) = v45;
      *(_QWORD *)(v46 + 8) = Pool2;
      v62 = 1;
      *v45 = Pool2;
      VmsOmObjectLockExclusive(a1, &v68, 0);
      *(_QWORD *)v76[0] = Pool2;
      *(_BYTE *)(v74 + 800) = 0;
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &v68);
      v6 = v73;
      LOBYTE(v47) = 1;
      *(_DWORD *)(v73 + 6372) = 1;
      *(_WORD *)(v6 + 6384) = *((_WORD *)Pool2 + 20);
      *(_DWORD *)(v6 + 6388) = v72[4];
      VmsOmpObjectReference(v5, v47);
      LOBYTE(v48) = 1;
      VmsOmpObjectReference(a1, v48);
      v49 = v72;
      *v72 = *((unsigned __int16 *)Pool2 + 20);
      if ( byte_140223F44 )
      {
        memset(v76, 0, 12);
        MappedNicIndexByObjNic = VmsPtNicProcessPublicOid(a1, v5, 0, 66144, v61[0], 0, 0, 0, (__int64)v76, 12, 12);
        if ( MappedNicIndexByObjNic )
        {
          v13 = 110;
          goto LABEL_42;
        }
        v49 = v72;
        *(_QWORD *)(v21 + 1388) = *(_QWORD *)((char *)v76 + 4);
      }
      v13 = 0;
      if ( v60 )
      {
        v50 = v65;
        if ( !v65 )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            0,
            19,
            74,
            (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
            "memberAdapter != NULL");
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
          v49 = v72;
        }
        *(_QWORD *)(v49 + 1) = *(_QWORD *)(v50 + 3696);
        v51 = *(_QWORD *)(v50 + 112);
      }
      else
      {
        *(_QWORD *)(v49 + 1) = *(_QWORD *)(v21 + 1388);
        v51 = *(_QWORD *)(v21 + 2432);
      }
      *((_QWORD *)v49 + 3) = v51;
      v49[3] = *(_DWORD *)(v9 + 1628);
      goto LABEL_42;
    }
    v13 = 100;
    goto LABEL_67;
  }
  v13 = 10;
  MappedNicIndexByObjNic = -1073741436;
  EventDescriptor = (PCEVENT_DESCRIPTOR)VM_NIC_ALLOCATE_VF_FAILED_VSC_NOT_OPERATIONAL;
  WPP_RECORDER_SF_Ld(
    VmsIfrNicLog,
    (_DWORD)v12,
    -1073741436,
    51,
    (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
    *(_DWORD *)(v74 + 580),
    132);
LABEL_104:
  v29 = v65;
LABEL_105:
  VmsPtNicReleaseMemberAdapter(v5, 27, v29);
  if ( MappedNicIndexByObjNic )
  {
    LOBYTE(v53) = 2;
    WPP_RECORDER_SF_qqdd(
      VmsIfrNicLog,
      v53,
      20,
      75,
      (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
      a1,
      v70,
      v13,
      MappedNicIndexByObjNic);
    if ( v13 )
      VmsEtwTraceSwitchFailure(EventDescriptor, v13, a1 + 72, a1 + 616);
    if ( v62 )
    {
      VmsVmNicSendVFAssociationMesg(a1, 0, *(unsigned int *)(v70 + 264));
      if ( (unsigned int)VmsIovMoveFiltersToDefaultVPort(v8) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v54,
          19,
          76,
          (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
          "tempStatus == NDIS_STATUS_SUCCESS");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      if ( !*((_QWORD *)v8 + 5) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v54,
          19,
          77,
          (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
          "vmqBlock->Nic != NULL");
        if ( !*((_QWORD *)v8 + 5) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      if ( (unsigned int)VmsIovDeleteVPort(*((_QWORD *)v8 + 5), v5) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v55,
          19,
          78,
          (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
          "tempStatus == NDIS_STATUS_SUCCESS");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      *((_QWORD *)Pool2 + 6) = 0;
    }
    if ( v63 )
    {
      v56 = *((unsigned __int16 *)Pool2 + 20);
      *((_DWORD *)Pool2 + 8) = 5;
      if ( (unsigned int)VmsIovPvtIssueOidToDeleteVF(a1, v5, v56) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v57,
          19,
          79,
          (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
          "tempStatus == NDIS_STATUS_SUCCESS");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
    }
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
    if ( v64 )
    {
      VmsVmqDoVmqOperation(a1, v5, 1);
      if ( v6 )
        VmsIovUpdateMacFilters(v6);
    }
  }
  if ( v9 )
    ExFreePoolWithTag((PVOID)v9, 0);
  return NdisConvertNdisStatusToNtStatus((unsigned int)MappedNicIndexByObjNic);
}

```

## disassembly

```asm
0x14012edb0  mov     [rsp-8+arg_18], rbx
0x14012edb5  push    rbp
0x14012edb6  push    rsi
0x14012edb7  push    rdi
0x14012edb8  push    r12
0x14012edba  push    r13
0x14012edbc  push    r14
0x14012edbe  push    r15
0x14012edc0  lea     rbp, [rsp-27h]
0x14012edc5  sub     rsp, 0E0h
0x14012edcc  mov     rax, cs:__security_cookie
0x14012edd3  xor     rax, rsp
0x14012edd6  mov     [rbp+57h+var_40], rax
0x14012edda  xor     ebx, ebx
0x14012eddc  mov     [rbp+57h+var_70], r8
0x14012ede0  xor     eax, eax
0x14012ede2  mov     [rbp+57h+var_80], rdx
0x14012ede6  mov     word ptr [rbp+57h+var_8C.OldIrql], ax
0x14012edea  mov     rdi, rcx
0x14012eded  mov     [rbp+57h+var_8C.Flags], al
0x14012edf0  mov     r13d, ebx
0x14012edf3  mov     rax, [rcx+0CF0h]
0x14012edfa  mov     r15d, ebx
0x14012edfd  mov     [rbp+57h+var_60], rax
0x14012ee01  mov     r14d, ebx
0x14012ee04  lea     rax, VM_NIC_ALLOCATE_VF_FAILED
0x14012ee0b  mov     [rbp+57h+var_B0], ebx
0x14012ee0e  mov     [rbp+57h+EventDescriptor], rax
0x14012ee12  mov     esi, ebx
0x14012ee14  mov     [rbp+57h+var_88], ebx
0x14012ee17  mov     r12d, ebx
0x14012ee1a  mov     [rbp+57h+var_A3], bl
0x14012ee1d  mov     [rbp+57h+var_A4], bl
0x14012ee20  mov     [rbp+57h+var_A2], bl
0x14012ee23  mov     [rbp+57h+var_A8], bx
0x14012ee27  mov     [rbp+57h+var_98], rbx
0x14012ee2b  mov     [rbp+57h+var_A0], rbx
0x14012ee2f  mov     [rbp+57h+var_78], rbx
0x14012ee33  call    VmsOmAssertIoctlMutexIsHeld
0x14012ee38  mov     rax, [rbp+57h+var_60]
0x14012ee3c  lea     r11d, [rbx+14h]
0x14012ee40  mov     ecx, [rdi+758h]
0x14012ee46  lea     r10, WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids
0x14012ee4d  lea     rdx, [rax+318h]
0x14012ee54  mov     [rbp+57h+var_50], rdx
0x14012ee58  cmp     ecx, 1
0x14012ee5b  jnz     loc_14012FAC1
0x14012ee61  cmp     [rdx], rbx
0x14012ee64  jnz     loc_14012FAC1
0x14012ee6a  cmp     dword ptr [rax+244h], 3
0x14012ee71  jz      short loc_14012EEB5
0x14012ee73  lea     ebx, [rcx+9]
0x14012ee76  mov     r8d, 0C0000184h
0x14012ee7c  lea     rcx, VM_NIC_ALLOCATE_VF_FAILED_VSC_NOT_OPERATIONAL
0x14012ee83  mov     [rbp+57h+var_B0], r8d
0x14012ee87  mov     [rbp+57h+EventDescriptor], rcx
0x14012ee8b  mov     eax, [rax+244h]
0x14012ee91  lea     r9d, [r12+33h]
0x14012ee96  mov     rcx, cs:VmsIfrNicLog
0x14012ee9d  mov     dword ptr [rsp+110h+var_E0], r8d
0x14012eea2  mov     dword ptr [rsp+110h+var_E8], eax
0x14012eea6  mov     qword ptr [rsp+110h+var_F0], r10
0x14012eeab  call    WPP_RECORDER_SF_Ld
0x14012eeb0  jmp     loc_14012FAE6
0x14012eeb5  mov     ecx, 40000h
0x14012eeba  cmp     [rax+254h], ecx
0x14012eec0  jnb     short loc_14012EF03
0x14012eec2  mov     ebx, 0Ch
0x14012eec7  mov     [rbp+57h+var_B0], 0C00000BBh
0x14012eece  mov     eax, [rax+254h]
0x14012eed4  lea     r9d, [rbx+28h]
0x14012eed8  mov     [rsp+110h+var_D8], 0C00000BBh
0x14012eee0  mov     r8d, r11d
0x14012eee3  mov     dword ptr [rsp+110h+var_E0], ecx
0x14012eee7  mov     dl, 2
0x14012eee9  mov     rcx, cs:VmsIfrNicLog
0x14012eef0  mov     dword ptr [rsp+110h+var_E8], eax
0x14012eef4  mov     qword ptr [rsp+110h+var_F0], r10
0x14012eef9  call    WPP_RECORDER_SF_ddd
0x14012eefe  jmp     loc_14012FAE6
0x14012ef03  test    byte ptr [rax+234h], 4
0x14012ef0a  jnz     short loc_14012EF3F
0x14012ef0c  mov     ebx, 0Fh
0x14012ef11  mov     [rbp+57h+var_B0], 0C00000BBh
0x14012ef18  mov     rcx, cs:VmsIfrNicLog
0x14012ef1f  lea     r9d, [rbx+26h]
0x14012ef23  mov     dword ptr [rsp+110h+var_E8], 0C00000BBh
0x14012ef2b  mov     r8d, r11d
0x14012ef2e  mov     dl, 2
0x14012ef30  mov     qword ptr [rsp+110h+var_F0], r10
0x14012ef35  call    WPP_RECORDER_SF_d
0x14012ef3a  jmp     loc_14012FAE6
0x14012ef3f  mov     r15, [rdi+7C0h]
0x14012ef46  mov     [rbp+57h+var_68], r15
0x14012ef4a  mov     rax, [r15+4D8h]
0x14012ef51  cmp     [rax+2178h], ebx
0x14012ef57  jnz     short loc_14012EF89
0x14012ef59  mov     eax, 0C0000010h
0x14012ef5e  mov     ebx, r11d
0x14012ef61  mov     [rbp+57h+var_B0], eax
0x14012ef64  mov     rcx, cs:VmsIfrNicLog
0x14012ef6b  mov     r9d, 36h ; '6'
0x14012ef71  mov     dword ptr [rsp+110h+var_E8], eax
0x14012ef75  mov     r8d, r11d
0x14012ef78  mov     dl, 2
0x14012ef7a  mov     qword ptr [rsp+110h+var_F0], r10
0x14012ef7f  call    WPP_RECORDER_SF_d
0x14012ef84  jmp     loc_14012FAE6
0x14012ef89  cmp     [rax+217Ch], ebx
0x14012ef8f  jnz     short loc_14012EFC4
0x14012ef91  mov     r8d, 0C0000184h
0x14012ef97  mov     ebx, 19h
0x14012ef9c  mov     [rbp+57h+var_B0], r8d
0x14012efa0  mov     rcx, cs:VmsIfrNicLog
0x14012efa7  lea     r9d, [rbx+1Eh]
0x14012efab  mov     dword ptr [rsp+110h+var_E8], r8d
0x14012efb0  mov     dl, 2
0x14012efb2  mov     r8d, r11d
0x14012efb5  mov     qword ptr [rsp+110h+var_F0], r10
0x14012efba  call    WPP_RECORDER_SF_d
0x14012efbf  jmp     loc_14012FAE6
0x14012efc4  mov     eax, [rax+10B0h]
0x14012efca  mov     r9b, [rdi+75Ch]
0x14012efd1  sub     eax, 2
0x14012efd4  cmp     eax, 1
0x14012efd7  ja      loc_14012FA7B
0x14012efdd  test    r9b, r9b
0x14012efe0  jnz     loc_14012FA7B
0x14012efe6  cmp     [r15+18ACh], ebx
0x14012efed  jnz     short loc_14012F01F
0x14012efef  mov     eax, 0C000000Dh
0x14012eff4  mov     ebx, 23h ; '#'
0x14012eff9  mov     [rbp+57h+var_B0], eax
0x14012effc  mov     rcx, cs:VmsIfrNicLog
0x14012f003  lea     r9d, [rbx+16h]
0x14012f007  mov     dword ptr [rsp+110h+var_E8], eax
0x14012f00b  mov     r8d, r11d
0x14012f00e  mov     dl, 2
0x14012f010  mov     qword ptr [rsp+110h+var_F0], r10
0x14012f015  call    WPP_RECORDER_SF_d
0x14012f01a  jmp     loc_14012FAE6
0x14012f01f  mov     rcx, r15
0x14012f022  call    VmsOmPortIsIovConflictingPoliciesPresent
0x14012f027  test    al, al
0x14012f029  jz      short loc_14012F074
0x14012f02b  mov     ebx, 28h ; '('
0x14012f030  mov     [rbp+57h+var_B0], 0C00000BBh
0x14012f037  mov     rcx, r15
0x14012f03a  call    VmsOmPortIsIovConflictingPoliciesPresent
0x14012f03f  movzx   ecx, al
0x14012f042  lea     r9d, [rbx+12h]
0x14012f046  mov     eax, [rbp+57h+var_B0]
0x14012f049  lea     r8d, [rbx-14h]
0x14012f04d  mov     dword ptr [rsp+110h+var_E0], eax
0x14012f051  mov     dl, 2
0x14012f053  mov     dword ptr [rsp+110h+var_E8], ecx
0x14012f057  lea     rax, WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids
0x14012f05e  mov     rcx, cs:VmsIfrNicLog
0x14012f065  mov     qword ptr [rsp+110h+var_F0], rax
0x14012f06a  call    WPP_RECORDER_SF_ld
0x14012f06f  jmp     loc_14012FAE6
0x14012f074  mov     rax, [r15+4D8h]
0x14012f07b  cmp     [rax+10A8h], rbx
0x14012f082  jnz     short loc_14012F0C7
0x14012f084  mov     rcx, cs:VmsIfrLog
0x14012f08b  lea     rax, aPortParentswit; "port->ParentSwitch->ProtocolNic"
0x14012f092  mov     [rsp+110h+var_E8], rax
0x14012f097  mov     r9d, 3Bh ; ';'
0x14012f09d  lea     rax, WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids
0x14012f0a4  mov     qword ptr [rsp+110h+var_F0], rax
0x14012f0a9  lea     r8d, [r9-28h]
0x14012f0ad  call    WPP_RECORDER_SF_s
0x14012f0b2  mov     rax, [r15+4D8h]
0x14012f0b9  cmp     [rax+10A8h], rbx
0x14012f0c0  jnz     short loc_14012F0C7
0x14012f0c2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "port->ParentSwitch->ProtocolNic")
0x14012f0c7  mov     rax, [r15+4D8h]
0x14012f0ce  mov     r13, [rax+10A8h]
0x14012f0d5  lea     rax, [r13+0FB8h]
0x14012f0dc  cmp     [r13+0FB9h], bl
0x14012f0e3  jnz     loc_14012FA32
0x14012f0e9  cmp     [rax], bl
0x14012f0eb  jnz     loc_14012FA32
0x14012f0f1  mov     rsi, [r13+0CF0h]
0x14012f0f8  cmp     [rsi+131h], bl
0x14012f0fe  jnz     short loc_14012F13B
0x14012f100  mov     eax, 0C0000429h
0x14012f105  mov     ebx, 32h ; '2'
0x14012f10a  mov     [rbp+57h+var_B0], eax
0x14012f10d  mov     rcx, cs:VmsIfrNicLog
0x14012f114  lea     r9d, [rbx+0Bh]
0x14012f118  mov     dword ptr [rsp+110h+var_E8], eax
0x14012f11c  lea     r8d, [rbx-1Eh]
0x14012f120  lea     rax, WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids
0x14012f127  mov     dl, 2
0x14012f129  mov     qword ptr [rsp+110h+var_F0], rax
0x14012f12e  call    WPP_RECORDER_SF_d
0x14012f133  mov     rsi, r12
0x14012f136  jmp     loc_14012FAE6
0x14012f13b  cmp     [rsi+133h], bl
0x14012f141  jnz     short loc_14012F17E
0x14012f143  mov     rcx, cs:VmsIfrLog
0x14012f14a  lea     rax, aPtnicextVmqinf_12; "ptNicExt->VmqInfo.IovUsage"
0x14012f151  mov     [rsp+110h+var_E8], rax
0x14012f156  mov     r9d, 3Eh ; '>'
0x14012f15c  lea     rax, WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids
0x14012f163  mov     qword ptr [rsp+110h+var_F0], rax
0x14012f168  lea     r8d, [r9-2Bh]
0x14012f16c  call    WPP_RECORDER_SF_s
0x14012f171  cmp     [rsi+133h], bl
0x14012f177  jnz     short loc_14012F17E
0x14012f179  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ptNicExt->VmqInfo.IovUsage")
0x14012f17e  mov     ecx, [rsi+5ACh]
0x14012f184  cmp     [rsi+544h], ecx
0x14012f18a  jnz     short loc_14012F1D4
0x14012f18c  mov     eax, 0C000009Ah
0x14012f191  mov     ebx, 37h ; '7'
0x14012f196  mov     [rbp+57h+var_B0], eax
0x14012f199  mov     rcx, cs:VmsIfrNicLog
0x14012f1a0  lea     r9d, [rbx+8]
0x14012f1a4  mov     [rsp+110h+var_D8], eax
0x14012f1a8  mov     dl, 2
0x14012f1aa  mov     eax, [rsi+5ACh]
0x14012f1b0  mov     dword ptr [rsp+110h+var_E0], eax
0x14012f1b4  mov     eax, [rsi+544h]
0x14012f1ba  mov     dword ptr [rsp+110h+var_E8], eax
0x14012f1be  lea     rax, WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids
0x14012f1c5  mov     qword ptr [rsp+110h+var_F0], rax
0x14012f1ca  call    WPP_RECORDER_SF_LLd
0x14012f1cf  jmp     loc_14012F133
0x14012f1d4  xor     eax, eax
0x14012f1d6  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x14012f1da  mov     [rbp+57h+LockState.Flags], al
0x14012f1dd  call    VmsOmAssertIoctlMutexIsHeld
0x14012f1e2  xor     r8d, r8d
0x14012f1e5  lea     rdx, [rbp+57h+LockState]
0x14012f1e9  mov     rcx, rdi
0x14012f1ec  call    VmsOmObjectLockShared
0x14012f1f1  mov     rcx, rdi
0x14012f1f4  call    VmsMpCommonGetVmqExt
0x14012f1f9  test    rax, rax
0x14012f1fc  jz      short loc_14012F202
0x14012f1fe  mov     rbx, [rax+10h]
0x14012f202  mov     rcx, [rdi+38h]; Lock
0x14012f206  lea     rdx, [rbp+57h+LockState]; LockState
0x14012f20a  call    cs:__imp_NdisReleaseRWLock
0x14012f211  nop     dword ptr [rax+rax+00h]
0x14012f216  test    rbx, rbx
0x14012f219  jz      short loc_14012F243
0x14012f21b  mov     r8d, 2
0x14012f221  mov     rdx, r13
0x14012f224  mov     rcx, rdi
0x14012f227  call    VmsVmqDoVmqOperation
0x14012f22c  xor     ebx, ebx
0x14012f22e  mov     [rbp+57h+var_B0], eax
0x14012f231  test    eax, eax
0x14012f233  jns     short loc_14012F23F
0x14012f235  mov     ebx, 3Ch ; '<'
0x14012f23a  jmp     loc_14012F133
0x14012f23f  mov     [rbp+57h+var_A2], 1
0x14012f243  mov     edx, 168h
0x14012f248  mov     ecx, 40h ; '@'
0x14012f24d  mov     r8d, 74767356h
0x14012f253  call    cs:__imp_ExAllocatePool2
0x14012f25a  nop     dword ptr [rax+rax+00h]
0x14012f25f  mov     r14, rax
0x14012f262  test    rax, rax
0x14012f265  jnz     short loc_14012F2A0
0x14012f267  mov     [rbp+57h+var_B0], 0C0000017h
0x14012f26e  lea     ebx, [rax+41h]
0x14012f271  mov     rcx, cs:VmsIfrNicLog
0x14012f278  lea     r9d, [rax+40h]
0x14012f27c  lea     rax, WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids
0x14012f283  mov     dword ptr [rsp+110h+var_E8], 168h
0x14012f28b  lea     r8d, [r14+14h]
0x14012f28f  mov     qword ptr [rsp+110h+var_F0], rax
0x14012f294  mov     dl, 2
0x14012f296  call    WPP_RECORDER_SF_d
0x14012f29b  jmp     loc_14012F133
0x14012f2a0  mov     edx, 660h
0x14012f2a5  mov     ecx, 40h ; '@'
0x14012f2aa  mov     r8d, 74767356h
0x14012f2b0  call    cs:__imp_ExAllocatePool2
0x14012f2b7  nop     dword ptr [rax+rax+00h]
0x14012f2bc  mov     r12, rax
0x14012f2bf  test    rax, rax
0x14012f2c2  jnz     short loc_14012F302
0x14012f2c4  mov     [rbp+57h+var_B0], 0C0000017h
0x14012f2cb  lea     ebx, [rax+46h]
0x14012f2ce  mov     rcx, cs:VmsIfrNicLog
0x14012f2d5  lea     r9d, [rax+41h]
0x14012f2d9  lea     rax, WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids
0x14012f2e0  mov     dword ptr [rsp+110h+var_E8], 660h
0x14012f2e8  lea     r8d, [r12+14h]
0x14012f2ed  mov     qword ptr [rsp+110h+var_F0], rax
0x14012f2f2  mov     dl, 2
0x14012f2f4  call    WPP_RECORDER_SF_d
0x14012f2f9  mov     rsi, [rbp+57h+var_98]
0x14012f2fd  jmp     loc_14012FAE6
0x14012f302  mov     [r14+8], r14
  ... truncated ...
```
