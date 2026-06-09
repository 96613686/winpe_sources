# VmsPtNicSendNetBufferListsCompleteWithRss

- ea: `0x14004dcf8`
- end: `0x14004eb18`
- name: `VmsPtNicSendNetBufferListsCompleteWithRss`
- size: `3616`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004d490`

## callees

- `0x140010aa8`
- `0x140014330`
- `0x140017a7c`
- `0x140025be0`
- `0x140025d10`
- `0x140027a64`
- `0x1400313cc`
- `0x140032b1c`
- `0x14004d344`
- `0x14004dcf8`
- `0x14004f4fc`
- `0x14004f5d8`
- `0x14006b4dc`
- `0x14008497c`
- `0x1400f2a6c`
- `0x1401bbc40`
- `0x1401bbe10`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14004eaf6`
- `ntoskrnl!KeSetEvent` at `0x14004eaf6`
- `ntoskrnl!KeInsertQueueDpc` at `0x14004e580`
- `ntoskrnl!KeInsertQueueDpc` at `0x14004e580`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004e04a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004e04a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004e2b2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004e2b2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004dd8e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004df18`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004e5d0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004dd8e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004df18`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004e5d0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004de0c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004de0c`
- `NDIS!NdisAcquireRWLockRead` at `0x14004de6b`
- `NDIS!NdisAcquireRWLockRead` at `0x14004de6b`
- `NDIS!NdisReleaseRWLock` at `0x14004df45`
- `NDIS!NdisReleaseRWLock` at `0x14004ea4b`
- `NDIS!NdisReleaseRWLock` at `0x14004df45`
- `NDIS!NdisReleaseRWLock` at `0x14004ea4b`

## string_xrefs

- `0x14004dd64`: `VmsPtNicSendNetBufferListsCompleteWithRss`
- `0x14004e707`: `VmsPtNicSendNetBufferListsCompleteWithRss`
- `0x14004e754`: `VmsPtNicSendNetBufferListsCompleteWithRss`
- `0x14004ddbd`: `VmsIsValidProcessor(currentProcIndex)`

## pseudocode

```c
void __fastcall VmsPtNicSendNetBufferListsCompleteWithRss(__int64 a1, __int64 *a2, unsigned int a3, int a4)
{
  unsigned __int64 v4; // rbp
  __int64 v8; // r14
  __int64 v9; // rsi
  bool v10; // r12
  ULONG CurrentProcessorNumber; // eax
  int v12; // edx
  ULONG v13; // ebx
  KIRQL CurrentIrql; // al
  __int64 v15; // rax
  const char *v16; // rdx
  char v17; // al
  __int64 v18; // r14
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // r15
  __int64 v23; // r8
  __int64 v24; // r11
  __int64 v25; // rax
  __int64 v26; // rdx
  int v27; // r9d
  int v28; // r10d
  __int64 v29; // r11
  void *v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rcx
  _QWORD *i; // rcx
  __int64 v37; // rdx
  __int16 v38; // bx
  __int64 v39; // r15
  __int64 v40; // r14
  int PlannedDefaultCpuIndex; // eax
  char v42; // r12
  int OpenChannelProcIndex; // esi
  char v44; // cl
  PVOID v45; // rax
  __int64 v46; // r8
  __int64 (__fastcall *v47)(); // r13
  __int64 *v48; // rsi
  __int64 v49; // r9
  char v50; // r10
  unsigned int v51; // ecx
  int v52; // ebx
  unsigned int v53; // eax
  int v54; // eax
  __int64 NblGroup; // rax
  _QWORD **v56; // rcx
  unsigned __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // rcx
  unsigned __int8 v62; // dl
  char v63; // dl
  __int64 v64; // rbx
  int v65; // eax
  __int64 v66; // rcx
  unsigned int v67; // eax
  __int64 v68; // rdx
  int PlannedProcessorForEntry; // eax
  __int64 v70; // r9
  int v71; // r10d
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  unsigned int v78; // ecx
  int v79; // edx
  unsigned int v80; // eax
  unsigned int v81; // eax
  int v82; // edx
  __int64 v83; // r9
  __int64 v84; // rdx
  __int64 v85; // rdx
  __int64 NicHeaderAtIndex; // rax
  int v87; // eax
  __int64 v88; // rcx
  __int64 v89; // r8
  unsigned int v90; // ecx
  int v91; // edx
  char v92; // [rsp+80h] [rbp+0h] BYREF
  _UNKNOWN *retaddr; // [rsp+1C8h] [rbp+148h]

  v4 = (unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL;
  *(_DWORD *)(v4 + 24) = a4;
  *(_QWORD *)(v4 + 48) = 0;
  *(_QWORD *)(v4 + 56) = 0;
  v8 = 0;
  v9 = 0;
  memset((void *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 128), 0, 0x80u);
  *(_WORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = 0;
  *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x12) = 0;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( a2 )
    {
      v31 = a2[36];
      if ( v31 )
      {
        v32 = *(_QWORD *)(v31 + 16);
        if ( v32 )
        {
          *(_QWORD *)(v32 + 176) = "VmsPtNicSendNetBufferListsCompleteWithRss";
          *(_DWORD *)(v32 + 184) = 12420;
          *(_QWORD *)(v32 + 168) = retaddr;
        }
      }
    }
  }
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = 0;
  v10 = 0;
  *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14) = CurrentProcessorNumber;
  v13 = CurrentProcessorNumber;
  if ( CurrentProcessorNumber == -1
    || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, CurrentProcessorNumber) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v12,
      19,
      182,
      (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
      (__int64)"VmsIsValidProcessor(currentProcIndex)");
    if ( v13 == -1 || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v13) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( (*(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) & 1) != 0
    || (CurrentIrql = KeGetCurrentIrql(),
        *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 1) = 0,
        CurrentIrql == 2) )
  {
    *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 1) = 1;
  }
  if ( !a1
    || (v8 = *(_QWORD *)(a1 + 8), (*(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = v8) == 0) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v12,
      19,
      183,
      (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
      (__int64)"objNic");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v15 = *(_QWORD *)(v8 + 3312);
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = v15;
  if ( !v15 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v12,
      19,
      184,
      (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
      (__int64)"ptNicExt");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v8 + 56), (PLOCK_STATE_EX)(v4 + 16), 0);
  v17 = VmsDiagnosticFlags;
  v18 = 0;
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = 0;
  if ( (v17 & 1) != 0 )
  {
    if ( a2 )
    {
      v33 = a2[36];
      if ( v33 )
      {
        v34 = *(_QWORD *)(v33 + 16);
        if ( v34 )
        {
          v16 = "VmsPtNicGetVmqFromNBL";
          *(_DWORD *)(v34 + 184) = 21120;
          *(_QWORD *)(v34 + 176) = "VmsPtNicGetVmqFromNBL";
          *(_QWORD *)(v34 + 168) = retaddr;
        }
      }
    }
  }
  if ( !a1 || (v18 = *(_QWORD *)(a1 + 8)) == 0 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      (_DWORD)v16,
      19,
      353,
      (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
      (__int64)"ptNic");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v19 = *(_QWORD *)(v18 + 3312);
  if ( !v19 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      (_DWORD)v16,
      19,
      354,
      (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
      (__int64)"ptNicExt");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( !a3 || !*(_QWORD *)(v19 + 1424) )
  {
    if ( (unsigned __int8)VmsPtCheckIsEmbeddedTeamingEnabled(v18, 0) )
    {
      v20 = *(_QWORD *)(a1 + 1928);
    }
    else
    {
      v20 = *(_QWORD *)(v19 + 1480);
      if ( v20 == v19 + 1480 )
        goto LABEL_164;
    }
    if ( v20 )
    {
      v21 = *(_QWORD *)(v20 + 56);
      goto LABEL_52;
    }
    goto LABEL_22;
  }
  if ( !*(_BYTE *)(v19 + 2400) )
  {
    if ( *(_DWORD *)(v19 + 1420) >= a3 )
    {
      _mm_lfence();
      v35 = a3 - 1;
LABEL_51:
      v21 = *(_QWORD *)(*(_QWORD *)(v19 + 1424) + 8 * v35);
LABEL_52:
      *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v21;
      goto LABEL_23;
    }
    goto LABEL_22;
  }
  v84 = a2[36];
  if ( !v84 )
  {
LABEL_164:
    *(_BYTE *)v4 = 0;
    goto LABEL_165;
  }
  v85 = *(_QWORD *)(v84 + 16);
  if ( v85 )
  {
    if ( *(_DWORD *)(v85 + 68) == 1 )
    {
      NicHeaderAtIndex = VmsPtGetNicHeaderAtIndex(v18, *(unsigned __int16 *)(*(_QWORD *)(v85 + 72) + 4LL));
      if ( NicHeaderAtIndex )
      {
        if ( *(_QWORD *)(NicHeaderAtIndex + 616) )
        {
          if ( *(_DWORD *)(NicHeaderAtIndex + 624) >= a3 && *(_DWORD *)(NicHeaderAtIndex + 16) == 2 )
          {
            _mm_lfence();
            v87 = *(_DWORD *)(*(_QWORD *)(NicHeaderAtIndex + 616) + 8LL * (a3 - 1));
            if ( v87 )
            {
              v35 = (unsigned int)(v87 - 1);
              goto LABEL_51;
            }
          }
        }
      }
    }
  }
LABEL_22:
  v21 = 0;
LABEL_23:
  *(_BYTE *)v4 = 0;
  if ( v21 && *(_DWORD *)(v21 + 48) == 1 && (*(_DWORD *)(v21 + 52) & 0x20) == 0 )
  {
    _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v21 + 216)
                                                      + ((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)));
    *(_BYTE *)v4 = 1;
    goto LABEL_27;
  }
LABEL_165:
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = 0;
LABEL_27:
  v22 = *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v22 + 56), (PLOCK_STATE_EX)(v4 + 16));
  v24 = *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
  if ( !v24 )
  {
    v25 = *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
    v26 = 0;
    v27 = *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
LABEL_29:
    v28 = *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14);
    goto LABEL_30;
  }
  v9 = *(_QWORD *)(v24 + 8);
  v26 = *(_QWORD *)(v24 + 40);
  v27 = *(unsigned __int16 *)(v9 + 1282);
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = *(_QWORD *)(v9 + 640);
  v25 = *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
  *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = v27;
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v26;
  v10 = (v25 & 3) == 3;
  if ( *(_DWORD *)(v26 + 1872) == 3 )
  {
    v23 = *(_QWORD *)(v26 + 3312);
    *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = v23;
  }
  if ( (v25 & 3) == 3 )
    goto LABEL_29;
  v23 = 0;
  for ( i = a2; i; v23 = (unsigned int)(v23 + 1) )
    i = (_QWORD *)*i;
  v37 = 0;
  if ( *(_QWORD *)(v9 + 624) )
    v37 = v9 + 176;
  v28 = *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14);
  if ( *(_DWORD *)(v9 + 1328) != v28 )
    _InterlockedAdd64((volatile signed __int64 *)(v37 + 112), (unsigned int)v23);
  v26 = *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
