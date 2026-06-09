# VmsMpNicPvtPacketForward

- ea: `0x140026000`
- end: `0x140027910`
- name: `VmsMpNicPvtPacketForward`
- size: `6416`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1400143ac`
- `0x140017ca8`
- `0x140018330`
- `0x14001d520`
- `0x14001e598`
- `0x1400211c0`
- `0x140022200`
- `0x1400247dc`
- `0x140025be0`
- `0x140025d10`
- `0x140025f7c`
- `0x140026000`
- `0x140027920`
- `0x140027a64`
- `0x140027ba0`
- `0x14002ee00`
- `0x14004fd84`
- `0x14006b4dc`
- `0x1400762cc`
- `0x14008497c`
- `0x1400f2adc`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002781e`
- `ntoskrnl!KeSetEvent` at `0x14002781e`
- `ntoskrnl!KeInsertQueueDpc` at `0x1400268e3`
- `ntoskrnl!KeInsertQueueDpc` at `0x1400268e3`
- `ntoskrnl!KeIsExecutingDpc` at `0x14002718a`
- `ntoskrnl!KeIsExecutingDpc` at `0x140027461`
- `ntoskrnl!KeIsExecutingDpc` at `0x14002718a`
- `ntoskrnl!KeIsExecutingDpc` at `0x140027461`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400273c9`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140027490`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400273c9`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140027490`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140026571`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140026571`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002636a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002636a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400260e3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140026278`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400265be`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400266ca`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400266e6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400260e3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140026278`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400265be`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400266ca`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400266e6`
- `ntoskrnl!KeGetProcessorIndexFromNumber` at `0x140026320`
- `ntoskrnl!KeGetProcessorIndexFromNumber` at `0x140026320`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400260c5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140026226`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027176`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027451`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027610`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400260c5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140026226`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027176`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027451`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027610`
- `NDIS!NdisAcquireRWLockRead` at `0x140026246`
- `NDIS!NdisAcquireRWLockRead` at `0x140026246`
- `NDIS!NdisReleaseRWLock` at `0x14002712a`
- `NDIS!NdisReleaseRWLock` at `0x14002741d`
- `NDIS!NdisReleaseRWLock` at `0x140027884`
- `NDIS!NdisReleaseRWLock` at `0x14002712a`
- `NDIS!NdisReleaseRWLock` at `0x14002741d`
- `NDIS!NdisReleaseRWLock` at `0x140027884`

## pseudocode

```c
__int64 __fastcall VmsMpNicPvtPacketForward(__int64 a1, __int16 a2, __int64 a3, int a4, char a5, char a6)
{
  unsigned __int64 v6; // rbp
  __int64 v9; // r12
  int v11; // edx
  __int64 *v12; // r14
  BOOLEAN v13; // di
  KIRQL CurrentIrql; // al
  __int64 CurrentProcessorNumber; // r15
  __int64 v16; // rax
  __int64 v17; // rbx
  int v18; // edx
  __int64 v19; // rbx
  _BYTE *v20; // rsi
  char v21; // r15
  __int64 v22; // rdx
  unsigned __int8 v23; // cf
  __int64 v24; // rsi
  int v25; // edx
  UCHAR v26; // r8
  __int64 v27; // r11
  ULONG v28; // eax
  char v29; // cl
  __int64 v30; // r14
  __int16 v31; // r15
  ULONG ProcessorIndexFromNumber; // eax
  char v33; // al
  PVOID v34; // rax
  __int64 v35; // rax
  _QWORD *v36; // r13
  __int64 v37; // r10
  __int64 v38; // r8
  unsigned int i; // edx
  __int64 v40; // rax
  unsigned __int64 v41; // r9
  __int64 v42; // r8
  _QWORD *v43; // r15
  const char *v44; // rdx
  __int64 v45; // r13
  char v46; // al
  bool v47; // r14
  _QWORD *v48; // r14
  int v49; // r15d
  char v50; // al
  __int64 *v51; // rsi
  char v52; // r14
  void *v53; // rdx
  unsigned int v54; // edi
  __int64 v56; // r14
  char v57; // cl
  int v58; // eax
  _QWORD *v59; // rsi
  int v60; // ebx
  int v61; // r15d
  char v62; // r13
  __int64 v63; // rbx
  char v64; // r12
  int v65; // edx
  __int64 *v66; // r15
  char v67; // cl
  char v68; // dl
  int v69; // r9d
  bool v70; // al
  __int64 v71; // rax
  _QWORD **v72; // rcx
  unsigned __int64 v73; // rax
  __int64 v74; // rcx
  unsigned __int8 v75; // dl
  char v76; // dl
  __int64 v77; // rbx
  int v78; // eax
  int v79; // edx
  __int64 v80; // rcx
  char v81; // cl
  char v82; // dl
  char v83; // al
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // r9
  bool v87; // r10
  unsigned int v88; // ecx
  __int16 v89; // r14
  unsigned int v90; // eax
  int ReceiveProc; // eax
  __int64 NblGroup; // rax
  __int64 v93; // rsi
  int v94; // r9d
  __int64 v95; // rcx
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rax
  __int64 v105; // rax
  unsigned int v106; // ecx
  unsigned int v107; // eax
  int CloneNbl; // eax
  char v109; // r9
  char v110; // cl
  char v111; // dl
  char v112; // al
  __int64 v113; // rax
  __int64 v114; // rax
  _BYTE *v115; // r9
  _QWORD *v116; // rcx
  __int64 v117; // rax
  __int64 v118; // rax
  char v119; // al
  _QWORD *v120; // rax
  char v121; // r9
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rbx
  int v125; // esi
  int v126; // eax
  _QWORD *v127; // rdx
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rax
  void *v131; // rcx
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  NTSTATUS v137; // eax
  int v138; // edx
  NTSTATUS v139; // eax
  int v140; // edx
  int LsoHint; // eax
  __int64 v142; // r8
  int DuplicateNblsCopyData; // eax
  char v144; // [rsp+A0h] [rbp+0h] BYREF
  void *retaddr; // [rsp+268h] [rbp+1C8h]

  v6 = (unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL;
  *(_QWORD *)(v6 + 72) = a3;
  *(_QWORD *)(v6 + 216) = a1;
  v9 = a1;
  *(_DWORD *)(v6 + 20) = 0;
  memset((void *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 256), 0, 0x80u);
  *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = 0;
  *(_WORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = 0;
  *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA) = 0;
  *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC) = 0;
  *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0) = 0;
  *(_WORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = 0;
  *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 6) = 0;
  *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = 0;
  if ( a2 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v11,
      19,
      78,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      (__int64)"NicIndex == 0");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v12 = (__int64 *)(a3 + 16);
  if ( !*(_QWORD *)(a3 + 16) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v11,
      19,
      79,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      (__int64)"NetPacket->NetBufferLists != NULL");
    if ( !*v12 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( (a4 & 0xFFFFFFFE) != 0 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v11,
      19,
      80,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      (__int64)"(SendFlags & ~NDIS_SEND_FLAGS_DISPATCH_LEVEL) == 0");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v13 = 1;
  if ( (a4 & 1) != 0
    || (CurrentIrql = KeGetCurrentIrql(),
        *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 2) = 0,
        CurrentIrql == 2) )
  {
    *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 2) = 1;
  }
  *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = 0;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v16 = 0;
  v17 = 0;
  *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x68) = 0;
  *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) = 0;
  if ( !*v12 )
  {
    v54 = 0;
    goto LABEL_66;
  }
  v18 = *(_DWORD *)(v9 + 3476);
  v19 = (v18 & 0x300) != 0 ? -1 : -37;
  if ( (v18 & 0x30) == 0 || (*(_DWORD *)(v9 + 3492) & 0x30) == 0 )
    v19 = (unsigned int)v19 & 0xFFFFFFF6;
  if ( (v18 & 0xC0) == 0 || (*(_DWORD *)(v9 + 3492) & 0xC0) == 0 )
    v19 = (unsigned int)v19 & 0xFFFFFFED;
  if ( *(_DWORD *)(v9 + 68) != 1
    || (v20 = *(_BYTE **)(v9 + 3312),
        *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = v20,
        !(unsigned __int8)VmsMpNicPvtAcquireOutgoingRefCount(v9)) )
  {
    v54 = -1073741823;
    VmsPktReportDroppedPacketEx(v9, *(_QWORD *)(a3 + 16), 2, 0, -1073676271, -536862666);
    goto LABEL_326;
  }
  if ( v20[709] >= 3u )
  {
    v81 = *(_BYTE *)(*(_QWORD *)(v9 + 1984) + 6364LL);
    if ( !*(_BYTE *)(v9 + 3954) || (v82 = 1, !v81) )
      v82 = 0;
    if ( !*(_BYTE *)(v9 + 3955) || (v83 = 1, !v81) )
      v83 = 0;
    if ( !v20[852] || (*(_BYTE *)v6 = 1, !v82) )
      *(_BYTE *)v6 = 0;
    if ( v20[853] && v83 )
    {
      *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 1) = 1;
      goto LABEL_18;
    }
  }
  else
  {
    *(_BYTE *)v6 = 0;
  }
  *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 1) = 0;
