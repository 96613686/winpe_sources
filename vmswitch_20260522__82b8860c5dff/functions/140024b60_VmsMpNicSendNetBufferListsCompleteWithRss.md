# VmsMpNicSendNetBufferListsCompleteWithRss

- ea: `0x140024b60`
- end: `0x140025bd4`
- name: `VmsMpNicSendNetBufferListsCompleteWithRss`
- size: `4212`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400135e0`
- `0x140024920`

## callees

- `0x140010940`
- `0x140012a90`
- `0x140014330`
- `0x140017a7c`
- `0x1400247dc`
- `0x140024b60`
- `0x140025be0`
- `0x140025d10`
- `0x140025f7c`
- `0x140027a64`
- `0x140046f1c`
- `0x14006b4dc`
- `0x14008497c`
- `0x1400f2a6c`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400254fc`
- `ntoskrnl!KeBugCheckEx` at `0x1400256e7`
- `ntoskrnl!KeBugCheckEx` at `0x1400257cc`
- `ntoskrnl!KeBugCheckEx` at `0x1400258a9`
- `ntoskrnl!KeBugCheckEx` at `0x1400254fc`
- `ntoskrnl!KeBugCheckEx` at `0x1400256e7`
- `ntoskrnl!KeBugCheckEx` at `0x1400257cc`
- `ntoskrnl!KeBugCheckEx` at `0x1400258a9`
- `ntoskrnl!KeSetEvent` at `0x140025b55`
- `ntoskrnl!KeSetEvent` at `0x140025b55`
- `ntoskrnl!KeInsertQueueDpc` at `0x140025094`
- `ntoskrnl!KeInsertQueueDpc` at `0x140025094`
- `ntoskrnl!KeIsExecutingDpc` at `0x140025509`
- `ntoskrnl!KeIsExecutingDpc` at `0x140025552`
- `ntoskrnl!KeIsExecutingDpc` at `0x140025509`
- `ntoskrnl!KeIsExecutingDpc` at `0x140025552`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140025394`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002557f`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140025394`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002557f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024ffe`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140024ffe`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140024d44`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140024d44`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140024bf9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140024c80`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002547f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400254b2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400254dd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002566a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002569d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400256c8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140025782`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400257ad`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002585f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002588a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140025918`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400259a1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140024bf9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140024c80`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002547f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400254b2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400254dd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002566a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002569d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400256c8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140025782`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400257ad`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002585f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002588a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140025918`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400259a1`
- `ntoskrnl!KeGetProcessorIndexFromNumber` at `0x140024d04`
- `ntoskrnl!KeGetProcessorIndexFromNumber` at `0x140024d04`
- `ntoskrnl!KeLowerIrql` at `0x140025725`
- `ntoskrnl!KeLowerIrql` at `0x140025802`
- `ntoskrnl!KeLowerIrql` at `0x140025725`
- `ntoskrnl!KeLowerIrql` at `0x140025802`
- `ntoskrnl!KfRaiseIrql` at `0x1400259ee`
- `ntoskrnl!KfRaiseIrql` at `0x140025b8e`
- `ntoskrnl!KfRaiseIrql` at `0x1400259ee`
- `ntoskrnl!KfRaiseIrql` at `0x140025b8e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140024c0f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140024c53`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025367`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002543e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025542`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025629`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002576c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025849`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025aaf`
- `ntoskrnl!KeGetCurrentIrql` at `0x140024c0f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140024c53`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025367`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002543e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025542`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025629`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002576c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025849`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025aaf`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140025709`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140025760`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400257e6`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x14002583d`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140025709`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140025760`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400257e6`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x14002583d`
- `NDIS!NdisAcquireRWLockRead` at `0x140024c72`
- `NDIS!NdisAcquireRWLockRead` at `0x140024c72`
- `NDIS!NdisReleaseRWLock` at `0x140024fd2`
- `NDIS!NdisReleaseRWLock` at `0x140024fd2`

## string_xrefs

- `0x14002541c`: `VmsMpNicSendNetBufferListsCompleteInternal`
- `0x140025607`: `VmsMpNicSendNetBufferListsCompleteInternal`
- `0x14002511e`: `VmsMpNicSendNetBufferListsCompleteWithRss`

## pseudocode

