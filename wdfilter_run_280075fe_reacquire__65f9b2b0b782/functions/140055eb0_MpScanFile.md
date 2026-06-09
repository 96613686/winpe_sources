# MpScanFile

- ea: `0x140055eb0`
- end: `0x140056b42`
- name: `MpScanFile`
- size: `3218`
- prototype: ``
- caller_count: `3`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002d520`
- `0x140030380`
- `0x140051af0`

## callees

- `0x1400018a4`
- `0x140002450`
- `0x1400026c0`
- `0x1400028b4`
- `0x1400034e0`
- `0x140003950`
- `0x140003af0`
- `0x140003b50`
- `0x140003d20`
- `0x140003d80`
- `0x140004558`
- `0x140005944`
- `0x140009bf0`
- `0x14000c6b4`
- `0x1400118d0`
- `0x140011900`
- `0x140011bc0`
- `0x140047950`
- `0x140055d50`
- `0x140055eb0`
- `0x140056b50`
- `0x140056c20`
- `0x140056dc0`
- `0x140067ac0`
- `0x140067ad0`
- `0x140068d64`
- `0x14006c9bc`
- `0x14006f480`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400562dd`
- `ntoskrnl!ObfReferenceObject` at `0x1400562dd`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400561d4`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400561d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140055f57`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140055f57`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140055f1d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140055f1d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400561ec`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400561ec`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056738`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056738`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005638e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056ac3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005638e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056ac3`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14005669a`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14005669a`
- `ntoskrnl!KeBugCheck` at `0x140056765`
- `ntoskrnl!KeBugCheck` at `0x140056765`
- `ntoskrnl!ObfDereferenceObject` at `0x140056314`
- `ntoskrnl!ObfDereferenceObject` at `0x140056314`
- `FLTMGR!FltGetFileNameInformation` at `0x140055fd2`
- `FLTMGR!FltGetFileNameInformation` at `0x140055fd2`
- `FLTMGR!FltReferenceContext` at `0x1400563fc`
- `FLTMGR!FltReferenceContext` at `0x140056b31`
- `FLTMGR!FltReferenceContext` at `0x1400563fc`
- `FLTMGR!FltReferenceContext` at `0x140056b31`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400562bc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400562bc`

## pseudocode

```c
__int64 __fastcall MpScanFile(
        _QWORD *a1,
        struct _FLT_CALLBACK_DATA *a2,
        __int64 a3,
        int a4,
        int a5,
        const void **a6,
        __int64 a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  unsigned int v12; // esi
  const void **v13; // rdi
  char v14; // r14
  _DWORD *v19; // rbx
  NTSTATUS FileName; // eax
  NTSTATUS v21; // eax
  _DWORD *PoolWithTag; // rax
  int v23; // eax
  bool v24; // zf
  int v25; // edx
  __int64 v26; // xmm0_8
  struct _KPROCESS *RequestorProcess; // rax
  LONGLONG TimeQuadPart; // rax
  HANDLE CurrentThreadId; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rax
  size_t v34; // rcx
  ULONG v35; // r12d
  int v36; // edi
  _QWORD *v37; // rax
  _QWORD *v38; // rbx
  __int64 v39; // r8
  __int64 v40; // rcx
  __int64 v41; // r10
  int v42; // r9d
  __int64 v43; // rdx
  int v44; // eax
  int v45; // ecx
  int v46; // ecx
  int v47; // eax
  int v48; // eax
  _BYTE *v49; // rax
  const void *v50; // rdx
  __int64 v51; // rax
  int v52; // eax
  int v53; // eax
  NTSTATUS v54; // eax
  int v55; // eax
  struct _KTHREAD *Thread; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  int v58; // ecx
  __int64 v59; // rcx
  __int128 v60; // xmm0
  __int64 v61; // rax
  int v62; // eax
  _WORD *v63; // rax
  unsigned __int16 *v64; // rax
  const void *v65; // r9
  unsigned int v66; // eax
  size_t v67; // r8
  char v68; // [rsp+30h] [rbp-69h]
  NTSTATUS v69; // [rsp+40h] [rbp-59h]
  PVOID Entry; // [rsp+50h] [rbp-49h] BYREF
  PVOID P; // [rsp+58h] [rbp-41h]
  __int64 v73; // [rsp+60h] [rbp-39h]
  void *Src[2]; // [rsp+68h] [rbp-31h]
  const void **v75; // [rsp+78h] [rbp-21h]
  ULONG pulResult; // [rsp+80h] [rbp-19h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+88h] [rbp-11h] BYREF
  char v78; // [rsp+90h] [rbp-9h]

  v12 = 0;
  v13 = a6;
  v14 = 0;
  v73 = a11;
  v75 = a6;
  Entry = 0;
  if ( *(_DWORD *)(MpData + 4176) )
  {
    KeEnterCriticalRegion();
    v14 = 1;
  }
  if ( !*(_DWORD *)(MpData + 440) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids, a10 + 240);
    goto LABEL_5;
  }
  if ( (*(_DWORD *)(a7 + 32) & 0x400200) == 0x200 )
  {
    v58 = *(_DWORD *)(*(_QWORD *)(a10 + 8) + 120LL);
    if ( v58 == 2 || v58 == 28 )
    {
      if ( (unsigned __int8)MpIsEmptySparseFile(a3) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_Zd(
            WPP_GLOBAL_Control->AttachedDevice,
            29,
            (unsigned int)WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
            *(_QWORD *)(a3 + 32) + 88,
            *(_DWORD *)(a7 + 32));
        MpSetStreamState_0(a1, *(unsigned __int16 *)(a3 + 2), a10, 3);
        v12 = 3;
        goto LABEL_5;
      }
    }
  }
  FileNameInformation = 0;
  v19 = 0;
  v78 = 0;
  v68 = 0;
  P = 0;
  *(_OWORD *)Src = 0;
  if ( a4 == 4 && (*(_DWORD *)(MpData + 868) & 1) != 0 )
    FileName = MpQueryFileName(a2);
  else
    FileName = FltGetFileNameInformation(a2, 0x102u, &FileNameInformation);
  if ( FileName < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
        (unsigned int)FileName);
    }
  }
  else
  {
    *(UNICODE_STRING *)Src = FileNameInformation->Name;
  }
  pulResult = 820;
  v21 = RtlULongAdd(0x334u, LOWORD(Src[0]) + 2, &pulResult);
  v69 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    {
      v36 = v21;
    }
    else
    {
      _mm_lfence();
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
        (unsigned int)v21);
      v36 = v69;
    }
    v35 = 0;
    goto LABEL_33;
  }
  if ( a6 )
  {
    v53 = *(unsigned __int16 *)a6;
    if ( (_WORD)v53 )
    {
      v54 = RtlULongAdd(pulResult, v53 + 2, &pulResult);
      if ( v54 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
            (unsigned int)v54);
        }
      }
      else
      {
        v68 = 1;
      }
    }
  }
  PoolWithTag = (_DWORD *)MpAllocatePoolWithTag(1, pulResult, 1936085069);
  v19 = PoolWithTag;
  if ( !PoolWithTag )
  {
    v36 = -1073741670;
    v35 = 0;
    goto LABEL_33;
  }
  *PoolWithTag = 65957;
  PoolWithTag[1] = pulResult;
  PoolWithTag[6] = a4;
  if ( ((a4 - 3) & 0xFFFFFFFD) == 0 )
  {
    if ( a12 && (v49 = *(_BYTE **)(a12 + 104)) != 0 && *v49 )
    {
      v59 = *(_QWORD *)(a12 + 104);
      *((_OWORD *)v19 + 33) = *(_OWORD *)v59;
      *((_OWORD *)v19 + 34) = *(_OWORD *)(v59 + 16);
      *((_OWORD *)v19 + 35) = *(_OWORD *)(v59 + 32);
      *((_OWORD *)v19 + 36) = *(_OWORD *)(v59 + 48);
      *((_OWORD *)v19 + 37) = *(_OWORD *)(v59 + 64);
      *((_OWORD *)v19 + 38) = *(_OWORD *)(v59 + 80);
      *((_OWORD *)v19 + 39) = *(_OWORD *)(v59 + 96);
      v60 = *(_OWORD *)(v59 + 112);
      v59 += 128;
      *((_OWORD *)v19 + 40) = v60;
      *((_OWORD *)v19 + 41) = *(_OWORD *)v59;
      *((_OWORD *)v19 + 42) = *(_OWORD *)(v59 + 16);
      *((_OWORD *)v19 + 43) = *(_OWORD *)(v59 + 32);
      *((_OWORD *)v19 + 44) = *(_OWORD *)(v59 + 48);
      *((_OWORD *)v19 + 45) = *(_OWORD *)(v59 + 64);
      *((_QWORD *)v19 + 92) = *(_QWORD *)(v59 + 80);
      v19[186] = *(_DWORD *)(v59 + 88);
    }
    else
    {
      *((_BYTE *)v19 + 528) = 0;
    }
  }
  v23 = v19[6];
  if ( v23 == 3 )
  {
    v19[104] = *(_DWORD *)(a2->Iopb->Parameters.WMI.ProviderId + 16);
    v19[105] = a2->Iopb->Parameters.Create.ShareAccess;
    v19[106] = a2->Iopb->Parameters.Create.Options;
LABEL_19:
    *((_QWORD *)v19 + 46) = a10;
    MpGetPriorityInfo(a2, *(_QWORD *)(a3 + 32), v19 + 2);
    if ( (*(_DWORD *)(MpData + 868) & 0x10000) != 0 )
    {
      Thread = a2->Thread;
      CurrentProcess = IoGetCurrentProcess();
      MpQuerySessionIdFromObjects(Thread, CurrentProcess, v73, v19 + 18);
      v13 = v75;
    }
    else
    {
      MpQuerySessionId(-2, -1, v19 + 18);
    }
    v24 = v19[6] == 4;
    v25 = a10;
    *((_QWORD *)v19 + 48) = *(_QWORD *)(a10 + 168);
    v19[101] = *(_DWORD *)(*(_QWORD *)(a10 + 8) + 84LL);
    v19[102] = *(_DWORD *)(*(_QWORD *)(a10 + 8) + 96LL);
    *((_OWORD *)v19 + 30) = *(_OWORD *)a7;
    *((_OWORD *)v19 + 31) = *(_OWORD *)(a7 + 16);
    v26 = *(_QWORD *)(a7 + 32);
    v19[7] = a5;
    *((_QWORD *)v19 + 64) = v26;
    v19[100] = a2->RequestorMode;
    v19[108] = a8;
    if ( v24 )
    {
      v19[103] = _InterlockedExchange((volatile __int32 *)(a10 + 52), -1);
      v55 = MpGetFileWriteHistoryAndReset(a1, *(unsigned __int16 *)(a3 + 2), a10, v19 + 132);
      if ( v55 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
          (unsigned int)v55);
      }
      v25 = a10;
    }
    else
    {
      *(_OWORD *)(v19 + 110) = *(_OWORD *)a9;
      *(_OWORD *)(v19 + 114) = *(_OWORD *)(a9 + 16);
      *((_QWORD *)v19 + 59) = *(_QWORD *)(a9 + 32);
      v19[103] = -1;
    }
    MpGetStreamSize((_DWORD)a1, *(unsigned __int16 *)(a3 + 2), v25, *(_QWORD *)(a3 + 32), (__int64)(v19 + 8));
    *((_QWORD *)v19 + 5) = (unsigned int)MpGetRequestorProcessId(a2);
    RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(a2);
    TimeQuadPart = PsGetProcessCreateTimeQuadPart(RequestorProcess);
    *((_QWORD *)v19 + 7) = MpFileTimeToUlong64(TimeQuadPart);
    CurrentThreadId = PsGetCurrentThreadId();
    v30 = v73;
    *((_QWORD *)v19 + 8) = CurrentThreadId;
    if ( v30 )
    {
      v19[12] = *(_DWORD *)(v30 + 56);
      v19[13] = *(_DWORD *)(v30 + 60);
    }
    v31 = a10;
    v32 = *(_QWORD *)(a10 + 8);
    if ( *(_QWORD *)(v32 + 48) )
    {
      *((_WORD *)v19 + 44) = *(_WORD *)(v32 + 40);
      v33 = *(_QWORD *)(*(_QWORD *)(a10 + 8) + 48LL);
      *(_OWORD *)((char *)v19 + 90) = *(_OWORD *)v33;
      *(_OWORD *)((char *)v19 + 106) = *(_OWORD *)(v33 + 16);
      *(_OWORD *)((char *)v19 + 122) = *(_OWORD *)(v33 + 32);
      *(_OWORD *)((char *)v19 + 138) = *(_OWORD *)(v33 + 48);
      *(_OWORD *)((char *)v19 + 154) = *(_OWORD *)(v33 + 64);
      *(_OWORD *)((char *)v19 + 170) = *(_OWORD *)(v33 + 80);
      *((_WORD *)v19 + 93) = *(_WORD *)(v33 + 96);
    }
    if ( a1 )
    {
      v63 = (_WORD *)a1[19];
      if ( v63 )
      {
        *((_WORD *)v19 + 144) = *v63;
        v64 = (unsigned __int16 *)a1[19];
        v65 = (const void *)*((_QWORD *)v64 + 1);
        if ( v65 )
        {
          v66 = *v64;
          if ( (_WORD)v66 )
          {
            v67 = v66;
            if ( v66 >= 0x4C )
              v67 = 76;
            memmove((char *)v19 + 290, v65, v67);
            v31 = a10;
          }
        }
      }
      *((_WORD *)v19 + 143) = *(_WORD *)(a3 + 2);
    }
    if ( ((a4 - 3) & 0xFFFFFFFD) == 0
      && (*(_DWORD *)(*(_QWORD *)(a3 + 32) + 80LL) & 0x100008) == 0
      && (*(_DWORD *)(*(_QWORD *)(v31 + 8) + 84LL) & 0x10) == 0 )
    {
      if ( a2->Thread )
      {
        if ( (unsigned int)MpSeqDetectCtxCheck(&MpSeqDetectCtx) )
        {
          v19[7] |= 8u;
          if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 4) != 0 )
            McTemplateK0_EtwWriteTransfer(&Microsoft_Antimalware_AMFilter_Context, AMFilter_SeqReadFlagEvent, 0);
        }
      }
    }
    v34 = LOWORD(Src[0]);
    if ( LOWORD(Src[0]) )
    {
      if ( v78 )
        v19[7] |= 0x10u;
      v50 = Src[1];
      *((_WORD *)v19 + 261) = v34;
      memmove(v19 + 205, v50, v34);
      LOWORD(v34) = Src[0];
    }
    if ( v68 )
    {
      *((_WORD *)v19 + 260) = *(_WORD *)v13;
      memmove((char *)v19 + (unsigned __int16)v34 + 822, v13[1], *(unsigned __int16 *)v13);
      v19[7] |= 0x10000u;
    }
    v35 = pulResult;
    v36 = 0;
    P = v19;
    v19 = 0;
    goto LABEL_33;
  }
  if ( v23 != 5 )
    goto LABEL_19;
  if ( a12 )
  {
    v19[104] = *(_DWORD *)(a12 + 88);
    v51 = *(_QWORD *)(a12 + 96);
    if ( v51 )
      v52 = *(_DWORD *)(v51 + 8);
    else
      v52 = 0;
    v19[105] = v52;
    v61 = *(_QWORD *)(a12 + 96);
    if ( v61 )
      v62 = *(_DWORD *)(v61 + 12);
    else
      v62 = 0;
    v19[106] = v62;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids, a2->Thread);
  v36 = -1073741811;
  v35 = 0;