LABEL_30:
  *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) = 0;
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = ((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL)
                                                                       + 136;
  *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4) = VmsExecutionMode;
  *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB4) = 0;
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88) = 0;
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) = 0;
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = 0;
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = 0;
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = 0;
  *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0) = v28;
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8) = v9;
  *(_WORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBA) = v27;
  *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBC) = v10;
  if ( !v24 )
    goto LABEL_31;
  if ( *(_DWORD *)(v26 + 1872) == 3 )
  {
    if ( (*(_BYTE *)(v9 + 640) & 1) != 0 )
    {
      v38 = 16;
      if ( (*(_DWORD *)(v9 + 40) & 0x10) != 0 )
      {
LABEL_66:
        *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8) = v22;
        v39 = *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38);
        v40 = 0;
        *(_WORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0) = 0;
        *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) = 0;
        *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8) = VmsPtPvtRssSendCompleteProcessNblGroup;
        if ( v39 )
        {
          v42 = *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 1);
          v88 = *(_QWORD *)(v39 + 680);
          LOBYTE(v23) = v42;
          *(_WORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
          *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 6) = 0;
          VmsOmObjectLockShared(v88, v4 + 4, v23);
          LOBYTE(v89) = 1;
          OpenChannelProcIndex = VmsVmNicPvtChannelGetOpenChannelProcIndex(v39, *(unsigned __int16 *)(v9 + 442), v89);
          NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)(v39 + 680) + 56LL), (PLOCK_STATE_EX)(v4 + 4));
          if ( OpenChannelProcIndex == -1 )
            OpenChannelProcIndex = *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0);
        }
        else
        {
          PlannedDefaultCpuIndex = VmsPlanGetPlannedDefaultCpuIndex(v9 + 640);
          v42 = *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 1);
          OpenChannelProcIndex = PlannedDefaultCpuIndex;
        }
        v44 = *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) & 0xFC | 1;
        *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0) = *(_QWORD *)(((unsigned __int64)&v92
                                                                                          & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                         + 0xA8);
        *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) = v44;
        *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xEC) = OpenChannelProcIndex;
        *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD0) = v39;
        *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2) = v42;
        *(_WORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8) = v38;
        v45 = ExAllocateFromNPagedLookasideList(&stru_1401FA0C0);
        v29 = 0;
        *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = v45;
        if ( v45 )
        {
          memset(v45, 0, 0x408u);
          v29 = 0;
        }
        else
        {
          *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) &= 0xFCu;
        }
        if ( a2 )
        {
          v47 = VmsPtVrssGetSendProc;
          if ( !v39 )
            v47 = VmsPtVrssGetRecvProc;
          while ( 1 )
          {
            v48 = (__int64 *)*a2;
            if ( (VmsDiagnosticFlags & 1) != 0 )
            {
              if ( v48 )
              {
                v72 = v48[36];
                if ( v72 )
                {
                  v73 = *(_QWORD *)(v72 + 16);
                  if ( v73 )
                  {
                    *(_DWORD *)(v73 + 184) = 12657;
                    *(_QWORD *)(v73 + 176) = "VmsPtNicSendNetBufferListsCompleteWithRss";
                    *(_QWORD *)(v73 + 168) = retaddr;
                  }
                }
              }
            }
            *a2 = v29;
            if ( (VmsDiagnosticFlags & 1) != 0 )
            {
              v76 = a2[36];
              if ( v76 )
              {
                v77 = *(_QWORD *)(v76 + 16);
                if ( v77 )
                {
                  *(_DWORD *)(v77 + 184) = 1123;
                  *(_QWORD *)(v77 + 176) = "VmsVrssPrimeVrssContextForNextNbl";
                  *(_QWORD *)(v77 + 168) = retaddr;
                }
              }
            }
            LOBYTE(v46) = *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD);
            v49 = 0xFFFFFFFFLL;
            if ( (v46 & 4) != 0 || (v50 = v29, (v46 & 2) != 0) )
              v50 = 1;
            if ( (v46 & 1) != 0 )
            {
              v51 = *(unsigned __int16 *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8);
              LOWORD(v52) = -1;
              if ( (_WORD)v51 )
              {
                v53 = *((_DWORD *)a2 + 52);
                if ( v53 )
                  v52 = v53 % v51;
              }
              if ( (_WORD)v52 == 0xFFFF )
                v49 = *(unsigned int *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xEC);
              v40 = *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0)
                              + 8LL * (__int16)v52
                              + 8);
              if ( !v40 )
              {
                if ( (_DWORD)v49 == -1 )
                {
                  LOBYTE(v49) = *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2);
                  v54 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64))v47)(
                          *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0),
                          (unsigned __int16)v52,
                          *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD0),
                          v49);
                  LOBYTE(v46) = *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD);
                  LODWORD(v49) = v54;
                  v29 = 0;
                }
                if ( (v46 & 4) != 0
                  || (v46 & 2) != 0
                  || (_DWORD)v49 != -1
                  && ((_DWORD)v49 != *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0)
                   || (*(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4) & 6) != 0) )
                {
                  v50 = 1;
                }
                else
                {
                  v50 = v29;
                }
              }
            }
            else
            {
              v40 &= -(__int64)(v50 != 0);
              if ( *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBC) == (_BYTE)v29 )
              {
                LOWORD(v52) = -2;
              }
              else
              {
                v78 = *(unsigned __int16 *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8);
                LOWORD(v79) = -1;
                if ( (_WORD)v78 )
                {
                  v80 = *((_DWORD *)a2 + 52);
                  if ( v80 )
                    v79 = v80 % v78;
                }
                LOWORD(v52) = v79;
              }
            }
            if ( v50 )
            {
              if ( v40 )
                goto LABEL_122;
              if ( (_DWORD)v49 == -1 )
                LODWORD(v49) = *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0);
              NblGroup = VmsVrssPvtFindNblGroup(
                           *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8),
                           *(unsigned __int16 *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0),
                           *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8),
                           v49,
                           *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8),
                           v4 + 128);
              v29 = 0;
              v40 = NblGroup;
              if ( (*(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) & 1) != 0 )
                *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) + 8LL * (__int16)v52 + 8) = NblGroup;
            }
            if ( !v40 )
            {
              v56 = (_QWORD **)(v4 + 144);
              v57 = v4 + 180;
              goto LABEL_96;
            }