LABEL_18:
  if ( *(_BYTE *)(a3 + 12) )
  {
    v93 = *(_QWORD *)(v9 + 1888);
    if ( !*(_BYTE *)(v93 + 9176) )
    {
      memset((void *)(v6 + 128), 0, 0x40u);
      *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = *(_QWORD *)(v9 + 9376)
                                                                            + (CurrentProcessorNumber << 7);
      if ( *(_BYTE *)(v93 + 9194) )
        v94 = *(unsigned __int16 *)(v93 + 9196);
      else
        v94 = 4789;
      NvLibRscCoalesceNbls(
        a3 + 16,
        (unsigned int)&VmsRscLayerNvspHVNicCookie,
        v6 + 128,
        v94,
        *(_BYTE *)v6,
        *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 1),
        v6 + 32);
    }
  }
  if ( !VmsHostNicIndicateNblsInline || *(_DWORD *)(a3 + 8) == 1 )
  {
    v21 = 1;
    *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 1;
    if ( *(_DWORD *)(a3 + 8) == 1 )
      goto LABEL_297;
    if ( ((*(_DWORD *)(v9 + 1872) - 1) & 0xFFFFFFFD) != 0 )
      __fastfail(0xC0000024);
    v22 = 0;
    if ( *(_QWORD *)(v9 + 6320) )
      v22 = v9 + 5696;
    v23 = _bittest16((const signed __int16 *)(v22 + 640), 0xDu);
    *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 3) = 0;
    if ( v23 )