LABEL_33:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v19 )
    ExFreePoolWithTag(v19, 0x7366504Du);
  if ( v36 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        30,
        WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids,
        (unsigned int)v36);
    }
    MpSetStreamState_0(a1, *(unsigned __int16 *)(a3 + 2), a10, 0);
    goto LABEL_43;
  }
  ObfReferenceObject(*(PVOID *)(a3 + 32));
  _InterlockedIncrement64(&ObTotalReferences);
  v37 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 2240));
  v38 = v37;
  if ( !v37 )
  {
    ObfDereferenceObject(*(PVOID *)(a3 + 32));
    if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
    {
      if ( KdRefreshDebuggerNotPresent() )
        KeBugCheck(1u);
      __debugbreak();
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids, 3221225626LL);
    }
LABEL_43:
    if ( P )
      ExFreePoolWithTag(P, 0x7366504Du);
    goto LABEL_58;
  }
  memset(v37, 0, 0x78u);
  v38[6] = P;
  *(_DWORD *)v38 = 7920161;
  *((_DWORD *)v38 + 14) = v35;
  v38[8] = a10;
  FltReferenceContext((PFLT_CONTEXT)a10);
  if ( a1 )
  {
    v38[9] = a1;
    FltReferenceContext(a1);
  }
  if ( v73 )
  {
    v38[10] = v73;
    MpReferenceProcessContext();
  }
  v38[11] = *(_QWORD *)(a3 + 32);
  if ( a2 )
  {
    v38[13] = a2;
    v38[14] = a3;
  }
  v39 = v38[6];
  v40 = v38[8];
  v41 = v38[10];
  v42 = *(_DWORD *)(MpData + 868) & 0x2000;
  Entry = v38;
  if ( !v38[9] )
  {
    v43 = *(_QWORD *)(v40 + 8);
    v44 = *(_DWORD *)(v43 + 120);
    if ( (v44 == 2 || !v42 && v44 == 28) && (*(_DWORD *)(v40 + 48) & 2) == 0 )
    {
      v45 = *(_DWORD *)(v39 + 24);
      if ( v45 == 5 || (v46 = v45 - 3) == 0 )
      {
        if ( !v42 )
        {
          v47 = *(_DWORD *)(v43 + 80);
          if ( (v47 & 0x50) != 0
            && (v47 & 8) != 0
            && (*(_DWORD *)(v39 + 28) & 0x20) == 0
            && v41
            && (*(_DWORD *)(v41 + 60) & 0x100) != 0 )
          {
            goto LABEL_66;
          }
        }
      }
      else if ( v46 == 1
             && (*(_DWORD *)(MpData + 868) & 0x100) == 0
             && (*(int *)(MpData + 868) < 0 || dword_140026A1C == 2 || v41 && (*(_DWORD *)(v41 + 60) & 1) != 0) )
      {
LABEL_66:
        v48 = MpAsyncScanEnqueue(Entry);
        if ( !v48 )
          goto LABEL_5;
        if ( v48 == -1073741058 )
          goto LABEL_58;
        *(_BYTE *)(*((_QWORD *)Entry + 6) + 819LL) = 1;
      }
    }
  }
  v12 = MpDoScanFile((__int64)Entry);
