# VhdmpiMirrorThread(_VHD_HANDLE_CONTEXT *,_VHD_ASYNC_OP_CONTEXT *)

- ea: `0x1400b4950`
- end: `0x1400b5e05`
- name: `?VhdmpiMirrorThread@@YAXPEAU_VHD_HANDLE_CONTEXT@@PEAU_VHD_ASYNC_OP_CONTEXT@@@Z`
- size: `5301`
- prototype: `void(struct _VHD_HANDLE_CONTEXT *, struct _VHD_ASYNC_OP_CONTEXT *)`
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1400010d0`
- `0x140001130`
- `0x14000159c`
- `0x14001dbb4`
- `0x140022234`
- `0x140023560`
- `0x140026510`
- `0x140029070`
- `0x14002a9e8`
- `0x14002ac08`
- `0x14002fb1c`
- `0x14002fc50`
- `0x14002fcb8`
- `0x140032834`
- `0x140035e94`
- `0x14004a384`
- `0x14004a46c`
- `0x14004a540`
- `0x14005d7c0`
- `0x14005d840`
- `0x1400a67b8`
- `0x1400a6b6c`
- `0x1400b4950`
- `0x1400b5e0c`
- `0x1400b6fcc`
- `0x1400ceb9c`
- `0x1400cff8c`
- `0x1400d0458`
- `0x1400e0a14`
- `0x1400edad0`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtection` at `0x1400b4ff4`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x1400b4ff4`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400b5b49`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400b5b49`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400b4fe5`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400b4fe5`
- `ntoskrnl!ZwSetInformationFile` at `0x1400b531d`
- `ntoskrnl!ZwSetInformationFile` at `0x1400b531d`
- `ntoskrnl!KeSetEvent` at `0x1400b4fc5`
- `ntoskrnl!KeSetEvent` at `0x1400b4fc5`
- `ntoskrnl!EtwActivityIdControl` at `0x1400b49c6`
- `ntoskrnl!EtwActivityIdControl` at `0x1400b4ec7`
- `ntoskrnl!EtwActivityIdControl` at `0x1400b5808`
- `ntoskrnl!EtwActivityIdControl` at `0x1400b49c6`
- `ntoskrnl!EtwActivityIdControl` at `0x1400b4ec7`
- `ntoskrnl!EtwActivityIdControl` at `0x1400b5808`

## string_xrefs

- `0x1400b4d9d`: `Taking the final snapshot of CTLogMirroringMaxCopyOffset.New values of CTLogMirroringMaxCopyOffset = %llu & Progress.Total = %llu`
- `0x1400b4b94`: `CurrentZeroLength >= PreviousZeroLength.Source cumulative writes = %llu; destination cumulative writes = %llu: CurrentZeroLength = %llu; PreviousZeroLength = %llu`
- `0x1400b4c28`: `Taking a snapshot of CTLogMirroringMaxCopyOffset again.New values of CTLogMirroringMaxCopyOffset = %llu `
- `0x1400b4a71`: `VhdmpiMirrorThread`
- `0x1400b4ac3`: `VhdmpiMirrorThread`
- `0x1400b4b61`: `VhdmpiMirrorThread`
- `0x1400b4c17`: `VhdmpiMirrorThread`
- `0x1400b4d7a`: `VhdmpiMirrorThread`
- `0x1400b4e37`: `VhdmpiMirrorThread`
- `0x1400b4e8b`: `VhdmpiMirrorThread`
- `0x1400b4f6c`: `VhdmpiMirrorThread`
- `0x1400b503c`: `VhdmpiMirrorThread`
- `0x1400b5136`: `VhdmpiMirrorThread`
- `0x1400b51d2`: `VhdmpiMirrorThread`
- `0x1400b5247`: `VhdmpiMirrorThread`
- `0x1400b52d6`: `VhdmpiMirrorThread`
- `0x1400b5748`: `VhdmpiMirrorThread`
- `0x1400b59a2`: `VhdmpiMirrorThread`
- `0x1400b5a41`: `VhdmpiMirrorThread`
- `0x1400b5afd`: `VhdmpiMirrorThread`
- `0x1400b5ca3`: `VhdmpiMirrorThread`
- `0x1400b5de3`: `VhdmpiMirrorThread`
- `0x1400b4ad4`: `Starting the zeroing loop.Initial value of CTLogMirroringMaxCopyOffset = %llu`
- `0x1400b5a2d`: `Progress value updated to %llu.`
- `0x1400b5ae9`: `Progress value updated to %llu.`
- `0x1400b598b`: `Start log copy.`
- `0x1400b5025`: `MirrorThread All WorkerThreads finished`
- `0x1400b5128`: `Mirror Worker Threads completed with status 0x%08x`
- `0x1400b4ea2`: `Start Copying MirrorBlocks. BlockSize %lx MaxOffset %I64x ThreadCount %d`
- `0x1400b4f7c`: `MirrorThread starting %d WorkerThreads`
- `0x1400b522e`: `Mirror operation on disk %p completes with status 0x%08x`

## pseudocode

```c
void __fastcall VhdmpiMirrorThread(struct _VHD_HANDLE_CONTEXT *a1, struct _VHD_ASYNC_OP_CONTEXT *a2)
{
  __int64 v2; // rsi
  char v3; // r12
  __int64 v6; // rdx
  __int64 v7; // r8
  wchar_t *v8; // r13
  __int64 v9; // r9
  int *v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // r14
  int AsyncOpOverrideStatus; // ebx
  __int64 v16; // r8
  char v17; // r14
  __int64 v18; // rcx
  unsigned int v19; // r9d
  unsigned int v20; // edx
  unsigned int v21; // edx
  int *v22; // rcx
  unsigned __int64 v23; // r14
  unsigned int v24; // r9d
  unsigned int i; // ebx
  int *v26; // rax
  int *v27; // rcx
  bool v28; // zf
  unsigned int v29; // edx
  __int64 v30; // rdx
  __int64 *v31; // rcx
  int v32; // r8d
  __int64 v33; // rax
  unsigned __int8 v34; // cl
  unsigned int v35; // r8d
  __int64 v36; // rcx
  wchar_t *v37; // rax
  __int64 v38; // rcx
  unsigned __int64 v39; // rcx
  int *v40; // rax
  int *v41; // rcx
  __int16 *v42; // rdx
  struct _VHD_BACKING_STORE_HEADER *v43; // rcx
  unsigned int v44; // edx
  __int64 v45; // rdx
  __int64 v46; // rcx
  int *v47; // rcx
  int *v48; // rax
  int *v49; // rcx
  unsigned __int64 v50; // rax
  unsigned int v51; // edx
  bool v52; // cc
  unsigned __int64 v53; // rax
  unsigned int v54; // edx
  unsigned __int64 v55; // r8
  unsigned int v56; // edx
  __int64 v57; // rax
  unsigned __int8 v58; // cl
  int v59; // ecx
  __int64 v60; // rcx
  __int64 v61; // rax
  struct _VHD_BACKING_STORE_HEADER *v62; // rdx
  struct _VHD_BACKING_STORE_HEADER *v63; // r14
  int v64; // ecx
  int v65; // r8d
  __int64 v66; // rax
  __int64 v67; // rbx
  char *FileInformationClass; // [rsp+20h] [rbp-E0h]
  char FileInformation[4]; // [rsp+70h] [rbp-90h] BYREF
  char v70[4]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int8 v71; // [rsp+78h] [rbp-88h]
  unsigned __int8 v72; // [rsp+79h] [rbp-87h]
  int *v73; // [rsp+80h] [rbp-80h] BYREF
  struct _VHD_BACKING_STORE_HEADER *v74; // [rsp+88h] [rbp-78h] BYREF
  HANDLE FileHandle; // [rsp+90h] [rbp-70h] BYREF
  __int64 v76; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v77[5]; // [rsp+A0h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  PVOID Object[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v80; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v81; // [rsp+F8h] [rbp-8h]
  GUID v82; // [rsp+100h] [rbp+0h] BYREF
  const GUID *p_ActivityId; // [rsp+110h] [rbp+10h]
  GUID ActivityId; // [rsp+118h] [rbp+18h] BYREF
  __int64 v85; // [rsp+128h] [rbp+28h]
  GUID v86; // [rsp+130h] [rbp+30h] BYREF
  const GUID *v87; // [rsp+140h] [rbp+40h]

  v2 = *((_QWORD *)a1 + 7);
  v3 = 0;
  FileHandle = 0;
  v76 = 0;
  v77[0] = 0;
  v81 = 0;
  v72 = 0;
  v71 = 0;
  v80 = 0;
  v74 = 0;
  *(_OWORD *)Object = 0;
  FileInformation[0] = 0;
  ActivityId = 0;
  v85 = 0;
  EtwActivityIdControl(3u, &ActivityId);
  v85 = (__int64)a2 + 144;
  v8 = L"Unknown";
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    v10 = (int *)L"Unknown";
    if ( *((_QWORD *)a2 + 21) )
      v10 = (int *)*((_QWORD *)a2 + 21);
    v73 = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v10,
      (__int64)&byte_14007D15F,
      (__int64)&ActivityId,
      v9,
      &v73);
  }
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
    TraceEvents("VhdmpiMirrorThread", 0x696u, 4u, 4u, "Mirror operation on disk %p starts", (const void *)v2);
  if ( *((_BYTE *)a2 + 680) )
  {
    *((_QWORD *)a2 + 87) = *(_QWORD *)(*(_QWORD *)(v2 + 1536) + 56LL);
    if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
      TraceEvents(
        "VhdmpiMirrorThread",
        0x6A6u,
        4u,
        0x1000u,
        "Starting the zeroing loop.Initial value of CTLogMirroringMaxCopyOffset = %llu",
        *((_QWORD *)a2 + 87));
    *(_WORD *)(v2 + 2112) = 256;
    *(_QWORD *)(v2 + 2096) = 0;
    *(_QWORD *)(v2 + 2104) = 0;
    v11 = *((_QWORD *)a2 + 86);
    v12 = *((_QWORD *)a2 + 87);
    if ( v12 > *(_QWORD *)(v11 + 56) + 0x800000LL )
    {
      v13 = 0;
      do
      {
        v14 = v12 - *(_QWORD *)(v11 + 56);
        if ( v13
          && v14 >= v13
          && (unsigned int)dword_140087708 > 3
          && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
        {
          TraceEvents(
            "VhdmpiMirrorThread",
            0x6C2u,
            3u,
            0x1000u,
            "CurrentZeroLength >= PreviousZeroLength.Source cumulative writes = %llu; destination cumulative writes = %ll"
            "u: CurrentZeroLength = %llu; PreviousZeroLength = %llu",
            *(_QWORD *)(v2 + 2096),
            *(_QWORD *)(v2 + 2104),
            v14,
            v13);
        }
        AsyncOpOverrideStatus = VhdmpiCTLogMirroringZeroLogFilePortion(
                                  *((_QWORD *)a2 + 86),
                                  *(_QWORD *)(*((_QWORD *)a2 + 86) + 56LL),
                                  *((_QWORD *)a2 + 87),
                                  a2);
        if ( AsyncOpOverrideStatus < 0 )
          goto LABEL_67;
        v13 = v14;
        *(_QWORD *)(*((_QWORD *)a2 + 86) + 56LL) = *((_QWORD *)a2 + 87);
        *((_QWORD *)a2 + 87) = *(_QWORD *)(*(_QWORD *)(v2 + 1536) + 56LL);
        if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
          TraceEvents(
            "VhdmpiMirrorThread",
            0x6D9u,
            4u,
            0x1000u,
            "Taking a snapshot of CTLogMirroringMaxCopyOffset again.New values of CTLogMirroringMaxCopyOffset = %llu ",
            *((_QWORD *)a2 + 87));
        v11 = *((_QWORD *)a2 + 86);
        v12 = *((_QWORD *)a2 + 87);
      }
      while ( v12 > *(_QWORD *)(v11 + 56) + 0x800000LL );
    }
  }
  *(_WORD *)(v2 + 2112) = 0;
  VhdmpiTriggerCTLogSrbProcessingRoutine(v2, v6, v7);
  VhdmpiHoldAllIoAndWait(v2);
  VhdmpiActivateIoTracking((PEX_RUNDOWN_REF)(v2 + 384));
  v3 = 1;
  LOBYTE(v16) = 1;
  AsyncOpOverrideStatus = VhdmpiSetSecondaryBackingStore(v2, *((_QWORD *)a2 + 22), v16);
  *(_BYTE *)(*((_QWORD *)a2 + 22) + 1864LL) = 1;
  if ( AsyncOpOverrideStatus < 0 )
  {
    VhdmpiReleaseAllIo(v2);
LABEL_27:
    v17 = FileInformation[0];
    goto LABEL_68;
  }
  v17 = 1;
  *(_QWORD *)(v2 + 1016) = *((unsigned int *)a2 + 48);
  *(_QWORD *)(v2 + 1024) = *((unsigned int *)a2 + 48);
  if ( *((_BYTE *)a2 + 680) )
  {
    VhdmpiCTLogFlushFileData(*(struct _CTLOG_BACKING_STORE **)(v2 + 1536));
    *(_QWORD *)(*((_QWORD *)a2 + 86) + 4180LL) = *(_QWORD *)(*(_QWORD *)(v2 + 1536) + 4180LL);
    *(_QWORD *)(*((_QWORD *)a2 + 86) + 180LL) = *(_QWORD *)(*(_QWORD *)(v2 + 1536) + 180LL);
    v18 = *(_QWORD *)(*(_QWORD *)(v2 + 1536) + 56LL);
    *((_QWORD *)a2 + 87) = v18;
    *((_QWORD *)a2 + 14) = *((_QWORD *)a2 + 25) + v18;
    if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
      TraceEvents(
        "VhdmpiMirrorThread",
        0x72Bu,
        4u,
        v19,
        "Taking the final snapshot of CTLogMirroringMaxCopyOffset.New values of CTLogMirroringMaxCopyOffset = %llu & Prog"
        "ress.Total = %llu",
        *((_QWORD *)a2 + 87),
        *((_QWORD *)a2 + 14));
    AsyncOpOverrideStatus = VhdmpiCTLogMirroringZeroLogFilePortion(
                              *((_QWORD *)a2 + 86),
                              *(_QWORD *)(*((_QWORD *)a2 + 86) + 56LL),
                              *((_QWORD *)a2 + 87),
                              a2);
    if ( AsyncOpOverrideStatus < 0 )
    {
      VhdmpiReleaseAllIo(v2);
      goto LABEL_68;
    }
    *(_QWORD *)(*((_QWORD *)a2 + 86) + 56LL) = *((_QWORD *)a2 + 87);
    *(_QWORD *)(v2 + 2088) = *((_QWORD *)a2 + 86);
    if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
      TraceEvents("VhdmpiMirrorThread", 0x74Du, 4u, v20, "Start active log mirroring.");
  }
  VhdmpiReleaseAllIo(v2);
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x40000) )
    TraceEvents(
      "VhdmpiMirrorThread",
      0x757u,
      5u,
      v21,
      "Start Copying MirrorBlocks. BlockSize %lx MaxOffset %I64x ThreadCount %d",
      *((_DWORD *)a2 + 48),
      *((_QWORD *)a2 + 25),
      *((_DWORD *)a2 + 196));
  p_ActivityId = 0;
  v82 = 0;
  EtwActivityIdControl(3u, &v82);
  p_ActivityId = &ActivityId;
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    v22 = (int *)L"Unknown";
    if ( *((_QWORD *)a2 + 21) )
      v22 = (int *)*((_QWORD *)a2 + 21);
    v73 = v22;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v22,
      (__int64)&unk_14007D130,
      (__int64)&v82,
      (__int64)&ActivityId,
      &v73);
  }
  v23 = *((unsigned int *)a2 + 48);
  if ( !*((_QWORD *)a2 + 107) )
  {
    while ( 1 )
    {
      if ( v23 >= *((_QWORD *)a2 + 25) )
      {
        if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
        {
          v40 = (int *)*((_QWORD *)a2 + 21);
          *(_DWORD *)v70 = AsyncOpOverrideStatus;
          v41 = (int *)L"Unknown";
          if ( v40 )
            v41 = v40;
          v73 = v41;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (__int64)v41,
            (unsigned __int8 *)word_14007CF8A,
            &v82,
            p_ActivityId,
            &v73,
            (__int64)v70);
        }
        goto LABEL_129;
      }
      v38 = *((unsigned int *)a2 + 48);
      if ( v23 - v38 > *((_QWORD *)a2 + 13) )
        *((_QWORD *)a2 + 13) = v23 - v38;
      AsyncOpOverrideStatus = VhdmpiMirrorVirtualBlock(a1, (struct _VHD_VIRTUAL_DISK *)v2, a2, v23, v38);
      if ( AsyncOpOverrideStatus < 0 )
        break;
      VhdmpiWaitOnSingleStepAsyncOp(a1, 3);
      v39 = v23 + *((unsigned int *)a2 + 48);
      if ( v39 < v23 )
      {
        AsyncOpOverrideStatus = -1073741675;
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
        {
          *(_DWORD *)v70 = -1073741675;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>();
        }
        if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
        {
          *(_DWORD *)v70 = -1073741675;
          v42 = word_14007D24A;
LABEL_120:
          v43 = (struct _VHD_BACKING_STORE_HEADER *)L"Unknown";
          if ( *((_QWORD *)a2 + 21) )
            v43 = (struct _VHD_BACKING_STORE_HEADER *)*((_QWORD *)a2 + 21);
          v74 = v43;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (__int64)v43,
            (unsigned __int8 *)v42,
            &v82,
            p_ActivityId,
            (int **)&v74,
            (__int64)v70);
          goto LABEL_67;
        }
        goto LABEL_67;
      }
      v23 = *((_QWORD *)a2 + 25);
      AsyncOpOverrideStatus = 0;
      if ( v39 <= v23 )
        v23 = v39;
      VhdmpiAdjustRedirectRange(v2, *(_QWORD *)(v2 + 1016), v23);
    }
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
    {
      *(_DWORD *)v70 = AsyncOpOverrideStatus;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>();
    }
    if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
    {
      *(_DWORD *)v70 = AsyncOpOverrideStatus;
      v42 = word_14007D1EA;
      goto LABEL_120;
    }
    goto LABEL_67;
  }
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x40000) )
    TraceEvents("VhdmpiMirrorThread", 0x770u, 5u, v24, "MirrorThread starting %d WorkerThreads", *((_DWORD *)a2 + 196));
  *((_QWORD *)a2 + 96) = v23;
  for ( i = 0; i < *((_DWORD *)a2 + 196); ++i )
    KeSetEvent((PRKEVENT)(*((_QWORD *)a2 + 107) + 16LL + 456LL * i), 0, 0);
  ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)a2 + 97);
  ExReInitializeRundownProtection((PEX_RUNDOWN_REF)a2 + 97);
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x40000) )
    TraceEvents("VhdmpiMirrorThread", 0x782u, 5u, v6, "MirrorThread All WorkerThreads finished");
  AsyncOpOverrideStatus = *((_DWORD *)a2 + 190);
  if ( AsyncOpOverrideStatus < 0
    && (unsigned int)dword_1400876D0 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    FileInformationClass = v70;
    *(_DWORD *)v70 = AsyncOpOverrideStatus;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>();
  }
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    v26 = (int *)*((_QWORD *)a2 + 21);
    *(_DWORD *)v70 = AsyncOpOverrideStatus;
    v27 = (int *)L"Unknown";
    if ( v26 )
      v27 = v26;
    v73 = v27;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v27,
      (unsigned __int8 *)word_14007D18A,
      &v82,
      p_ActivityId,
      &v73,
      (__int64)v70);
  }
  if ( AsyncOpOverrideStatus < 0 )
  {
    if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
      TraceEvents(
        "VhdmpiMirrorThread",
        0x791u,
        5u,
        v6,
        "Mirror Worker Threads completed with status 0x%08x",
        AsyncOpOverrideStatus);
    goto LABEL_67;
  }
