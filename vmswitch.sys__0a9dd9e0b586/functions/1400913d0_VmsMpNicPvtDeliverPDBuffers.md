# VmsMpNicPvtDeliverPDBuffers

- ea: `0x1400913d0`
- end: `0x14009203e`
- name: `VmsMpNicPvtDeliverPDBuffers`
- size: `3182`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140012d18`
- `0x140017a7c`
- `0x140017ca8`
- `0x1400211c0`
- `0x1400247dc`
- `0x140025be0`
- `0x140025d10`
- `0x140025f7c`
- `0x140027a64`
- `0x140027ba0`
- `0x14002ee00`
- `0x1400313cc`
- `0x14005e990`
- `0x14008497c`
- `0x1400913d0`
- `0x140092044`
- `0x140097d50`
- `0x1400f2adc`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140091e5f`
- `ntoskrnl!KeSetEvent` at `0x140091e5f`
- `ntoskrnl!KeInsertQueueDpc` at `0x140091e8b`
- `ntoskrnl!KeInsertQueueDpc` at `0x140091e8b`
- `ntoskrnl!KeIsExecutingDpc` at `0x140091f01`
- `ntoskrnl!KeIsExecutingDpc` at `0x140091f01`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140091f3a`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140091f3a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140091fbe`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140091fbe`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400915e3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400915e3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400914ef`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400918f1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400914ef`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400918f1`
- `ntoskrnl!KeGetProcessorIndexFromNumber` at `0x140091591`
- `ntoskrnl!KeGetProcessorIndexFromNumber` at `0x140091591`
- `ntoskrnl!KeGetCurrentIrql` at `0x14009144a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140091ef1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14009144a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140091ef1`
- `NDIS!NdisReleaseRWLock` at `0x140091eb2`
- `NDIS!NdisReleaseRWLock` at `0x140091fe1`
- `NDIS!NdisReleaseRWLock` at `0x140091eb2`
- `NDIS!NdisReleaseRWLock` at `0x140091fe1`

## string_xrefs

- `0x140091655`: `NT_SUCCESS(tempStatus)`

## pseudocode