```c
void __fastcall VmsMpNicSendNetBufferListsCompleteWithRss(__int64 a1, __int64 *a2, int a3, int a4)
{
  unsigned __int64 v4; // rbp
  __int64 v5; // r13
  char v8; // al
  __int64 *v9; // rbx
  bool v10; // r14
  __int64 (__fastcall *v11)(); // rsi
  int v12; // edx
  UCHAR v13; // r8
  ULONG v14; // eax
  char v15; // cl
  __int64 v16; // rsi
  __int16 v17; // r15
  ULONG ProcessorIndexFromNumber; // eax
  PVOID v19; // rax
  char v20; // r12
  __int64 v21; // rsi
  __int64 *v22; // r15
  char v23; // r8
  int v24; // r9d
  bool v25; // r10
  unsigned int v26; // ecx
  int v27; // r14d
  unsigned int v28; // eax
  int ReceiveProc; // eax
  __int64 NblGroup; // rax
  _QWORD **v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rax
  unsigned __int8 v34; // dl
  char v35; // dl
  __int64 v36; // rbx
  int v37; // eax
  __int64 v38; // rbx
  void *v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  unsigned int v52; // ecx
  int v53; // edx
  unsigned int v54; // eax
  char v55; // cl
  bool v56; // dl
  bool v57; // al
  _QWORD *v58; // rax
  int i; // esi
  BOOLEAN v60; // r9
  NTSTATUS v61; // eax
  int v62; // edx
  int v63; // esi
  int v64; // r14d
  struct _NET_BUFFER_LIST *v65; // r15
  __int64 v66; // r13
  _QWORD *v67; // rax
  __int64 v68; // rax
  int v69; // r12d
  KIRQL CurrentIrql; // bl
  __int64 NicHeaderAtIndex; // rax
  ULONG CurrentProcessorNumber; // eax
  ULONG_PTR v73; // rbx
  ULONG v74; // eax
  int v75; // esi
  BOOLEAN v76; // r9
  NTSTATUS v77; // eax
  int v78; // edx
  int v79; // esi
  int v80; // r14d
  struct _NET_BUFFER_LIST *v81; // r15
  __int64 v82; // r13
  _QWORD *v83; // rax
  __int64 v84; // rax
  int v85; // r12d
  KIRQL v86; // bl
  __int64 v87; // rax
  ULONG v88; // eax
  ULONG_PTR v89; // rbx
  ULONG v90; // eax
  char *v91; // rcx
  ULONG v92; // eax
  ULONG_PTR v93; // rbx
  ULONG v94; // eax
  char *v95; // rcx
  ULONG v96; // eax
  ULONG_PTR v97; // rbx
  ULONG v98; // eax
  char *v99; // rcx
  __int64 v100; // rbx
  char *v101; // rcx
  __int64 v102; // rbx
  int v103; // edx
  int v104; // [rsp+80h] [rbp+0h] BYREF
  _UNKNOWN *retaddr; // [rsp+198h] [rbp+118h]

  v4 = (unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL;
  *(_QWORD *)(v4 + 16) = a1;
  *(_DWORD *)(v4 + 8) = a4;
  *(_WORD *)(v4 + 4) = 0;
  v5 = a1;
  *(_BYTE *)(v4 + 6) = 0;
  v8 = VmsDiagnosticFlags;
  v9 = a2;
  *(_DWORD *)v4 = a3;
  *(_OWORD *)(v4 + 64) = 0;
  *(_OWORD *)(v4 + 80) = 0;
  *(_OWORD *)(v4 + 96) = 0;
  *(_OWORD *)(v4 + 112) = 0;
  *(_OWORD *)(v4 + 128) = 0;
  *(_OWORD *)(v4 + 144) = 0;
  *(_OWORD *)(v4 + 160) = 0;
  *(_OWORD *)(v4 + 176) = 0;
  if ( (v8 & 1) != 0 )
  {
    if ( a2 )
    {
      v45 = a2[36];
      if ( v45 )
      {
        v46 = *(_QWORD *)(v45 + 16);
        if ( v46 )
        {
          *(_DWORD *)(v46 + 184) = 4169;
          *(_QWORD *)(v46 + 176) = "VmsMpNicSendNetBufferListsCompleteWithRss";
          *(_QWORD *)(v46 + 168) = retaddr;
        }
      }
    }
  }
  KeGetCurrentProcessorNumberEx(0);
  v10 = (a3 & 1) != 0 || KeGetCurrentIrql() == 2;
  if ( VmsHostNicIndicateNblsInline )
  {
    v58 = v9;
    for ( i = 0; v58; ++i )
      v58 = (_QWORD *)*v58;
    *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x34) = 0;
    *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v5;
    *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v9;
    *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = i;
    *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x2C) = a3;
    *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = a4;
    v60 = KeGetCurrentIrql() < 2u && !(unsigned int)KeIsExecutingDpc();
    v61 = KeExpandKernelStackAndCalloutEx(VmsMpNicSendNetBufferListsCompleteCallout, (PVOID)(v4 + 24), 0x6000u, v60, 0);
    if ( v61 < 0 )
    {
      LOBYTE(v62) = 2;
      WPP_RECORDER_SF_qdd(
        VmsIfrLog,
        v62,
        20,
        11,
        (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
        (char)v9,
        i,
        v61);
      v63 = *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x2C);
      v64 = *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
      v65 = *(struct _NET_BUFFER_LIST **)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
      v66 = *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
      *(_DWORD *)((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) = *(_DWORD *)(((unsigned __int64)&v104
                                                                                & 0xFFFFFFFFFFFFFFC0uLL)
                                                                               + 0x30);
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( v65 )
        {
          v67 = v65->NetBufferListInfo[18];
          if ( v67 )
          {
            v68 = v67[2];
            if ( v68 )
            {
              *(_DWORD *)(v68 + 184) = 588;
              *(_QWORD *)(v68 + 176) = "VmsMpNicSendNetBufferListsCompleteInternal";
              *(_QWORD *)(v68 + 168) = retaddr;
            }
          }
        }
      }
      v69 = 0;
      CurrentIrql = KeGetCurrentIrql();
      *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = *(_QWORD *)(*(_QWORD *)(v66 + 3312) + 24LL);
      if ( !CurrentIrql && (VmsExecutionMode & 8) == 0 )
      {
        v69 = 1;
        CurrentIrql = KfRaiseIrql(2u);
      }
      if ( (*(_BYTE *)v4 & 2) != 0 )
      {
        NicHeaderAtIndex = VmsPtGetNicHeaderAtIndex(v66, 0);
        *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = NicHeaderAtIndex;
        if ( NicHeaderAtIndex )
          _InterlockedAdd64(
            (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                      + *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10)
                                                  + 24LL)
                                      + 16),
            -v64);
      }
      if ( CurrentIrql == 2 )
      {
        CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
        v73 = CurrentProcessorNumber;
        if ( CurrentProcessorNumber == -1
          || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, CurrentProcessorNumber)
          || (v91 = (char *)VmsPlanCpuTable + 5440 * v73) == 0 )
        {
          v74 = KeGetCurrentProcessorNumberEx(0);
          KeBugCheckEx(0x121u, v73, v74, 0, 0);
        }
        NetDispatchProfilerLeave(v91 + 1152);
        NdisMSendNetBufferListsComplete(
          *(NDIS_HANDLE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 8),
          v65,
          v69 | v63);
      }
      else
      {
        NdisMSendNetBufferListsComplete(
          *(NDIS_HANDLE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 8),
          v65,
          v69 | v63);
        if ( !CurrentIrql && (VmsExecutionMode & 8) == 0 )
          KeLowerIrql(0);
      }
      if ( KeGetCurrentIrql() == 2 )
      {
        v92 = KeGetCurrentProcessorNumberEx(0);
        v93 = v92;
        if ( v92 == -1
          || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v92)
          || (v99 = (char *)VmsPlanCpuTable + 5440 * v93) == 0 )
        {
          v94 = KeGetCurrentProcessorNumberEx(0);
          KeBugCheckEx(0x121u, v93, v94, 0, 0);
        }
        NetDispatchProfilerEnter(v99 + 1152, 1);
      }
      if ( (*(_BYTE *)v4 & 1) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) > 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_id(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            22,
            12,
            (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
            v66,
            v64);
        v100 = VmsPtGetNicHeaderAtIndex(v66, 0);
        if ( v100 )
          _InterlockedAdd64(
            (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                      + *(_QWORD *)(v100 + 24)
                                      + 8),
            -v64);
      }
    }
    return;
  }
  if ( a4 )
  {
    switch ( a4 )
    {
      case 1:
        v11 = VmsMpNicSendCompleteDecrementRoutedCount;
        goto LABEL_8;
      case 2:
        v11 = VmsMpNicSendCompleteDecrementEdgeCount;
        goto LABEL_8;
      case 255:
        v11 = VmsMpNicSendCompleteDecrementAllCount;
        goto LABEL_8;
    }
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      (unsigned int)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      19,
      71,
      (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
      (__int64)"!\"Unexpected process function\"");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v11 = VmsMpNicSendComplete;
LABEL_8:
  if ( v10 )
  {
    if ( KeGetCurrentIrql() != 2 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v12,
        19,
        24,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
      if ( KeGetCurrentIrql() != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v5 + 56), (PLOCK_STATE_EX)(v4 + 4), v13);
  v14 = KeGetCurrentProcessorNumberEx(0);
  *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = v5;
  *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) = v14;
  *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB4) = VmsExecutionMode;
  *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) = ((unsigned __int64)&v104
                                                                         & 0xFFFFFFFFFFFFFFC0uLL)
                                                                        + 72;
  v15 = 0;
  *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x74) = 0;
  *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48) = 0;
  *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) = 0;
  *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = 0;
  *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) = 0;
  *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = 0;
  *(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7D) = 0;
  *(_WORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0) = 0;
  *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8) = a3 & 0xFFFFFFFE;
  *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88) = v11;
  if ( *(_BYTE *)(v5 + 4930) )
  {
    v16 = v5 + 4976;
    v17 = *(_WORD *)(v5 + 4976);
    ProcessorIndexFromNumber = KeGetProcessorIndexFromNumber((PPROCESSOR_NUMBER)(v5 + 4972));
    v15 = *(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7D);
  }
  else
  {
    v16 = 0;
    ProcessorIndexFromNumber = 0;
    v17 = 0;
  }
  *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = v16;
  *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xAC) = ProcessorIndexFromNumber;
  *(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7D) = v15 & 0xF8 | 3;
  *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = 0;
  *(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB2) = v10;
  *(_WORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x78) = v17;
  v19 = ExAllocateFromNPagedLookasideList(&stru_1401FA0C0);
  *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) = v19;
  if ( v19 )
    memset(v19, 0, 0x408u);
  else
    *(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7D) &= 0xFCu;
  v20 = *(_BYTE *)(v5 + 4930);
  v21 = 0;
  if ( (VmsDiagnosticFlags & 1) == 0 )
    goto LABEL_16;
  if ( v9 )
  {
    v47 = v9[36];
    if ( !v47 )
      goto LABEL_17;
    v48 = *(_QWORD *)(v47 + 16);
    if ( v48 )
    {
      *(_QWORD *)(v48 + 176) = "VmsMpNicPvtRssSortNbls";
      *(_DWORD *)(v48 + 184) = 288;
      *(_QWORD *)(v48 + 168) = retaddr;
      goto LABEL_17;
    }
LABEL_16:
    if ( !v9 )
      goto LABEL_44;
    while ( 1 )
    {
LABEL_17:
      v22 = (__int64 *)*v9;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( v22 )
        {
          v40 = v22[36];
          if ( v40 )
          {
            v41 = *(_QWORD *)(v40 + 16);
            if ( v41 )
            {
              *(_QWORD *)(v41 + 176) = "VmsMpNicPvtRssSortNbls";
              *(_DWORD *)(v41 + 184) = 296;
              *(_QWORD *)(v41 + 168) = retaddr;
            }
          }
        }
      }
      *v9 = 0;
      if ( v20 )
      {
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          v49 = v9[36];
          if ( v49 )
          {
            v50 = *(_QWORD *)(v49 + 16);
            if ( v50 )
            {
              *(_QWORD *)(v50 + 176) = "VmsVrssPrimeVrssContextForNextNbl";
              *(_DWORD *)(v50 + 184) = 1123;
              *(_QWORD *)(v50 + 168) = retaddr;
            }
          }
        }
        v23 = *(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7D);
        v24 = -1;
        v25 = (v23 & 4) != 0 || (v23 & 2) != 0;
        if ( (v23 & 1) != 0 )
        {
          v26 = *(unsigned __int16 *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x78);
          LOWORD(v27) = -1;
          if ( (_WORD)v26 )
          {
            v28 = *((_DWORD *)v9 + 52);
            if ( v28 )
              v27 = v28 % v26;
          }
          if ( (_WORD)v27 == 0xFFFF )
            v24 = *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xAC);
          v21 = *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0)
                          + 8LL * (__int16)v27
                          + 8);
          if ( !v21 )
          {
            if ( v24 == -1 )
            {
              ReceiveProc = VmsMpNicPvtRssGetReceiveProc(
                              *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80),
                              (unsigned __int16)v27,
                              *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90),
                              *(unsigned __int8 *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB2));
              v23 = *(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7D);
              v24 = ReceiveProc;
            }
            v25 = (v23 & 4) != 0
               || (v23 & 2) != 0
               || v24 != -1
               && (v24 != *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70)
                || (*(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB4) & 6) != 0);
          }
        }
        else
        {
          v51 = 0;
          if ( v25 )
            v51 = v21;
          v21 = v51;
          if ( *(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7C) )
          {
            v52 = *(unsigned __int16 *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x78);
            LOWORD(v53) = -1;
            if ( (_WORD)v52 )
            {
              v54 = *((_DWORD *)v9 + 52);
              if ( v54 )
                v53 = v54 % v52;
            }
            LOWORD(v27) = v53;
          }
          else
          {
            LOWORD(v27) = -2;
          }
        }
        if ( !v25 )
          goto LABEL_39;
        if ( !v21 )
        {
          if ( v24 == -1 )
            v24 = *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70);
          NblGroup = VmsVrssPvtFindNblGroup(
                       *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98),
                       *(unsigned __int16 *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0),
                       *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8),
                       v24,
                       *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88),
                       v4 + 64);
          v21 = NblGroup;
          if ( (*(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7D) & 1) != 0 )
            *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) + 8LL * (__int16)v27 + 8) = NblGroup;
LABEL_39:
          if ( !v21 )
          {
            v31 = (_QWORD **)(v4 + 80);
            v32 = v4 + 116;
            goto LABEL_41;
          }
        }
        v31 = (_QWORD **)(v21 + 32);
        v32 = v21 + 48;
        goto LABEL_41;
      }
      v55 = *(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7D);
      v56 = (v55 & 4) != 0 || (v55 & 2) != 0;
      if ( (v55 & 1) != 0 )
      {
        v57 = (v55 & 4) != 0
           || (v55 & 2) != 0
           || *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70)
           || (*(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB4) & 6) != 0;
        v21 = 0;
        if ( !v57 )
          goto LABEL_99;
      }
      else if ( !v56 )
      {
        v21 = 0;
        goto LABEL_99;
      }
      if ( v21
        || (v21 = VmsVrssPvtFindNblGroup(
                    *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98),
                    *(unsigned __int16 *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0),
                    *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8),
                    0,
                    *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88),
                    v4 + 64)) != 0 )
      {
        v31 = (_QWORD **)(v21 + 32);
        v32 = v21 + 48;
        goto LABEL_41;
      }
LABEL_99:
      v31 = (_QWORD **)(v4 + 80);
      v32 = v4 + 116;
LABEL_41:
      *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = v31;
      *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) = v32;
      **v31 = v9;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( *v9 )
        {
          v43 = *(_QWORD *)(*v9 + 288);
          if ( v43 )
          {
            v44 = *(_QWORD *)(v43 + 16);
            if ( v44 )
            {
              *(_QWORD *)(v44 + 176) = "VmsMpNicPvtRssSortNbls";
              *(_DWORD *)(v44 + 184) = 334;
              *(_QWORD *)(v44 + 168) = retaddr;
            }
          }
        }
      }
      **(_QWORD **)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = v9;
      v9 = v22;
      ++**(_DWORD **)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60);
      if ( !v22 )
      {
        v5 = *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
        break;
      }
    }
  }
LABEL_44:
  v33 = *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40);
  if ( v33 )
  {
    while ( 1 )
    {
      v34 = *(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7D);
      *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = *(_QWORD *)v33;
      v35 = *(_BYTE *)(v33 + 58) ^ (*(_BYTE *)(v33 + 58) ^ (v34 >> 2)) & 2;
      *(_BYTE *)(v33 + 58) = v35;
      *(_BYTE *)(v33 + 58) = v35
                           ^ (v35
                            ^ (*(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7D) >> 2))
                           & 4;
      if ( (*(_BYTE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7D) & 4) != 0 && !*(_QWORD *)(v33 + 16) )
        break;
      v36 = *(_QWORD *)(v33 + 16);
      v37 = VmsVrssPvtPushNblGroupToQueue(
              v33,
              *(unsigned int *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB4),
              *(unsigned __int8 *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xB2));
      if ( v37 )
      {
        if ( v37 == 1 )
        {
          _InterlockedIncrement64((volatile signed __int64 *)(v36 + 464));
          v42 = v36;
        }
        else
        {
          v103 = v37 - 2;
          if ( v37 != 2 )
          {
            if ( v37 == 3 )
            {
              _InterlockedIncrement64((volatile signed __int64 *)(v36 + 448));
              KeSetEvent((PRKEVENT)(v36 + 192), 3, 0);
            }
            else
            {
              LOBYTE(v103) = 2;
              WPP_RECORDER_SF_dq(
                VmsIfrLog,
                v103,
                20,
                14,
                (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids,
                v37,
                v36);
            }
            goto LABEL_47;
          }
          _InterlockedIncrement64((volatile signed __int64 *)(v36 + 456));
          v42 = v36 + 64;
        }
LABEL_59:
        KeInsertQueueDpc((PRKDPC)v42, 0, 0);
      }
LABEL_47:
      v33 = *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40);
      if ( !v33 )
        goto LABEL_48;
    }
    if ( !(unsigned __int8)VmsVrssPushNblGroupToBreakerQueue(v33) )
      goto LABEL_47;
    v42 = 128;
    goto LABEL_59;
  }
LABEL_48:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v5 + 56), (PLOCK_STATE_EX)(v4 + 4));
  v38 = *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48);
  if ( v38 )
  {
    v75 = *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x74);
    *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x2C) = *(_DWORD *)((unsigned __int64)&v104
                                                                                      & 0xFFFFFFFFFFFFFFC0uLL);
    *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = *(_DWORD *)(((unsigned __int64)&v104
                                                                                       & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                      + 8);
    *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x34) = 0;
    *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v5;
    *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v38;
    *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = v75;
    v76 = KeGetCurrentIrql() < 2u && !(unsigned int)KeIsExecutingDpc();
    v77 = KeExpandKernelStackAndCalloutEx(VmsMpNicSendNetBufferListsCompleteCallout, (PVOID)(v4 + 24), 0x6000u, v76, 0);
    if ( v77 < 0 )
    {
      LOBYTE(v78) = 2;
      WPP_RECORDER_SF_qdd(
        VmsIfrLog,
        v78,
        20,
        11,
        (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
        v38,
        v75,
        v77);
      v79 = *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x2C);
      v80 = *(_DWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
      v81 = *(struct _NET_BUFFER_LIST **)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
      v82 = *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
      *(_DWORD *)((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) = *(_DWORD *)(((unsigned __int64)&v104
                                                                                & 0xFFFFFFFFFFFFFFC0uLL)
                                                                               + 0x30);
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( v81 )
        {
          v83 = v81->NetBufferListInfo[18];
          if ( v83 )
          {
            v84 = v83[2];
            if ( v84 )
            {
              *(_DWORD *)(v84 + 184) = 588;
              *(_QWORD *)(v84 + 176) = "VmsMpNicSendNetBufferListsCompleteInternal";
              *(_QWORD *)(v84 + 168) = retaddr;
            }
          }
        }
      }
      v85 = 0;
      v86 = KeGetCurrentIrql();
      *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = *(_QWORD *)(*(_QWORD *)(v82 + 3312) + 24LL);
      if ( !v86 && (VmsExecutionMode & 8) == 0 )
      {
        v85 = 1;
        v86 = KfRaiseIrql(2u);
      }
      if ( (*(_BYTE *)v4 & 2) != 0 )
      {
        v87 = VmsPtGetNicHeaderAtIndex(v82, 0);
        *(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v87;
        if ( v87 )
          _InterlockedAdd64(
            (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                      + *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10)
                                                  + 24LL)
                                      + 16),
            -v80);
      }
      if ( v86 == 2 )
      {
        v88 = KeGetCurrentProcessorNumberEx(0);
        v89 = v88;
        if ( v88 == -1
          || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v88)
          || (v95 = (char *)VmsPlanCpuTable + 5440 * v89) == 0 )
        {
          v90 = KeGetCurrentProcessorNumberEx(0);
          KeBugCheckEx(0x121u, v89, v90, 0, 0);
        }
        NetDispatchProfilerLeave(v95 + 1152);
        NdisMSendNetBufferListsComplete(
          *(NDIS_HANDLE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 8),
          v81,
          v85 | v79);
      }
      else
      {
        NdisMSendNetBufferListsComplete(
          *(NDIS_HANDLE *)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 8),
          v81,
          v85 | v79);
        if ( !v86 && (VmsExecutionMode & 8) == 0 )
          KeLowerIrql(0);
      }
      if ( KeGetCurrentIrql() == 2 )
      {
        v96 = KeGetCurrentProcessorNumberEx(0);
        v97 = v96;
        if ( v96 == -1
          || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v96)
          || (v101 = (char *)VmsPlanCpuTable + 5440 * v97) == 0 )
        {
          v98 = KeGetCurrentProcessorNumberEx(0);
          KeBugCheckEx(0x121u, v97, v98, 0, 0);
        }
        NetDispatchProfilerEnter(v101 + 1152, 1);
      }
      if ( (*(_BYTE *)v4 & 1) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) > 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_id(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            22,
            12,
            (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
            v82,
            v80);
        v102 = VmsPtGetNicHeaderAtIndex(v82, 0);
        if ( v102 )
          _InterlockedAdd64(
            (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                      + *(_QWORD *)(v102 + 24)
                                      + 8),
            -v80);
      }
    }
  }
  v39 = *(void **)(((unsigned __int64)&v104 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0);
  if ( v39 )
    ExFreeToNPagedLookasideList(&stru_1401FA0C0, v39);
}

```

