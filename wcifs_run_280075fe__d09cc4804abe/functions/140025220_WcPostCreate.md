# WcPostCreate

- ea: `0x140025220`
- end: `0x140026079`
- name: `WcPostCreate`
- size: `3673`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `24`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callees

- `0x1400016b4`
- `0x1400020c4`
- `0x140002294`
- `0x140002be4`
- `0x140002e48`
- `0x140004310`
- `0x140004448`
- `0x1400048a4`
- `0x140004b0c`
- `0x140005050`
- `0x1400051b0`
- `0x1400053f8`
- `0x140006160`
- `0x14001c688`
- `0x140020754`
- `0x140025220`
- `0x140026080`
- `0x140026210`
- `0x140026b58`
- `0x140026c9c`
- `0x140026de0`
- `0x14002893c`
- `0x14002bd20`
- `0x14002f21c`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002537b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140025391`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140025e05`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140026068`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002537b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140025391`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140025e05`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140026068`
- `ntoskrnl!ObfDereferenceObject` at `0x1400255a1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400255b2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400255a1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400255b2`
- `FLTMGR!FltCancelFileOpen` at `0x140025700`
- `FLTMGR!FltCancelFileOpen` at `0x140025a5e`
- `FLTMGR!FltCancelFileOpen` at `0x140025c57`
- `FLTMGR!FltCancelFileOpen` at `0x140025cb2`
- `FLTMGR!FltCancelFileOpen` at `0x140025ee4`
- `FLTMGR!FltCancelFileOpen` at `0x140025700`
- `FLTMGR!FltCancelFileOpen` at `0x140025a5e`
- `FLTMGR!FltCancelFileOpen` at `0x140025c57`
- `FLTMGR!FltCancelFileOpen` at `0x140025cb2`
- `FLTMGR!FltCancelFileOpen` at `0x140025ee4`
- `FLTMGR!FltReissueSynchronousIo` at `0x14002553b`
- `FLTMGR!FltReissueSynchronousIo` at `0x140025e27`
- `FLTMGR!FltReissueSynchronousIo` at `0x14002553b`
- `FLTMGR!FltReissueSynchronousIo` at `0x140025e27`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140025338`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140025364`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140025dee`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140026051`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140025338`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140025364`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140025dee`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140026051`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002531a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002531a`
- `FLTMGR!FltReleaseContext` at `0x140025f5d`
- `FLTMGR!FltReleaseContext` at `0x140025f5d`

## string_xrefs

- `0x1400252e8`: `onecore\base\fs\wci\wcifs\create.c`
- `0x14002562e`: `onecore\base\fs\wci\wcifs\create.c`
- `0x14002586e`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025a00`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025a50`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025b60`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025be0`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025d07`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025d53`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025e7f`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025f8d`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WcPostCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, unsigned int *a3)
{
  char v5; // cl
  ULONG_PTR *p_Information; // r14
  _QWORD *v8; // r15
  IO_STATUS_BLOCK *p_IoStatus; // rsi
  char v10; // r12
  int v11; // edx
  USHORT UnparsedNameLength; // di
  unsigned int v13; // eax
  PFLT_CONTEXT v14; // r9
  _QWORD *v15; // r10
  ULONG_PTR *v16; // r8
  int v17; // r11d
  NTSTATUS v18; // ecx
  char v19; // r12
  unsigned int v20; // edi
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // r8
  PFLT_IO_PARAMETER_BLOCK v25; // rcx
  NTSTATUS Status; // eax
  PFLT_IO_PARAMETER_BLOCK v27; // r9
  ULONG Options; // r8d
  int v29; // eax
  int v30; // r8d
  int v31; // r9d
  ULONG_PTR v32; // rax
  __int64 v33; // rcx
  ULONG_PTR *v34; // rax
  int v35; // eax
  int v36; // r8d
  int v37; // edx
  int v38; // r8d
  int v39; // r9d
  int v40; // eax
  int v41; // edx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  int v43; // r9d
  ULONG_PTR v44; // rdi
  PFLT_INSTANCE *v45; // rax
  PFLT_INSTANCE *v46; // rsi
  PFILE_OBJECT *v47; // rdi
  struct _FILE_OBJECT *v48; // rdx
  struct _FLT_INSTANCE *v49; // rcx
  int SetStreamHandleContext; // eax
  int v51; // edx
  PFLT_CONTEXT v52; // rcx
  int v53; // r11d
  int v54; // [rsp+20h] [rbp-D8h]
  int *v55; // [rsp+28h] [rbp-D0h]
  char *v56; // [rsp+30h] [rbp-C8h]
  char v57; // [rsp+30h] [rbp-C8h]
  __int64 v58; // [rsp+38h] [rbp-C0h]
  int IsTombstoneByName; // [rsp+60h] [rbp-98h]
  char v60[8]; // [rsp+68h] [rbp-90h] BYREF
  ULONG_PTR *v61; // [rsp+70h] [rbp-88h]
  PFLT_CONTEXT Context; // [rsp+78h] [rbp-80h]
  int v63; // [rsp+80h] [rbp-78h]
  PFLT_INSTANCE *v64; // [rsp+88h] [rbp-70h]
  int v65; // [rsp+90h] [rbp-68h] BYREF
  PVOID Object; // [rsp+98h] [rbp-60h]
  ULONG_PTR *v67; // [rsp+A0h] [rbp-58h]
  ULONG_PTR *v68; // [rsp+A8h] [rbp-50h]
  char v69; // [rsp+110h] [rbp+18h] BYREF

  v5 = 0;
  IsTombstoneByName = 0;
  v60[0] = 0;
  p_Information = &CallbackData->IoStatus.Information;
  v69 = 0;
  v8 = (_QWORD *)(a2 + 24);
  v63 = 0;
  p_IoStatus = &CallbackData->IoStatus;
  Object = 0;
  v10 = 0;
  v65 = 0;
  v11 = 0;
  UnparsedNameLength = 0;
  while ( 1 )
  {
    v13 = a3[5];
    v68 = p_Information;
    v14 = v8;
    Context = v8;
    v15 = v8;
    v67 = p_Information;
    v16 = p_Information;
    v64 = (PFLT_INSTANCE *)v8;
    v61 = p_Information;
    if ( (v13 & 1) == 0 )
      goto LABEL_3;
    Status = CallbackData->IoStatus.Status;
    p_IoStatus = &CallbackData->IoStatus;
    if ( Status != 260 )
    {
      if ( Status )
        goto LABEL_3;
      v35 = WcProcessWciReparsePointOpen(CallbackData, *v8, *(_QWORD *)(a2 + 32), 0);
      IsTombstoneByName = v35;
      v17 = v35;
      if ( v35 == -1073741772 )
      {
        v40 = WcSetDispositionFile(*v8, *(_QWORD *)(a2 + 32));
        v19 = v40;
        if ( v40 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v41) = 2;
          WPP_RECORDER_SF_sDqd(
            WPP_GLOBAL_Control->DeviceExtension,
            v41,
            5,
            65,
            (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
            136,
            *(_QWORD *)(a2 + 32),
            v40);
        }
        FltCancelFileOpen((PFLT_INSTANCE)*v8, *(PFILE_OBJECT *)(a2 + 32));
        Iopb = CallbackData->Iopb;
        p_IoStatus->Status = -1073741772;
        *p_Information = 0;
        if ( (Iopb->Parameters.Create.Options & 0x2000) != 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            goto LABEL_8;
          }
          v43 = 66;
          v58 = *(_QWORD *)(a2 + 32) + 88LL;
          v57 = -110;
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            goto LABEL_8;
          }
          v43 = 67;
          v58 = *((_QWORD *)a3 + 6) + 8LL;
          v57 = -108;
        }
        WPP_RECORDER_SF_sDZ(
          WcVerboseRecorder,
          5,
          5,
          v43,
          (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
          v57,
          v58);
        v20 = 0;
        goto LABEL_9;
      }
      if ( v35 == -1073741195 )
      {
        IsTombstoneByName = WcClearOfflineAttribute(*(PFILE_OBJECT *)(a2 + 32), (PFLT_INSTANCE)*v8);
        if ( IsTombstoneByName < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v37) = 2;
            WPP_RECORDER_SF_sDqd(
              WPP_GLOBAL_Control->DeviceExtension,
              v37,
              5,
              68,
              (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
              171,
              *(_QWORD *)(a2 + 32),
              IsTombstoneByName);
          }
          FltCancelFileOpen((PFLT_INSTANCE)*v8, *(PFILE_OBJECT *)(a2 + 32));
          p_IoStatus->Status = IsTombstoneByName;
          *p_Information = 0;
          goto LABEL_7;
        }
        IsTombstoneByName = WcClearSparseAttribute(*(PFILE_OBJECT *)(a2 + 32), (PFLT_INSTANCE)*v8);
        v17 = IsTombstoneByName;
        if ( IsTombstoneByName < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v11) = 2;
            WPP_RECORDER_SF_sDqd(
              WPP_GLOBAL_Control->DeviceExtension,
              v11,
              5,
              69,
              (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
              195,
              *(_QWORD *)(a2 + 32),
              IsTombstoneByName);
          }
LABEL_107:
          FltCancelFileOpen((PFLT_INSTANCE)*v8, *(PFILE_OBJECT *)(a2 + 32));
          v19 = IsTombstoneByName;
          p_IoStatus->Status = IsTombstoneByName;
          *p_Information = 0;
          goto LABEL_8;
        }
      }
      else
      {
        if ( v35 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_sDqDld(
              WPP_GLOBAL_Control->DeviceExtension,
              CallbackData->Iopb->Parameters.Create.Options & 0xFFFFFF,
              v36,
              70,
              v54,
              (_DWORD)v55,
              215,
              *(_QWORD *)(a2 + 32),
              CallbackData->Iopb->Parameters.Create.Options,
              HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass),
              v35);
          goto LABEL_107;
        }
        if ( v35 == 259 )
        {
          v20 = 1;
          v19 = 3;
          goto LABEL_9;
        }
        if ( v35 == 260 )
        {
          v17 = 0;
          IsTombstoneByName = 0;
          if ( !*((_QWORD *)a3 + 7) )
          {
            v44 = a3[4];
            FltCancelFileOpen((PFLT_INSTANCE)*v8, *(PFILE_OBJECT *)(a2 + 32));
            *p_Information = v44;
            v20 = 0;
            v19 = 0;
            p_IoStatus->Status = -1073741191;
            goto LABEL_9;
          }
        }
        v10 = 1;
      }
      v16 = p_Information;
      v14 = v8;
      v15 = v8;
      goto LABEL_4;
    }
    v27 = CallbackData->Iopb;
    Options = v27->Parameters.Create.Options;
    if ( (Options & 0x2000) != 0 )
    {
      p_IoStatus->Status = -1073741766;
      *p_Information = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sDqZDld(
          WPP_GLOBAL_Control->DeviceExtension,
          v27->Parameters.Create.Options & 0xFFFFFF,
          *(_QWORD *)(a2 + 32),
          (_DWORD)v27,
          v54,
          (_DWORD)v55,
          (_DWORD)v56,
          *(_QWORD *)(a2 + 32),
          *(_QWORD *)(a2 + 32) + 88LL,
          (char)v27->Parameters.QueryEa.EaList,
          HIBYTE(v27->Parameters.SetVolumeInformation.FsInformationClass),
          58);
      goto LABEL_7;
    }
    if ( v5 )
    {
      p_IoStatus->Status = -1073741766;
      *p_Information = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sDqDld(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          Options,
          60,
          v54,
          (_DWORD)v55,
          182,
          *(_QWORD *)(a2 + 32),
          (char)v27->Parameters.QueryEa.EaList,
          HIBYTE(v27->Parameters.SetVolumeInformation.FsInformationClass),
          58);
      goto LABEL_7;
    }
    if ( UnparsedNameLength == CallbackData->TagData->UnparsedNameLength
      && !v11
      && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_sDDqDlZ(
        WPP_GLOBAL_Control->DeviceExtension,
        a3[12] + 8,
        Options & 0xFFFFFF,
        (_DWORD)v27,
        v54,
        (_DWORD)v55,
        (_DWORD)v56,
        UnparsedNameLength,
        *(_QWORD *)(a2 + 32),
        Options,
        SHIBYTE(Options),
        *((_QWORD *)a3 + 6) + 8LL);
    }
    v8 = (_QWORD *)(a2 + 24);
    UnparsedNameLength = CallbackData->TagData->UnparsedNameLength;
    v56 = &v69;
    v55 = &v65;
    LOWORD(v54) = UnparsedNameLength;
    v29 = WcProcessWciReparsePointBounce(CallbackData, *(_QWORD *)(a2 + 24), a3[4], *((_QWORD *)a3 + 6));
    IsTombstoneByName = v29;
    if ( v29 < 0 )
    {
      p_IoStatus->Status = v29;
      *p_Information = 0;
      if ( v29 == -1073741772 || v29 == -1073741766 )
      {
        v19 = v29;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_sDZDld(
            WPP_GLOBAL_Control->DeviceExtension,
            CallbackData->Iopb->Parameters.Create.Options & 0xFFFFFF,
            v30,
            v31,
            v54,
            (unsigned int)&v65,
            (unsigned int)&v69,
            *((_QWORD *)a3 + 6) + 8LL,
            CallbackData->Iopb->Parameters.Create.Options,
            HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass),
            v29);
          goto LABEL_7;
        }
        v19 = v29;
      }
LABEL_8:
      v20 = 0;
      goto LABEL_9;
    }
    if ( v63 == 2 )
    {
      v20 = 0;
      v19 = v29;
      goto LABEL_9;
    }
    a3[5] = -2147483644;
    *((_WORD *)a3 + 21) = 0;
    if ( v69 )
      a3[5] = 0x80000000;
    FltReissueSynchronousIo((PFLT_INSTANCE)*v8, CallbackData);
    if ( p_IoStatus->Status < 0 )
      break;
    p_Information = &CallbackData->IoStatus.Information;
    if ( CallbackData->IoStatus.Information == 2 )
    {
      IsTombstoneByName = WcSetPlaceHolderFlagsSynchronized(CallbackData, (PVOID)*v8, Object);
      v17 = IsTombstoneByName;
      if ( IsTombstoneByName < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_sDDld(
          WPP_GLOBAL_Control->DeviceExtension,
          CallbackData->Iopb->Parameters.Create.Options & 0xFFFFFF,
          v38,
          v39,
          v54,
          (unsigned int)&v65,
          (unsigned int)&v69,
          (char)CallbackData->Iopb->Parameters.QueryEa.EaList,
          HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass),
          IsTombstoneByName);
        v17 = IsTombstoneByName;
      }
      v14 = Context;
      v16 = v61;
      v15 = Context;
      goto LABEL_4;
    }
    if ( Object )
    {
      ObfDereferenceObject(Object);
      Object = 0;
    }
    v5 = v69;
    v11 = v65;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_sDZd(
      WcVerboseRecorder,
      5,
      5,
      63,
      (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
      57,
      *((_QWORD *)a3 + 6) + 8LL,
      p_IoStatus->Status);
  v14 = Context;
  v16 = p_Information;
  v15 = Context;
LABEL_3:
  v17 = IsTombstoneByName;
LABEL_4:
  v18 = p_IoStatus->Status;
  if ( p_IoStatus->Status >= 0 )
    goto LABEL_21;
  if ( (a3[5] & 1) != 0
    || v18 != -1073741638
    && v18 != -1073741565
    && (v18 != -1073741771 || HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass) != 2) )
  {
    goto LABEL_6;
  }
  if ( (CallbackData->Iopb->Parameters.Create.Options & 0x2000) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_6;
    LOBYTE(v11) = 3;
    WPP_RECORDER_SF_sDZ(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      5,
      71,
      (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
      37,
      *(_QWORD *)(a2 + 32) + 88LL);
    v17 = IsTombstoneByName;
LABEL_34:
    v16 = v61;
    goto LABEL_6;
  }
  IsTombstoneByName = WcIsTombstoneByName(a2, *((_QWORD *)a3 + 6) + 8LL, v60, v14);
  v17 = IsTombstoneByName;
  if ( IsTombstoneByName < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 3;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        5,
        72,
        (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
        47,
        IsTombstoneByName);
    }
    v17 = 0;
    LOBYTE(IsTombstoneByName) = 0;
    goto LABEL_34;
  }
  if ( !v60[0] )
    goto LABEL_34;
  v16 = v61;
  p_IoStatus->Status = 260;
  *v16 = 2684354591LL;
LABEL_6:
  v18 = p_IoStatus->Status;
  if ( p_IoStatus->Status < 0 )
    goto LABEL_7;
  v14 = Context;
  v15 = Context;
LABEL_21:
  if ( v18 == 260 )
  {
    v32 = *v16;
    if ( *v16 == 2684354591 )
    {
      if ( !(unsigned __int8)WcUnionExistsForFileObject(CallbackData, *v15, *(_QWORD *)(a2 + 32), v14) )
      {
        if ( (CallbackData->Iopb->Parameters.Create.Options & 0x200000) != 0 )
        {
          FltRemoveOpenReparseEntry(Globals, CallbackData, *((_QWORD *)a3 + 7));
          ExFreeToPagedLookasideList(&stru_14000E380, *((PVOID *)a3 + 7));
          v45 = v64;
          *((_QWORD *)a3 + 7) = 0;
          FltReissueSynchronousIo(*v45, CallbackData);
          goto LABEL_22;
        }
LABEL_7:
        v19 = IsTombstoneByName;
        goto LABEL_8;
      }
      IsTombstoneByName = WcProcessTombstoneBounce(CallbackData, *v64);
      v17 = IsTombstoneByName;
      if ( IsTombstoneByName >= 0 )
        goto LABEL_22;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          5,
          73,
          (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
          126,
          IsTombstoneByName);
        v17 = IsTombstoneByName;
      }
      v34 = v67;
LABEL_60:
      v19 = IsTombstoneByName;
      p_IoStatus->Status = v17;
      *v34 = 0;
      goto LABEL_131;
    }
    v33 = *((_QWORD *)a3 + 8);
    if ( v33 )
    {
      if ( (*(_DWORD *)(v33 + 20) & 1) == 0 )
        goto LABEL_56;
    }
    else if ( (v32 & 0x20000000) == 0 || v32 == 2684354572 || v32 == 2684354563 )
    {
      goto LABEL_56;
    }
    v17 = WcProcessWciLinkBounce(CallbackData);
LABEL_56:
    IsTombstoneByName = v17;
    if ( v17 >= 0 )
      goto LABEL_22;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        5,
        74,
        (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
        163,
        v17);
      v17 = IsTombstoneByName;
    }
    v34 = v68;
    goto LABEL_60;
  }
LABEL_22:
  if ( p_IoStatus->Status )
    goto LABEL_24;
  v25 = CallbackData->Iopb;
  if ( (v25->Parameters.Create.Options & 0x1000) == 0 || v63 == 2 || (v25->OperationFlags & 2) != 0 )
    goto LABEL_24;
  v48 = *(struct _FILE_OBJECT **)(a2 + 32);
  v49 = *(struct _FLT_INSTANCE **)(a2 + 24);
  Context = 0;
  SetStreamHandleContext = WcGetSetStreamHandleContext(v49, v48);
  v52 = Context;
  v53 = SetStreamHandleContext;
  IsTombstoneByName = SetStreamHandleContext;
  if ( SetStreamHandleContext >= 0 )
    *((_DWORD *)Context + 10) |= 1u;
  if ( v52 )
  {
    FltReleaseContext(v52);
    v53 = IsTombstoneByName;
  }
  v47 = (PFILE_OBJECT *)(a2 + 32);
  v46 = (PFLT_INSTANCE *)(a2 + 24);
  if ( v53 >= 0 )
  {
LABEL_24:
    if ( v10 )
      WcAcknowledgeRedirectionEcp(CallbackData, *(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
    WcHandleQueryOnCreateEcp(CallbackData, *(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
    goto LABEL_7;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v46 = (PFLT_INSTANCE *)(a2 + 24);
    v47 = (PFILE_OBJECT *)(a2 + 32);
  }
  else
  {
    LOBYTE(v51) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v51,
      5,
      75,
      (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
      190,
      v53);
  }
  FltCancelFileOpen(*v46, *v47);
  v19 = IsTombstoneByName;
  CallbackData->IoStatus.Status = IsTombstoneByName;
  CallbackData->IoStatus.Information = 0;
LABEL_131:
  v20 = 0;
LABEL_9:
  if ( Object )
    ObfDereferenceObject(Object);
  v21 = *((_QWORD *)a3 + 6);
  if ( v21 )
  {
    if ( CallbackData->IoStatus.Status == -1073741191
      && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 3;
      WPP_RECORDER_SF_sDdZ(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        5,
        76,
        (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
        228,
        v19,
        v21 + 8);
    }
    FltReleaseFileNameInformation(*((PFLT_FILE_NAME_INFORMATION *)a3 + 6));
  }
  if ( *(unsigned int **)a3 != a3 )
    FltRemoveOpenReparseEntry(Globals, CallbackData, a3);
  v22 = *((_QWORD *)a3 + 8);
  if ( v22 )
  {
    FltRemoveOpenReparseEntry(Globals, CallbackData, v22);
    ExFreeToPagedLookasideList(&stru_14000E380, *((PVOID *)a3 + 8));
  }
  v23 = *((_QWORD *)a3 + 7);
  if ( v23 )
  {
    FltRemoveOpenReparseEntry(Globals, CallbackData, v23);
    ExFreeToPagedLookasideList(&stru_14000E380, *((PVOID *)a3 + 7));
  }
  ExFreeToPagedLookasideList(&stru_14000E400, a3);
  return v20;
}

```