```c
__int64 __fastcall VmsMpNicPvtDeliverPDBuffers(__int64 a1, __int64 a2, _QWORD *a3, int a4)
{
  unsigned __int64 v4; // rbp
  __int64 v6; // r13
  __int16 v7; // r12
  BOOLEAN v9; // di
  char v10; // r14
  __int64 EnabledReceiveChecksums; // rbx
  __int64 v12; // r8
  __int64 v13; // rcx
  ULONG CurrentProcessorNumber; // eax
  char v15; // cl
  __int64 v16; // r15
  ULONG ProcessorIndexFromNumber; // eax
  PVOID v18; // rax
  const char *v19; // r8
  int v20; // r9d
  _QWORD *v21; // r14
  __int64 v22; // r12
  int v23; // edx
  int v24; // esi
  int v25; // r12d
  __int64 *v26; // rsi
  __int64 *v27; // r15
  __int64 v28; // rcx
  __int64 v29; // rsi
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 *v32; // rcx
  __int64 *v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 *v39; // r14
  __int16 v40; // si
  __int64 NicHeaderAtIndex; // rax
  __int64 v42; // r8
  char v43; // r12
  __int64 NblGroup; // rbx
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 *v47; // r15
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // r9
  bool v53; // r10
  unsigned int v54; // ecx
  __int16 v55; // si
  unsigned int v56; // eax
  int ReceiveProc; // eax
  unsigned int v58; // ecx
  int v59; // edx
  unsigned int v60; // eax
  __int64 v61; // rax
  _QWORD **v62; // rcx
  __int64 v63; // rax
  char v64; // cl
  char v65; // dl
  char v66; // al
  int v67; // r9d
  char v68; // cl
  char v69; // dl
  bool v70; // al
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // r9
  unsigned __int8 v74; // cl
  char v75; // cl
  int v76; // ecx
  _QWORD *v77; // rax
  __int64 v78; // rcx
  __int64 v79; // rbx
  int v80; // eax
  int v81; // edx
  __int64 v82; // rbx
  char v83; // si
  int v84; // esi
  NTSTATUS v85; // eax
  int v86; // edx
  void *v87; // rdx
  _BYTE v89[2]; // [rsp+80h] [rbp+0h] BYREF
  _UNKNOWN *retaddr; // [rsp+1C8h] [rbp+148h]

  v4 = (unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL;
  *(_QWORD *)(v4 + 88) = a1;
  *(_WORD *)(v4 + 4) = 0;
  v6 = a1;
  *(_BYTE *)(v4 + 6) = 0;
  v7 = 0;
  *(_QWORD *)(v4 + 16) = 0;
  memset((void *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 128), 0, 0x80u);
  v9 = 1;
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = *(_QWORD *)(v6 + 3312);
  if ( (a4 & 1) != 0 || (v10 = 0, KeGetCurrentIrql() == 2) )
    v10 = 1;
  EnabledReceiveChecksums = (unsigned int)VmsMpCommonGetEnabledReceiveChecksums(v6, 6);
  if ( *(_DWORD *)(v6 + 68) != 1 || !(unsigned __int8)VmsMpNicIsStarted(v6) )
  {
    VmsPktReportDroppedPacketEx(v6, *a3, 4, 0, -1073676271, -536862612);
    return 0;
  }
  VmsPDSetCsoMetaDataForInternalForward(*a3, v6);
  if ( ((*(_DWORD *)(v6 + 1872) - 1) & 0xFFFFFFFD) != 0 )
    __fastfail(0xC0000024);
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = 0;
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = 0;
  v13 = 0;
  *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = 0;
  if ( *(_QWORD *)(v6 + 6320) )
    v13 = v6 + 5696;
  *(_WORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 2) = *(_WORD *)(v13 + 640);
  LOBYTE(v12) = v10;
  VmsOmObjectLockShared(v6, v4 + 4, v12);
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB4) = 0;
  *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0) = CurrentProcessorNumber;
  *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4) = VmsExecutionMode;
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = ((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL)
                                                                      + 136;
  v15 = 0;
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8) = VmsMpNicPvtReceiveRssProcessNblGroup;
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88) = 0;
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) = 0;
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = 0;
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = 0;
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = 0;
  *(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) = 0;
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8) = v6;
  *(_WORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0) = 0;
  *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) = a4 & 0xFFFFFFFE;
  if ( *(_BYTE *)(v6 + 4930) )
  {
    v16 = v6 + 4976;
    v7 = *(_WORD *)(v6 + 4976);
    ProcessorIndexFromNumber = KeGetProcessorIndexFromNumber((PPROCESSOR_NUMBER)(v6 + 4972));
    v15 = *(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD);
  }
  else
  {
    v16 = 0;
    ProcessorIndexFromNumber = 0;
  }
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0) = v16;
  *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xEC) = ProcessorIndexFromNumber;
  *(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) = v15 & 0xF8 | 3;
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD0) = 0;
  *(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2) = v10;
  *(_WORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8) = v7;
  v18 = ExAllocateFromNPagedLookasideList(&stru_1401FA0C0);
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = v18;
  if ( v18 )
    memset(v18, 0, 0x408u);
  else
    *(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) &= 0xFCu;
  v21 = (_QWORD *)*a3;
  *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = *a3;
  if ( !v21 )
    goto LABEL_168;
  do
  {
    v22 = *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
    v24 = VmsPDConvertPDBufferToNbl((_DWORD)v21, *(_QWORD *)(v22 + 392), (_DWORD)v19, v20, v4 + 16);
    if ( v24 >= 0 )
    {
      v26 = *(__int64 **)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
      v27 = v26;
      v26[15] = *(_QWORD *)(v22 + 24);
      VmsMpNicPvtDoReceiveChecksum(EnabledReceiveChecksums, v26, v6);
      v20 = 0;
      v28 = *v26;
      v25 = *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 8) + 1;
      *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v25;
      if ( v28 )
      {
        v29 = *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
        do
        {
          *(_QWORD *)(v28 + 120) = *(_QWORD *)(v29 + 24);
          VmsMpNicPvtDoReceiveChecksum(EnabledReceiveChecksums, *v27, v6);
          v27 = (__int64 *)*v27;
          ++v25;
          v28 = *v27;
        }
        while ( *v27 );
        v26 = *(__int64 **)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
        v20 = 0;
        v21 = *(_QWORD **)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
        *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v25;
      }
      if ( !*(_BYTE *)(v6 + 4930) || *(_DWORD *)(*(_QWORD *)(v21[3] + 8LL) + 1872LL) != 2 )
      {
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( v26 )
          {
            v30 = v26[36];
            if ( v30 )
            {
              v31 = *(_QWORD *)(v30 + 16);
              if ( v31 )
              {
                *(_QWORD *)(v31 + 176) = "VmsMpNicPvtSetRssHash";
                *(_DWORD *)(v31 + 184) = 4816;
                *(_QWORD *)(v31 + 168) = retaddr;
              }
            }
          }
        }
        v32 = v26;
        if ( *(_BYTE *)(v6 + 5496) )
        {
          VmsNblGenerateToeplitzRssHash(v26, 1, 0, v6 + 5496);
          v20 = 0;
        }
        else if ( v26 )
        {
          do
          {
            v33 = (__int64 *)*v32;
            LODWORD(v19) = (_DWORD)retaddr;
            if ( (VmsDiagnosticFlags & 1) != 0 )
            {
              if ( v33 )
              {
                v34 = v33[36];
                if ( v34 )
                {
                  v35 = *(_QWORD *)(v34 + 16);
                  if ( v35 )
                  {
                    *(_QWORD *)(v35 + 176) = "VmsMpNicPvtSetRssHash";
                    *(_DWORD *)(v35 + 184) = 4842;
                    *(_QWORD *)(v35 + 168) = retaddr;
                  }
                }
              }
            }
            v32[27] = 0;
            v32[26] = 0;
            *v32 = (__int64)v33;
            v32 = v33;
          }
          while ( v33 );
        }
      }
      v36 = *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
      if ( v36 )
      {
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( *(_QWORD *)v36 )
          {
            v37 = *(_QWORD *)(*(_QWORD *)v36 + 288LL);
            if ( v37 )
            {
              v38 = *(_QWORD *)(v37 + 16);
              if ( v38 )
              {
                v19 = "VmsMpNicPvtDeliverPDBuffers";
                *(_DWORD *)(v38 + 184) = 5825;
                *(_QWORD *)(v38 + 176) = "VmsMpNicPvtDeliverPDBuffers";
                *(_QWORD *)(v38 + 168) = retaddr;
              }
            }
          }
        }
        *(_QWORD *)v36 = v26;
      }
      else
      {
        *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = v26;
      }
      *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = v27;
    }
    else
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v23,
        19,
        83,
        (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
        (__int64)"NT_SUCCESS(tempStatus)");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
      VmsPktReportDroppedPacketEx(v6, (_DWORD)v21, 3, 0, v24, -536862611);
      v25 = *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
      v20 = 0;
    }
    v21 = (_QWORD *)*v21;
    *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v21;
  }
  while ( v21 );
  v39 = *(__int64 **)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30);
  if ( !v39 )
  {
LABEL_168:
    v83 = 1;
    goto LABEL_170;
  }
  v40 = *(_WORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 2) & 0x2000;
  *(_WORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 2) = v40;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) > 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_dq(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      22,
      84,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      v25,
      v6);
  NicHeaderAtIndex = VmsPtGetNicHeaderAtIndex(v6, 0);
  if ( NicHeaderAtIndex )
    _InterlockedAdd64(
      (volatile signed __int64 *)(*(_QWORD *)(NicHeaderAtIndex + 24)
                                + ((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)),
      v25);
  v43 = *(_BYTE *)(v6 + 4930);
  NblGroup = 0;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    v45 = v39[36];
    if ( v45 )
    {
      v46 = *(_QWORD *)(v45 + 16);
      if ( v46 )
      {
        *(_QWORD *)(v46 + 176) = "VmsMpNicPvtRssSortNbls";
        *(_DWORD *)(v46 + 184) = 288;
        *(_QWORD *)(v46 + 168) = retaddr;
      }
    }
  }
  do
  {
    v47 = (__int64 *)*v39;
    if ( (VmsDiagnosticFlags & 1) != 0 )
    {
      if ( v47 )
      {
        v48 = v47[36];
        if ( v48 )
        {
          v49 = *(_QWORD *)(v48 + 16);
          if ( v49 )
          {
            *(_QWORD *)(v49 + 176) = "VmsMpNicPvtRssSortNbls";
            *(_DWORD *)(v49 + 184) = 296;
            *(_QWORD *)(v49 + 168) = retaddr;
          }
        }
      }
    }
    *v39 = 0;
    if ( !v40 )
    {
      v68 = *(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD);
      if ( (v68 & 4) != 0 || (v69 = 0, (v68 & 2) != 0) )
        v69 = 1;
      v67 = *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0);
      if ( (v68 & 1) != 0 )
      {
        v70 = (*(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) & 4) != 0
           || (v68 & 2) != 0
           || v67 != -1 && (*(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4) & 6) != 0;
        NblGroup = 0;
        if ( !v70 )
          goto LABEL_137;
      }
      else if ( !v69 )
      {
LABEL_136:
        NblGroup = 0;
LABEL_137:
        v63 = v4 + 180;
        v62 = (_QWORD **)(v4 + 144);
        goto LABEL_138;
      }
      if ( NblGroup )
        goto LABEL_120;
      goto LABEL_119;
    }
    if ( !v43 )
    {
      v64 = *(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD);
      if ( (v64 & 4) != 0 || (v65 = 0, (v64 & 2) != 0) )
        v65 = 1;
      if ( (v64 & 1) != 0 )
      {
        if ( (*(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) & 4) != 0
          || (v64 & 2) != 0
          || *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0)
          || (v66 = 0, (*(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4) & 6) != 0) )
        {
          v66 = 1;
        }
        NblGroup = 0;
        if ( !v66 )
          goto LABEL_137;
      }
      else if ( !v65 )
      {
        goto LABEL_136;
      }
      if ( NblGroup )
        goto LABEL_120;
      v67 = 0;
LABEL_119:
      NblGroup = VmsVrssPvtFindNblGroup(
                   *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8),
                   *(unsigned __int16 *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0),
                   *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8),
                   v67,
                   *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8),
                   v4 + 128);
      if ( !NblGroup )
        goto LABEL_137;
LABEL_120:
      v62 = (_QWORD **)(NblGroup + 32);
      v63 = NblGroup + 48;
      goto LABEL_138;
    }
    if ( (VmsDiagnosticFlags & 1) != 0 )
    {
      v50 = v39[36];
      if ( v50 )
      {
        v51 = *(_QWORD *)(v50 + 16);
        if ( v51 )
        {
          *(_DWORD *)(v51 + 184) = 1123;
          *(_QWORD *)(v51 + 176) = "VmsVrssPrimeVrssContextForNextNbl";
          *(_QWORD *)(v51 + 168) = retaddr;
        }
      }
    }
    LOBYTE(v42) = *(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD);
    v52 = 0xFFFFFFFFLL;
    if ( (v42 & 4) != 0 || (v53 = 0, (v42 & 2) != 0) )
      v53 = 1;
    if ( (v42 & 1) != 0 )
    {
      v54 = *(unsigned __int16 *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8);
      v55 = -1;
      if ( (_WORD)v54 )
      {
        v56 = *((_DWORD *)v39 + 52);
        if ( v56 )
          v55 = v56 % v54;
      }
      if ( v55 == -1 )
        v52 = *(unsigned int *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xEC);
      NblGroup = *(_QWORD *)(*(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) + 8LL * v55 + 8);
      if ( !NblGroup )
      {
        if ( (_DWORD)v52 == -1 )
        {
          LOBYTE(v52) = *(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2);
          ReceiveProc = VmsMpNicPvtRssGetReceiveProc(
                          *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0),
                          (unsigned __int16)v55,
                          *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD0),
                          v52);
          LOBYTE(v42) = *(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD);
          LODWORD(v52) = ReceiveProc;
        }
        v53 = (v42 & 4) != 0
           || (v42 & 2) != 0
           || (_DWORD)v52 != -1
           && ((_DWORD)v52 != *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0)
            || (*(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4) & 6) != 0);
      }
    }
    else
    {
      NblGroup &= -(__int64)v53;
      if ( *(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBC) )
      {
        v58 = *(unsigned __int16 *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8);
        LOWORD(v59) = -1;
        if ( (_WORD)v58 )
        {
          v60 = *((_DWORD *)v39 + 52);
          if ( v60 )
            v59 = v60 % v58;
        }
        v55 = v59;
      }
      else
      {
        v55 = -2;
      }
    }
    if ( v53 )
    {
      if ( NblGroup )
        goto LABEL_103;
      if ( (_DWORD)v52 == -1 )
        LODWORD(v52) = *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0);
      v61 = VmsVrssPvtFindNblGroup(
              *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8),
              *(unsigned __int16 *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0),
              *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8),
              v52,
              *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8),
              v4 + 128);
      NblGroup = v61;
      if ( (*(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) & 1) != 0 )
        *(_QWORD *)(*(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) + 8LL * v55 + 8) = v61;
    }
    if ( NblGroup )
    {
LABEL_103:
      v62 = (_QWORD **)(NblGroup + 32);
      v63 = NblGroup + 48;
      goto LABEL_104;
    }
    v62 = (_QWORD **)(v4 + 144);
    v63 = v4 + 180;
LABEL_104:
    v40 = *(_WORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 2);
LABEL_138:
    *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = v62;
    *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) = v63;
    **v62 = v39;
    if ( (VmsDiagnosticFlags & 1) != 0 )
    {
      if ( *v39 )
      {
        v71 = *(_QWORD *)(*v39 + 288);
        if ( v71 )
        {
          v72 = *(_QWORD *)(v71 + 16);
          if ( v72 )
          {
            *(_QWORD *)(v72 + 176) = "VmsMpNicPvtRssSortNbls";
            *(_DWORD *)(v72 + 184) = 334;
            *(_QWORD *)(v72 + 168) = retaddr;
          }
        }
      }
    }
    **(_QWORD **)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = v39;
    v39 = v47;
    ++**(_DWORD **)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0);
  }
  while ( v47 );
  v73 = *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80);
  v6 = *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58);
  if ( v73 )
  {
    while ( 1 )
    {
      v74 = *(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD);
      *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = *(_QWORD *)v73;
      v75 = *(_BYTE *)(v73 + 58) ^ (*(_BYTE *)(v73 + 58) ^ (v74 >> 2)) & 2;
      *(_BYTE *)(v73 + 58) = v75;
      *(_BYTE *)(v73 + 58) = v75 ^ (v75 ^ (*(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) >> 2)) & 4;
      if ( (*(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) & 4) != 0 && !*(_QWORD *)(v73 + 16) )
        break;
      LOBYTE(v42) = *(_BYTE *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2);
      v79 = *(_QWORD *)(v73 + 16);
      v80 = VmsVrssPvtPushNblGroupToQueue(
              v73,
              *(unsigned int *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4),
              v42);
      if ( v80 )
      {
        if ( v80 == 1 )
        {
          _InterlockedAdd64((volatile signed __int64 *)(v79 + 464), 1u);
          v78 = v79;
        }
        else
        {
          v81 = v80 - 2;
          if ( v80 != 2 )
          {
            if ( v80 == 3 )
            {
              _InterlockedAdd64((volatile signed __int64 *)(v79 + 448), 1u);
              KeSetEvent((PRKEVENT)(v79 + 192), 3, 0);
            }
            else
            {
              LOBYTE(v81) = 2;
              WPP_RECORDER_SF_dq(
                VmsIfrLog,
                v81,
                20,
                14,
                (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids,
                v80,
                v79);
            }
            goto LABEL_159;
          }
          _InterlockedAdd64((volatile signed __int64 *)(v79 + 456), 1u);
          v78 = v79 + 64;
        }
        goto LABEL_158;
      }
LABEL_159:
      v73 = *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80);
      if ( !v73 )
        goto LABEL_160;
    }
    v76 = MEMORY[0x110];
    v77 = (_QWORD *)MEMORY[0x108];
    if ( *MEMORY[0x108] != 256 )
      __fastfail(3u);
    *(_QWORD *)(v73 + 8) = MEMORY[0x108];
    *(_QWORD *)v73 = 256;
    *v77 = v73;
    MEMORY[0x108] = v73;
    ++MEMORY[0x110];
    if ( v76 )
      goto LABEL_159;
    v78 = 128;
LABEL_158:
    KeInsertQueueDpc((PRKDPC)v78, 0, 0);
    goto LABEL_159;
  }
LABEL_160:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 56), (PLOCK_STATE_EX)(v4 + 4));
  v82 = *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88);
  *(_BYTE *)v4 = 0;
  v83 = 0;
  if ( v82 )
  {
    v84 = *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB4);
    *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48) = v84;
    *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) = 0;
    *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = v6;
    *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = v82;
    *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x4C) = 0;
    if ( KeGetCurrentIrql() >= 2u || (unsigned int)KeIsExecutingDpc() )
      v9 = 0;
    v85 = KeExpandKernelStackAndCalloutEx(VmsMpNicPvtIndicateCallout, (PVOID)(v4 + 56), 0x6000u, v9, 0);
    if ( v85 >= 0 )
    {
      v83 = 0;
    }
    else
    {
      LOBYTE(v86) = 2;
      WPP_RECORDER_SF_qdd(
        VmsIfrLog,
        v86,
        20,
        11,
        (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
        v82,
        v84,
        v85);
      VmsMpNicPvtIndicate(
        *(NDIS_HANDLE *)(*(_QWORD *)(*(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) + 3312LL) + 24LL),
        *(PNET_BUFFER_LIST *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40),
        *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48),
        *(_DWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0x4C));
      v83 = *(_BYTE *)v4;
    }
  }
LABEL_170:
  v87 = *(void **)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0);
  if ( v87 )
  {
    ExFreeToNPagedLookasideList(&stru_1401FA0C0, v87);
    *(_QWORD *)(((unsigned __int64)v89 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = 0;
  }
  if ( v83 )
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 56), (PLOCK_STATE_EX)(v4 + 4));
  return 0;
}

```