## disassembly

```asm
0x140024b60  push    rbp
0x140024b62  push    rbx
0x140024b63  push    rsi
0x140024b64  push    rdi
0x140024b65  push    r12
0x140024b67  push    r13
0x140024b69  push    r14
0x140024b6b  push    r15
0x140024b6d  sub     rsp, 158h
0x140024b74  lea     rbp, [rsp+80h]
0x140024b7c  and     rbp, 0FFFFFFFFFFFFFFC0h
0x140024b80  mov     rax, cs:__security_cookie
0x140024b87  xor     rax, rsp
0x140024b8a  mov     [rbp+110h+var_50], rax
0x140024b91  xorps   xmm0, xmm0
0x140024b94  mov     [rbp+110h+var_100], rcx
0x140024b98  xor     eax, eax
0x140024b9a  mov     dword ptr [rbp+110h+MiniportAdapterHandle], r9d
0x140024b9e  mov     word ptr [rbp+110h+LockState.OldIrql], ax
0x140024ba2  mov     r13, rcx
0x140024ba5  mov     rcx, [rsp+198h]
0x140024bad  mov     r12d, r9d
0x140024bb0  mov     [rbp+110h+LockState.Flags], al
0x140024bb3  mov     r15d, r8d
0x140024bb6  mov     eax, cs:VmsDiagnosticFlags
0x140024bbc  mov     rbx, rdx
0x140024bbf  mov     [rbp+110h+var_110], r8d
0x140024bc3  movups  [rbp+110h+var_D0], xmm0
0x140024bc7  movups  [rbp+110h+var_C0], xmm0
0x140024bcb  movups  [rbp+110h+var_B0], xmm0
0x140024bcf  movups  [rbp+110h+var_A0], xmm0
0x140024bd3  movups  [rbp+110h+var_90], xmm0
0x140024bda  movups  [rbp+110h+var_80], xmm0
0x140024be1  movups  xmmword ptr [rbp+110h+Entry], xmm0
0x140024be8  movups  [rbp+110h+var_60], xmm0
0x140024bef  test    al, 1
0x140024bf1  jnz     loc_1400250F8
0x140024bf7  xor     ecx, ecx; ProcNumber
0x140024bf9  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140024c00  nop     dword ptr [rax+rax+00h]
0x140024c05  test    r15b, 1
0x140024c09  jnz     loc_140025071
0x140024c0f  call    cs:__imp_KeGetCurrentIrql
0x140024c16  nop     dword ptr [rax+rax+00h]
0x140024c1b  cmp     al, 2
0x140024c1d  jz      loc_140025071
0x140024c23  xor     r14b, r14b
0x140024c26  cmp     cs:VmsHostNicIndicateNblsInline, 0
0x140024c2d  jnz     loc_140025341
0x140024c33  lea     rdx, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x140024c3a  test    r12d, r12d
0x140024c3d  jnz     loc_1400251C7
0x140024c43  lea     rsi, VmsMpNicSendComplete
0x140024c4a  test    r14b, r14b
0x140024c4d  jz      loc_140025185
0x140024c53  call    cs:__imp_KeGetCurrentIrql
0x140024c5a  nop     dword ptr [rax+rax+00h]
0x140024c5f  cmp     al, 2
0x140024c61  jnz     loc_140025A7F
0x140024c67  mov     r8b, 1; Flags
0x140024c6a  mov     rcx, [r13+38h]; Lock
0x140024c6e  lea     rdx, [rbp+110h+LockState]; LockState
0x140024c72  call    cs:__imp_NdisAcquireRWLockRead
0x140024c79  nop     dword ptr [rax+rax+00h]
0x140024c7e  xor     ecx, ecx; ProcNumber
0x140024c80  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140024c87  nop     dword ptr [rax+rax+00h]
0x140024c8c  xor     edi, edi
0x140024c8e  mov     qword ptr [rbp+110h+var_80+8], r13
0x140024c95  mov     dword ptr [rbp+110h+var_A0], eax
0x140024c98  lea     rcx, [rbp+110h+var_D0+8]
0x140024c9c  mov     eax, cs:VmsExecutionMode
0x140024ca2  mov     dword ptr [rbp+110h+var_60+4], eax
0x140024ca8  mov     eax, r15d
0x140024cab  and     eax, 0FFFFFFFEh
0x140024cae  mov     qword ptr [rbp+110h+var_C0], rcx
0x140024cb2  xor     cl, cl
0x140024cb4  mov     dword ptr [rbp+110h+var_A0+4], edi
0x140024cb7  mov     qword ptr [rbp+110h+var_D0+8], rdi
0x140024cbb  mov     qword ptr [rbp+110h+var_B0], rdi
0x140024cbf  mov     qword ptr [rbp+110h+var_C0+8], rdi
0x140024cc3  mov     [rbp+110h+Entry], rdi
0x140024cca  mov     qword ptr [rbp+110h+var_D0], rdi
0x140024cce  mov     byte ptr [rbp+110h+var_A0+0Dh], cl
0x140024cd1  mov     word ptr [rbp+110h+var_60], di
0x140024cd8  mov     dword ptr [rbp+110h+Entry+8], eax
0x140024cde  mov     qword ptr [rbp+110h+var_90+8], rsi
0x140024ce5  cmp     [r13+1342h], cl
0x140024cec  jz      loc_140025ACD
0x140024cf2  lea     rsi, [r13+1370h]
0x140024cf9  movzx   r15d, word ptr [rsi]
0x140024cfd  lea     rcx, [r13+136Ch]; ProcNumber
0x140024d04  call    cs:__imp_KeGetProcessorIndexFromNumber
0x140024d0b  nop     dword ptr [rax+rax+00h]
0x140024d10  movzx   ecx, byte ptr [rbp+110h+var_A0+0Dh]
0x140024d14  and     cl, 0FBh
0x140024d17  mov     qword ptr [rbp+110h+var_90], rsi
0x140024d1e  or      cl, 3
0x140024d21  mov     dword ptr [rbp+110h+Entry+0Ch], eax
0x140024d27  mov     byte ptr [rbp+110h+var_A0+0Dh], cl
0x140024d2a  lea     rcx, stru_1401FA0C0; Lookaside
0x140024d31  mov     qword ptr [rbp+110h+var_80], rdi
0x140024d38  mov     byte ptr [rbp+110h+var_60+2], r14b
0x140024d3f  mov     word ptr [rbp+110h+var_A0+8], r15w
0x140024d44  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140024d4b  nop     dword ptr [rax+rax+00h]
0x140024d50  mov     [rbp+110h+Entry], rax
0x140024d57  test    rax, rax
0x140024d5a  jz      loc_140025338
0x140024d60  xor     edx, edx; Val
0x140024d62  mov     r8d, 408h; Size
0x140024d68  mov     rcx, rax; void *
0x140024d6b  call    memset
0x140024d70  mov     eax, cs:VmsDiagnosticFlags
0x140024d76  lea     r14, aVmsmpnicpvtrss; "VmsMpNicPvtRssSortNbls"
0x140024d7d  movzx   r12d, byte ptr [r13+1342h]
0x140024d85  mov     rsi, rdi
0x140024d88  mov     rcx, [rsp+198h]
0x140024d90  test    al, 1
0x140024d92  jnz     loc_140025142
0x140024d98  test    rbx, rbx
0x140024d9b  jz      loc_140024F58
0x140024da1  lea     rdx, aVmsvrssprimevr; "VmsVrssPrimeVrssContextForNextNbl"
0x140024da8  mov     r13d, 0FFFFFFFFh
0x140024dae  mov     r11d, 0FFFFFFFEh
0x140024db4  mov     eax, cs:VmsDiagnosticFlags
0x140024dba  mov     r15, [rbx]
0x140024dbd  mov     rcx, [rsp+198h]
0x140024dc5  test    al, 1
0x140024dc7  jnz     loc_14002502E
0x140024dcd  mov     [rbx], rdi
0x140024dd0  test    r12b, r12b
0x140024dd3  jz      loc_14002522F
0x140024dd9  mov     eax, cs:VmsDiagnosticFlags
0x140024ddf  mov     rcx, [rsp+198h]
0x140024de7  test    al, 1
0x140024de9  jnz     loc_14002518D
0x140024def  movzx   r8d, byte ptr [rbp+110h+var_A0+0Dh]
0x140024df4  mov     r9d, 0FFFFFFFFh
0x140024dfa  test    r8b, 4
0x140024dfe  jz      loc_140025301
0x140024e04  mov     r10b, 1
0x140024e07  test    r8b, 1
0x140024e0b  jz      loc_1400251F4
0x140024e11  movzx   ecx, word ptr [rbp+110h+var_A0+8]
0x140024e15  movzx   r14d, r13w
0x140024e19  test    cx, cx
0x140024e1c  jz      short loc_140024E2F
0x140024e1e  mov     eax, [rbx+0D0h]
0x140024e24  test    eax, eax
0x140024e26  jz      short loc_140024E2F
0x140024e28  xor     edx, edx
0x140024e2a  div     ecx
0x140024e2c  mov     r14d, edx
0x140024e2f  cmp     r14w, r13w
0x140024e33  jnz     short loc_140024E3C
0x140024e35  mov     r9d, dword ptr [rbp+110h+Entry+0Ch]
0x140024e3c  mov     rax, [rbp+110h+Entry]
0x140024e43  movsx   rcx, r14w
0x140024e47  mov     rsi, [rax+rcx*8+8]
0x140024e4c  test    rsi, rsi
0x140024e4f  jnz     short loc_140024E92
0x140024e51  cmp     r9d, 0FFFFFFFFh
0x140024e55  jnz     short loc_140024E7E
0x140024e57  movzx   r9d, byte ptr [rbp+110h+var_60+2]
0x140024e5f  movzx   edx, r14w
0x140024e63  mov     r8, qword ptr [rbp+110h+var_80]
0x140024e6a  mov     rcx, qword ptr [rbp+110h+var_90]
0x140024e71  call    VmsMpNicPvtRssGetReceiveProc
0x140024e76  movzx   r8d, byte ptr [rbp+110h+var_A0+0Dh]
0x140024e7b  mov     r9d, eax
0x140024e7e  cmp     r9d, dword ptr [rbp+110h+var_A0]
0x140024e82  setnz   al
0x140024e85  test    r8b, 4
0x140024e89  jz      loc_1400252D4
0x140024e8f  mov     r10b, 1
0x140024e92  test    r10b, r10b
0x140024e95  jz      short loc_140024EF2
0x140024e97  test    rsi, rsi
0x140024e9a  jnz     loc_1400250EB
0x140024ea0  cmp     r9d, 0FFFFFFFFh
0x140024ea4  jz      loc_140025ADA
0x140024eaa  mov     r8d, dword ptr [rbp+110h+Entry+8]
0x140024eb1  lea     rax, [rbp+110h+var_D0]
0x140024eb5  movzx   edx, word ptr [rbp+110h+var_60]
0x140024ebc  mov     rcx, qword ptr [rbp+110h+var_80+8]
0x140024ec3  mov     [rsp+190h+var_168], rax
0x140024ec8  mov     rax, qword ptr [rbp+110h+var_90+8]
0x140024ecf  mov     [rsp+190h+Context], rax
0x140024ed4  call    VmsVrssPvtFindNblGroup
0x140024ed9  test    byte ptr [rbp+110h+var_A0+0Dh], 1
0x140024edd  mov     rsi, rax
0x140024ee0  jz      short loc_140024EF2
0x140024ee2  mov     rcx, [rbp+110h+Entry]
0x140024ee9  movsx   rdx, r14w
0x140024eed  mov     [rcx+rdx*8+8], rax
0x140024ef2  test    rsi, rsi
0x140024ef5  jnz     loc_1400250EB
0x140024efb  lea     rcx, [rbp+110h+var_C0]
0x140024eff  lea     rax, [rbp+110h+var_A0+4]
0x140024f03  lea     r14, aVmsmpnicpvtrss; "VmsMpNicPvtRssSortNbls"
0x140024f0a  mov     qword ptr [rbp+110h+var_C0+8], rcx
0x140024f0e  mov     qword ptr [rbp+110h+var_B0], rax
0x140024f12  mov     rax, [rcx]
0x140024f15  mov     rcx, [rsp+198h]
0x140024f1d  mov     [rax], rbx
0x140024f20  mov     eax, cs:VmsDiagnosticFlags
0x140024f26  test    al, 1
0x140024f28  jnz     loc_1400250A5
0x140024f2e  mov     rax, qword ptr [rbp+110h+var_C0+8]
0x140024f32  lea     rdx, aVmsvrssprimevr; "VmsVrssPrimeVrssContextForNextNbl"
0x140024f39  mov     r11d, 0FFFFFFFEh
0x140024f3f  mov     [rax], rbx
0x140024f42  mov     rbx, r15
0x140024f45  mov     rax, qword ptr [rbp+110h+var_B0]
0x140024f49  inc     dword ptr [rax]
0x140024f4b  test    r15, r15
0x140024f4e  jnz     loc_140024DB4
0x140024f54  mov     r13, [rbp+110h+var_100]
0x140024f58  mov     rax, qword ptr [rbp+110h+var_D0]
0x140024f5c  test    rax, rax
0x140024f5f  jz      short loc_140024FCA
0x140024f61  lea     rsi, WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids
0x140024f68  mov     rcx, [rax]
0x140024f6b  movzx   edx, byte ptr [rbp+110h+var_A0+0Dh]
0x140024f6f  mov     qword ptr [rbp+110h+var_D0], rcx
0x140024f73  movzx   ecx, byte ptr [rax+3Ah]
0x140024f77  shr     dl, 2
0x140024f7a  xor     dl, cl
0x140024f7c  and     dl, 2
0x140024f7f  xor     dl, cl
0x140024f81  mov     [rax+3Ah], dl
0x140024f84  movzx   ecx, byte ptr [rbp+110h+var_A0+0Dh]
0x140024f88  shr     cl, 2
0x140024f8b  xor     cl, dl
0x140024f8d  and     cl, 4
0x140024f90  xor     cl, dl
0x140024f92  mov     [rax+3Ah], cl
0x140024f95  test    byte ptr [rbp+110h+var_A0+0Dh], 4
0x140024f99  jnz     loc_140025AE3
0x140024f9f  movzx   r8d, byte ptr [rbp+110h+var_60+2]
0x140024fa7  mov     rcx, rax
0x140024faa  mov     edx, dword ptr [rbp+110h+var_60+4]
0x140024fb0  mov     rbx, [rax+10h]
0x140024fb4  call    VmsVrssPvtPushNblGroupToQueue
0x140024fb9  test    eax, eax
0x140024fbb  jnz     loc_140025079
0x140024fc1  mov     rax, qword ptr [rbp+110h+var_D0]
0x140024fc5  test    rax, rax
0x140024fc8  jnz     short loc_140024F68
0x140024fca  mov     rcx, [r13+38h]; Lock
0x140024fce  lea     rdx, [rbp+110h+LockState]; LockState
0x140024fd2  call    cs:__imp_NdisReleaseRWLock
0x140024fd9  nop     dword ptr [rax+rax+00h]
0x140024fde  mov     rbx, qword ptr [rbp+110h+var_D0+8]
0x140024fe2  test    rbx, rbx
0x140024fe5  jnz     loc_140025525
0x140024feb  mov     rdx, [rbp+110h+Entry]; Entry
0x140024ff2  test    rdx, rdx
0x140024ff5  jz      short loc_14002500A
0x140024ff7  lea     rcx, stru_1401FA0C0; Lookaside
0x140024ffe  call    cs:__imp_ExFreeToNPagedLookasideList
0x140025005  nop     dword ptr [rax+rax+00h]
0x14002500a  mov     rcx, [rbp+110h+var_50]
0x140025011  xor     rcx, rsp; StackCookie
0x140025014  call    __security_check_cookie
0x140025019  add     rsp, 158h
0x140025020  pop     r15
0x140025022  pop     r14
0x140025024  pop     r13
0x140025026  pop     r12
0x140025028  pop     rdi
0x140025029  pop     rsi
0x14002502a  pop     rbx
0x14002502b  pop     rbp
0x14002502c  retn
0x14002502e  test    r15, r15
0x140025031  jz      loc_140024DCD
0x140025037  mov     rax, [r15+120h]
0x14002503e  test    rax, rax
0x140025041  jz      loc_140024DCD
0x140025047  mov     rax, [rax+10h]
0x14002504b  test    rax, rax
0x14002504e  jz      loc_140024DCD
0x140025054  mov     [rax+0B0h], r14
0x14002505b  mov     dword ptr [rax+0B8h], 128h
0x140025065  mov     [rax+0A8h], rcx
0x14002506c  jmp     loc_140024DCD
0x140025071  mov     r14b, 1
0x140025074  jmp     loc_140024C26
0x140025079  mov     edx, eax
0x14002507b  sub     edx, 1
0x14002507e  jnz     loc_140025B07
0x140025084  lock inc qword ptr [rbx+1D0h]
0x14002508c  mov     rcx, rbx; Dpc
0x14002508f  xor     r8d, r8d; SystemArgument2
0x140025092  xor     edx, edx; SystemArgument1
0x140025094  call    cs:__imp_KeInsertQueueDpc
0x14002509b  nop     dword ptr [rax+rax+00h]
0x1400250a0  jmp     loc_140024FC1
  ... truncated ...
```
