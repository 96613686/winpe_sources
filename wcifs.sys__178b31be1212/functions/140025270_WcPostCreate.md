# WcPostCreate

- ea: `0x140025270`
- end: `0x1400260c9`
- name: `WcPostCreate`
- size: `3673`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, unsigned int *)`
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
- `0x140025270`
- `0x1400260d0`
- `0x140026260`
- `0x140026ba8`
- `0x140026cec`
- `0x140026e30`
- `0x14002898c`
- `0x14002bd70`
- `0x14002f26c`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400253cb`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400253e1`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140025e55`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400260b8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400253cb`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400253e1`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140025e55`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400260b8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400255f1`
- `ntoskrnl!ObfDereferenceObject` at `0x140025602`
- `ntoskrnl!ObfDereferenceObject` at `0x1400255f1`
- `ntoskrnl!ObfDereferenceObject` at `0x140025602`
- `FLTMGR!FltCancelFileOpen` at `0x140025750`
- `FLTMGR!FltCancelFileOpen` at `0x140025aae`
- `FLTMGR!FltCancelFileOpen` at `0x140025ca7`
- `FLTMGR!FltCancelFileOpen` at `0x140025d02`
- `FLTMGR!FltCancelFileOpen` at `0x140025f34`
- `FLTMGR!FltCancelFileOpen` at `0x140025750`
- `FLTMGR!FltCancelFileOpen` at `0x140025aae`
- `FLTMGR!FltCancelFileOpen` at `0x140025ca7`
- `FLTMGR!FltCancelFileOpen` at `0x140025d02`
- `FLTMGR!FltCancelFileOpen` at `0x140025f34`
- `FLTMGR!FltReissueSynchronousIo` at `0x14002558b`
- `FLTMGR!FltReissueSynchronousIo` at `0x140025e77`
- `FLTMGR!FltReissueSynchronousIo` at `0x14002558b`
- `FLTMGR!FltReissueSynchronousIo` at `0x140025e77`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140025388`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x1400253b4`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140025e3e`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x1400260a1`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140025388`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x1400253b4`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x140025e3e`
- `FLTMGR!FltRemoveOpenReparseEntry` at `0x1400260a1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002536a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002536a`
- `FLTMGR!FltReleaseContext` at `0x140025fad`
- `FLTMGR!FltReleaseContext` at `0x140025fad`

## string_xrefs

- `0x140025338`: `onecore\base\fs\wci\wcifs\create.c`
- `0x14002567e`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400258be`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025a50`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025aa0`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025bb0`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025c30`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025d57`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025da3`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025ecf`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140025fdd`: `onecore\base\fs\wci\wcifs\create.c`

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
            wil_details_featureDescriptors_a->DeviceExtension,
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
            || !LOWORD(wil_details_featureDescriptors_a->DeviceType) )
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
            || !LOWORD(wil_details_featureDescriptors_a->DeviceType) )
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
              wil_details_featureDescriptors_a->DeviceExtension,
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
              wil_details_featureDescriptors_a->DeviceExtension,
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
              wil_details_featureDescriptors_a->DeviceExtension,
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
          wil_details_featureDescriptors_a->DeviceExtension,
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
          wil_details_featureDescriptors_a->DeviceExtension,
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
        wil_details_featureDescriptors_a->DeviceExtension,
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
            wil_details_featureDescriptors_a->DeviceExtension,
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
          wil_details_featureDescriptors_a->DeviceExtension,
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
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && LOWORD(wil_details_featureDescriptors_a->DeviceType) )
  {
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
  }
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
      wil_details_featureDescriptors_a->DeviceExtension,
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
        wil_details_featureDescriptors_a->DeviceExtension,
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
  v15 = Context;