LABEL_297:
      *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 3) = 1;
  }
  else
  {
    *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 3) = 0;
    v21 = 0;
    *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
  }
  v24 = *v12;
  *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = *v12;
  *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 5) = 0;
  *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 6) = 1;
  if ( a6 )
  {
    if ( KeGetCurrentIrql() != 2 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v25,
        19,
        24,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
      if ( KeGetCurrentIrql() != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v26 = 1;
  }
  else
  {
    v26 = 0;
  }
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v9 + 56), (PLOCK_STATE_EX)(v6 + 8), v26);
  v27 = 0;
  if ( !*(_BYTE *)(v9 + 4930) || !*(_BYTE *)(a3 + 12) )
  {
    v115 = (_BYTE *)(v9 + 5496);
    if ( (VmsDiagnosticFlags & 1) != 0 )
    {
      if ( v24 )
      {
        v117 = *(_QWORD *)(v24 + 288);
        if ( v117 )
        {
          v118 = *(_QWORD *)(v117 + 16);
          if ( v118 )
          {
            *(_QWORD *)(v118 + 176) = "VmsMpNicPvtSetRssHash";
            *(_DWORD *)(v118 + 184) = 4816;
            *(_QWORD *)(v118 + 168) = retaddr;
          }
        }
      }
    }
    v116 = (_QWORD *)v24;
    if ( *v115 )
    {
      VmsNblGenerateToeplitzRssHash((__int64 *)v24, 1, 0, (__int64)v115);
      v27 = 0;
    }
    else if ( v24 )
    {
      do
      {
        v127 = (_QWORD *)*v116;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( v127 )
          {
            v128 = v127[36];
            if ( v128 )
            {
              v129 = *(_QWORD *)(v128 + 16);
              if ( v129 )
              {
                *(_QWORD *)(v129 + 176) = "VmsMpNicPvtSetRssHash";
                *(_DWORD *)(v129 + 184) = 4842;
                *(_QWORD *)(v129 + 168) = retaddr;
              }
            }
          }
        }
        v116[27] = 0;
        v116[26] = 0;
        *v116 = v127;
        v116 = v127;
      }
      while ( v127 );
    }
  }
  if ( v21 )
  {
    v28 = KeGetCurrentProcessorNumberEx(0);
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x158) = v9;
    *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x130) = v28;
    *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x174) = VmsExecutionMode;
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x110) = ((unsigned __int64)&v144
                                                                            & 0xFFFFFFFFFFFFFFC0uLL)
                                                                           + 264;
    v29 = 0;
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x148) = VmsMpNicPvtReceiveRssProcessNblGroup;
    *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x134) = 0;
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x108) = 0;
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x120) = 0;
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x118) = 0;
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160) = 0;
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x100) = 0;
    *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D) = 0;
    *(_WORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x170) = 0;
    *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x168) = 0;
    if ( *(_BYTE *)(v9 + 4930) )
    {
      v30 = v9 + 4976;
      v31 = *(_WORD *)(v9 + 4976);
      ProcessorIndexFromNumber = KeGetProcessorIndexFromNumber((PPROCESSOR_NUMBER)(v9 + 4972));
      v29 = *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D);
    }
    else
    {
      v30 = 0;
      ProcessorIndexFromNumber = 0;
      v31 = 0;
    }
    *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x16C) = ProcessorIndexFromNumber;
    v33 = *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 2);
    *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D) = v29 & 0xF8 | 3;
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x140) = v30;
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x150) = 0;
    *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x172) = v33;
    *(_WORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x138) = v31;
    v34 = ExAllocateFromNPagedLookasideList(&stru_1401FA0C0);
    v27 = 0;
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160) = v34;
    if ( v34 )
    {
      memset(v34, 0, 0x408u);
      v27 = 0;
    }
    else
    {
      *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D) &= 0xFCu;
    }
    *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 5) = 1;
  }
  v35 = *(_QWORD *)(v24 + 288);
  v36 = (_QWORD *)(v6 + 200);
  *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8) = 0;
  v37 = 0;
  *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) = ((unsigned __int64)&v144
                                                                         & 0xFFFFFFFFFFFFFFC0uLL)
                                                                        + 200;
  *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = 0;
  *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x78) = 0;
  if ( v35 )
  {
    v95 = *(_QWORD *)(v35 + 16);
    if ( v95 )
    {
      v37 = *(_QWORD *)(v95 + 24);
      *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x78) = v37;
    }
  }
  v38 = 0;
  for ( i = 0; i < VmsActiveProcCount; v38 += *((_QWORD *)VmsPlanCpuTable + 680 * v40 + 672) )
    v40 = i++;
  v41 = 0;
  if ( v38 >= 0 )
    v41 = v38;
  v42 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48);
  *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = v41;
  if ( *(_BYTE *)(v42 + 12) )
  {
    v43 = (_QWORD *)(v6 + 104);
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = ((unsigned __int64)&v144
                                                                           & 0xFFFFFFFFFFFFFFC0uLL)
                                                                          + 104;
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) = ((unsigned __int64)&v144
                                                                           & 0xFFFFFFFFFFFFFFC0uLL)
                                                                          + 96;
    v44 = "VmsMpNicPvtPacketForward";
    while ( 1 )
    {
      v45 = *(_QWORD *)v24;
      v46 = VmsDiagnosticFlags;
      *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD0) = *(_QWORD *)v24;
      if ( (v46 & 1) != 0 )
      {
        if ( v45 )
        {
          v96 = *(_QWORD *)(v45 + 288);
          if ( v96 )
          {
            v97 = *(_QWORD *)(v96 + 16);
            if ( v97 )
            {
              *(_QWORD *)(v97 + 176) = "VmsMpNicPvtPacketForward";
              *(_DWORD *)(v97 + 184) = 5334;
              *(_QWORD *)(v97 + 168) = retaddr;
            }
          }
        }
      }
      *(_QWORD *)v24 = 0;
      v47 = *(_WORD *)(v24 + 320)
         && (!*(_BYTE *)v6 || !*(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 1));
      if ( **(_QWORD **)(v24 + 8) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          (unsigned int)"VmsMpNicPvtPacketForward",
          19,
          81,
          (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
          (__int64)"curNbl->FirstNetBuffer->Next == NULL");
        v27 = 0;
        if ( **(_QWORD **)(v24 + 8) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
          v27 = 0;
        }
        v42 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48);
        v41 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
      }
      if ( !v47 )
      {
        if ( a5 )
        {
          v48 = (_QWORD *)v24;
          *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = v24;
          goto LABEL_50;
        }
        CloneNbl = VmsNblHelperCreateCloneNbl(
                     (PNET_BUFFER_LIST)v24,
                     *(NDIS_HANDLE *)(*(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) + 400LL),
                     *(void **)(*(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) + 408LL),
                     *(_BYTE *)(v42 + 12),
                     0,
                     0,
                     0,
                     (struct _NET_BUFFER_LIST **)(v6 + 56));
        v27 = 0;
        if ( CloneNbl >= 0 )
          goto LABEL_203;
        *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = 0;
        VmsPktGetDropReason((unsigned int)CloneNbl, v6 + 32);
        VmsPktReportDroppedNbl(
          v9,
          v24,
          0,
          *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20),
          v109,
          -536862661);
        v27 = 0;
LABEL_188:
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( *(_QWORD *)v24 )
          {
            v113 = *(_QWORD *)(*(_QWORD *)v24 + 288LL);
            if ( v113 )
            {
              v114 = *(_QWORD *)(v113 + 16);
              if ( v114 )
              {
                *(_DWORD *)(v114 + 184) = 5496;
                *(_QWORD *)(v114 + 176) = "VmsMpNicPvtPacketForward";
                *(_QWORD *)(v114 + 168) = retaddr;
              }
            }
          }
        }
        *(_QWORD *)v24 = v45;
        goto LABEL_56;
      }
      if ( v41 < VmsMaxOutstandingDuplicateNblBytes )
      {
        LsoHint = NvLibRscGetLsoHint(v24, (_DWORD)v44, (int)v6 + 192, (int)v6 + 12, v6 + 24);
        if ( LsoHint >= 0 )
        {
          v142 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48);
          LOBYTE(v142) = *(_BYTE *)(v142 + 12);
          DuplicateNblsCopyData = VmsNblHelperCreateDuplicateNblsCopyData(
                                    v24,
                                    *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40)
                                              + 392LL),
                                    v142,
                                    0,
                                    0,
                                    0,
                                    v6 + 192,
                                    *(_WORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18),
                                    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x78),
                                    v9,
                                    v6 + 56,
                                    v6 + 48);
          v27 = 0;
          if ( DuplicateNblsCopyData >= 0 )
          {
            *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) += *(unsigned int *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30);
            if ( a5 )
            {
              **(_QWORD **)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) = v24;
              if ( (VmsDiagnosticFlags & 1) != 0 )
              {
                if ( *(_QWORD *)v24 )
                {
                  v135 = *(_QWORD *)(*(_QWORD *)v24 + 288LL);
                  if ( v135 )
                  {
                    v136 = *(_QWORD *)(v135 + 16);
                    if ( v136 )
                    {
                      *(_DWORD *)(v136 + 184) = 5434;
                      *(_QWORD *)(v136 + 176) = "VmsMpNicPvtPacketForward";
                      *(_QWORD *)(v136 + 168) = retaddr;
                    }
                  }
                }
              }
              *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) = v24;
            }
LABEL_203:
            v48 = *(_QWORD **)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38);