LABEL_58:
  if ( Entry )
    MpCleanupScanRequestContext(&Entry);
LABEL_5:
  if ( v14 )
    KeLeaveCriticalRegion();
  return v12;
}

```

## disassembly

```asm
0x140055eb0  mov     [rsp-8+arg_18], rbx
0x140055eb5  push    rbp
0x140055eb6  push    rsi
0x140055eb7  push    rdi
0x140055eb8  push    r12
0x140055eba  push    r13
0x140055ebc  push    r14
0x140055ebe  push    r15
0x140055ec0  lea     rbp, [rsp-7]
0x140055ec5  sub     rsp, 0A0h
0x140055ecc  mov     rax, cs:__security_cookie
0x140055ed3  xor     rax, rsp
0x140055ed6  mov     [rbp+37h+var_38], rax
0x140055eda  mov     rax, [rbp+37h+arg_50]
0x140055ee1  xor     esi, esi
0x140055ee3  mov     rdi, [rbp+37h+arg_28]
0x140055ee7  xor     r14b, r14b
0x140055eea  mov     rbx, [rbp+37h+arg_48]
0x140055ef1  mov     r12d, r9d
0x140055ef4  mov     [rbp+37h+var_70], rax
0x140055ef8  mov     r13, r8
0x140055efb  mov     rax, cs:MpData
0x140055f02  mov     r15, rdx
0x140055f05  mov     [rbp+37h+var_88], rcx
0x140055f09  mov     [rbp+37h+var_58], rdi
0x140055f0d  mov     [rbp+37h+Context], rbx
0x140055f11  mov     [rbp+37h+Entry], rsi
0x140055f15  cmp     [rax+1050h], esi
0x140055f1b  jz      short loc_140055F2C
0x140055f1d  call    cs:__imp_KeEnterCriticalRegion
0x140055f24  nop     dword ptr [rax+rax+00h]
0x140055f29  mov     r14b, 1
0x140055f2c  mov     rax, cs:MpData
0x140055f33  cmp     [rax+1B8h], esi
0x140055f39  jnz     short loc_140055F8D
0x140055f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140055f42  lea     rax, WPP_GLOBAL_Control
0x140055f49  cmp     rcx, rax
0x140055f4c  jnz     loc_1400567F5
0x140055f52  test    r14b, r14b
0x140055f55  jz      short loc_140055F63
0x140055f57  call    cs:__imp_KeLeaveCriticalRegion
0x140055f5e  nop     dword ptr [rax+rax+00h]
0x140055f63  mov     eax, esi
0x140055f65  mov     rcx, [rbp+37h+var_38]
0x140055f69  xor     rcx, rsp; StackCookie
0x140055f6c  call    __security_check_cookie
0x140055f71  mov     rbx, [rsp+0D0h+arg_18]
0x140055f79  add     rsp, 0A0h
0x140055f80  pop     r15
0x140055f82  pop     r14
0x140055f84  pop     r13
0x140055f86  pop     r12
0x140055f88  pop     rdi
0x140055f89  pop     rsi
0x140055f8a  pop     rbp
0x140055f8b  retn
0x140055f8d  mov     rax, [rbp+37h+arg_30]
0x140055f91  mov     eax, [rax+20h]
0x140055f94  and     eax, 400200h
0x140055f99  cmp     eax, 200h
0x140055f9e  jz      loc_140056772
0x140055fa4  mov     [rbp+37h+FileNameInformation], rsi
0x140055fa8  mov     rbx, rsi
0x140055fab  mov     [rbp+37h+var_40], bl
0x140055fae  xorps   xmm0, xmm0
0x140055fb1  mov     [rbp+37h+var_A0], bl
0x140055fb4  mov     [rbp+37h+P], rsi
0x140055fb8  movups  xmmword ptr [rbp+37h+Src], xmm0
0x140055fbc  cmp     r12d, 4
0x140055fc0  jz      loc_14005664F
0x140055fc6  lea     r8, [rbp+37h+FileNameInformation]; FileNameInformation
0x140055fca  mov     edx, 102h; NameOptions
0x140055fcf  mov     rcx, r15; CallbackData
0x140055fd2  call    cs:__imp_FltGetFileNameInformation
0x140055fd9  nop     dword ptr [rax+rax+00h]
0x140055fde  mov     r9d, eax
0x140055fe1  lea     rax, WPP_GLOBAL_Control
0x140055fe8  test    r9d, r9d
0x140055feb  js      loc_14005682F
0x140055ff1  mov     rax, [rbp+37h+FileNameInformation]
0x140055ff5  movups  xmm0, xmmword ptr [rax+8]
0x140055ff9  movups  xmmword ptr [rbp+37h+Src], xmm0
0x140055ffd  movzx   edx, word ptr [rbp+37h+Src]
0x140056001  lea     r8, [rbp+37h+pulResult]; pulResult
0x140056005  add     edx, 2; ulAddend
0x140056008  mov     [rbp+37h+pulResult], 334h
0x14005600f  mov     ecx, 334h; ulAugend
0x140056014  call    RtlULongAdd
0x140056019  mov     [rbp+37h+var_90], eax
0x14005601c  test    eax, eax
0x14005601e  js      loc_14005686E
0x140056024  test    rdi, rdi
0x140056027  jnz     loc_1400566B4
0x14005602d  mov     edx, [rbp+37h+pulResult]
0x140056030  mov     ecx, 1
0x140056035  mov     r8d, 7366504Dh
0x14005603b  call    MpAllocatePoolWithTag
0x140056040  mov     rbx, rax
0x140056043  test    rax, rax
0x140056046  jz      loc_140056901
0x14005604c  mov     r8, [rbp+37h+arg_58]
0x140056053  mov     dword ptr [rax], 101A5h
0x140056059  mov     eax, [rbp+37h+pulResult]
0x14005605c  mov     [rbx+4], eax
0x14005605f  lea     eax, [r12-3]
0x140056064  mov     [rbx+18h], r12d
0x140056068  test    eax, 0FFFFFFFDh
0x14005606d  jz      loc_140056509
0x140056073  mov     eax, [rbx+18h]
0x140056076  cmp     eax, 3
0x140056079  jnz     loc_1400565A7
0x14005607f  mov     rax, [r15+10h]
0x140056083  mov     rcx, [rax+18h]
0x140056087  mov     eax, [rcx+10h]
0x14005608a  mov     [rbx+1A0h], eax
0x140056090  mov     rax, [r15+10h]
0x140056094  movzx   ecx, word ptr [rax+2Ah]
0x140056098  mov     [rbx+1A4h], ecx
0x14005609e  mov     rax, [r15+10h]
0x1400560a2  mov     ecx, [rax+20h]
0x1400560a5  mov     [rbx+1A8h], ecx
0x1400560ab  mov     rax, [rbp+37h+Context]
0x1400560af  lea     r8, [rbx+8]
0x1400560b3  mov     [rbx+170h], rax
0x1400560ba  mov     rcx, r15
0x1400560bd  mov     rdx, [r13+20h]
0x1400560c1  call    MpGetPriorityInfo
0x1400560c6  mov     rax, cs:MpData
0x1400560cd  mov     ecx, [rax+364h]
0x1400560d3  bt      ecx, 10h
0x1400560d7  jb      loc_140056734
0x1400560dd  lea     r8, [rbx+48h]
0x1400560e1  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1400560e8  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x1400560ef  call    MpQuerySessionId
0x1400560f4  cmp     dword ptr [rbx+18h], 4
0x1400560f8  mov     rdx, [rbp+37h+Context]
0x1400560fc  mov     rax, [rdx+0A8h]
0x140056103  mov     [rbx+180h], rax
0x14005610a  mov     rax, [rdx+8]
0x14005610e  mov     ecx, [rax+54h]
0x140056111  mov     [rbx+194h], ecx
0x140056117  mov     rax, [rdx+8]
0x14005611b  mov     ecx, [rax+60h]
0x14005611e  mov     rax, [rbp+37h+arg_30]
0x140056122  mov     [rbx+198h], ecx
0x140056128  movups  xmm0, xmmword ptr [rax]
0x14005612b  movups  xmmword ptr [rbx+1E0h], xmm0
0x140056132  movups  xmm1, xmmword ptr [rax+10h]
0x140056136  movups  xmmword ptr [rbx+1F0h], xmm1
0x14005613d  movsd   xmm0, qword ptr [rax+20h]
0x140056142  mov     eax, [rbp+37h+arg_20]
0x140056145  mov     [rbx+1Ch], eax
0x140056148  movsd   qword ptr [rbx+200h], xmm0
0x140056150  movsx   eax, byte ptr [r15+50h]
0x140056155  mov     [rbx+190h], eax
0x14005615b  mov     eax, [rbp+37h+arg_38]
0x14005615e  mov     [rbx+1B0h], eax
0x140056164  jz      loc_1400566E3
0x14005616a  mov     rax, [rbp+37h+arg_40]
0x140056171  movups  xmm0, xmmword ptr [rax]
0x140056174  movups  xmmword ptr [rbx+1B8h], xmm0
0x14005617b  movups  xmm1, xmmword ptr [rax+10h]
0x14005617f  movups  xmmword ptr [rbx+1C8h], xmm1
0x140056186  movsd   xmm0, qword ptr [rax+20h]
0x14005618b  movsd   qword ptr [rbx+1D8h], xmm0
0x140056193  mov     dword ptr [rbx+19Ch], 0FFFFFFFFh
0x14005619d  mov     r9, [r13+20h]
0x1400561a1  lea     rax, [rbx+20h]
0x1400561a5  mov     rcx, [rbp+37h+var_88]
0x1400561a9  mov     r8, rdx
0x1400561ac  movzx   edx, word ptr [r13+2]
0x1400561b1  mov     [rsp+0D0h+var_B0], rax
0x1400561b6  call    MpGetStreamSize
0x1400561bb  mov     rcx, r15
0x1400561be  call    MpGetRequestorProcessId
0x1400561c3  mov     eax, eax
0x1400561c5  mov     rcx, r15
0x1400561c8  mov     [rbx+28h], rax
0x1400561cc  call    MpGetRequestorProcess
0x1400561d1  mov     rcx, rax; Process
0x1400561d4  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x1400561db  nop     dword ptr [rax+rax+00h]
0x1400561e0  mov     rcx, rax
0x1400561e3  call    MpFileTimeToUlong64
0x1400561e8  mov     [rbx+38h], rax
0x1400561ec  call    cs:__imp_PsGetCurrentThreadId
0x1400561f3  nop     dword ptr [rax+rax+00h]
0x1400561f8  mov     rcx, [rbp+37h+var_70]
0x1400561fc  mov     [rbx+40h], rax
0x140056200  test    rcx, rcx
0x140056203  jz      short loc_140056211
0x140056205  mov     eax, [rcx+38h]
0x140056208  mov     [rbx+30h], eax
0x14005620b  mov     eax, [rcx+3Ch]
0x14005620e  mov     [rbx+34h], eax
0x140056211  mov     rdx, [rbp+37h+Context]
0x140056215  mov     rax, [rdx+8]
0x140056219  cmp     [rax+30h], rsi
0x14005621d  jz      short loc_140056272
0x14005621f  movzx   eax, word ptr [rax+28h]
0x140056223  mov     [rbx+58h], ax
0x140056227  mov     rax, [rdx+8]
0x14005622b  mov     rax, [rax+30h]
0x14005622f  movups  xmm0, xmmword ptr [rax]
0x140056232  movups  xmmword ptr [rbx+5Ah], xmm0
0x140056236  movups  xmm1, xmmword ptr [rax+10h]
0x14005623a  movups  xmmword ptr [rbx+6Ah], xmm1
0x14005623e  movups  xmm0, xmmword ptr [rax+20h]
0x140056242  movups  xmmword ptr [rbx+7Ah], xmm0
0x140056246  movups  xmm1, xmmword ptr [rax+30h]
0x14005624a  movups  xmmword ptr [rbx+8Ah], xmm1
0x140056251  movups  xmm0, xmmword ptr [rax+40h]
0x140056255  movups  xmmword ptr [rbx+9Ah], xmm0
0x14005625c  movups  xmm1, xmmword ptr [rax+50h]
0x140056260  movups  xmmword ptr [rbx+0AAh], xmm1
0x140056267  movzx   eax, word ptr [rax+60h]
0x14005626b  mov     [rbx+0BAh], ax
0x140056272  mov     rcx, [rbp+37h+var_88]
0x140056276  test    rcx, rcx
0x140056279  jnz     loc_140056A51
0x14005627f  lea     eax, [r12-3]
0x140056284  test    eax, 0FFFFFFFDh
0x140056289  jz      loc_1400565E1
0x14005628f  movzx   ecx, word ptr [rbp+37h+Src]
0x140056293  test    cx, cx
0x140056296  jnz     loc_140056527
0x14005629c  cmp     [rbp+37h+var_A0], sil
0x1400562a0  jnz     loc_14005639F
0x1400562a6  mov     r12d, [rbp+37h+pulResult]
0x1400562aa  mov     edi, esi
0x1400562ac  mov     [rbp+37h+P], rbx
0x1400562b0  mov     rbx, rsi
0x1400562b3  mov     rcx, [rbp+37h+FileNameInformation]; FileNameInformation
0x1400562b7  test    rcx, rcx
0x1400562ba  jz      short loc_1400562C8
0x1400562bc  call    cs:__imp_FltReleaseFileNameInformation
0x1400562c3  nop     dword ptr [rax+rax+00h]
0x1400562c8  test    rbx, rbx
0x1400562cb  jnz     loc_140056ABB
0x1400562d1  test    edi, edi
0x1400562d3  js      loc_140056AD4
0x1400562d9  mov     rcx, [r13+20h]; Object
0x1400562dd  call    cs:__imp_ObfReferenceObject
0x1400562e4  nop     dword ptr [rax+rax+00h]
0x1400562e9  lock inc cs:ObTotalReferences
0x1400562f1  mov     rcx, cs:MpData
0x1400562f8  add     rcx, 8C0h; Lookaside
0x1400562ff  call    ExAllocateFromPagedLookasideList
0x140056304  mov     rbx, rax
0x140056307  test    rax, rax
0x14005630a  jnz     loc_1400563CF
0x140056310  mov     rcx, [r13+20h]; Object
0x140056314  call    cs:__imp_ObfDereferenceObject
0x14005631b  nop     dword ptr [rax+rax+00h]
0x140056320  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140056327  lock xadd cs:ObTotalReferences, rax
0x140056330  cmp     rax, 1
0x140056334  js      loc_140056685
0x14005633a  mov     rcx, cs:WPP_GLOBAL_Control
0x140056341  lea     rax, WPP_GLOBAL_Control
0x140056348  cmp     rcx, rax
0x14005634b  jz      short loc_140056379
0x14005634d  mov     eax, [rcx+2Ch]
0x140056350  test    al, 1
0x140056352  jz      short loc_140056379
0x140056354  lfence
0x140056357  mov     rcx, cs:WPP_GLOBAL_Control
0x14005635e  lea     r8, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids
0x140056365  mov     edx, 1Fh
0x14005636a  mov     r9d, 0C000009Ah
0x140056370  mov     rcx, [rcx+18h]
0x140056374  call    WPP_SF_d
0x140056379  mov     rax, [rbp+37h+P]
0x14005637d  test    rax, rax
0x140056380  jz      loc_1400564A0
0x140056386  mov     edx, 7366504Dh; Tag
0x14005638b  mov     rcx, rax; P
0x14005638e  call    cs:__imp_ExFreePoolWithTag
0x140056395  nop     dword ptr [rax+rax+00h]
0x14005639a  jmp     loc_1400564A0
0x14005639f  movzx   eax, word ptr [rdi]
0x1400563a2  movzx   ecx, cx
0x1400563a5  mov     [rbx+208h], ax
0x1400563ac  add     rcx, 336h
0x1400563b3  movzx   r8d, word ptr [rdi]; Size
0x1400563b7  add     rcx, rbx; void *
0x1400563ba  mov     rdx, [rdi+8]; Src
0x1400563be  call    memmove
0x1400563c3  or      dword ptr [rbx+1Ch], 10000h
0x1400563ca  jmp     loc_1400562A6
0x1400563cf  xor     edx, edx; Val
0x1400563d1  mov     r8d, 78h ; 'x'; Size
0x1400563d7  mov     rcx, rbx; void *
0x1400563da  call    memset
0x1400563df  mov     rax, [rbp+37h+P]
0x1400563e3  mov     [rbx+30h], rax
0x1400563e7  mov     rax, [rbp+37h+Context]
0x1400563eb  mov     rcx, rax; Context
  ... truncated ...
```