LABEL_129:
  if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x40000) )
    TraceEvents("VhdmpiMirrorThread", 0x7D8u, 5u, v44, "Successfully Copied all but the first MirrorBlock");
  VhdmpiWaitOnSingleStepAsyncOp(a1, 4);
  v45 = *((_QWORD *)a2 + 22);
  v46 = *((_QWORD *)a2 + 17);
  v80 = (unsigned __int64)a2;
  v81 = 100;
  LOBYTE(FileInformationClass) = 0;
  AsyncOpOverrideStatus = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, char *, char *))(*(_QWORD *)v45
                                                                                                  + 184LL))(
                            v46,
                            v45,
                            &v80,
                            (char *)a2 + 520,
                            FileInformationClass);
  if ( AsyncOpOverrideStatus < 0 )
    goto LABEL_67;
  AsyncOpOverrideStatus = VhdmpiMirrorVirtualBlock(a1, (struct _VHD_VIRTUAL_DISK *)v2, a2, 0, *((_DWORD *)a2 + 48));
  if ( AsyncOpOverrideStatus < 0 )
    goto LABEL_67;
  VhdmpiWaitOnSingleStepAsyncOp(a1, 3);
  VhdmpiAdjustRedirectRange(v2, 0, *(_QWORD *)(v2 + 1024));
  VhdmpiReleaseAllIo(v2);
  v86 = 0;
  v87 = 0;
  EtwActivityIdControl(3u, &v86);
  v87 = &ActivityId;
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    v47 = (int *)L"Unknown";
    if ( *((_QWORD *)a2 + 21) )
      v47 = (int *)*((_QWORD *)a2 + 21);
    v73 = v47;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v47,
      (__int64)word_14007CFEA,
      (__int64)&v86,
      (__int64)&ActivityId,
      &v73);
  }
  AsyncOpOverrideStatus = VhdmpiInternalIoSync(*((_QWORD *)a2 + 17), *((_QWORD *)a2 + 22), 3, 0, 0, (__int64)a2 + 232);
  if ( AsyncOpOverrideStatus < 0
    && (unsigned int)dword_1400876D0 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    *(_DWORD *)v70 = AsyncOpOverrideStatus;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>();
  }
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    v48 = (int *)*((_QWORD *)a2 + 21);
    *(_DWORD *)v70 = AsyncOpOverrideStatus;
    v49 = (int *)L"Unknown";
    if ( v48 )
      v49 = v48;
    v73 = v49;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)v49,
      (unsigned __int8 *)&dword_14007D014,
      &v86,
      v87,
      &v73,
      (__int64)v70);
  }
  if ( AsyncOpOverrideStatus < 0 )
    goto LABEL_67;
  v50 = *((_QWORD *)a2 + 25);
  if ( v50 > *((_QWORD *)a2 + 13) )
    *((_QWORD *)a2 + 13) = v50;
  if ( !*((_BYTE *)a2 + 680) )
    goto LABEL_169;
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
    TraceEvents("VhdmpiMirrorThread", 0x833u, 4u, v51, "Start log copy.");
  v52 = *((_QWORD *)a2 + 87) <= 0x800000u;
  *((_QWORD *)a2 + 88) = 0;
  if ( !v52 )
  {
    do
    {
      AsyncOpOverrideStatus = VhdmpiCTLogMirroringCopyLogBlocks(a2);
      if ( AsyncOpOverrideStatus < 0 )
        goto LABEL_67;
      v53 = *((_QWORD *)a2 + 13);
      if ( v53 + 0x800000 >= v53 )
        *((_QWORD *)a2 + 13) = v53 + 0x800000;
      if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
        TraceEvents("VhdmpiMirrorThread", 0x849u, 5u, v54, "Progress value updated to %llu.", *((_QWORD *)a2 + 13));
      *((_QWORD *)a2 + 88) += 0x800000LL;
    }
    while ( (unsigned __int64)(*((_QWORD *)a2 + 88) + 0x800000LL) < *((_QWORD *)a2 + 87) );
  }
  AsyncOpOverrideStatus = VhdmpiCTLogMirroringCopyLogBlocks(a2);
  if ( AsyncOpOverrideStatus >= 0 )
  {
    v55 = *((_QWORD *)a2 + 87) + *((_QWORD *)a2 + 13) - *((_QWORD *)a2 + 88);
    if ( v55 > *((_QWORD *)a2 + 13) )
      *((_QWORD *)a2 + 13) = v55;
    if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
      TraceEvents("VhdmpiMirrorThread", 0x867u, 5u, v56, "Progress value updated to %llu.", *((_QWORD *)a2 + 13));
LABEL_169:
    VhdmpiWaitOnSingleStepAsyncOp(a1, 5);
    Object[0] = (char *)a2 + 48;
    Object[1] = (char *)a2 + 72;
    KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
    AsyncOpOverrideStatus = VhdmpiGetAsyncOpOverrideStatus(a2);
    if ( AsyncOpOverrideStatus >= 0 )
    {
      v57 = *((_QWORD *)a2 + 22);
      v58 = *(_BYTE *)(v57 + 1809);
      LOBYTE(v57) = *(_BYTE *)(v57 + 1810);
      v72 = v58;
      v71 = v57;
      VhdmpiWaitOnSingleStepAsyncOp(a1, 6);
      VhdmpiHoldAllIoAndWait(v2);
      if ( *((_BYTE *)a2 + 680) )
        VhdmpiCTLogFlushFileData(*(struct _CTLOG_BACKING_STORE **)(v2 + 2088));
      AsyncOpOverrideStatus = *(_DWORD *)(v2 + 1036);
      if ( AsyncOpOverrideStatus >= 0 )
      {
        if ( *((_BYTE *)a2 + 186) )
        {
          if ( (Microsoft_Windows_VHDMPEnableBits & 8) != 0 )
            McTemplateK0szq_EtwWriteTransfer(
              v59,
              (unsigned int)VhdMetaOpsSuccess,
              v7,
              (unsigned int)"Mirror",
              *(_QWORD *)(*(_QWORD *)(v2 + 144) + 120LL),
              0);
          AsyncOpOverrideStatus = 0;
        }
        else
        {
          *(_QWORD *)(*((_QWORD *)a2 + 22) + 1152LL) = *(_QWORD *)(*(_QWORD *)(v2 + 144) + 1144LL);
          v60 = *(_QWORD *)(*(_QWORD *)(v2 + 144) + 1144LL);
          if ( v60 )
          {
            do
            {
              v61 = *(_QWORD *)(v60 + 1144);
              *(_QWORD *)(v60 + 1152) = v61;
              v60 = v61;
            }
            while ( v61 );
          }
          AsyncOpOverrideStatus = VhdmpiGetFileSizeAndVdl(*((_QWORD *)a2 + 22) + 72LL, &v76, v77);
          if ( AsyncOpOverrideStatus >= 0 )
          {
            *(_QWORD *)(*((_QWORD *)a2 + 22) + 1176LL) = v77[0];
            *(_BYTE *)(*((_QWORD *)a2 + 22) + 1864LL) = 0;
            AsyncOpOverrideStatus = VhdmpiActivateProposedBackingStoreChain(
                                      (struct _VHD_VIRTUAL_DISK *)v2,
                                      *((struct _VHD_BACKING_STORE_HEADER **)a2 + 22));
            if ( AsyncOpOverrideStatus >= 0 )
            {
              *((_QWORD *)a2 + 22) = 0;
              v62 = *(struct _VHD_BACKING_STORE_HEADER **)(v2 + 144);
              FileInformation[0] = 0;
              VhdmpiReleaseBackingStoreAndRctAccess((struct _VHD_HANDLE_CONTEXT *)((char *)a1 + 16), v62);
              *((_BYTE *)a2 + 185) = 0;
              v63 = v74;
              VhdmpiReleaseBackingStoreAndRctAccess((struct _VHD_HANDLE_CONTEXT *)((char *)a1 + 16), v74);
              *((_BYTE *)a2 + 184) = 0;
              if ( (Microsoft_Windows_VHDMPEnableBits & 8) != 0 )
                McTemplateK0szq_EtwWriteTransfer(
                  v64,
                  (unsigned int)VhdMetaOpsSuccess,
                  v65,
                  (unsigned int)"Mirror",
                  *((_QWORD *)v63 + 15),
                  0);
              VhdmpiReleaseBackingStore((char)v63);
              if ( *((_BYTE *)a2 + 680) )
              {
                v66 = *(_QWORD *)(v2 + 2088);
                v67 = *(_QWORD *)(v2 + 1536);
                *(_QWORD *)(v2 + 1536) = v66;
                *(_QWORD *)(v2 + 2088) = 0;
                *(_BYTE *)(v66 + 4432) = 0;
                if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
                  TraceEvents("VhdmpiMirrorThread", 0x93Cu, 4u, v6, "Stop active log mirroring.");
                *(_BYTE *)(v67 + 4432) = 1;
                *((_QWORD *)a2 + 86) = v67;
              }
              AsyncOpOverrideStatus = 0;
              goto LABEL_27;
            }
          }
          else if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x40000) )
          {
            TraceEvents(
              "VhdmpiMirrorThread",
              0x8E3u,
              2u,
              v6,
              "Get VDL for mirror on disk %p failed with 0x%08x",
              (const void *)v2,
              AsyncOpOverrideStatus);
          }
        }
      }
    }
  }