LABEL_50:
            **(_QWORD **)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) = v48;
            if ( v48 )
            {
              v49 = *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
              do
              {
                v48[15] = *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) + 24LL);
                VmsMpNicPvtDoReceiveChecksum(v19, v48, v9);
                v50 = VmsDiagnosticFlags;
                v27 = 0;
                *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) = v48;
                if ( (v50 & 1) != 0 )
                {
                  if ( *v48 )
                  {
                    v84 = *(_QWORD *)(*v48 + 288LL);
                    if ( v84 )
                    {
                      v85 = *(_QWORD *)(v84 + 16);
                      if ( v85 )
                      {
                        *(_QWORD *)(v85 + 176) = "VmsMpNicPvtPacketForward";
                        *(_DWORD *)(v85 + 184) = 5488;
                        *(_QWORD *)(v85 + 168) = retaddr;
                      }
                    }
                  }
                }
                ++v49;
                v48 = (_QWORD *)*v48;
              }
              while ( v48 );
              v24 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
              v45 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD0);
              *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v49;
              v43 = *(_QWORD **)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58);
              *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = 0;
            }
            if ( a5 )
              goto LABEL_56;
            goto LABEL_188;
          }
          VmsPktReportDroppedPacketEx(v9, v24, 1, 0, DuplicateNblsCopyData, -536862662);
          v27 = 0;
          if ( !a5 )
            goto LABEL_188;
          v131 = retaddr;
          *v43 = v24;
          if ( (VmsDiagnosticFlags & 1) != 0 )
          {
            if ( *(_QWORD *)v24 )
            {
              v134 = *(_QWORD *)(*(_QWORD *)v24 + 288LL);
              if ( v134 )
              {
                v130 = *(_QWORD *)(v134 + 16);
                if ( v130 )
                {
                  *(_DWORD *)(v130 + 184) = 5424;
                  goto LABEL_261;
                }
              }
            }
          }
        }
        else
        {
          VmsPktReportDroppedPacketEx(v9, v24, 1, 0, LsoHint, -536862663);
          v27 = 0;
          if ( !a5 )
            goto LABEL_188;
          v131 = retaddr;
          *v43 = v24;
          if ( (VmsDiagnosticFlags & 1) != 0 )
          {
            if ( *(_QWORD *)v24 )
            {
              v133 = *(_QWORD *)(*(_QWORD *)v24 + 288LL);
              if ( v133 )
              {
                v130 = *(_QWORD *)(v133 + 16);
                if ( v130 )
                {
                  *(_DWORD *)(v130 + 184) = 5389;
LABEL_261:
                  *(_QWORD *)(v130 + 176) = "VmsMpNicPvtPacketForward";
                  *(_QWORD *)(v130 + 168) = v131;
                }
              }
            }
          }
        }
      }
      else
      {
        VmsPktReportDroppedNbl(v9, v24, 0, 3, 154, -536862664);
        v27 = 0;
        if ( !a5 )
          goto LABEL_188;
        v131 = retaddr;
        *v43 = v24;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( *(_QWORD *)v24 )
          {
            v132 = *(_QWORD *)(*(_QWORD *)v24 + 288LL);
            if ( v132 )
            {
              v130 = *(_QWORD *)(v132 + 16);
              if ( v130 )
              {
                *(_DWORD *)(v130 + 184) = 5363;
                goto LABEL_261;
              }
            }
          }
        }
      }
      v43 = (_QWORD *)v24;
      *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = v24;
LABEL_56:
      v41 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
      v24 = v45;
      v42 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48);
      v44 = "VmsMpNicPvtPacketForward";
      *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v45;
      if ( !v45 )
      {
        **(_QWORD **)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) = 0;
        goto LABEL_58;
      }
    }
  }
  do
  {
    v56 = *(_QWORD *)v24;
    if ( v41 >= VmsMaxOutstandingDuplicateNblBytes )
    {
      VmsPktReportDroppedNbl(v9, v24, 0, 3, 154, -536862664);
LABEL_233:
      v27 = 0;
      goto LABEL_226;
    }
    if ( !*(_BYTE *)v6 || (v57 = 1, !*(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 1)) )
      v57 = 0;
    v58 = VmsNblHelperCreateDuplicateNblsCopyData(
            v24,
            *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) + 392LL),
            0,
            0,
            1,
            v57,
            0,
            0,
            v37,
            v9,
            v6 + 56,
            v6 + 48);
    v27 = 0;
    if ( v58 < 0 )
    {
      *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14) = 0;
      VmsPktGetDropReason((unsigned int)v58, v6 + 20);
      VmsPktReportDroppedNbl(
        v9,
        v24,
        0,
        *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14),
        v121,
        -536862665);
      goto LABEL_233;
    }
    v59 = *(_QWORD **)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38);
    v41 = *(unsigned int *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30)
        + *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
    *v36 = v59;
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = v41;
    if ( !v59 )
      goto LABEL_78;
    do
    {
      v59[15] = *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) + 24LL);
      VmsMpNicPvtDoReceiveChecksum(v19, v59, v9);
      v119 = VmsDiagnosticFlags;
      v27 = 0;
      *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) = v59;
      if ( (v119 & 1) != 0 )
      {
        if ( *v59 )
        {
          v122 = *(_QWORD *)(*v59 + 288LL);
          if ( v122 )
          {
            v123 = *(_QWORD *)(v122 + 16);
            if ( v123 )
            {
              *(_QWORD *)(v123 + 176) = "VmsMpNicPvtPacketForward";
              *(_DWORD *)(v123 + 184) = 5317;
              *(_QWORD *)(v123 + 168) = retaddr;
            }
          }
        }
      }
      v120 = (_QWORD *)*v59;
      ++*(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
      v59 = v120;
    }
    while ( v120 );
    v36 = *(_QWORD **)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50);
    *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = 0;
LABEL_226:
    v41 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
LABEL_78:
    v37 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x78);
    v24 = v56;
  }
  while ( v56 );
  *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14) = -1073741823;
LABEL_58:
  v51 = *(__int64 **)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8);
  if ( !v51 )
  {
    v52 = 1;
    if ( *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        (_DWORD)v44,
        19,
        82,
        (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
        (__int64)"nblsCount == 0");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    goto LABEL_61;
  }
  v60 = *(unsigned __int8 *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 2);
  *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v60;
  v61 = *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
  if ( v9 != -1232 )
  {
    _InterlockedAdd64(
      (volatile signed __int64 *)(*(_QWORD *)(v9 + 1256) + ((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)),
      v61);
    _InterlockedAdd64(
      (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6) + *(_QWORD *)(v9 + 1256) + 24),
      v61);
    v60 = *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
    v27 = 0;
  }
  if ( *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 4) )
  {
    v62 = *(_BYTE *)(v9 + 4930);
    v63 = 0;
    if ( (VmsDiagnosticFlags & 1) != 0 )
    {
      v102 = v51[36];
      if ( v102 )
      {
        v103 = *(_QWORD *)(v102 + 16);
        if ( v103 )
        {
          *(_QWORD *)(v103 + 176) = "VmsMpNicPvtRssSortNbls";
          *(_DWORD *)(v103 + 184) = 288;
          *(_QWORD *)(v103 + 168) = retaddr;
        }
      }
    }
    v64 = *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 3);
    LOWORD(v65) = -1;
    while ( 2 )
    {
      v66 = (__int64 *)*v51;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( v66 )
        {
          v98 = v66[36];
          if ( v98 )
          {
            v99 = *(_QWORD *)(v98 + 16);
            if ( v99 )
            {
              *(_QWORD *)(v99 + 176) = "VmsMpNicPvtRssSortNbls";
              *(_DWORD *)(v99 + 184) = 296;
              *(_QWORD *)(v99 + 168) = retaddr;
            }
          }
        }
      }
      *v51 = 0;
      if ( !v64 )
      {
        v67 = *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D);
        if ( (v67 & 4) != 0 || (v68 = 0, (v67 & 2) != 0) )
          v68 = 1;
        v69 = *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x130);
        if ( (v67 & 1) != 0 )
        {
          v70 = (*(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D) & 4) != 0
             || (v67 & 2) != 0
             || v69 != -1 && (*(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x174) & 6) != 0;
          v63 = 0;
          if ( v70 )
          {
LABEL_93:
            if ( !v63 )
              goto LABEL_94;
            goto LABEL_95;
          }
LABEL_98:
          v73 = v6 + 308;
          v72 = (_QWORD **)(v6 + 272);
          goto LABEL_99;
        }
        if ( v68 )
          goto LABEL_93;