LABEL_21:
  if ( v18 == 260 )
  {
    v32 = *v16;
    if ( *v16 == 2684354591 )
    {
      if ( !(unsigned __int8)WcUnionExistsForFileObject(CallbackData, *v15, *(_QWORD *)(a2 + 32)) )
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
          wil_details_featureDescriptors_a->DeviceExtension,
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
        wil_details_featureDescriptors_a->DeviceExtension,
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
      wil_details_featureDescriptors_a->DeviceExtension,
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
        wil_details_featureDescriptors_a->DeviceExtension,
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
0x140025270  mov     r11, rsp
0x140025273  push    rbx
0x140025274  push    rbp
0x140025275  push    rsi
0x140025276  push    rdi
0x140025277  push    r12
0x140025279  push    r13
0x14002527b  push    r14
0x14002527d  push    r15
0x14002527f  sub     rsp, 0B8h
0x140025286  xor     eax, eax
0x140025288  mov     rbp, rcx
0x14002528b  mov     r13, rdx
0x14002528e  mov     [rsp+0F8h+var_94], eax
0x140025292  xor     cl, cl
0x140025294  mov     [rsp+0F8h+var_98], eax
0x140025298  mov     rbx, r8
0x14002529b  mov     [rsp+0F8h+var_90], al
0x14002529f  lea     r14, [rbp+20h]
0x1400252a3  mov     [r11+18h], cl
0x1400252a7  lea     r15, [r13+18h]
0x1400252ab  mov     [r11-78h], eax
0x1400252af  lea     rsi, [rbp+18h]
0x1400252b3  mov     [r11-60h], rax
0x1400252b7  xor     r12b, r12b
0x1400252ba  mov     [r11-68h], eax
0x1400252be  mov     edx, eax
0x1400252c0  mov     edi, eax
0x1400252c2  mov     eax, [rbx+14h]
0x1400252c5  lea     r11, WPP_RECORDER_INITIALIZED
0x1400252cc  mov     [rsp+0F8h+var_50], r14
0x1400252d4  mov     r9, r15
0x1400252d7  mov     [rsp+0F8h+Context], r15
0x1400252dc  mov     r10, r15
0x1400252df  mov     [rsp+0F8h+var_58], r14
0x1400252e7  mov     r8, r14
0x1400252ea  mov     [rsp+0F8h+var_70], r15
0x1400252f2  mov     [rsp+0F8h+var_88], r14
0x1400252f7  test    al, 1
0x1400252f9  jnz     loc_1400254B8
0x1400252ff  mov     r11d, [rsp+0F8h+var_98]
0x140025304  mov     ecx, [rsi]
0x140025306  mov     edi, 0A000001Fh
0x14002530b  test    ecx, ecx
0x14002530d  jns     loc_140025404
0x140025313  mov     eax, [rbx+14h]
0x140025316  test    al, 1
0x140025318  jz      loc_140025444
0x14002531e  mov     ecx, [rsi]
0x140025320  test    ecx, ecx
0x140025322  jns     loc_140025DFF
0x140025328  mov     r12d, [rsp+0F8h+var_98]
0x14002532d  mov     edi, [rsp+0F8h+var_94]
0x140025331  lea     rsi, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140025338  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x14002533f  mov     rcx, [rsp+0F8h+Object]; Object
0x140025347  test    rcx, rcx
0x14002534a  jnz     loc_1400255F1
0x140025350  mov     rax, [rbx+30h]
0x140025354  test    rax, rax
0x140025357  jz      short loc_140025376
0x140025359  cmp     dword ptr [rbp+18h], 0C0000279h
0x140025360  jz      loc_140026040
0x140025366  mov     rcx, [rbx+30h]; FileNameInformation
0x14002536a  call    cs:__imp_FltReleaseFileNameInformation
0x140025371  nop     dword ptr [rax+rax+00h]
0x140025376  cmp     [rbx], rbx
0x140025379  jz      short loc_140025394
0x14002537b  mov     rcx, cs:Globals
0x140025382  mov     r8, rbx
0x140025385  mov     rdx, rbp
0x140025388  call    cs:__imp_FltRemoveOpenReparseEntry
0x14002538f  nop     dword ptr [rax+rax+00h]
0x140025394  mov     r8, [rbx+40h]
0x140025398  test    r8, r8
0x14002539b  jnz     loc_140026097
0x1400253a1  mov     r8, [rbx+38h]
0x1400253a5  test    r8, r8
0x1400253a8  jz      short loc_1400253D7
0x1400253aa  mov     rcx, cs:Globals
0x1400253b1  mov     rdx, rbp
0x1400253b4  call    cs:__imp_FltRemoveOpenReparseEntry
0x1400253bb  nop     dword ptr [rax+rax+00h]
0x1400253c0  mov     rdx, [rbx+38h]; Entry
0x1400253c4  lea     rcx, stru_14000E380; Lookaside
0x1400253cb  call    cs:__imp_ExFreeToPagedLookasideList
0x1400253d2  nop     dword ptr [rax+rax+00h]
0x1400253d7  mov     rdx, rbx; Entry
0x1400253da  lea     rcx, stru_14000E400; Lookaside
0x1400253e1  call    cs:__imp_ExFreeToPagedLookasideList
0x1400253e8  nop     dword ptr [rax+rax+00h]
0x1400253ed  mov     eax, edi
0x1400253ef  add     rsp, 0B8h
0x1400253f6  pop     r15
0x1400253f8  pop     r14
0x1400253fa  pop     r13
0x1400253fc  pop     r12
0x1400253fe  pop     rdi
0x1400253ff  pop     rsi
0x140025400  pop     rbp
0x140025401  pop     rbx
0x140025402  retn
0x140025404  cmp     ecx, 104h
0x14002540a  jz      loc_14002561C
0x140025410  cmp     dword ptr [rsi], 0
0x140025413  jnz     short loc_140025426
0x140025415  mov     rcx, [rbp+10h]
0x140025419  test    dword ptr [rcx+20h], 1000h
0x140025420  jnz     loc_140025F61
0x140025426  test    r12b, r12b
0x140025429  jnz     loc_14002602B
0x14002542f  mov     r8, [r13+20h]; FileObject
0x140025433  mov     rcx, rbp; CallbackData
0x140025436  mov     rdx, [r13+18h]; Instance
0x14002543a  call    WcHandleQueryOnCreateEcp
0x14002543f  jmp     loc_140025328
0x140025444  cmp     ecx, 0C00000BAh
0x14002544a  jz      short loc_14002546E
0x14002544c  cmp     ecx, 0C0000103h
0x140025452  jz      short loc_14002546E
0x140025454  cmp     ecx, 0C0000035h
0x14002545a  jnz     loc_14002531E
0x140025460  mov     rax, [rbp+10h]
0x140025464  cmp     byte ptr [rax+23h], 2
0x140025468  jnz     loc_14002531E
0x14002546e  mov     rax, [rbp+10h]
0x140025472  test    dword ptr [rax+20h], 2000h
0x140025479  jnz     loc_140025D23
0x14002547f  mov     rdx, [rbx+30h]
0x140025483  lea     r8, [rsp+0F8h+var_90]
0x140025488  add     rdx, 8
0x14002548c  mov     rcx, r13
0x14002548f  call    WcIsTombstoneByName
0x140025494  mov     [rsp+0F8h+var_98], eax
0x140025498  mov     r11d, eax
0x14002549b  test    eax, eax
0x14002549d  js      loc_140025D8C
0x1400254a3  cmp     [rsp+0F8h+var_90], 0
0x1400254a8  jnz     loc_140025DEC
0x1400254ae  mov     r8, [rsp+0F8h+var_88]
0x1400254b3  jmp     loc_14002531E
0x1400254b8  mov     eax, [rbp+18h]
0x1400254bb  lea     rsi, [rbp+18h]
0x1400254bf  cmp     eax, 104h
0x1400254c4  jnz     loc_1400256E4
0x1400254ca  mov     r9, [rbp+10h]
0x1400254ce  mov     r8d, [r9+20h]
0x1400254d2  bt      r8d, 0Dh
0x1400254d7  jb      loc_1400259CF
0x1400254dd  test    cl, cl
0x1400254df  jnz     loc_14002596A
0x1400254e5  mov     rax, [rbp+28h]
0x1400254e9  cmp     di, [rax+6]
0x1400254ed  jz      loc_14002576A
0x1400254f3  mov     rax, [rbp+28h]
0x1400254f7  lea     r15, [r13+18h]
0x1400254fb  mov     r9, [rbx+30h]
0x1400254ff  mov     rcx, rbp
0x140025502  mov     r8d, [rbx+10h]
0x140025506  mov     rdx, [r15]
0x140025509  movzx   edi, word ptr [rax+6]
0x14002550d  lea     rax, [rsp+0F8h+Object]
0x140025515  mov     [rsp+0F8h+var_B8], rax
0x14002551a  lea     rax, [rsp+0F8h+var_78]
0x140025522  mov     [rsp+0F8h+var_C0], rax
0x140025527  lea     rax, [rsp+0F8h+arg_10]
0x14002552f  mov     [rsp+0F8h+var_C8], rax
0x140025534  lea     rax, [rsp+0F8h+var_68]
0x14002553c  mov     [rsp+0F8h+var_D0], rax
0x140025541  mov     word ptr [rsp+0F8h+var_D8], di
0x140025546  call    WcProcessWciReparsePointBounce
0x14002554b  mov     [rsp+0F8h+var_98], eax
0x14002554f  mov     r11d, eax
0x140025552  test    eax, eax
0x140025554  js      loc_1400258F2
0x14002555a  cmp     [rsp+0F8h+var_78], 2
0x140025562  jz      loc_1400258E8
0x140025568  xor     eax, eax
0x14002556a  mov     dword ptr [rbx+14h], 80000004h
0x140025571  mov     [rbx+2Ah], ax
0x140025575  cmp     [rsp+0F8h+arg_10], al
0x14002557c  jz      short loc_140025585
0x14002557e  mov     dword ptr [rbx+14h], 80000000h
0x140025585  mov     rcx, [r15]; InitiatingInstance
0x140025588  mov     rdx, rbp; CallbackData
0x14002558b  call    cs:__imp_FltReissueSynchronousIo
0x140025592  nop     dword ptr [rax+rax+00h]
0x140025597  mov     ecx, [rsi]
0x140025599  test    ecx, ecx
0x14002559b  jns     short loc_1400255C1
0x14002559d  lea     rax, WPP_RECORDER_INITIALIZED
0x1400255a4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400255ab  jnz     loc_140025884
0x1400255b1  mov     r9, [rsp+0F8h+Context]
0x1400255b6  mov     r8, r14
0x1400255b9  mov     r10, r9
0x1400255bc  jmp     loc_1400252FF
0x1400255c1  cmp     qword ptr [rbp+20h], 2
0x1400255c6  lea     r14, [rbp+20h]
0x1400255ca  jz      loc_14002580B
0x1400255d0  mov     rcx, [rsp+0F8h+Object]; Object
0x1400255d8  test    rcx, rcx
0x1400255db  jnz     short loc_140025602
0x1400255dd  movzx   ecx, [rsp+0F8h+arg_10]
0x1400255e5  mov     edx, [rsp+0F8h+var_68]
0x1400255ec  jmp     loc_1400252C2
0x1400255f1  call    cs:__imp_ObfDereferenceObject
0x1400255f8  nop     dword ptr [rax+rax+00h]
0x1400255fd  jmp     loc_140025350
0x140025602  call    cs:__imp_ObfDereferenceObject
0x140025609  nop     dword ptr [rax+rax+00h]
0x14002560e  mov     [rsp+0F8h+Object], 0
0x14002561a  jmp     short loc_1400255DD
0x14002561c  mov     rax, [r8]
0x14002561f  cmp     rax, rdi
0x140025622  jz      loc_140025E0C
0x140025628  mov     rcx, [rbx+40h]
0x14002562c  test    rcx, rcx
0x14002562f  jnz     loc_1400257C7
0x140025635  bt      rax, 1Dh
0x14002563a  jnb     short loc_140025662
0x14002563c  mov     ecx, 0A000000Ch
0x140025641  cmp     rax, rcx
0x140025644  jz      short loc_140025662
0x140025646  mov     ecx, 0A0000003h
0x14002564b  cmp     rax, rcx
0x14002564e  jz      short loc_140025662
0x140025650  mov     r8, [r13+20h]
0x140025654  mov     rcx, rbp; Data
0x140025657  mov     rdx, [r9]
0x14002565a  call    WcProcessWciLinkBounce
0x14002565f  mov     r11d, eax
0x140025662  mov     [rsp+0F8h+var_98], r11d
0x140025667  test    r11d, r11d
0x14002566a  jns     loc_140025410
0x140025670  lea     rax, WPP_RECORDER_INITIALIZED
0x140025677  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002567e  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140025685  jz      short loc_1400256C8
0x140025687  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002568e  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140025695  mov     dword ptr [rsp+0F8h+var_C0], r11d
0x14002569a  mov     r9d, 4Ah ; 'J'
0x1400256a0  mov     dword ptr [rsp+0F8h+var_C8], 0CA3h
0x1400256a8  mov     r8d, 5
0x1400256ae  mov     [rsp+0F8h+var_D0], r14
0x1400256b3  mov     dl, 2
0x1400256b5  mov     rcx, [rcx+40h]
0x1400256b9  mov     [rsp+0F8h+var_D8], rax
0x1400256be  call    WPP_RECORDER_SF_sDd
0x1400256c3  mov     r11d, [rsp+0F8h+var_98]
0x1400256c8  mov     rax, [rsp+0F8h+var_50]
0x1400256d0  mov     r12d, [rsp+0F8h+var_98]
0x1400256d5  mov     [rsi], r11d
0x1400256d8  mov     qword ptr [rax], 0
0x1400256df  jmp     loc_140025F51
0x1400256e4  test    eax, eax
0x1400256e6  jnz     loc_1400252FF
0x1400256ec  mov     r8, [r13+20h]
0x1400256f0  xor     r9d, r9d
0x1400256f3  mov     rdx, [r15]
0x1400256f6  mov     rcx, rbp
0x1400256f9  call    WcProcessWciReparsePointOpen
0x1400256fe  mov     [rsp+0F8h+var_98], eax
0x140025702  mov     r11d, eax
0x140025705  cmp     eax, 0C0000034h
0x14002570a  jz      loc_140025A2F
0x140025710  cmp     eax, 0C0000275h
0x140025715  jnz     loc_1400257D7
0x14002571b  mov     rdx, [r15]; Instance
0x14002571e  mov     rcx, [r13+20h]; FileObject
0x140025722  call    WcClearOfflineAttribute
0x140025727  mov     [rsp+0F8h+var_98], eax
0x14002572b  mov     edi, eax
0x14002572d  test    eax, eax
0x14002572f  jns     loc_140025BDE
0x140025735  lea     rax, WPP_RECORDER_INITIALIZED
0x14002573c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140025743  jnz     loc_140025B8E
0x140025749  mov     rdx, [r13+20h]; FileObject
0x14002574d  mov     rcx, [r15]; Instance
0x140025750  call    cs:__imp_FltCancelFileOpen
0x140025757  nop     dword ptr [rax+rax+00h]
0x14002575c  mov     [rsi], edi
0x14002575e  mov     qword ptr [r14], 0
0x140025765  jmp     loc_140025328
0x14002576a  test    edx, edx
0x14002576c  jnz     loc_1400254F3
0x140025772  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x140025779  jz      loc_1400254F3
0x14002577f  mov     rdx, [rbx+30h]
0x140025783  mov     eax, r8d
0x140025786  shr     eax, 18h
0x140025789  add     rdx, 8
0x14002578d  mov     [rsp+0F8h+var_A0], rdx
0x140025792  and     r8d, 0FFFFFFh
0x140025799  mov     [rsp+0F8h+var_A8], eax
0x14002579d  mov     rax, [r13+20h]
0x1400257a1  mov     [rsp+0F8h+var_B0], r8d
0x1400257a6  movzx   ecx, di
  ... truncated ...
```