## disassembly

```asm
0x140025220  mov     r11, rsp
0x140025223  push    rbx
0x140025224  push    rbp
0x140025225  push    rsi
0x140025226  push    rdi
0x140025227  push    r12
0x140025229  push    r13
0x14002522b  push    r14
0x14002522d  push    r15
0x14002522f  sub     rsp, 0B8h
0x140025236  xor     eax, eax
0x140025238  mov     rbp, rcx
0x14002523b  mov     r13, rdx
0x14002523e  mov     [rsp+0F8h+var_94], eax
0x140025242  xor     cl, cl
0x140025244  mov     [rsp+0F8h+var_98], eax
0x140025248  mov     rbx, r8
0x14002524b  mov     [rsp+0F8h+var_90], al
0x14002524f  lea     r14, [rbp+20h]
0x140025253  mov     [r11+18h], cl
0x140025257  lea     r15, [r13+18h]
0x14002525b  mov     [r11-78h], eax
0x14002525f  lea     rsi, [rbp+18h]
0x140025263  mov     [r11-60h], rax
0x140025267  xor     r12b, r12b
0x14002526a  mov     [r11-68h], eax
0x14002526e  mov     edx, eax
0x140025270  mov     edi, eax
0x140025272  mov     eax, [rbx+14h]
0x140025275  lea     r11, WPP_RECORDER_INITIALIZED
0x14002527c  mov     [rsp+0F8h+var_50], r14
0x140025284  mov     r9, r15
0x140025287  mov     [rsp+0F8h+Context], r15
0x14002528c  mov     r10, r15
0x14002528f  mov     [rsp+0F8h+var_58], r14
0x140025297  mov     r8, r14
0x14002529a  mov     [rsp+0F8h+var_70], r15
0x1400252a2  mov     [rsp+0F8h+var_88], r14
0x1400252a7  test    al, 1
0x1400252a9  jnz     loc_140025468
0x1400252af  mov     r11d, [rsp+0F8h+var_98]
0x1400252b4  mov     ecx, [rsi]
0x1400252b6  mov     edi, 0A000001Fh
0x1400252bb  test    ecx, ecx
0x1400252bd  jns     loc_1400253B4
0x1400252c3  mov     eax, [rbx+14h]
0x1400252c6  test    al, 1
0x1400252c8  jz      loc_1400253F4
0x1400252ce  mov     ecx, [rsi]
0x1400252d0  test    ecx, ecx
0x1400252d2  jns     loc_140025DAF
0x1400252d8  mov     r12d, [rsp+0F8h+var_98]
0x1400252dd  mov     edi, [rsp+0F8h+var_94]
0x1400252e1  lea     rsi, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x1400252e8  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400252ef  mov     rcx, [rsp+0F8h+Object]; Object
0x1400252f7  test    rcx, rcx
0x1400252fa  jnz     loc_1400255A1
0x140025300  mov     rax, [rbx+30h]
0x140025304  test    rax, rax
0x140025307  jz      short loc_140025326
0x140025309  cmp     dword ptr [rbp+18h], 0C0000279h
0x140025310  jz      loc_140025FF0
0x140025316  mov     rcx, [rbx+30h]; FileNameInformation
0x14002531a  call    cs:__imp_FltReleaseFileNameInformation
0x140025321  nop     dword ptr [rax+rax+00h]
0x140025326  cmp     [rbx], rbx
0x140025329  jz      short loc_140025344
0x14002532b  mov     rcx, cs:Globals
0x140025332  mov     r8, rbx
0x140025335  mov     rdx, rbp
0x140025338  call    cs:__imp_FltRemoveOpenReparseEntry
0x14002533f  nop     dword ptr [rax+rax+00h]
0x140025344  mov     r8, [rbx+40h]
0x140025348  test    r8, r8
0x14002534b  jnz     loc_140026047
0x140025351  mov     r8, [rbx+38h]
0x140025355  test    r8, r8
0x140025358  jz      short loc_140025387
0x14002535a  mov     rcx, cs:Globals
0x140025361  mov     rdx, rbp
0x140025364  call    cs:__imp_FltRemoveOpenReparseEntry
0x14002536b  nop     dword ptr [rax+rax+00h]
0x140025370  mov     rdx, [rbx+38h]; Entry
0x140025374  lea     rcx, stru_14000E380; Lookaside
0x14002537b  call    cs:__imp_ExFreeToPagedLookasideList
0x140025382  nop     dword ptr [rax+rax+00h]
0x140025387  mov     rdx, rbx; Entry
0x14002538a  lea     rcx, stru_14000E400; Lookaside
0x140025391  call    cs:__imp_ExFreeToPagedLookasideList
0x140025398  nop     dword ptr [rax+rax+00h]
0x14002539d  mov     eax, edi
0x14002539f  add     rsp, 0B8h
0x1400253a6  pop     r15
0x1400253a8  pop     r14
0x1400253aa  pop     r13
0x1400253ac  pop     r12
0x1400253ae  pop     rdi
0x1400253af  pop     rsi
0x1400253b0  pop     rbp
0x1400253b1  pop     rbx
0x1400253b2  retn
0x1400253b4  cmp     ecx, 104h
0x1400253ba  jz      loc_1400255CC
0x1400253c0  cmp     dword ptr [rsi], 0
0x1400253c3  jnz     short loc_1400253D6
0x1400253c5  mov     rcx, [rbp+10h]
0x1400253c9  test    dword ptr [rcx+20h], 1000h
0x1400253d0  jnz     loc_140025F11
0x1400253d6  test    r12b, r12b
0x1400253d9  jnz     loc_140025FDB
0x1400253df  mov     r8, [r13+20h]; FileObject
0x1400253e3  mov     rcx, rbp; CallbackData
0x1400253e6  mov     rdx, [r13+18h]; Instance
0x1400253ea  call    WcHandleQueryOnCreateEcp
0x1400253ef  jmp     loc_1400252D8
0x1400253f4  cmp     ecx, 0C00000BAh
0x1400253fa  jz      short loc_14002541E
0x1400253fc  cmp     ecx, 0C0000103h
0x140025402  jz      short loc_14002541E
0x140025404  cmp     ecx, 0C0000035h
0x14002540a  jnz     loc_1400252CE
0x140025410  mov     rax, [rbp+10h]
0x140025414  cmp     byte ptr [rax+23h], 2
0x140025418  jnz     loc_1400252CE
0x14002541e  mov     rax, [rbp+10h]
0x140025422  test    dword ptr [rax+20h], 2000h
0x140025429  jnz     loc_140025CD3
0x14002542f  mov     rdx, [rbx+30h]
0x140025433  lea     r8, [rsp+0F8h+var_90]
0x140025438  add     rdx, 8
0x14002543c  mov     rcx, r13
0x14002543f  call    WcIsTombstoneByName
0x140025444  mov     [rsp+0F8h+var_98], eax
0x140025448  mov     r11d, eax
0x14002544b  test    eax, eax
0x14002544d  js      loc_140025D3C
0x140025453  cmp     [rsp+0F8h+var_90], 0
0x140025458  jnz     loc_140025D9C
0x14002545e  mov     r8, [rsp+0F8h+var_88]
0x140025463  jmp     loc_1400252CE
0x140025468  mov     eax, [rbp+18h]
0x14002546b  lea     rsi, [rbp+18h]
0x14002546f  cmp     eax, 104h
0x140025474  jnz     loc_140025694
0x14002547a  mov     r9, [rbp+10h]
0x14002547e  mov     r8d, [r9+20h]
0x140025482  bt      r8d, 0Dh
0x140025487  jb      loc_14002597F
0x14002548d  test    cl, cl
0x14002548f  jnz     loc_14002591A
0x140025495  mov     rax, [rbp+28h]
0x140025499  cmp     di, [rax+6]
0x14002549d  jz      loc_14002571A
0x1400254a3  mov     rax, [rbp+28h]
0x1400254a7  lea     r15, [r13+18h]
0x1400254ab  mov     r9, [rbx+30h]
0x1400254af  mov     rcx, rbp
0x1400254b2  mov     r8d, [rbx+10h]
0x1400254b6  mov     rdx, [r15]
0x1400254b9  movzx   edi, word ptr [rax+6]
0x1400254bd  lea     rax, [rsp+0F8h+Object]
0x1400254c5  mov     [rsp+0F8h+var_B8], rax
0x1400254ca  lea     rax, [rsp+0F8h+var_78]
0x1400254d2  mov     [rsp+0F8h+var_C0], rax
0x1400254d7  lea     rax, [rsp+0F8h+arg_10]
0x1400254df  mov     [rsp+0F8h+var_C8], rax
0x1400254e4  lea     rax, [rsp+0F8h+var_68]
0x1400254ec  mov     [rsp+0F8h+var_D0], rax
0x1400254f1  mov     word ptr [rsp+0F8h+var_D8], di
0x1400254f6  call    WcProcessWciReparsePointBounce
0x1400254fb  mov     [rsp+0F8h+var_98], eax
0x1400254ff  mov     r11d, eax
0x140025502  test    eax, eax
0x140025504  js      loc_1400258A2
0x14002550a  cmp     [rsp+0F8h+var_78], 2
0x140025512  jz      loc_140025898
0x140025518  xor     eax, eax
0x14002551a  mov     dword ptr [rbx+14h], 80000004h
0x140025521  mov     [rbx+2Ah], ax
0x140025525  cmp     [rsp+0F8h+arg_10], al
0x14002552c  jz      short loc_140025535
0x14002552e  mov     dword ptr [rbx+14h], 80000000h
0x140025535  mov     rcx, [r15]; InitiatingInstance
0x140025538  mov     rdx, rbp; CallbackData
0x14002553b  call    cs:__imp_FltReissueSynchronousIo
0x140025542  nop     dword ptr [rax+rax+00h]
0x140025547  mov     ecx, [rsi]
0x140025549  test    ecx, ecx
0x14002554b  jns     short loc_140025571
0x14002554d  lea     rax, WPP_RECORDER_INITIALIZED
0x140025554  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002555b  jnz     loc_140025834
0x140025561  mov     r9, [rsp+0F8h+Context]
0x140025566  mov     r8, r14
0x140025569  mov     r10, r9
0x14002556c  jmp     loc_1400252AF
0x140025571  cmp     qword ptr [rbp+20h], 2
0x140025576  lea     r14, [rbp+20h]
0x14002557a  jz      loc_1400257BB
0x140025580  mov     rcx, [rsp+0F8h+Object]; Object
0x140025588  test    rcx, rcx
0x14002558b  jnz     short loc_1400255B2
0x14002558d  movzx   ecx, [rsp+0F8h+arg_10]
0x140025595  mov     edx, [rsp+0F8h+var_68]
0x14002559c  jmp     loc_140025272
0x1400255a1  call    cs:__imp_ObfDereferenceObject
0x1400255a8  nop     dword ptr [rax+rax+00h]
0x1400255ad  jmp     loc_140025300
0x1400255b2  call    cs:__imp_ObfDereferenceObject
0x1400255b9  nop     dword ptr [rax+rax+00h]
0x1400255be  mov     [rsp+0F8h+Object], 0
0x1400255ca  jmp     short loc_14002558D
0x1400255cc  mov     rax, [r8]
0x1400255cf  cmp     rax, rdi
0x1400255d2  jz      loc_140025DBC
0x1400255d8  mov     rcx, [rbx+40h]
0x1400255dc  test    rcx, rcx
0x1400255df  jnz     loc_140025777
0x1400255e5  bt      rax, 1Dh
0x1400255ea  jnb     short loc_140025612
0x1400255ec  mov     ecx, 0A000000Ch
0x1400255f1  cmp     rax, rcx
0x1400255f4  jz      short loc_140025612
0x1400255f6  mov     ecx, 0A0000003h
0x1400255fb  cmp     rax, rcx
0x1400255fe  jz      short loc_140025612
0x140025600  mov     r8, [r13+20h]
0x140025604  mov     rcx, rbp; Data
0x140025607  mov     rdx, [r9]
0x14002560a  call    WcProcessWciLinkBounce
0x14002560f  mov     r11d, eax
0x140025612  mov     [rsp+0F8h+var_98], r11d
0x140025617  test    r11d, r11d
0x14002561a  jns     loc_1400253C0
0x140025620  lea     rax, WPP_RECORDER_INITIALIZED
0x140025627  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002562e  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140025635  jz      short loc_140025678
0x140025637  mov     rcx, cs:WPP_GLOBAL_Control
0x14002563e  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140025645  mov     dword ptr [rsp+0F8h+var_C0], r11d
0x14002564a  mov     r9d, 4Ah ; 'J'
0x140025650  mov     dword ptr [rsp+0F8h+var_C8], 0CA3h
0x140025658  mov     r8d, 5
0x14002565e  mov     [rsp+0F8h+var_D0], r14
0x140025663  mov     dl, 2
0x140025665  mov     rcx, [rcx+40h]
0x140025669  mov     [rsp+0F8h+var_D8], rax
0x14002566e  call    WPP_RECORDER_SF_sDd
0x140025673  mov     r11d, [rsp+0F8h+var_98]
0x140025678  mov     rax, [rsp+0F8h+var_50]
0x140025680  mov     r12d, [rsp+0F8h+var_98]
0x140025685  mov     [rsi], r11d
0x140025688  mov     qword ptr [rax], 0
0x14002568f  jmp     loc_140025F01
0x140025694  test    eax, eax
0x140025696  jnz     loc_1400252AF
0x14002569c  mov     r8, [r13+20h]
0x1400256a0  xor     r9d, r9d
0x1400256a3  mov     rdx, [r15]
0x1400256a6  mov     rcx, rbp
0x1400256a9  call    WcProcessWciReparsePointOpen
0x1400256ae  mov     [rsp+0F8h+var_98], eax
0x1400256b2  mov     r11d, eax
0x1400256b5  cmp     eax, 0C0000034h
0x1400256ba  jz      loc_1400259DF
0x1400256c0  cmp     eax, 0C0000275h
0x1400256c5  jnz     loc_140025787
0x1400256cb  mov     rdx, [r15]; Instance
0x1400256ce  mov     rcx, [r13+20h]; FileObject
0x1400256d2  call    WcClearOfflineAttribute
0x1400256d7  mov     [rsp+0F8h+var_98], eax
0x1400256db  mov     edi, eax
0x1400256dd  test    eax, eax
0x1400256df  jns     loc_140025B8E
0x1400256e5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400256ec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400256f3  jnz     loc_140025B3E
0x1400256f9  mov     rdx, [r13+20h]; FileObject
0x1400256fd  mov     rcx, [r15]; Instance
0x140025700  call    cs:__imp_FltCancelFileOpen
0x140025707  nop     dword ptr [rax+rax+00h]
0x14002570c  mov     [rsi], edi
0x14002570e  mov     qword ptr [r14], 0
0x140025715  jmp     loc_1400252D8
0x14002571a  test    edx, edx
0x14002571c  jnz     loc_1400254A3
0x140025722  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x140025729  jz      loc_1400254A3
0x14002572f  mov     rdx, [rbx+30h]
0x140025733  mov     eax, r8d
0x140025736  shr     eax, 18h
0x140025739  add     rdx, 8
0x14002573d  mov     [rsp+0F8h+var_A0], rdx
0x140025742  and     r8d, 0FFFFFFh
0x140025749  mov     [rsp+0F8h+var_A8], eax
0x14002574d  mov     rax, [r13+20h]
0x140025751  mov     [rsp+0F8h+var_B0], r8d
0x140025756  movzx   ecx, di
  ... truncated ...
```