LABEL_97:
        v63 = 0;
        goto LABEL_98;
      }
      if ( v62 )
      {
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          v104 = v51[36];
          if ( v104 )
          {
            v105 = *(_QWORD *)(v104 + 16);
            if ( v105 )
            {
              *(_DWORD *)(v105 + 184) = 1123;
              *(_QWORD *)(v105 + 176) = "VmsVrssPrimeVrssContextForNextNbl";
              LOWORD(v65) = -1;
              *(_QWORD *)(v105 + 168) = retaddr;
            }
          }
        }
        LOBYTE(v42) = *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D);
        v86 = 0xFFFFFFFFLL;
        if ( (v42 & 4) != 0 || (v87 = 0, (v42 & 2) != 0) )
          v87 = 1;
        if ( (v42 & 1) != 0 )
        {
          v88 = *(unsigned __int16 *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x138);
          v89 = -1;
          if ( (_WORD)v88 )
          {
            v90 = *((_DWORD *)v51 + 52);
            if ( v90 )
              v89 = v90 % v88;
          }
          if ( v89 == -1 )
            v86 = *(unsigned int *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x16C);
          v63 = *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160) + 8LL * v89 + 8);
          if ( !v63 )
          {
            if ( (_DWORD)v86 == -1 )
            {
              LOBYTE(v86) = *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x172);
              ReceiveProc = VmsMpNicPvtRssGetReceiveProc(
                              *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x140),
                              (unsigned __int16)v89,
                              *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x150),
                              v86);
              LOBYTE(v42) = *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D);
              LODWORD(v86) = ReceiveProc;
              v27 = 0;
            }
            v87 = (v42 & 4) != 0
               || (v42 & 2) != 0
               || (_DWORD)v86 != -1
               && ((_DWORD)v86 != *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x130)
                || (*(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x174) & 6) != 0);
          }
        }
        else
        {
          v63 &= -(__int64)v87;
          if ( *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13C) )
          {
            v106 = *(unsigned __int16 *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x138);
            if ( (_WORD)v106 )
            {
              v107 = *((_DWORD *)v51 + 52);
              if ( v107 )
                v65 = v107 % v106;
            }
            v89 = v65;
          }
          else
          {
            v89 = -2;
          }
        }
        if ( !v87 )
          goto LABEL_147;
        if ( !v63 )
        {
          if ( (_DWORD)v86 == -1 )
            LODWORD(v86) = *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x130);
          NblGroup = VmsVrssPvtFindNblGroup(
                       *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x158),
                       *(unsigned __int16 *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x170),
                       *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x168),
                       v86,
                       *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x148),
                       v6 + 256);
          v27 = 0;
          v63 = NblGroup;
          if ( (*(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D) & 1) != 0 )
            *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160) + 8LL * v89 + 8) = NblGroup;
LABEL_147:
          if ( !v63 )
          {
            v72 = (_QWORD **)(v6 + 272);
            v73 = v6 + 308;
            goto LABEL_99;
          }
        }
        v72 = (_QWORD **)(v63 + 32);
        v73 = v63 + 48;
        goto LABEL_99;
      }
      v110 = *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D);
      if ( (v110 & 4) != 0 || (v111 = 0, (v110 & 2) != 0) )
        v111 = 1;
      if ( (v110 & 1) != 0 )
      {
        if ( (*(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D) & 4) != 0
          || (v110 & 2) != 0
          || *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x130)
          || (v112 = 0, (*(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x174) & 6) != 0) )
        {
          v112 = 1;
        }
        v63 = 0;
        if ( !v112 )
          goto LABEL_98;
      }
      else if ( !v111 )
      {
        goto LABEL_97;
      }
      if ( !v63 )
      {
        v69 = 0;
LABEL_94:
        v71 = VmsVrssPvtFindNblGroup(
                *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x158),
                *(unsigned __int16 *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x170),
                *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x168),
                v69,
                *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x148),
                v6 + 256);
        v27 = 0;
        v63 = v71;
        if ( !v71 )
          goto LABEL_98;
      }
LABEL_95:
      v72 = (_QWORD **)(v63 + 32);
      v73 = v63 + 48;