## disassembly

```asm
0x1400913d0  mov     [rsp-8+arg_8], rbx
0x1400913d5  push    rbp
0x1400913d6  push    rsi
0x1400913d7  push    rdi
0x1400913d8  push    r12
0x1400913da  push    r13
0x1400913dc  push    r14
0x1400913de  push    r15
0x1400913e0  sub     rsp, 190h
0x1400913e7  lea     rbp, [rsp+80h]
0x1400913ef  and     rbp, 0FFFFFFFFFFFFFFC0h
0x1400913f3  mov     rax, cs:__security_cookie
0x1400913fa  xor     rax, rsp
0x1400913fd  mov     [rbp+140h+var_40], rax
0x140091404  xor     eax, eax
0x140091406  mov     [rbp+140h+var_E8], rcx
0x14009140a  mov     rsi, r8
0x14009140d  mov     word ptr [rbp+140h+LockState.OldIrql], ax
0x140091411  mov     r13, rcx
0x140091414  mov     [rbp+140h+LockState.Flags], al
0x140091417  xor     r12d, r12d
0x14009141a  lea     rcx, [rbp+140h+var_C0]; void *
0x140091421  mov     r8d, 80h; Size
0x140091427  mov     [rbp+140h+var_130], r12
0x14009142b  xor     edx, edx; Val
0x14009142d  mov     r15d, r9d
0x140091430  call    memset
0x140091435  mov     rax, [r13+0CF0h]
0x14009143c  lea     edi, [r12+1]
0x140091441  mov     [rbp+140h+var_120], rax
0x140091445  test    dil, r15b
0x140091448  jnz     short loc_14009145D
0x14009144a  call    cs:__imp_KeGetCurrentIrql
0x140091451  nop     dword ptr [rax+rax+00h]
0x140091456  mov     r14b, r12b
0x140091459  cmp     al, 2
0x14009145b  jnz     short loc_140091460
0x14009145d  mov     r14b, dil
0x140091460  mov     edx, 6
0x140091465  mov     rcx, r13
0x140091468  call    VmsMpCommonGetEnabledReceiveChecksums
0x14009146d  mov     ebx, eax
0x14009146f  cmp     [r13+44h], edi
0x140091473  jnz     loc_140091FEF
0x140091479  mov     rcx, r13
0x14009147c  call    VmsMpNicIsStarted
0x140091481  test    al, al
0x140091483  jz      loc_140091FEF
0x140091489  mov     rcx, [rsi]
0x14009148c  mov     rdx, r13
0x14009148f  call    VmsPDSetCsoMetaDataForInternalForward
0x140091494  mov     eax, [r13+750h]
0x14009149b  mov     edx, 0FFFFFFFDh
0x1400914a0  lea     ecx, [rax-1]
0x1400914a3  test    edx, ecx
0x1400914a5  jz      short loc_1400914AE
0x1400914a7  mov     ecx, 0C0000024h
0x1400914ac  int     29h; Win8: RtlFailFast(ecx)
0x1400914ae  dec     eax
0x1400914b0  mov     [rbp+140h+var_110], r12
0x1400914b4  mov     [rbp+140h+var_118], r12
0x1400914b8  mov     rcx, r12
0x1400914bb  mov     [rbp+140h+var_138], r12d
0x1400914bf  test    edx, eax
0x1400914c1  jnz     short loc_1400914D3
0x1400914c3  cmp     [r13+18B0h], r12
0x1400914ca  jz      short loc_1400914D3
0x1400914cc  lea     rcx, [r13+1640h]
0x1400914d3  movzx   eax, word ptr [rcx+280h]
0x1400914da  lea     rdx, [rbp+140h+LockState]
0x1400914de  mov     rcx, r13
0x1400914e1  mov     [rbp+140h+var_13E], ax
0x1400914e5  mov     r8b, r14b
0x1400914e8  call    VmsOmObjectLockShared
0x1400914ed  xor     ecx, ecx; ProcNumber
0x1400914ef  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400914f6  nop     dword ptr [rax+rax+00h]
0x1400914fb  lea     rcx, [rbp+140h+var_B8]
0x140091502  mov     [rbp+140h+var_8C], r12d
0x140091509  mov     [rbp+140h+var_90], eax
0x14009150f  and     r15d, 0FFFFFFFEh
0x140091513  mov     eax, cs:VmsExecutionMode
0x140091519  mov     [rbp+140h+var_4C], eax
0x14009151f  lea     rax, VmsMpNicPvtReceiveRssProcessNblGroup
0x140091526  mov     [rbp+140h+var_B0], rcx
0x14009152d  mov     cl, r12b
0x140091530  mov     [rbp+140h+var_78], rax
0x140091537  mov     [rbp+140h+var_B8], r12
0x14009153e  mov     [rbp+140h+var_A0], r12
0x140091545  mov     [rbp+140h+var_A8], r12
0x14009154c  mov     [rbp+140h+Entry], r12
0x140091553  mov     [rbp+140h+var_C0], r12
0x14009155a  mov     [rbp+140h+var_83], cl
0x140091560  mov     [rbp+140h+var_68], r13
0x140091567  mov     [rbp+140h+var_50], r12w
0x14009156f  mov     [rbp+140h+var_58], r15d
0x140091576  cmp     [r13+1342h], r12b
0x14009157d  jz      short loc_1400915A5
0x14009157f  lea     r15, [r13+1370h]
0x140091586  movzx   r12d, word ptr [r15]
0x14009158a  lea     rcx, [r13+136Ch]; ProcNumber
0x140091591  call    cs:__imp_KeGetProcessorIndexFromNumber
0x140091598  nop     dword ptr [rax+rax+00h]
0x14009159d  mov     cl, [rbp+140h+var_83]
0x1400915a3  jmp     short loc_1400915AB
0x1400915a5  mov     r15, r12
0x1400915a8  mov     eax, r12d
0x1400915ab  and     cl, 0FBh
0x1400915ae  mov     [rbp+140h+var_80], r15
0x1400915b5  or      cl, 3
0x1400915b8  mov     [rbp+140h+var_54], eax
0x1400915be  mov     [rbp+140h+var_83], cl
0x1400915c4  xor     ecx, ecx
0x1400915c6  mov     [rbp+140h+var_70], rcx
0x1400915cd  lea     rcx, stru_1401FA0C0; Lookaside
0x1400915d4  mov     [rbp+140h+var_4E], r14b
0x1400915db  mov     [rbp+140h+var_88], r12w
0x1400915e3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400915ea  nop     dword ptr [rax+rax+00h]
0x1400915ef  mov     [rbp+140h+Entry], rax
0x1400915f6  test    rax, rax
0x1400915f9  jz      short loc_14009160D
0x1400915fb  xor     edx, edx; Val
0x1400915fd  mov     r8d, 408h; Size
0x140091603  mov     rcx, rax; void *
0x140091606  call    memset
0x14009160b  jmp     short loc_140091614
0x14009160d  and     [rbp+140h+var_83], 0FCh
0x140091614  mov     r14, [rsi]
0x140091617  mov     [rbp+140h+var_128], r14
0x14009161b  test    r14, r14
0x14009161e  jz      loc_140091FA3
0x140091624  lea     r15, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x14009162b  mov     r12, [rbp+140h+var_120]
0x14009162f  lea     rax, [rbp+140h+var_130]
0x140091633  mov     rcx, r14
0x140091636  mov     [rsp+1C0h+Context], rax
0x14009163b  mov     rdx, [r12+188h]
0x140091643  call    VmsPDConvertPDBufferToNbl
0x140091648  mov     esi, eax
0x14009164a  test    eax, eax
0x14009164c  jns     short loc_1400916A4
0x14009164e  mov     rcx, cs:VmsIfrLog
0x140091655  lea     rax, aNtSuccessTemps; "NT_SUCCESS(tempStatus)"
0x14009165c  mov     r9d, 53h ; 'S'
0x140091662  mov     [rsp+1C0h+var_198], rax
0x140091667  mov     [rsp+1C0h+Context], r15
0x14009166c  lea     r8d, [r9-40h]
0x140091670  call    WPP_RECORDER_SF_s
0x140091675  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "(((NTSTATUS)(tempStatus)) >= 0)")
0x14009167a  xor     r9d, r9d
0x14009167d  mov     dword ptr [rsp+1C0h+var_198], 0E000206Dh
0x140091685  mov     rdx, r14
0x140091688  mov     dword ptr [rsp+1C0h+Context], esi
0x14009168c  mov     rcx, r13
0x14009168f  lea     r8d, [r9+3]
0x140091693  call    VmsPktReportDroppedPacketEx
0x140091698  mov     r12d, [rbp+140h+var_138]
0x14009169c  xor     r9d, r9d
0x14009169f  jmp     loc_140091875
0x1400916a4  mov     rsi, [rbp+140h+var_130]
0x1400916a8  mov     r8, r13
0x1400916ab  mov     rax, [r12+18h]
0x1400916b0  mov     rdx, rsi
0x1400916b3  mov     rcx, rbx
0x1400916b6  mov     r15, rsi
0x1400916b9  mov     [rsi+78h], rax
0x1400916bd  call    VmsMpNicPvtDoReceiveChecksum
0x1400916c2  mov     r12d, [rbp+140h+var_138]
0x1400916c6  xor     r9d, r9d
0x1400916c9  mov     rcx, [rsi]
0x1400916cc  add     r12d, edi
0x1400916cf  mov     [rbp+140h+var_138], r12d
0x1400916d3  test    rcx, rcx
0x1400916d6  jz      short loc_14009170F
0x1400916d8  mov     rsi, [rbp+140h+var_120]
0x1400916dc  mov     rax, [rsi+18h]
0x1400916e0  mov     r8, r13
0x1400916e3  mov     [rcx+78h], rax
0x1400916e7  mov     rcx, rbx
0x1400916ea  mov     rdx, [r15]
0x1400916ed  call    VmsMpNicPvtDoReceiveChecksum
0x1400916f2  mov     r15, [r15]
0x1400916f5  add     r12d, edi
0x1400916f8  mov     rcx, [r15]
0x1400916fb  test    rcx, rcx
0x1400916fe  jnz     short loc_1400916DC
0x140091700  mov     rsi, [rbp+140h+var_130]
0x140091704  xor     r9d, r9d
0x140091707  mov     r14, [rbp+140h+var_128]
0x14009170b  mov     [rbp+140h+var_138], r12d
0x14009170f  cmp     [r13+1342h], r9b
0x140091716  jz      short loc_14009172D
0x140091718  mov     rax, [r14+18h]
0x14009171c  mov     rcx, [rax+8]
0x140091720  cmp     dword ptr [rcx+750h], 2
0x140091727  jz      loc_140091809
0x14009172d  mov     eax, cs:VmsDiagnosticFlags
0x140091733  lea     r10, aVmsmpnicpvtset; "VmsMpNicPvtSetRssHash"
0x14009173a  mov     rcx, [rsp+1C8h]
0x140091742  test    dil, al
0x140091745  jz      short loc_140091779
0x140091747  test    rsi, rsi
0x14009174a  jz      short loc_140091779
0x14009174c  mov     rax, [rsi+120h]
0x140091753  test    rax, rax
0x140091756  jz      short loc_140091779
0x140091758  mov     rax, [rax+10h]
0x14009175c  test    rax, rax
0x14009175f  jz      short loc_140091779
0x140091761  mov     [rax+0B0h], r10
0x140091768  mov     dword ptr [rax+0B8h], 12D0h
0x140091772  mov     [rax+0A8h], rcx
0x140091779  lea     rax, [r13+1578h]
0x140091780  mov     rcx, rsi
0x140091783  cmp     [rax], r9b
0x140091786  jz      short loc_14009179B
0x140091788  xor     r8d, r8d
0x14009178b  mov     r9, rax
0x14009178e  mov     dl, dil
0x140091791  call    VmsNblGenerateToeplitzRssHash
0x140091796  xor     r9d, r9d
0x140091799  jmp     short loc_140091809
0x14009179b  test    rsi, rsi
0x14009179e  jz      short loc_140091809
0x1400917a0  mov     eax, cs:VmsDiagnosticFlags
0x1400917a6  mov     rdx, [rcx]
0x1400917a9  mov     r8, [rsp+1C8h]
0x1400917b1  test    dil, al
0x1400917b4  jz      short loc_1400917E8
0x1400917b6  test    rdx, rdx
0x1400917b9  jz      short loc_1400917E8
0x1400917bb  mov     rax, [rdx+120h]
0x1400917c2  test    rax, rax
0x1400917c5  jz      short loc_1400917E8
0x1400917c7  mov     rax, [rax+10h]
0x1400917cb  test    rax, rax
0x1400917ce  jz      short loc_1400917E8
0x1400917d0  mov     [rax+0B0h], r10
0x1400917d7  mov     dword ptr [rax+0B8h], 12EAh
0x1400917e1  mov     [rax+0A8h], r8
0x1400917e8  mov     rax, [rsp+1C8h]
0x1400917f0  mov     [rcx+0D8h], r9
0x1400917f7  mov     [rcx+0D0h], r9
0x1400917fe  mov     [rcx], rdx
0x140091801  mov     rcx, rdx
0x140091804  test    rdx, rdx
0x140091807  jnz     short loc_1400917A0
0x140091809  mov     rdx, [rbp+140h+var_118]
0x14009180d  test    rdx, rdx
0x140091810  jz      short loc_140091866
0x140091812  mov     eax, cs:VmsDiagnosticFlags
0x140091818  mov     rcx, [rsp+1C8h]
0x140091820  test    dil, al
0x140091823  jz      short loc_140091861
0x140091825  mov     rax, [rdx]
0x140091828  test    rax, rax
0x14009182b  jz      short loc_140091861
0x14009182d  mov     rax, [rax+120h]
0x140091834  test    rax, rax
0x140091837  jz      short loc_140091861
0x140091839  mov     rax, [rax+10h]
0x14009183d  test    rax, rax
0x140091840  jz      short loc_140091861
0x140091842  lea     r8, aVmsmpnicpvtdel; "VmsMpNicPvtDeliverPDBuffers"
0x140091849  mov     dword ptr [rax+0B8h], 16C1h
0x140091853  mov     [rax+0B0h], r8
0x14009185a  mov     [rax+0A8h], rcx
0x140091861  mov     [rdx], rsi
0x140091864  jmp     short loc_14009186A
0x140091866  mov     [rbp+140h+var_110], rsi
0x14009186a  mov     [rbp+140h+var_118], r15
0x14009186e  lea     r15, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x140091875  mov     r14, [r14]
0x140091878  mov     [rbp+140h+var_128], r14
0x14009187c  test    r14, r14
0x14009187f  jnz     loc_14009162B
0x140091885  mov     r14, [rbp+140h+var_110]
0x140091889  test    r14, r14
0x14009188c  jz      loc_140091FA3
0x140091892  movzx   esi, [rbp+140h+var_13E]
0x140091896  mov     eax, 2000h
0x14009189b  and     si, ax
0x14009189e  mov     [rbp+140h+var_13E], si
0x1400918a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400918a9  cmp     byte ptr [rcx+29h], 5
0x1400918ad  ja      short loc_1400918B6
0x1400918af  cmp     [rcx+48h], r9w
0x1400918b4  jz      short loc_1400918DA
0x1400918b6  mov     rcx, [rcx+40h]
0x1400918ba  mov     r9d, 54h ; 'T'
0x1400918c0  mov     [rsp+1C0h+var_190], r13
0x1400918c5  xor     edx, edx
0x1400918c7  mov     dword ptr [rsp+1C0h+var_198], r12d
0x1400918cc  mov     [rsp+1C0h+Context], r15
0x1400918d1  lea     r8d, [r9-3Eh]
0x1400918d5  call    WPP_RECORDER_SF_dq
0x1400918da  xor     edx, edx
0x1400918dc  mov     rcx, r13
0x1400918df  call    VmsPtGetNicHeaderAtIndex
  ... truncated ...
```