LABEL_67:
  v17 = v3;
LABEL_68:
  v28 = *((_BYTE *)a2 + 680) == 0;
  *((_DWORD *)a2 + 3) = AsyncOpOverrideStatus;
  if ( !v28 )
  {
    *(_WORD *)(v2 + 2112) = 0;
    VhdmpiTriggerCTLogSrbProcessingRoutine(v2, v6, v7);
  }
  if ( v17 )
  {
    VhdmpiHoldAllIoAndWait(v2);
    VhdmpiSetSecondaryBackingStore(v2, 0, 0);
    if ( *((_BYTE *)a2 + 680) )
    {
      *(_QWORD *)(v2 + 2088) = 0;
      if ( (unsigned int)dword_140087708 > 4 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
          TraceEvents("VhdmpiMirrorThread", 0x96Bu, 4u, v29, "Stop active log mirroring (Cancel case).");
      }
    }
  }
  if ( v3 )
    VhdmpiDeactivateIoTracking((PEX_RUNDOWN_REF)(v2 + 384));
  VhdmpiReleaseAllIo(v2);
  VhdmpiWaitOnSingleStepAsyncOp(a1, 7);
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
    TraceEvents(
      "VhdmpiMirrorThread",
      0x984u,
      4u,
      4u,
      "Mirror operation on disk %p completes with status 0x%08x",
      (const void *)v2,
      AsyncOpOverrideStatus);
  if ( AsyncOpOverrideStatus < 0 )
  {
    v33 = *((_QWORD *)a2 + 22);
    if ( v33 && *(_DWORD *)(v33 + 672) == 3 )
    {
      v34 = *(_BYTE *)(v33 + 1809);
      v71 = *(_BYTE *)(v33 + 1810);
      v72 = v34;
      FileInformation[0] = 0;
      IoStatusBlock = 0;
      if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
        TraceEvents("VhdmpiMirrorThread", 0x994u, 4u, v35, "Deleting VHD file");
      LOBYTE(v30) = 1;
      if ( (int)VhdmpiPinFile(*((_QWORD *)a2 + 22), v30, &FileHandle, 0) >= 0 )
      {
        FileInformation[0] = 1;
        ZwSetInformationFile(FileHandle, &IoStatusBlock, FileInformation, 1u, FileDispositionInformation);
        v31 = (__int64 *)*((_QWORD *)a2 + 22);
        if ( v31 != &VhdmpiEmptyISOBackingStore )
          VhdmpiFileWrapperUnpinFile(v31 + 9, 1);
      }
    }
    if ( !*((_BYTE *)a2 + 16) && (Microsoft_Windows_VHDMPEnableBits & 4) != 0 )
      McTemplateK0szq_EtwWriteTransfer(
        (_DWORD)v31,
        (unsigned int)VhdMetaOpsError,
        v32,
        (unsigned int)"Mirror",
        *(_QWORD *)(*(_QWORD *)(v2 + 144) + 120LL),
        AsyncOpOverrideStatus);
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
    {
      *(_DWORD *)v70 = AsyncOpOverrideStatus;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>();
    }
  }
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    LODWORD(v76) = v71;
    LODWORD(v73) = v72;
    LODWORD(FileHandle) = *((unsigned __int8 *)a2 + 188);
    LODWORD(v74) = *((unsigned __int8 *)a2 + 187);
    v77[1] = *((_QWORD *)a2 + 28);
    v77[2] = *((_QWORD *)a2 + 27);
    v77[3] = *((_QWORD *)a2 + 26);
    v77[4] = *((unsigned int *)a2 + 48);
    v37 = (wchar_t *)*((_QWORD *)a2 + 21);
    *(_DWORD *)v70 = AsyncOpOverrideStatus;
    if ( v37 )
      v8 = v37;
    IoStatusBlock.Pointer = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v36,
      (__int64)&byte_14007D047,
      (__int64)&ActivityId,
      v85,
      &IoStatusBlock);
  }
}