LABEL_99:
      *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x118) = v72;
      *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x120) = v73;
      **v72 = v51;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( *v51 )
        {
          v100 = *(_QWORD *)(*v51 + 288);
          if ( v100 )
          {
            v101 = *(_QWORD *)(v100 + 16);
            if ( v101 )
            {
              *(_QWORD *)(v101 + 176) = "VmsMpNicPvtRssSortNbls";
              *(_DWORD *)(v101 + 184) = 334;
              *(_QWORD *)(v101 + 168) = retaddr;
            }
          }
        }
      }
      LOWORD(v65) = -1;
      **(_QWORD **)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x118) = v51;
      v51 = v66;
      ++**(_DWORD **)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x120);
      if ( v66 )
        continue;
      break;
    }
    v9 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8);
    while ( 1 )
    {
LABEL_102:
      v74 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x100);
      if ( !v74 )
      {
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v9 + 56), (PLOCK_STATE_EX)(v6 + 8));
        v124 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x108);
        v52 = 0;
        if ( v124 )
        {
          v125 = *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x134);
          v126 = *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
          *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = v125;
          *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x94) = v126;
          *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = 0;
          *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = v9;
          *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88) = v124;
          if ( KeGetCurrentIrql() >= 2u || (unsigned int)KeIsExecutingDpc() )
            v13 = 0;
          v137 = KeExpandKernelStackAndCalloutEx(VmsMpNicPvtIndicateCallout, (PVOID)(v6 + 128), 0x6000u, v13, 0);
          if ( v137 < 0 )
          {
            LOBYTE(v138) = 2;
            WPP_RECORDER_SF_qdd(
              VmsIfrLog,
              v138,
              20,
              11,
              (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
              v124,
              v125,
              v137);
            goto LABEL_290;
          }
        }
        goto LABEL_61;
      }
      v75 = *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D);
      *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x100) = *(_QWORD *)v74;
      v76 = *(_BYTE *)(v74 + 58) ^ (*(_BYTE *)(v74 + 58) ^ (v75 >> 2)) & 2;
      *(_BYTE *)(v74 + 58) = v76;
      *(_BYTE *)(v74 + 58) = v76
                           ^ (v76
                            ^ (*(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D) >> 2))
                           & 4;
      if ( (*(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x13D) & 4) == 0
        || *(_QWORD *)(v74 + 16) != v27 )
      {
        break;
      }
      if ( (unsigned __int8)VmsVrssPushNblGroupToBreakerQueue(v74) )
      {
        v80 = 128;
        goto LABEL_107;
      }
    }
    LOBYTE(v42) = *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x172);
    v77 = *(_QWORD *)(v74 + 16);
    v78 = VmsVrssPvtPushNblGroupToQueue(
            v74,
            *(unsigned int *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x174),
            v42);
    v27 = 0;
    switch ( v78 )
    {
      case 0:
        goto LABEL_102;
      case 1:
        _InterlockedAdd64((volatile signed __int64 *)(v77 + 464), 1u);
        v80 = v77;
        goto LABEL_107;
      case 2:
        _InterlockedAdd64((volatile signed __int64 *)(v77 + 456), 1u);
        v80 = v77 + 64;
LABEL_107:
        KeInsertQueueDpc((PRKDPC)v80, 0, 0);
        break;
      case 3:
        _InterlockedAdd64((volatile signed __int64 *)(v77 + 448), 1u);
        KeSetEvent((PRKEVENT)(v77 + 192), 3, 0);
        break;
      default:
        LOBYTE(v79) = 2;
        WPP_RECORDER_SF_dq(VmsIfrLog, v79, 20, 14, (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids, v78, v77);
        break;
    }
    v27 = 0;
    goto LABEL_102;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v9 + 56), (PLOCK_STATE_EX)(v6 + 8));
  *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = v9;
  v52 = 0;
  *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = 0;
  *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88) = v51;
  *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = v61;
  *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x94) = v60;
  if ( KeGetCurrentIrql() >= 2u || (unsigned int)KeIsExecutingDpc() )
    v13 = 0;
  v139 = KeExpandKernelStackAndCalloutEx(VmsMpNicPvtIndicateCallout, (PVOID)(v6 + 128), 0x6000u, v13, 0);
  if ( v139 < 0 )
  {
    LOBYTE(v140) = 2;
    WPP_RECORDER_SF_qdd(
      VmsIfrLog,
      v140,
      20,
      11,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      (char)v51,
      v61,
      v139);
LABEL_290:
    VmsMpNicPvtIndicate(
      *(NDIS_HANDLE *)(*(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) + 3312LL) + 24LL),
      *(PNET_BUFFER_LIST *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88),
      *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90),
      *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x94));
  }
LABEL_61:
  if ( *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 5) )
  {
    v53 = *(void **)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160);
    if ( v53 )
    {
      ExFreeToNPagedLookasideList(&stru_1401FA0C0, v53);
      *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x160) = 0;
    }
  }
  if ( !v52 )
  {
    v17 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60);
    v16 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x68);
    v54 = *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14);
    goto LABEL_66;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v9 + 56), (PLOCK_STATE_EX)(v6 + 8));
  v54 = *(_DWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14);
LABEL_326:
  v16 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x68);
  v17 = *(_QWORD *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60);
LABEL_66:
  if ( a5 )
  {
    if ( v16 )
      VmsNblHelperRefCountDecrementMany(v16, 0);
    if ( v17 )
      VmsNblHelperRefCountDecrementMany(v17, 0);
  }
  if ( *(_BYTE *)(((unsigned __int64)&v144 & 0xFFFFFFFFFFFFFFC0uLL) + 6) && v9 != -1232 )
    _InterlockedDecrement64((volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                                      + *(_QWORD *)(v9 + 1256)
                                                      + 24));
  return v54;
}