LABEL_122:
            v56 = (_QWORD **)(v40 + 32);
            v57 = v40 + 48;
LABEL_96:
            *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) = v57;
            *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = v56;
            **v56 = a2;
            if ( (VmsDiagnosticFlags & 1) != 0 )
            {
              if ( *a2 )
              {
                v74 = *(_QWORD *)(*a2 + 288);
                if ( v74 )
                {
                  v75 = *(_QWORD *)(v74 + 16);
                  if ( v75 )
                  {
                    *(_DWORD *)(v75 + 184) = 12692;
                    *(_QWORD *)(v75 + 176) = "VmsPtNicSendNetBufferListsCompleteWithRss";
                    *(_QWORD *)(v75 + 168) = retaddr;
                  }
                }
              }
            }
            **(_QWORD **)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = a2;
            v58 = v29;
            v59 = *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8);
            v60 = *(_QWORD *)(v59 + 624);
            if ( v60 )
            {
              if ( (_WORD)v52 == 0xFFFF )
              {
                v58 = v59 + 400;
              }
              else if ( (_WORD)v52 == 0xFFFE )
              {
                v58 = v59 + 176;
              }
              else
              {
                v58 = v60 + 224LL * (__int16)v52;
              }
            }
            _InterlockedIncrement64((volatile signed __int64 *)(v58 + 80));
            if ( *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBC) != (_BYTE)v29 )
            {
              if ( (v52 & 0x8000u) == 0 )
              {
                v90 = *(unsigned __int16 *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBA);
                if ( (_WORD)v90 )
                {
                  v81 = *((_DWORD *)a2 + 52);
                  LOWORD(v82) = -1;
                  if ( v81 )
                    v82 = v81 % v90;
                  LOWORD(v52) = v82;
                }
              }
              if ( (unsigned int)VmsPlanGetPlannedProcessorForEntry(
                                   *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8) + 640LL,
                                   (unsigned __int16)v52) != *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL)
                                                                       + 0xB0) )
                _InterlockedIncrement64((volatile signed __int64 *)(v83 + 112));
            }
            a2 = v48;
            if ( !v48 )
              goto LABEL_103;
          }
        }
        while ( 1 )
        {
          do
          {
            while ( 1 )
            {
LABEL_103:
              v61 = *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80);
              if ( !v61 )
                goto LABEL_32;
              v62 = *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD);
              *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = *(_QWORD *)v61;
              v63 = *(_BYTE *)(v61 + 58) ^ (*(_BYTE *)(v61 + 58) ^ (v62 >> 2)) & 2;
              *(_BYTE *)(v61 + 58) = v63;
              *(_BYTE *)(v61 + 58) = v63
                                   ^ (v63
                                    ^ (*(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) >> 2))
                                   & 4;
              if ( (*(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBD) & 4) == 0
                || *(_QWORD *)(v61 + 16) != v29 )
              {
                break;
              }
              if ( (unsigned __int8)VmsVrssPushNblGroupToBreakerQueue(v61) )
              {
                v66 = 128;
                goto LABEL_108;
              }
            }
            LOBYTE(v46) = *(_BYTE *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF2);
            v64 = *(_QWORD *)(v61 + 16);
            v65 = VmsVrssPvtPushNblGroupToQueue(
                    v61,
                    *(unsigned int *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4),
                    v46);
            v29 = 0;
          }
          while ( !v65 );
          if ( v65 == 1 )
          {
            _InterlockedIncrement64((volatile signed __int64 *)(v64 + 464));
            v66 = v64;
LABEL_108:
            KeInsertQueueDpc((PRKDPC)v66, 0, 0);
            goto LABEL_109;
          }
          v91 = v65 - 2;
          if ( v65 == 2 )
          {
            _InterlockedIncrement64((volatile signed __int64 *)(v64 + 456));
            v66 = v64 + 64;
            goto LABEL_108;
          }
          if ( v65 == 3 )
          {
            _InterlockedIncrement64((volatile signed __int64 *)(v64 + 448));
            KeSetEvent((PRKEVENT)(v64 + 192), 3, 0);
          }
          else
          {
            LOBYTE(v91) = 2;
            WPP_RECORDER_SF_dq(
              VmsIfrLog,
              v91,
              20,
              14,
              (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids,
              v65,
              v64);
          }
LABEL_109:
          v29 = 0;
        }
      }
    }
  }
  else if ( (v25 & 1) != 0 )
  {
    v38 = *(_WORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x2A);
    goto LABEL_66;
  }