```

## disassembly

```asm
0x1400b4950  mov     [rsp-8+arg_10], rbx
0x1400b4955  push    rbp
0x1400b4956  push    rsi
0x1400b4957  push    rdi
0x1400b4958  push    r12
0x1400b495a  push    r13
0x1400b495c  push    r14
0x1400b495e  push    r15
0x1400b4960  lea     rbp, [rsp-50h]
0x1400b4965  sub     rsp, 150h
0x1400b496c  mov     rax, cs:__security_cookie
0x1400b4973  xor     rax, rsp
0x1400b4976  mov     [rbp+80h+var_38], rax
0x1400b497a  mov     rsi, [rcx+38h]
0x1400b497e  xor     r12d, r12d
0x1400b4981  xor     eax, eax
0x1400b4983  mov     [rbp+80h+FileHandle], r12
0x1400b4987  xorps   xmm0, xmm0
0x1400b498a  mov     [rbp+80h+var_E8], r12
0x1400b498e  mov     rdi, rdx
0x1400b4991  mov     [rbp+80h+var_E0], r12
0x1400b4995  mov     r15, rcx
0x1400b4998  mov     [rbp+80h+var_88], rax
0x1400b499c  lea     ecx, [rax+3]; ControlCode
0x1400b499f  mov     [rsp+180h+var_107], r12b
0x1400b49a4  lea     rdx, [rbp+80h+ActivityId]; ActivityId
0x1400b49a8  mov     [rsp+180h+var_108], r12b
0x1400b49ad  movups  [rbp+80h+var_98], xmm0
0x1400b49b1  mov     [rbp+80h+var_F8], r12
0x1400b49b5  movups  xmmword ptr [rbp+80h+Object], xmm0
0x1400b49b9  mov     [rsp+180h+FileInformation], r12b
0x1400b49be  movups  xmmword ptr [rbp+80h+ActivityId.Data1], xmm0
0x1400b49c2  mov     [rbp+80h+var_58], rax
0x1400b49c6  call    cs:__imp_EtwActivityIdControl
0x1400b49cd  nop     dword ptr [rax+rax+00h]
0x1400b49d2  mov     eax, cs:dword_1400876D0
0x1400b49d8  lea     r9, [rdi+90h]
0x1400b49df  mov     [rbp+80h+var_58], r9
0x1400b49e3  lea     r13, aUnknown; "Unknown"
0x1400b49ea  cmp     eax, 4
0x1400b49ed  jbe     short loc_1400B4A32
0x1400b49ef  mov     edx, 10000h
0x1400b49f4  lea     rcx, dword_1400876D0
0x1400b49fb  call    _tlgKeywordOn
0x1400b4a00  test    al, al
0x1400b4a02  jz      short loc_1400B4A32
0x1400b4a04  mov     rax, [rdi+0A8h]
0x1400b4a0b  lea     r8, [rbp+80h+ActivityId]
0x1400b4a0f  test    rax, rax
0x1400b4a12  lea     rdx, byte_14007D15F
0x1400b4a19  mov     rcx, r13
0x1400b4a1c  cmovnz  rcx, rax
0x1400b4a20  lea     rax, [rbp+80h+var_100]
0x1400b4a24  mov     qword ptr [rsp+180h+FileInformationClass], rax
0x1400b4a29  mov     [rbp+80h+var_100], rcx
0x1400b4a2d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1400b4a32  mov     eax, cs:dword_140087708
0x1400b4a38  cmp     eax, 4
0x1400b4a3b  jbe     short loc_1400B4A7D
0x1400b4a3d  mov     edx, 4
0x1400b4a42  lea     rcx, dword_140087708
0x1400b4a49  call    _tlgKeywordOn
0x1400b4a4e  test    al, al
0x1400b4a50  jz      short loc_1400B4A7D
0x1400b4a52  mov     r9d, 4; int
0x1400b4a58  mov     qword ptr [rsp+180h+Alertable], rsi; char
0x1400b4a5d  lea     rax, aMirrorOperatio; "Mirror operation on disk %p starts"
0x1400b4a64  mov     r8d, r9d; int
0x1400b4a67  mov     edx, 696h; int
0x1400b4a6c  mov     qword ptr [rsp+180h+FileInformationClass], rax; char *
0x1400b4a71  lea     rcx, aVhdmpimirrorth; "VhdmpiMirrorThread"
0x1400b4a78  call    TraceEvents
0x1400b4a7d  cmp     [rdi+2A8h], r12b
0x1400b4a84  jz      loc_1400B4C66
0x1400b4a8a  mov     rax, [rsi+600h]
0x1400b4a91  mov     rcx, [rax+38h]
0x1400b4a95  mov     [rdi+2B8h], rcx
0x1400b4a9c  mov     eax, cs:dword_140087708
0x1400b4aa2  cmp     eax, 4
0x1400b4aa5  jbe     short loc_1400B4AF1
0x1400b4aa7  mov     edx, 1000h
0x1400b4aac  lea     rcx, dword_140087708
0x1400b4ab3  call    _tlgKeywordOn
0x1400b4ab8  test    al, al
0x1400b4aba  jz      short loc_1400B4AF1
0x1400b4abc  mov     rax, [rdi+2B8h]
0x1400b4ac3  lea     rcx, aVhdmpimirrorth; "VhdmpiMirrorThread"
0x1400b4aca  mov     qword ptr [rsp+180h+Alertable], rax; char
0x1400b4acf  mov     edx, 6A6h; int
0x1400b4ad4  lea     rax, aStartingTheZer; "Starting the zeroing loop.Initial value"...
0x1400b4adb  mov     r9d, 1000h; int
0x1400b4ae1  mov     r8d, 4; int
0x1400b4ae7  mov     qword ptr [rsp+180h+FileInformationClass], rax; char *
0x1400b4aec  call    TraceEvents
0x1400b4af1  mov     word ptr [rsi+840h], 100h
0x1400b4afa  mov     [rsi+830h], r12
0x1400b4b01  mov     [rsi+838h], r12
0x1400b4b08  mov     rcx, [rdi+2B0h]
0x1400b4b0f  mov     r14, [rdi+2B8h]
0x1400b4b16  mov     rax, [rcx+38h]
0x1400b4b1a  add     rax, 800000h
0x1400b4b20  cmp     r14, rax
0x1400b4b23  jbe     loc_1400B4C66
0x1400b4b29  mov     rbx, r12
0x1400b4b2c  sub     r14, [rcx+38h]
0x1400b4b30  test    rbx, rbx
0x1400b4b33  jz      short loc_1400B4BA5
0x1400b4b35  cmp     r14, rbx
0x1400b4b38  jb      short loc_1400B4BA5
0x1400b4b3a  mov     eax, cs:dword_140087708
0x1400b4b40  cmp     eax, 3
0x1400b4b43  jbe     short loc_1400B4BA5
0x1400b4b45  mov     edx, 1000h
0x1400b4b4a  lea     rcx, dword_140087708
0x1400b4b51  call    _tlgKeywordOn
0x1400b4b56  test    al, al
0x1400b4b58  jz      short loc_1400B4BA5
0x1400b4b5a  mov     rax, [rsi+838h]
0x1400b4b61  lea     rcx, aVhdmpimirrorth; "VhdmpiMirrorThread"
0x1400b4b68  mov     [rsp+180h+var_140], rbx
0x1400b4b6d  mov     edx, 6C2h; int
0x1400b4b72  mov     [rsp+180h+WaitBlockArray], r14
0x1400b4b77  mov     r9d, 1000h; int
0x1400b4b7d  mov     [rsp+180h+Timeout], rax
0x1400b4b82  mov     r8d, 3; int
0x1400b4b88  mov     rax, [rsi+830h]
0x1400b4b8f  mov     qword ptr [rsp+180h+Alertable], rax; char
0x1400b4b94  lea     rax, aCurrentzerolen; "CurrentZeroLength >= PreviousZeroLength"...
0x1400b4b9b  mov     qword ptr [rsp+180h+FileInformationClass], rax; char *
0x1400b4ba0  call    TraceEvents
0x1400b4ba5  mov     rcx, [rdi+2B0h]
0x1400b4bac  mov     r9, rdi
0x1400b4baf  mov     r8, [rdi+2B8h]
0x1400b4bb6  mov     rdx, [rcx+38h]
0x1400b4bba  call    VhdmpiCTLogMirroringZeroLogFilePortion
0x1400b4bbf  mov     ebx, eax
0x1400b4bc1  test    eax, eax
0x1400b4bc3  js      loc_1400B5148
0x1400b4bc9  mov     rax, [rdi+2B8h]
0x1400b4bd0  mov     rbx, r14
0x1400b4bd3  mov     rcx, [rdi+2B0h]
0x1400b4bda  mov     [rcx+38h], rax
0x1400b4bde  mov     rax, [rsi+600h]
0x1400b4be5  mov     rcx, [rax+38h]
0x1400b4be9  mov     [rdi+2B8h], rcx
0x1400b4bf0  mov     eax, cs:dword_140087708
0x1400b4bf6  cmp     eax, 4
0x1400b4bf9  jbe     short loc_1400B4C45
0x1400b4bfb  mov     edx, 1000h
0x1400b4c00  lea     rcx, dword_140087708
0x1400b4c07  call    _tlgKeywordOn
0x1400b4c0c  test    al, al
0x1400b4c0e  jz      short loc_1400B4C45
0x1400b4c10  mov     rax, [rdi+2B8h]
0x1400b4c17  lea     rcx, aVhdmpimirrorth; "VhdmpiMirrorThread"
0x1400b4c1e  mov     qword ptr [rsp+180h+Alertable], rax; char
0x1400b4c23  mov     edx, 6D9h; int
0x1400b4c28  lea     rax, aTakingASnapsho; "Taking a snapshot of CTLogMirroringMaxC"...
0x1400b4c2f  mov     r9d, 1000h; int
0x1400b4c35  mov     r8d, 4; int
0x1400b4c3b  mov     qword ptr [rsp+180h+FileInformationClass], rax; char *
0x1400b4c40  call    TraceEvents
0x1400b4c45  mov     rcx, [rdi+2B0h]
0x1400b4c4c  mov     r14, [rdi+2B8h]
0x1400b4c53  mov     rax, [rcx+38h]
0x1400b4c57  add     rax, 800000h
0x1400b4c5d  cmp     r14, rax
0x1400b4c60  ja      loc_1400B4B2C
0x1400b4c66  mov     rcx, rsi
0x1400b4c69  mov     [rsi+840h], r12w
0x1400b4c71  call    VhdmpiTriggerCTLogSrbProcessingRoutine
0x1400b4c76  mov     rcx, rsi
0x1400b4c79  call    VhdmpiHoldAllIoAndWait
0x1400b4c7e  lea     rcx, [rsi+180h]; RunRef
0x1400b4c85  call    VhdmpiActivateIoTracking
0x1400b4c8a  mov     rdx, [rdi+0B0h]
0x1400b4c91  mov     r12b, 1
0x1400b4c94  mov     r8b, r12b
0x1400b4c97  mov     rcx, rsi
0x1400b4c9a  call    VhdmpiSetSecondaryBackingStore
0x1400b4c9f  mov     ebx, eax
0x1400b4ca1  mov     rax, [rdi+0B0h]
0x1400b4ca8  mov     [rax+748h], r12b
0x1400b4caf  test    ebx, ebx
0x1400b4cb1  jns     short loc_1400B4CC5
0x1400b4cb3  mov     rcx, rsi
0x1400b4cb6  call    VhdmpiReleaseAllIo
0x1400b4cbb  mov     r14b, [rsp+180h+FileInformation]
0x1400b4cc0  jmp     loc_1400B514B
0x1400b4cc5  mov     eax, [rdi+0C0h]
0x1400b4ccb  mov     r14b, r12b
0x1400b4cce  mov     [rsi+3F8h], rax
0x1400b4cd5  mov     eax, [rdi+0C0h]
0x1400b4cdb  mov     [rsi+400h], rax
0x1400b4ce2  cmp     byte ptr [rdi+2A8h], 0
0x1400b4ce9  jz      loc_1400B4E43
0x1400b4cef  mov     rcx, [rsi+600h]; struct _CTLOG_BACKING_STORE *
0x1400b4cf6  xor     edx, edx
0x1400b4cf8  call    VhdmpiCTLogFlushFileData
0x1400b4cfd  mov     rax, [rsi+600h]
0x1400b4d04  mov     rcx, [rdi+2B0h]
0x1400b4d0b  mov     rax, [rax+1054h]
0x1400b4d12  mov     [rcx+1054h], rax
0x1400b4d19  mov     rax, [rsi+600h]
0x1400b4d20  mov     rcx, [rdi+2B0h]
0x1400b4d27  mov     rax, [rax+0B4h]
0x1400b4d2e  mov     [rcx+0B4h], rax
0x1400b4d35  mov     rax, [rsi+600h]
0x1400b4d3c  mov     rcx, [rax+38h]
0x1400b4d40  mov     [rdi+2B8h], rcx
0x1400b4d47  add     rcx, [rdi+0C8h]
0x1400b4d4e  mov     [rdi+70h], rcx
0x1400b4d52  mov     eax, cs:dword_140087708
0x1400b4d58  cmp     eax, 4
0x1400b4d5b  jbe     short loc_1400B4DAE
0x1400b4d5d  mov     r9d, 1000h
0x1400b4d63  lea     rcx, dword_140087708
0x1400b4d6a  mov     edx, r9d
0x1400b4d6d  call    _tlgKeywordOn
0x1400b4d72  test    al, al
0x1400b4d74  jz      short loc_1400B4DAE
0x1400b4d76  mov     rax, [rdi+70h]
0x1400b4d7a  lea     rcx, aVhdmpimirrorth; "VhdmpiMirrorThread"
0x1400b4d81  mov     [rsp+180h+Timeout], rax
0x1400b4d86  mov     edx, 72Bh; int
0x1400b4d8b  mov     rax, [rdi+2B8h]
0x1400b4d92  mov     r8d, 4; int
0x1400b4d98  mov     qword ptr [rsp+180h+Alertable], rax; char
0x1400b4d9d  lea     rax, aTakingTheFinal; "Taking the final snapshot of CTLogMirro"...
0x1400b4da4  mov     qword ptr [rsp+180h+FileInformationClass], rax; char *
0x1400b4da9  call    TraceEvents
0x1400b4dae  mov     rcx, [rdi+2B0h]
0x1400b4db5  mov     r9, rdi
0x1400b4db8  mov     r8, [rdi+2B8h]
0x1400b4dbf  mov     rdx, [rcx+38h]
0x1400b4dc3  call    VhdmpiCTLogMirroringZeroLogFilePortion
0x1400b4dc8  mov     ebx, eax
0x1400b4dca  test    eax, eax
0x1400b4dcc  jns     short loc_1400B4DDB
0x1400b4dce  mov     rcx, rsi
0x1400b4dd1  call    VhdmpiReleaseAllIo
0x1400b4dd6  jmp     loc_1400B514B
0x1400b4ddb  mov     rax, [rdi+2B8h]
0x1400b4de2  mov     rcx, [rdi+2B0h]
0x1400b4de9  mov     [rcx+38h], rax
0x1400b4ded  mov     rax, [rdi+2B0h]
0x1400b4df4  mov     [rsi+828h], rax
0x1400b4dfb  mov     eax, cs:dword_140087708
0x1400b4e01  cmp     eax, 4
0x1400b4e04  jbe     short loc_1400B4E43
0x1400b4e06  mov     edx, 1000h
0x1400b4e0b  lea     rcx, dword_140087708
0x1400b4e12  call    _tlgKeywordOn
0x1400b4e17  test    al, al
0x1400b4e19  jz      short loc_1400B4E43
0x1400b4e1b  mov     ecx, 74Dh
0x1400b4e20  lea     rax, aStartActiveLog; "Start active log mirroring."
0x1400b4e27  mov     r9d, edx; int
0x1400b4e2a  mov     qword ptr [rsp+180h+FileInformationClass], rax; char *
0x1400b4e2f  mov     edx, ecx; int
0x1400b4e31  mov     r8d, 4; int
0x1400b4e37  lea     rcx, aVhdmpimirrorth; "VhdmpiMirrorThread"
0x1400b4e3e  call    TraceEvents
0x1400b4e43  mov     rcx, rsi
0x1400b4e46  call    VhdmpiReleaseAllIo
0x1400b4e4b  mov     eax, cs:dword_140087708
0x1400b4e51  mov     edx, 40000h
0x1400b4e56  cmp     eax, 5
0x1400b4e59  jbe     short loc_1400B4EB3
0x1400b4e5b  lea     rcx, dword_140087708
0x1400b4e62  call    _tlgKeywordOn
0x1400b4e67  test    al, al
0x1400b4e69  jz      short loc_1400B4EB3
0x1400b4e6b  mov     eax, [rdi+310h]
0x1400b4e71  mov     ecx, 757h
0x1400b4e76  mov     dword ptr [rsp+180h+WaitBlockArray], eax
0x1400b4e7a  mov     r9d, edx; int
0x1400b4e7d  mov     rax, [rdi+0C8h]
0x1400b4e84  mov     edx, ecx; int
0x1400b4e86  mov     [rsp+180h+Timeout], rax
0x1400b4e8b  lea     rcx, aVhdmpimirrorth; "VhdmpiMirrorThread"
0x1400b4e92  mov     eax, [rdi+0C0h]
0x1400b4e98  mov     r8d, 5; int
0x1400b4e9e  mov     dword ptr [rsp+180h+Alertable], eax; char
0x1400b4ea2  lea     rax, aStartCopyingMi; "Start Copying MirrorBlocks. BlockSize %"...
0x1400b4ea9  mov     qword ptr [rsp+180h+FileInformationClass], rax; char *
0x1400b4eae  call    TraceEvents
0x1400b4eb3  xor     eax, eax
0x1400b4eb5  lea     rdx, [rbp+80h+var_80]; ActivityId
0x1400b4eb9  xorps   xmm0, xmm0
0x1400b4ebc  mov     [rbp+80h+var_70], rax
0x1400b4ec0  movups  xmmword ptr [rbp+80h+var_80.Data1], xmm0
0x1400b4ec4  lea     ecx, [rax+3]; ControlCode
0x1400b4ec7  call    cs:__imp_EtwActivityIdControl
0x1400b4ece  nop     dword ptr [rax+rax+00h]
0x1400b4ed3  lea     rax, [rbp+80h+ActivityId]
0x1400b4ed7  mov     [rbp+80h+var_70], rax
0x1400b4edb  mov     eax, cs:dword_1400876D0
0x1400b4ee1  cmp     eax, 4
0x1400b4ee4  jbe     short loc_1400B4F2D
  ... truncated ...
```