```

## disassembly

```asm
0x140026000  mov     [rsp-8+arg_8], rbx
0x140026005  push    rbp
0x140026006  push    rsi
0x140026007  push    rdi
0x140026008  push    r12
0x14002600a  push    r13
0x14002600c  push    r14
0x14002600e  push    r15
0x140026010  sub     rsp, 230h
0x140026017  lea     rbp, [rsp+0A0h]
0x14002601f  and     rbp, 0FFFFFFFFFFFFFFC0h
0x140026023  mov     rax, cs:__security_cookie
0x14002602a  xor     rax, rsp
0x14002602d  mov     [rbp+1C0h+var_40], rax
0x140026034  mov     r13, r8
0x140026037  mov     [rbp+1C0h+var_178], r8
0x14002603b  movzx   ebx, dx
0x14002603e  mov     [rbp+1C0h+var_E8], rcx
0x140026045  mov     r12, rcx
0x140026048  xor     r15d, r15d
0x14002604b  xor     edx, edx; Val
0x14002604d  mov     [rbp+1C0h+var_1AC], r15d
0x140026051  mov     r8d, 80h; Size
0x140026057  lea     rcx, [rbp+1C0h+var_C0]; void *
0x14002605e  mov     esi, r9d
0x140026061  call    memset
0x140026066  xor     eax, eax
0x140026068  mov     dword ptr [rbp+1C0h+var_1A0], r15d
0x14002606c  mov     word ptr [rbp+1C0h+LockState.OldIrql], ax
0x140026070  lea     rcx, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x140026077  mov     [rbp+1C0h+LockState.Flags], al
0x14002607a  mov     [rbp+1C0h+var_1B4], r15b
0x14002607e  mov     [rbp+1C0h+var_100], r15
0x140026085  lea     edi, [rax+13h]
0x140026088  mov     [rbp+1C0h+var_1A8], r15w
0x14002608d  mov     [rbp+1C0h+var_1BA], r15b
0x140026091  mov     [rbp+1C0h+var_190], r15d
0x140026095  test    bx, bx
0x140026098  jnz     loc_140027508
0x14002609e  lea     r14, [r13+10h]
0x1400260a2  cmp     [r14], r15
0x1400260a5  jz      loc_14002753F
0x1400260ab  test    esi, 0FFFFFFFEh
0x1400260b1  jnz     loc_140027578
0x1400260b7  mov     edi, 1
0x1400260bc  test    dil, sil
0x1400260bf  jnz     loc_1400265E2
0x1400260c5  call    cs:__imp_KeGetCurrentIrql
0x1400260cc  nop     dword ptr [rax+rax+00h]
0x1400260d1  mov     [rbp+1C0h+var_1BE], r15b
0x1400260d5  cmp     al, 2
0x1400260d7  jz      loc_1400265E2
0x1400260dd  xor     ecx, ecx; ProcNumber
0x1400260df  mov     [rbp+1C0h+var_188], r15
0x1400260e3  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400260ea  nop     dword ptr [rax+rax+00h]
0x1400260ef  xor     r11d, r11d
0x1400260f2  mov     r15d, eax
0x1400260f5  mov     eax, r11d
0x1400260f8  mov     ebx, r11d
0x1400260fb  mov     [rbp+1C0h+var_158], rax
0x1400260ff  mov     [rbp+1C0h+var_160], rbx
0x140026103  cmp     [r14], r11
0x140026106  jz      loc_1400278CD
0x14002610c  mov     edx, [r12+0D94h]
0x140026114  mov     ecx, edx
0x140026116  and     ecx, 300h
0x14002611c  neg     ecx
0x14002611e  sbb     ebx, ebx
0x140026120  and     ebx, 24h
0x140026123  add     ebx, 0FFFFFFDBh
0x140026126  test    dl, 30h
0x140026129  jz      loc_1400275AF
0x14002612f  mov     eax, [r12+0DA4h]
0x140026137  test    al, 30h
0x140026139  jz      loc_1400275AF
0x14002613f  test    dl, 0C0h
0x140026142  jz      loc_1400275B7
0x140026148  mov     eax, [r12+0DA4h]
0x140026150  test    al, 0C0h
0x140026152  jz      loc_1400275B7
0x140026158  cmp     [r12+44h], edi
0x14002615d  jnz     loc_140027895
0x140026163  mov     rsi, [r12+0CF0h]
0x14002616b  mov     rcx, r12
0x14002616e  mov     [rbp+1C0h+var_180], rsi
0x140026172  call    VmsMpNicPvtAcquireOutgoingRefCount
0x140026177  xor     r8d, r8d
0x14002617a  test    al, al
0x14002617c  jz      loc_140027895
0x140026182  cmp     byte ptr [rsi+2C5h], 3
0x140026189  jnb     loc_14002691B
0x14002618f  mov     [rbp+1C0h+var_1C0], r8b
0x140026193  mov     [rbp+1C0h+var_1BF], r8b
0x140026197  cmp     [r13+0Ch], r8b
0x14002619b  jnz     loc_140026B34
0x1400261a1  cmp     cs:VmsHostNicIndicateNblsInline, r8b
0x1400261a8  jnz     loc_1400275BF
0x1400261ae  mov     r15b, dil
0x1400261b1  mov     [rbp+1C0h+var_1BC], dil
0x1400261b5  cmp     [r13+8], edi
0x1400261b9  jz      loc_1400275D9
0x1400261bf  mov     ecx, [r12+750h]
0x1400261c7  mov     r9d, 0FFFFFFFDh
0x1400261cd  lea     eax, [rcx-1]
0x1400261d0  test    r9d, eax
0x1400261d3  jnz     loc_1400271A5
0x1400261d9  lea     eax, [rcx-1]
0x1400261dc  mov     rdx, r8
0x1400261df  test    r9d, eax
0x1400261e2  jnz     short loc_1400261F6
0x1400261e4  cmp     [r12+18B0h], r8
0x1400261ec  jz      short loc_1400261F6
0x1400261ee  lea     rdx, [r12+1640h]
0x1400261f6  bt      word ptr [rdx+280h], 0Dh
0x1400261ff  mov     [rbp+1C0h+var_1BD], r8b
0x140026203  jb      loc_1400275D9
0x140026209  mov     rsi, [r14]
0x14002620c  mov     [rbp+1C0h+var_1A0], rsi
0x140026210  mov     [rbp+1C0h+var_1BB], r8b
0x140026214  mov     [rbp+1C0h+var_1BA], dil
0x140026218  cmp     [rsp+260h+arg_28], r8b
0x140026220  jz      loc_1400265EB
0x140026226  call    cs:__imp_KeGetCurrentIrql
0x14002622d  nop     dword ptr [rax+rax+00h]
0x140026232  cmp     al, 2
0x140026234  jnz     loc_1400275E2
0x14002623a  mov     r8b, dil; Flags
0x14002623d  mov     rcx, [r12+38h]; Lock
0x140026242  lea     rdx, [rbp+1C0h+LockState]; LockState
0x140026246  call    cs:__imp_NdisAcquireRWLockRead
0x14002624d  nop     dword ptr [rax+rax+00h]
0x140026252  xor     r11d, r11d
0x140026255  cmp     [r12+1342h], r11b
0x14002625d  jz      loc_140026F0C
0x140026263  cmp     [r13+0Ch], r11b
0x140026267  jz      loc_140026F0C
0x14002626d  test    r15b, r15b
0x140026270  jz      loc_1400263A0
0x140026276  xor     ecx, ecx; ProcNumber
0x140026278  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14002627f  nop     dword ptr [rax+rax+00h]
0x140026284  xor     r13d, r13d
0x140026287  mov     [rbp+1C0h+var_68], r12
0x14002628e  lea     rcx, [rbp+1C0h+var_B8]
0x140026295  mov     [rbp+1C0h+var_90], eax
0x14002629b  mov     eax, cs:VmsExecutionMode
0x1400262a1  mov     [rbp+1C0h+var_4C], eax
0x1400262a7  lea     rax, VmsMpNicPvtReceiveRssProcessNblGroup
0x1400262ae  mov     [rbp+1C0h+var_B0], rcx
0x1400262b5  mov     cl, r13b
0x1400262b8  mov     [rbp+1C0h+var_78], rax
0x1400262bf  mov     [rbp+1C0h+var_8C], r13d
0x1400262c6  mov     [rbp+1C0h+var_B8], r13
0x1400262cd  mov     [rbp+1C0h+var_A0], r13
0x1400262d4  mov     [rbp+1C0h+var_A8], r13
0x1400262db  mov     [rbp+1C0h+Entry], r13
0x1400262e2  mov     [rbp+1C0h+var_C0], r13
0x1400262e9  mov     [rbp+1C0h+var_83], cl
0x1400262ef  mov     [rbp+1C0h+var_50], r13w
0x1400262f7  mov     [rbp+1C0h+var_58], r13d
0x1400262fe  cmp     [r12+1342h], r13b
0x140026306  jz      loc_14002762E
0x14002630c  lea     r14, [r12+1370h]
0x140026314  movzx   r15d, word ptr [r14]
0x140026318  lea     rcx, [r12+136Ch]; ProcNumber
0x140026320  call    cs:__imp_KeGetProcessorIndexFromNumber
0x140026327  nop     dword ptr [rax+rax+00h]
0x14002632c  mov     cl, [rbp+1C0h+var_83]
0x140026332  and     cl, 0FBh
0x140026335  mov     [rbp+1C0h+var_54], eax
0x14002633b  mov     al, [rbp+1C0h+var_1BE]
0x14002633e  or      cl, 3
0x140026341  mov     [rbp+1C0h+var_83], cl
0x140026347  lea     rcx, stru_1401FA0C0; Lookaside
0x14002634e  mov     [rbp+1C0h+var_80], r14
0x140026355  mov     [rbp+1C0h+var_70], r13
0x14002635c  mov     [rbp+1C0h+var_4E], al
0x140026362  mov     [rbp+1C0h+var_88], r15w
0x14002636a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140026371  nop     dword ptr [rax+rax+00h]
0x140026376  xor     r11d, r11d
0x140026379  mov     [rbp+1C0h+Entry], rax
0x140026380  test    rax, rax
0x140026383  jz      loc_1400270BD
0x140026389  xor     edx, edx; Val
0x14002638b  mov     r8d, 408h; Size
0x140026391  mov     rcx, rax; void *
0x140026394  call    memset
0x140026399  xor     r11d, r11d
0x14002639c  mov     [rbp+1C0h+var_1BB], dil
0x1400263a0  mov     rax, [rsi+120h]
0x1400263a7  lea     r13, [rbp+1C0h+var_F8]
0x1400263ae  mov     [rbp+1C0h+var_F8], r11
0x1400263b5  mov     r10, r11
0x1400263b8  mov     [rbp+1C0h+var_170], r13
0x1400263bc  mov     [rbp+1C0h+var_1B0], r11d
0x1400263c0  mov     [rbp+1C0h+var_148], r11
0x1400263c4  test    rax, rax
0x1400263c7  jnz     loc_140026BBA
0x1400263cd  cmp     cs:VmsActiveProcCount, r11d
0x1400263d4  mov     r8, r11
0x1400263d7  mov     edx, r11d
0x1400263da  jbe     short loc_140026401
0x1400263dc  mov     eax, edx
0x1400263de  add     edx, edi
0x1400263e0  imul    rcx, rax, 1540h
0x1400263e7  mov     rax, cs:VmsPlanCpuTable
0x1400263ee  mov     rcx, [rcx+rax+1500h]
0x1400263f6  add     r8, rcx
0x1400263f9  cmp     edx, cs:VmsActiveProcCount
0x1400263ff  jb      short loc_1400263DC
0x140026401  test    r8, r8
0x140026404  mov     r9, r11
0x140026407  cmovns  r9, r8
0x14002640b  mov     r8, [rbp+1C0h+var_178]
0x14002640f  mov     [rbp+1C0h+var_198], r9
0x140026413  cmp     [r8+0Ch], r11b
0x140026417  jz      loc_1400265F3
0x14002641d  lea     r15, [rbp+1C0h+var_158]
0x140026421  lea     rax, [rbp+1C0h+var_160]
0x140026425  mov     [rbp+1C0h+var_168], r15
0x140026429  mov     [rbp+1C0h+var_150], rax
0x14002642d  lea     rdx, aVmsmpnicpvtpac_0; "VmsMpNicPvtPacketForward"
0x140026434  mov     r13, [rsi]
0x140026437  mov     eax, cs:VmsDiagnosticFlags
0x14002643d  mov     rcx, [rsp+268h]
0x140026445  mov     [rbp+1C0h+var_F0], r13
0x14002644c  test    dil, al
0x14002644f  jnz     loc_140026BD4
0x140026455  mov     [rsi], r11
0x140026458  cmp     [rsi+140h], r11w
0x140026460  ja      loc_14002763C
0x140026466  mov     r14b, r11b
0x140026469  mov     rax, [rsi+8]
0x14002646d  cmp     [rax], r11
0x140026470  jnz     loc_140027654
0x140026476  test    r14b, r14b
0x140026479  jnz     loc_140026E10
0x14002647f  cmp     [rsp+260h+arg_20], r11b
0x140026487  jz      loc_140026D99
0x14002648d  mov     r14, rsi
0x140026490  mov     [rbp+1C0h+var_188], rsi
0x140026494  mov     rax, [rbp+1C0h+var_170]
0x140026498  mov     [rax], r14
0x14002649b  test    r14, r14
0x14002649e  jz      short loc_140026508
0x1400264a0  mov     r15d, [rbp+1C0h+var_1B0]
0x1400264a4  lea     r13, aVmsmpnicpvtpac_0; "VmsMpNicPvtPacketForward"
0x1400264ab  mov     rax, [rbp+1C0h+var_180]
0x1400264af  mov     r8, r12
0x1400264b2  mov     rdx, r14
0x1400264b5  mov     rcx, rbx
0x1400264b8  mov     rax, [rax+18h]
0x1400264bc  mov     [r14+78h], rax
0x1400264c0  call    VmsMpNicPvtDoReceiveChecksum
0x1400264c5  mov     eax, cs:VmsDiagnosticFlags
0x1400264cb  xor     r11d, r11d
0x1400264ce  mov     rcx, [rsp+268h]
0x1400264d6  mov     [rbp+1C0h+var_170], r14
0x1400264da  test    dil, al
0x1400264dd  jnz     loc_140026992
0x1400264e3  mov     rax, [r14]
0x1400264e6  add     r15d, edi
0x1400264e9  mov     r14, rax
0x1400264ec  test    rax, rax
0x1400264ef  jnz     short loc_1400264AB
0x1400264f1  mov     rsi, [rbp+1C0h+var_1A0]
0x1400264f5  mov     r13, [rbp+1C0h+var_F0]
0x1400264fc  mov     [rbp+1C0h+var_1B0], r15d
0x140026500  mov     r15, [rbp+1C0h+var_168]
0x140026504  mov     [rbp+1C0h+var_188], rax
0x140026508  cmp     [rsp+260h+arg_20], r11b
0x140026510  jz      loc_140026E52
0x140026516  mov     r9, [rbp+1C0h+var_198]
0x14002651a  mov     rsi, r13
0x14002651d  mov     r8, [rbp+1C0h+var_178]
0x140026521  lea     rdx, aVmsmpnicpvtpac_0; "VmsMpNicPvtPacketForward"
0x140026528  mov     [rbp+1C0h+var_1A0], r13
0x14002652c  test    r13, r13
0x14002652f  jnz     loc_140026434
0x140026535  mov     rax, [rbp+1C0h+var_170]
0x140026539  mov     [rax], r11
0x14002653c  mov     rsi, [rbp+1C0h+var_F8]
0x140026543  test    rsi, rsi
0x140026546  jnz     loc_1400266A9
0x14002654c  mov     r14b, dil
0x14002654f  cmp     [rbp+1C0h+var_1B0], esi
0x140026552  jnz     loc_140027840
0x140026558  cmp     [rbp+1C0h+var_1BB], r11b
0x14002655c  jz      short loc_140026587
0x14002655e  mov     rdx, [rbp+1C0h+Entry]; Entry
0x140026565  test    rdx, rdx
0x140026568  jz      short loc_140026587
0x14002656a  lea     rcx, stru_1401FA0C0; Lookaside
0x140026571  call    cs:__imp_ExFreeToNPagedLookasideList
0x140026578  nop     dword ptr [rax+rax+00h]
0x14002657d  xor     r11d, r11d
0x140026580  mov     [rbp+1C0h+Entry], r11
0x140026587  test    r14b, r14b
  ... truncated ...
```