LABEL_31:
  LOBYTE(v29) = 0;
  *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88) = a2;
  if ( v10 )
  {
    if ( !a2 )
      goto LABEL_36;
    do
    {
      if ( (_WORD)v27 )
      {
        v67 = *((_DWORD *)a2 + 52);
        v68 = 0xFFFF;
        if ( v67 )
          v68 = v67 % (unsigned __int16)v27;
        PlannedProcessorForEntry = VmsPlanGetPlannedProcessorForEntry(v9 + 640, v68);
        if ( PlannedProcessorForEntry == v71 )
        {
          v27 = *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
        }
        else
        {
          _InterlockedIncrement64((volatile signed __int64 *)(v70 + 96));
          v27 = *(unsigned __int16 *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xBA);
          v9 = *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8);
          *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = v27;
        }
      }
      a2 = (__int64 *)*a2;
    }
    while ( a2 );
  }
LABEL_32:
  if ( *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88) )
  {
    VmsPtNicExpandStackAndCallout(
      VmsPtpFinalCompleteCallout,
      *(_DWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18));
    LOBYTE(v29) = 0;
  }
  v30 = *(void **)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0);
  if ( v30 )
  {
    ExFreeToNPagedLookasideList(&stru_1401FA0C0, v30);
    LOBYTE(v29) = 0;
    *(_QWORD *)(((unsigned __int64)&v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = 0;
  }
LABEL_36:
  if ( *(_BYTE *)v4 != (_BYTE)v29 )
    _InterlockedDecrement64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v92
                                                                               & 0xFFFFFFFFFFFFFFC0uLL)
                                                                              + 8)
                                                                  + 216LL)
                                                      + ((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)));
}

```

## disassembly

```asm
0x14004dcf8  mov     [rsp-8+arg_18], rbx
0x14004dcfd  push    rbp
0x14004dcfe  push    rsi
0x14004dcff  push    rdi
0x14004dd00  push    r12
0x14004dd02  push    r13
0x14004dd04  push    r14
0x14004dd06  push    r15
0x14004dd08  sub     rsp, 190h
0x14004dd0f  lea     rbp, [rsp+80h]
0x14004dd17  and     rbp, 0FFFFFFFFFFFFFFC0h
0x14004dd1b  mov     rax, cs:__security_cookie
0x14004dd22  xor     rax, rsp
0x14004dd25  mov     [rbp+140h+var_40], rax
0x14004dd2c  xor     ebx, ebx
0x14004dd2e  mov     [rbp+140h+var_128], r9d
0x14004dd32  mov     r13d, r8d
0x14004dd35  mov     [rbp+140h+var_110], rbx
0x14004dd39  mov     rdi, rdx
0x14004dd3c  mov     [rbp+140h+var_108], rbx
0x14004dd40  mov     r15, rcx
0x14004dd43  xor     edx, edx; Val
0x14004dd45  mov     r8d, 80h; Size
0x14004dd4b  lea     rcx, [rbp+140h+var_C0]; void *
0x14004dd52  mov     r14d, ebx
0x14004dd55  mov     esi, ebx
0x14004dd57  call    memset
0x14004dd5c  mov     rcx, [rsp+1C8h]
0x14004dd64  lea     rdx, aVmsptnicsendne; "VmsPtNicSendNetBufferListsCompleteWithR"...
0x14004dd6b  xor     eax, eax
0x14004dd6d  mov     word ptr [rbp+140h+LockState.OldIrql], ax
0x14004dd71  mov     [rbp+140h+LockState.Flags], al
0x14004dd74  mov     eax, cs:VmsDiagnosticFlags
0x14004dd7a  test    al, 1
0x14004dd7c  jnz     loc_14004E09E
0x14004dd82  xor     ecx, ecx; ProcNumber
0x14004dd84  mov     [rbp+140h+var_118], rbx
0x14004dd88  mov     r12b, bl
0x14004dd8b  mov     dword ptr [rbp+140h+var_13C.OldIrql], ebx
0x14004dd8e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004dd95  nop     dword ptr [rax+rax+00h]
0x14004dd9a  mov     [rbp+140h+var_12C], eax
0x14004dd9d  mov     ebx, eax
0x14004dd9f  cmp     eax, 0FFFFFFFFh
0x14004dda2  jz      short loc_14004DDB6
0x14004dda4  mov     edx, eax
0x14004dda6  lea     rcx, VmsKnownProcessors
0x14004ddad  call    VmsCpuSetContainsProcessor
0x14004ddb2  test    al, al
0x14004ddb4  jnz     short loc_14004DE02
0x14004ddb6  mov     rcx, cs:VmsIfrLog
0x14004ddbd  lea     rax, aVmsisvalidproc_0; "VmsIsValidProcessor(currentProcIndex)"
0x14004ddc4  mov     [rsp+1C0h+var_198], rax
0x14004ddc9  mov     r9d, 0B6h
0x14004ddcf  lea     rax, WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids
0x14004ddd6  mov     r8d, 13h
0x14004dddc  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x14004dde1  call    WPP_RECORDER_SF_s
0x14004dde6  cmp     ebx, 0FFFFFFFFh
0x14004dde9  jz      short loc_14004DDFD
0x14004ddeb  mov     edx, ebx
0x14004dded  lea     rcx, VmsKnownProcessors
0x14004ddf4  call    VmsCpuSetContainsProcessor
0x14004ddf9  test    al, al
0x14004ddfb  jnz     short loc_14004DE02
0x14004ddfd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmsIsValidProcessor(currentProcIndex)")
0x14004de02  test    byte ptr [rbp+140h+var_128], 1
0x14004de06  jnz     loc_14004E095
0x14004de0c  call    cs:__imp_KeGetCurrentIrql
0x14004de13  nop     dword ptr [rax+rax+00h]
0x14004de18  mov     [rbp+140h+var_13F], sil
0x14004de1c  cmp     al, 2
0x14004de1e  jz      loc_14004E095
0x14004de24  test    r15, r15
0x14004de27  jz      loc_14004E594
0x14004de2d  mov     r14, [r15+8]
0x14004de31  mov     [rbp+140h+var_110], r14
0x14004de35  test    r14, r14
0x14004de38  jz      loc_14004E594
0x14004de3e  lea     rbx, WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids
0x14004de45  mov     rax, [r14+0CF0h]
0x14004de4c  lea     rcx, aPtnicext; "ptNicExt"
0x14004de53  mov     [rbp+140h+var_100], rax
0x14004de57  test    rax, rax
0x14004de5a  jz      loc_14004E8DE
0x14004de60  mov     rcx, [r14+38h]; Lock
0x14004de64  lea     rdx, [rbp+140h+LockState]; LockState
0x14004de68  xor     r8d, r8d; Flags
0x14004de6b  call    cs:__imp_NdisAcquireRWLockRead
0x14004de72  nop     dword ptr [rax+rax+00h]
0x14004de77  mov     eax, cs:VmsDiagnosticFlags
0x14004de7d  xor     r14d, r14d
0x14004de80  mov     rcx, [rsp+1C8h]
0x14004de88  mov     [rbp+140h+var_138], rsi
0x14004de8c  test    al, 1
0x14004de8e  jnz     loc_14004E0E1
0x14004de94  test    r15, r15
0x14004de97  jz      loc_14004E5F6
0x14004de9d  mov     r14, [r15+8]
0x14004dea1  test    r14, r14
0x14004dea4  jz      loc_14004E5F6
0x14004deaa  mov     rbx, [r14+0CF0h]
0x14004deb1  test    rbx, rbx
0x14004deb4  jz      loc_14004E90A
0x14004deba  test    r13d, r13d
0x14004debd  jnz     loc_14004E12B
0x14004dec3  xor     edx, edx
0x14004dec5  mov     rcx, r14
0x14004dec8  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x14004decd  test    al, al
0x14004decf  jnz     loc_14004E9D2
0x14004ded5  lea     rax, [rbx+5C8h]
0x14004dedc  mov     rcx, [rax]
0x14004dedf  cmp     rcx, rax
0x14004dee2  jz      loc_14004E9C5
0x14004dee8  test    rcx, rcx
0x14004deeb  jnz     loc_14004E9DE
0x14004def1  mov     rbx, rsi
0x14004def4  mov     [rbp+140h+var_140], sil
0x14004def8  test    rbx, rbx
0x14004defb  jz      loc_14004E9C9
0x14004df01  cmp     dword ptr [rbx+30h], 1
0x14004df05  jnz     loc_14004E9C9
0x14004df0b  mov     eax, [rbx+34h]
0x14004df0e  test    al, 20h
0x14004df10  jnz     loc_14004E9C9
0x14004df16  xor     ecx, ecx; ProcNumber
0x14004df18  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004df1f  nop     dword ptr [rax+rax+00h]
0x14004df24  mov     ecx, eax
0x14004df26  shl     rcx, 6
0x14004df2a  add     rcx, [rbx+0D8h]
0x14004df31  lock inc qword ptr [rcx]
0x14004df35  mov     [rbp+140h+var_140], 1
0x14004df39  mov     r15, [rbp+140h+var_110]
0x14004df3d  lea     rdx, [rbp+140h+LockState]; LockState
0x14004df41  mov     rcx, [r15+38h]; Lock
0x14004df45  call    cs:__imp_NdisReleaseRWLock
0x14004df4c  nop     dword ptr [rax+rax+00h]
0x14004df51  mov     r11, [rbp+140h+var_138]
0x14004df55  mov     r13d, 3
0x14004df5b  test    r11, r11
0x14004df5e  jnz     loc_14004E16D
0x14004df64  mov     rax, [rbp+140h+var_118]
0x14004df68  mov     rdx, rsi
0x14004df6b  mov     r9d, dword ptr [rbp+140h+var_13C.OldIrql]
0x14004df6f  mov     r10d, [rbp+140h+var_12C]
0x14004df73  mov     [rbp+140h+var_83], 0
0x14004df7a  lea     rcx, [rbp+140h+var_B8]
0x14004df81  mov     [rbp+140h+var_B0], rcx
0x14004df88  mov     ecx, cs:VmsExecutionMode
0x14004df8e  mov     [rbp+140h+var_4C], ecx
0x14004df94  mov     [rbp+140h+var_8C], 0
0x14004df9e  mov     [rbp+140h+var_B8], 0
0x14004dfa9  mov     [rbp+140h+var_A0], 0
0x14004dfb4  mov     [rbp+140h+var_A8], 0
0x14004dfbf  mov     [rbp+140h+Entry], 0
0x14004dfca  mov     [rbp+140h+var_C0], 0
0x14004dfd5  mov     [rbp+140h+var_90], r10d
0x14004dfdc  mov     [rbp+140h+var_98], rsi
0x14004dfe3  mov     [rbp+140h+var_86], r9w
0x14004dfeb  mov     [rbp+140h+var_84], r12b
0x14004dff2  test    r11, r11
0x14004dff5  jnz     loc_14004E200
0x14004dffb  xor     r11d, r11d
0x14004dffe  mov     [rbp+140h+var_B8], rdi
0x14004e005  test    r12b, r12b
0x14004e008  jnz     loc_14004E629
0x14004e00e  mov     r9, [rbp+140h+var_B8]
0x14004e015  test    r9, r9
0x14004e018  jz      short loc_14004E037
0x14004e01a  mov     eax, [rbp+140h+var_128]
0x14004e01d  lea     rcx, VmsPtpFinalCompleteCallout; Callout
0x14004e024  mov     rdx, [rbp+140h+var_100]
0x14004e028  xor     r8d, r8d
0x14004e02b  mov     [rsp+1C0h+var_1A0], eax; int
0x14004e02f  call    VmsPtNicExpandStackAndCallout
0x14004e034  xor     r11d, r11d
0x14004e037  mov     rdx, [rbp+140h+Entry]; Entry
0x14004e03e  test    rdx, rdx
0x14004e041  jz      short loc_14004E060
0x14004e043  lea     rcx, stru_1401FA0C0; Lookaside
0x14004e04a  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004e051  nop     dword ptr [rax+rax+00h]
0x14004e056  xor     r11d, r11d
0x14004e059  mov     [rbp+140h+Entry], r11
0x14004e060  cmp     [rbp+140h+var_140], r11b
0x14004e064  jnz     loc_14004E5CE
0x14004e06a  mov     rcx, [rbp+140h+var_40]
0x14004e071  xor     rcx, rsp; StackCookie
0x14004e074  call    __security_check_cookie
0x14004e079  mov     rbx, [rsp+1C0h+arg_18]
0x14004e081  add     rsp, 190h
0x14004e088  pop     r15
0x14004e08a  pop     r14
0x14004e08c  pop     r13
0x14004e08e  pop     r12
0x14004e090  pop     rdi
0x14004e091  pop     rsi
0x14004e092  pop     rbp
0x14004e093  retn
0x14004e095  mov     [rbp+140h+var_13F], 1
0x14004e099  jmp     loc_14004DE24
0x14004e09e  test    rdi, rdi
0x14004e0a1  jz      loc_14004DD82
0x14004e0a7  mov     rax, [rdi+120h]
0x14004e0ae  test    rax, rax
0x14004e0b1  jz      loc_14004DD82
0x14004e0b7  mov     rax, [rax+10h]
0x14004e0bb  test    rax, rax
0x14004e0be  jz      loc_14004DD82
0x14004e0c4  mov     [rax+0B0h], rdx
0x14004e0cb  mov     dword ptr [rax+0B8h], 3084h
0x14004e0d5  mov     [rax+0A8h], rcx
0x14004e0dc  jmp     loc_14004DD82
0x14004e0e1  test    rdi, rdi
0x14004e0e4  jz      loc_14004DE94
0x14004e0ea  mov     rax, [rdi+120h]
0x14004e0f1  test    rax, rax
0x14004e0f4  jz      loc_14004DE94
0x14004e0fa  mov     rax, [rax+10h]
0x14004e0fe  test    rax, rax
0x14004e101  jz      loc_14004DE94
0x14004e107  lea     rdx, aVmsptnicgetvmq; "VmsPtNicGetVmqFromNBL"
0x14004e10e  mov     dword ptr [rax+0B8h], 5280h
0x14004e118  mov     [rax+0B0h], rdx
0x14004e11f  mov     [rax+0A8h], rcx
0x14004e126  jmp     loc_14004DE94
0x14004e12b  cmp     [rbx+590h], rsi
0x14004e132  jz      loc_14004DEC3
0x14004e138  cmp     [rbx+960h], sil
0x14004e13f  jnz     loc_14004E944
0x14004e145  cmp     [rbx+58Ch], r13d
0x14004e14c  jb      loc_14004DEF1
0x14004e152  lfence
0x14004e155  lea     ecx, [r13-1]
0x14004e159  mov     rax, [rbx+590h]
0x14004e160  mov     rbx, [rax+rcx*8]
0x14004e164  mov     [rbp+140h+var_138], rbx
0x14004e168  jmp     loc_14004DEF4
0x14004e16d  mov     rsi, [r11+8]
0x14004e171  mov     rax, [rsi+280h]
0x14004e178  mov     rdx, [r11+28h]
0x14004e17c  movzx   r9d, word ptr [rsi+502h]
0x14004e184  mov     [rbp+140h+var_118], rax
0x14004e188  mov     rax, [rbp+140h+var_118]
0x14004e18c  movzx   ecx, ax
0x14004e18f  mov     dword ptr [rbp+140h+var_13C.OldIrql], r9d
0x14004e193  and     cx, r13w
0x14004e197  mov     [rbp+140h+var_120], rdx
0x14004e19b  cmp     cx, r13w
0x14004e19f  setz    r12b
0x14004e1a3  cmp     [rdx+750h], r13d
0x14004e1aa  jz      loc_14004E9E7
0x14004e1b0  cmp     cx, r13w
0x14004e1b4  jz      loc_14004DF6F
0x14004e1ba  xor     r8d, r8d
0x14004e1bd  mov     rcx, rdi
0x14004e1c0  test    rdi, rdi
0x14004e1c3  jz      short loc_14004E1D0
0x14004e1c5  mov     rcx, [rcx]
0x14004e1c8  inc     r8d
0x14004e1cb  test    rcx, rcx
0x14004e1ce  jnz     short loc_14004E1C5
0x14004e1d0  xor     edx, edx
0x14004e1d2  cmp     [rsi+270h], rdx
0x14004e1d9  jz      short loc_14004E1E2
0x14004e1db  lea     rdx, [rsi+0B0h]
0x14004e1e2  mov     r10d, [rbp+140h+var_12C]
0x14004e1e6  cmp     [rsi+530h], r10d
0x14004e1ed  jz      short loc_14004E1F7
0x14004e1ef  mov     ecx, r8d
0x14004e1f2  lock add [rdx+70h], rcx
0x14004e1f7  mov     rdx, [rbp+140h+var_120]
0x14004e1fb  jmp     loc_14004DF73
0x14004e200  cmp     [rdx+750h], r13d
0x14004e207  jnz     loc_14004E9F7
0x14004e20d  test    byte ptr [rsi+280h], 1
0x14004e214  jz      loc_14004DFFB
0x14004e21a  mov     eax, [rsi+28h]
0x14004e21d  mov     ebx, 10h
0x14004e222  test    bl, al
0x14004e224  jz      loc_14004DFFB
0x14004e22a  xor     eax, eax
0x14004e22c  mov     [rbp+140h+var_68], r15
0x14004e233  mov     r15, [rbp+140h+var_108]
0x14004e237  xor     r14d, r14d
0x14004e23a  mov     [rbp+140h+var_50], ax
0x14004e241  mov     [rbp+140h+var_58], eax
0x14004e247  lea     rax, VmsPtPvtRssSendCompleteProcessNblGroup
0x14004e24e  mov     [rbp+140h+var_78], rax
0x14004e255  test    r15, r15
0x14004e258  jnz     loc_14004EA08
0x14004e25e  lea     rcx, [rsi+280h]
0x14004e265  call    VmsPlanGetPlannedDefaultCpuIndex
0x14004e26a  mov     r12b, [rbp+140h+var_13F]
0x14004e26e  mov     esi, eax
0x14004e270  mov     cl, [rbp+140h+var_83]
0x14004e276  mov     rdx, [rbp+140h+var_98]
0x14004e27d  and     cl, 0FDh
  ... truncated ...
```
