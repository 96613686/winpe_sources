# WcPopulateFile

- ea: `0x140030da4`
- end: `0x140031936`
- name: `WcPopulateFile`
- size: `2962`
- prototype: `__int64 __fastcall(PUNICODE_STRING FileName, _QWORD *, __int64, void *, struct _LIST_ENTRY *, PFILE_OBJECT FileObject, char, char)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140018b9c`
- `0x14002ef90`

## callees

- `0x140001008`
- `0x140001030`
- `0x140001500`
- `0x1400020c4`
- `0x140002294`
- `0x1400024d4`
- `0x1400048a4`
- `0x140007c60`
- `0x14001d8dc`
- `0x140029d84`
- `0x14002cb38`
- `0x14002daa4`
- `0x14002eec8`
- `0x14002f9e4`
- `0x140030da4`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x140030f60`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140030f60`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031510`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031510`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140030f16`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140030f16`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003183c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003183c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140031907`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140031907`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400314be`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400314be`
- `ntoskrnl!KeWaitForSingleObject` at `0x140030ee0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003166b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140030ee0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003166b`
- `ntoskrnl!KeSetEvent` at `0x140030feb`
- `ntoskrnl!KeSetEvent` at `0x140031860`
- `ntoskrnl!KeSetEvent` at `0x140030feb`
- `ntoskrnl!KeSetEvent` at `0x140031860`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140031175`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140031175`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003149d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003149d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140030e55`
- `ntoskrnl!RtlInitUnicodeString` at `0x140030e55`
- `ntoskrnl!RtlHashUnicodeString` at `0x140030f39`
- `ntoskrnl!RtlHashUnicodeString` at `0x140031198`
- `ntoskrnl!RtlHashUnicodeString` at `0x140030f39`
- `ntoskrnl!RtlHashUnicodeString` at `0x140031198`
- `ntoskrnl!ObfDereferenceObject` at `0x1400318c0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400318c0`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400314db`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400314db`
- `ntoskrnl!KeInitializeEvent` at `0x1400315ab`
- `ntoskrnl!KeInitializeEvent` at `0x1400315ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031881`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031881`
- `ntoskrnl!ExAllocatePool2` at `0x1400313da`
- `ntoskrnl!ExAllocatePool2` at `0x1400313da`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14003160e`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14003160e`
- `FLTMGR!FltQueryDirectoryFile` at `0x140030e9e`
- `FLTMGR!FltQueryDirectoryFile` at `0x140030e9e`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14003111a`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14003111a`
- `FLTMGR!FltClose` at `0x1400318ab`
- `FLTMGR!FltClose` at `0x1400318ab`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031896`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031896`
- `FLTMGR!FltParseFileNameInformation` at `0x140031134`
- `FLTMGR!FltParseFileNameInformation` at `0x140031134`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140031623`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140031623`
- `FLTMGR!FltReleaseContext` at `0x1400318d8`
- `FLTMGR!FltReleaseContext` at `0x1400318ec`
- `FLTMGR!FltReleaseContext` at `0x1400318d8`
- `FLTMGR!FltReleaseContext` at `0x1400318ec`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400315b7`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x1400315b7`

## pseudocode

```c
__int64 __fastcall WcPopulateFile(
        PUNICODE_STRING FileName,
        _QWORD *a2,
        __int64 a3,
        void *a4,
        struct _LIST_ENTRY *a5,
        PFILE_OBJECT FileObject,
        char a7,
        char a8)
{
  __int128 *v9; // rdi
  struct _KEVENT *v10; // r14
  NTSTATUS v14; // eax
  unsigned int v15; // edx
  _QWORD *v16; // rbx
  struct _KEVENT *v17; // rsi
  __int64 v18; // rax
  int FileNameInformationUnsafe; // ebx
  int v20; // edx
  int v21; // r9d
  PVOID DeviceExtension; // rcx
  int v23; // r8d
  __int64 v24; // r13
  USHORT Length; // cx
  UNICODE_STRING *p_FinalComponent; // rsi
  _QWORD *v27; // rax
  unsigned int v28; // r15d
  int v29; // edx
  int v30; // edx
  int v31; // r9d
  int v32; // r15d
  int v33; // eax
  __int64 Pool2; // rax
  USHORT *v35; // r8
  USHORT v36; // r9
  _QWORD *v37; // r12
  int v38; // eax
  struct _KEVENT *v39; // rax
  struct _LIST_ENTRY *v40; // rbx
  struct _LIST_ENTRY *v41; // rcx
  PFILE_OBJECT v42; // rax
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rax
  struct _FLT_GENERIC_WORKITEM *v44; // r15
  PFLT_CONTEXT v45; // rsi
  char FileNamea; // [rsp+30h] [rbp-D0h]
  char FileNameb; // [rsp+30h] [rbp-D0h]
  PUNICODE_STRING RestartScan; // [rsp+38h] [rbp-C8h]
  BOOLEAN RestartScana[8]; // [rsp+38h] [rbp-C8h]
  char LengthReturned; // [rsp+40h] [rbp-C0h]
  char v52; // [rsp+70h] [rbp-90h]
  bool v53; // [rsp+71h] [rbp-8Fh] BYREF
  bool v54; // [rsp+72h] [rbp-8Eh] BYREF
  bool v55; // [rsp+73h] [rbp-8Dh] BYREF
  char v56; // [rsp+74h] [rbp-8Ch] BYREF
  bool v57; // [rsp+75h] [rbp-8Bh] BYREF
  char v58; // [rsp+76h] [rbp-8Ah]
  __int64 v59; // [rsp+78h] [rbp-88h] BYREF
  PFILE_OBJECT v60; // [rsp+80h] [rbp-80h] BYREF
  ULONG HashValue; // [rsp+88h] [rbp-78h] BYREF
  ULONG v62; // [rsp+8Ch] [rbp-74h] BYREF
  PFLT_CONTEXT v63; // [rsp+90h] [rbp-70h] BYREF
  HANDLE FileHandle; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+A0h] [rbp-60h] BYREF
  UNICODE_STRING SourceString; // [rsp+B0h] [rbp-50h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+C0h] [rbp-40h] BYREF
  PFILE_OBJECT v68; // [rsp+C8h] [rbp-38h]
  struct _LIST_ENTRY *v69; // [rsp+D0h] [rbp-30h]
  PVOID FltObject; // [rsp+D8h] [rbp-28h]
  PFLT_CONTEXT Context; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v72; // [rsp+E8h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v74; // [rsp+100h] [rbp+0h] BYREF
  __int64 v75; // [rsp+110h] [rbp+10h]
  __int128 FileInformation; // [rsp+118h] [rbp+18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v77; // [rsp+128h] [rbp+28h] BYREF
  struct _UNICODE_STRING *p_Destination; // [rsp+148h] [rbp+48h]
  __int64 v79; // [rsp+150h] [rbp+50h]

  v69 = a5;
  *(_QWORD *)&Destination.Length = 0;
  FileHandle = 0;
  v9 = 0;
  v60 = 0;
  v10 = 0;
  *(_QWORD *)&SourceString.Length = 0;
  v58 = 0;
  LODWORD(v59) = 0;
  v57 = 0;
  v55 = 0;
  v54 = 0;
  v56 = 0;
  v53 = 0;
  FileNameInformation = 0;
  v62 = 0;
  v63 = 0;
  Context = 0;
  HashValue = 0;
  v72 = a2;
  v75 = 0;
  FltObject = a4;
  v68 = FileObject;
  DestinationString = 0;
  v74 = 0;
  FileInformation = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  WcGetContextFileObject((PFLT_INSTANCE)a4, FileObject, &Context, &v63);
  v14 = FltQueryDirectoryFile(
          (PFLT_INSTANCE)a4,
          FileObject,
          &FileInformation,
          0x10u,
          FileNamesInformation,
          1u,
          FileName,
          1u,
          0);
  v15 = 0x80000000;
  if ( (int)(v14 + 0x80000000) < 0 || v14 == -2147483643 )
  {
    FileNameInformationUnsafe = 0;
    v52 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && LOWORD(wil_details_featureDescriptors_a->DeviceType) )
    {
      LOBYTE(v15) = 5;
      WPP_RECORDER_SF_sDZ(
        WcVerboseRecorder,
        v15,
        10,
        26,
        (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
        47,
        (__int64)FileName);
    }
    goto LABEL_84;
  }
  v16 = v63;
  v17 = (struct _KEVENT *)((char *)v63 + 232);
  KeWaitForSingleObject((char *)v63 + 232, Executive, 0, 0, 0);
  v18 = v16[32];
  if ( v18 && *(_DWORD *)(v18 + 20) )
  {
    v52 = 1;
    FileNameInformationUnsafe = RtlDowncaseUnicodeString(&DestinationString, FileName, 1u);
    if ( FileNameInformationUnsafe < 0 )
      goto LABEL_84;
    FileNameInformationUnsafe = RtlHashUnicodeString(&DestinationString, 1u, 0, &HashValue);
    if ( FileNameInformationUnsafe < 0 )
      goto LABEL_84;
    if ( RtlLookupEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)v63 + 32), HashValue, 0) )
    {
      FileNameInformationUnsafe = -1073741267;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && LOWORD(wil_details_featureDescriptors_a->DeviceType) )
      {
        LengthReturned = 45;
        v21 = 27;
        RestartScan = FileName;
        FileNamea = 105;
LABEL_11:
        LODWORD(DeviceExtension) = WcVerboseRecorder;
        v23 = 10;
        LOBYTE(v20) = 5;
LABEL_12:
        WPP_RECORDER_SF_sDZd(
          (_DWORD)DeviceExtension,
          v20,
          v23,
          v21,
          (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
          FileNamea,
          (__int64)RestartScan,
          LengthReturned);
        goto LABEL_84;
      }
      goto LABEL_84;
    }
  }
  KeSetEvent(v17, 0, 0);
  v52 = 0;
  FileNameInformationUnsafe = WcLocateSourceDirectory(FileName, a2, &Destination);
  if ( FileNameInformationUnsafe < 0 )
    goto LABEL_84;
  v24 = *(_QWORD *)&Destination.Length;
  FileNameInformationUnsafe = WcOpenAsReparsePoint(
                                FileName,
                                *(void **)(*(_QWORD *)(*(_QWORD *)&Destination.Length + 24LL) + 8LL),
                                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&Destination.Length + 24LL) + 16LL),
                                **(struct _FLT_INSTANCE ***)(*(_QWORD *)&Destination.Length + 24LL),
                                0x120088u,
                                **((_DWORD **)Context + 8),
                                &FileHandle,
                                &v60,
                                &v57,
                                &v55,
                                &v54,
                                &v56,
                                &v53);
  if ( FileNameInformationUnsafe < 0 )
    goto LABEL_84;
  if ( a8 )
  {
    FileNameInformationUnsafe = -1073741772;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && LOWORD(wil_details_featureDescriptors_a->DeviceType) )
    {
      LengthReturned = 52;
      v21 = 28;
      RestartScan = FileName;
      FileNamea = -101;
      goto LABEL_11;
    }
    goto LABEL_84;
  }
  if ( v53 )
  {
LABEL_20:
    FileNameInformationUnsafe = -1073741772;
    goto LABEL_84;
  }
  if ( a7 )
  {
    FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(
                                  v60,
                                  **(PFLT_INSTANCE **)(v24 + 24),
                                  0x101u,
                                  &FileNameInformation);
    if ( FileNameInformationUnsafe < 0 )
      goto LABEL_84;
    FileNameInformationUnsafe = FltParseFileNameInformation(FileNameInformation);
    if ( FileNameInformationUnsafe < 0 )
      goto LABEL_84;
    Length = FileNameInformation->Stream.Length;
    p_FinalComponent = &FileNameInformation->FinalComponent;
    if ( Length )
      p_FinalComponent->Length -= Length;
    if ( FileName->Length <= 0x18u && RtlCompareUnicodeString(p_FinalComponent, FileName, 1u) )
    {
      RtlHashUnicodeString(p_FinalComponent, 1u, 0, &v62);
      if ( (unsigned int)dword_14000E060 > 5 && tlgKeywordOn((__int64)&dword_14000E060, 0x400000000000LL) )
      {
        *(_QWORD *)&Destination.Length = v62;
        v79 = 8;
        p_Destination = &Destination;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14000E060, (unsigned __int8 *)byte_14000B591, 0, 0, 3u, &v77);
      }
      goto LABEL_20;
    }
  }
  else
  {
    p_FinalComponent = FileName;
  }
  v27 = (_QWORD *)*v72;
  v72 = (_QWORD *)*v72;
  if ( v54 || v55 )
  {
    FileNameInformationUnsafe = WcCopyFile(
                                  (__int64)FileHandle,
                                  v60,
                                  **(struct _FLT_INSTANCE ***)(v24 + 24),
                                  p_FinalComponent,
                                  (struct _FLT_INSTANCE *)FltObject,
                                  v69,
                                  (__int64)v68,
                                  0,
                                  *(_DWORD *)(*(_QWORD *)(v27[3] + 32LL) + 16LL));
    if ( FileNameInformationUnsafe >= 0 )
      goto LABEL_84;
    if ( FileNameInformationUnsafe == -1073741771 || FileNameInformationUnsafe == -1073739511 )
    {
      FileNameInformationUnsafe = 0;
      goto LABEL_84;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_84;
    LengthReturned = FileNameInformationUnsafe;
    v21 = 29;
    RestartScan = p_FinalComponent;
    FileNamea = 26;
    v23 = 10;
    goto LABEL_79;
  }
  if ( v56 )
  {
    LODWORD(v74) = -2147483616;
    v9 = &v74;
    WORD2(v74) = 0;
    v28 = 8;
    v58 = 1;
    goto LABEL_57;
  }
  if ( v57 )
  {
    FileNameInformationUnsafe = WcGetReparseData(
                                  **(PFLT_INSTANCE **)(v24 + 24),
                                  v60,
                                  512,
                                  (unsigned __int16 **)&SourceString,
                                  (ULONG *)&v59);
    if ( FileNameInformationUnsafe < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        *(_DWORD *)RestartScana = FileNameInformationUnsafe;
        LOBYTE(v29) = 2;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v29,
          15,
          30,
          (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
          57,
          *(_QWORD *)RestartScana);
      }
      v9 = *(__int128 **)&SourceString.Length;
      goto LABEL_84;
    }
    v9 = *(__int128 **)&SourceString.Length;
    v28 = v59;
    FileNameInformationUnsafe = WcValidateWcReparseInfo(*(__int64 *)&SourceString.Length, v59);
    if ( FileNameInformationUnsafe < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_84;
      *(_DWORD *)RestartScana = FileNameInformationUnsafe;
      v31 = 31;
      FileNameb = 64;
      goto LABEL_44;
    }
    if ( *((_QWORD *)v9 + 2) == *(_QWORD *)&GUID_NULL.Data1 && *((_QWORD *)v9 + 3) == *(_QWORD *)GUID_NULL.Data4 )
      v9[1] = *(_OWORD *)*(_QWORD *)(*(_QWORD *)(v24 + 24) + 32LL);
    *((_DWORD *)v9 + 3) &= 0xFFFFFFF1;
    goto LABEL_57;
  }
  v32 = *(unsigned __int16 *)(a3 + 32) + 34;
  v33 = (*(_WORD *)(a3 + 32) != 0 ? 2 : 0) + p_FinalComponent->Length;
  LODWORD(v59) = *(_WORD *)(a3 + 32) != 0 ? 2 : 0;
  v28 = v33 + v32;
  Destination = 0;
  SourceString = 0;
  Pool2 = ExAllocatePool2(256, v28, 1769096023);
  v9 = (__int128 *)Pool2;
  if ( !Pool2 )
  {
    FileNameInformationUnsafe = -1073741670;
    goto LABEL_84;
  }
  *(_QWORD *)(Pool2 + 8) = 1;
  *(_OWORD *)(Pool2 + 16) = *(_OWORD *)*(_QWORD *)(*(_QWORD *)(v24 + 24) + 32LL);
  FileNameInformationUnsafe = RtlUShortAdd(p_FinalComponent->Length, *(_WORD *)(a3 + 32), (USHORT *)(Pool2 + 32));
  if ( FileNameInformationUnsafe >= 0 )
  {
    FileNameInformationUnsafe = RtlUShortAdd(*((_WORD *)v9 + 16), v59, v35);
    if ( FileNameInformationUnsafe >= 0 )
    {
      *(_DWORD *)v9 = *(_DWORD *)a3;
      FileNameInformationUnsafe = RtlUShortAdd(0x1Au, *((_WORD *)v9 + 16), (USHORT *)v9 + 2);
      if ( FileNameInformationUnsafe >= 0 )
      {
        Destination.MaximumLength = *((_WORD *)v9 + 16);
        Destination.Length = v36;
        Destination.Buffer = (PWSTR)v9 + 17;
        SourceString.MaximumLength = *(_WORD *)(a3 + 32);
        SourceString.Length = SourceString.MaximumLength;
        SourceString.Buffer = (PWSTR)(a3 + 34);
        RtlCopyUnicodeString(&Destination, &SourceString);
        if ( !*(_WORD *)(a3 + 32)
          || (FileNameInformationUnsafe = RtlAppendUnicodeToString(&Destination, L"\\"), FileNameInformationUnsafe >= 0) )
        {
          FileNameInformationUnsafe = RtlAppendUnicodeStringToString(&Destination, p_FinalComponent);
          if ( FileNameInformationUnsafe >= 0 )
          {
LABEL_57:
            v37 = v72;
            v38 = *(_DWORD *)(*(_QWORD *)(v72[3] + 32LL) + 16LL);
            if ( (v38 & 0x20) != 0 )
            {
              v39 = (struct _KEVENT *)ExAllocateFromNPagedLookasideList(&stru_14000E600);
              v10 = v39;
              if ( !v39 )
              {
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  goto LABEL_84;
                *(_DWORD *)RestartScana = FileNameInformationUnsafe;
                v31 = 32;
                FileNameb = -86;
                goto LABEL_44;
              }
              v40 = (struct _LIST_ENTRY *)FltObject;
              *(_QWORD *)&v39->Header.Lock = FileHandle;
              v39->Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v60;
              v41 = **(struct _LIST_ENTRY ***)(v24 + 24);
              v39[1].Header.WaitListHead.Blink = v69;
              v42 = v68;
              v10->Header.WaitListHead.Blink = v41;
              *(_QWORD *)&v10[2].Header.Lock = v42;
              *(_QWORD *)&v10[1].Header.Lock = p_FinalComponent;
              v10[1].Header.WaitListHead.Flink = v40;
              v10[2].Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v9;
              LODWORD(v10[2].Header.WaitListHead.Blink) = v28;
              v10[4].Header.LockNV = 0;
              v10[4].Header.SignalState = *(_DWORD *)(*(_QWORD *)(v37[3] + 32LL) + 16LL);
              KeInitializeEvent(v10 + 3, NotificationEvent, 0);
              GenericWorkItem = FltAllocateGenericWorkItem();
              v44 = GenericWorkItem;
              if ( !GenericWorkItem )
              {
                FileNameInformationUnsafe = -1073741670;
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  goto LABEL_84;
                *(_DWORD *)RestartScana = -1073741670;
                v31 = 33;
                FileNameb = -63;
                goto LABEL_44;
              }
              FileNameInformationUnsafe = FltQueueGenericWorkItem(
                                            GenericWorkItem,
                                            v40,
                                            (PFLT_GENERIC_WORKITEM_ROUTINE)WcCopyAsPlaceHolderWorker,
                                            CriticalWorkQueue,
                                            v10);
              if ( FileNameInformationUnsafe < 0 )
              {
                FltFreeGenericWorkItem(v44);
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  goto LABEL_84;
                *(_DWORD *)RestartScana = FileNameInformationUnsafe;
                v31 = 34;
                FileNameb = -50;
LABEL_44:
                LOBYTE(v30) = 2;
                WPP_RECORDER_SF_sDd(
                  wil_details_featureDescriptors_a->DeviceExtension,
                  v30,
                  15,
                  v31,
                  (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
                  (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
                  FileNameb,
                  *(_QWORD *)RestartScana);
                goto LABEL_84;
              }
              KeWaitForSingleObject(&v10[3], Executive, 0, 0, 0);
              FileNameInformationUnsafe = v10[4].Header.Lock;
              if ( FileNameInformationUnsafe >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_84;
              LengthReturned = v10[4].Header.LockNV;
              v21 = 35;
              RestartScan = p_FinalComponent;
              FileNamea = -37;
            }
            else
            {
              FileNameInformationUnsafe = WcCopyAsPlaceHolder(
                                            (__int64)FileHandle,
                                            v60,
                                            **(struct _FLT_INSTANCE ***)(v24 + 24),
                                            p_FinalComponent,
                                            (struct _FLT_INSTANCE *)FltObject,
                                            v69,
                                            (__int64)v68,
                                            (__int64)v9,
                                            v28,
                                            v38);
              if ( FileNameInformationUnsafe >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_84;
              LengthReturned = FileNameInformationUnsafe;
              v21 = 36;
              RestartScan = p_FinalComponent;
              FileNamea = -19;
            }
            v23 = 15;
LABEL_79:
            LOBYTE(v20) = 2;
            DeviceExtension = wil_details_featureDescriptors_a->DeviceExtension;
            goto LABEL_12;
          }
        }
      }
    }
  }
LABEL_84:
  RtlFreeUnicodeString(&DestinationString);
  v45 = v63;
  if ( v52 )
    KeSetEvent((PRKEVENT)((char *)v63 + 232), 0, 0);
  if ( v9 && !v58 )
    ExFreePoolWithTag(v9, 0x69724357u);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v60 )
    ObfDereferenceObject(v60);
  if ( Context )
    FltReleaseContext(Context);
  if ( v45 )
    FltReleaseContext(v45);
  if ( v10 )
    ExFreeToNPagedLookasideList(&stru_14000E600, v10);
  return (unsigned int)FileNameInformationUnsafe;
}

```

## disassembly

```asm
0x140030da4  push    rbp
0x140030da6  push    rbx
0x140030da7  push    rsi
0x140030da8  push    rdi
0x140030da9  push    r12
0x140030dab  push    r13
0x140030dad  push    r14
0x140030daf  push    r15
0x140030db1  lea     rbp, [rsp-68h]
0x140030db6  sub     rsp, 168h
0x140030dbd  mov     rax, cs:__security_cookie
0x140030dc4  xor     rax, rsp
0x140030dc7  mov     [rbp+0A0h+var_48], rax
0x140030dcb  mov     rax, [rbp+0A0h+arg_20]
0x140030dd2  xorps   xmm0, xmm0
0x140030dd5  mov     rsi, [rbp+0A0h+FileObject]
0x140030ddc  mov     r15, rcx
0x140030ddf  xor     ecx, ecx
0x140030de1  mov     [rbp+0A0h+var_D0], rax
0x140030de5  mov     qword ptr [rbp+0A0h+Destination.Length], rcx
0x140030de9  xor     eax, eax
0x140030deb  mov     [rbp+0A0h+FileHandle], rcx
0x140030def  mov     edi, ecx
0x140030df1  mov     [rbp+0A0h+var_120], rcx
0x140030df5  mov     r14d, ecx
0x140030df8  mov     qword ptr [rbp+0A0h+SourceString.Length], rcx
0x140030dfc  mov     rbx, r9
0x140030dff  mov     [rsp+1A0h+var_12A], cl
0x140030e03  mov     r13, rdx
0x140030e06  mov     dword ptr [rsp+1A0h+var_128], ecx
0x140030e0a  mov     r12, r8
0x140030e0d  mov     [rsp+1A0h+var_12B], cl
0x140030e11  mov     [rsp+1A0h+var_12D], cl
0x140030e15  mov     [rsp+1A0h+var_12E], cl
0x140030e19  mov     [rsp+1A0h+var_12C], cl
0x140030e1d  mov     [rsp+1A0h+var_12F], cl
0x140030e21  mov     [rbp+0A0h+FileNameInformation], rcx
0x140030e25  mov     [rbp+0A0h+var_114], ecx
0x140030e28  mov     [rbp+0A0h+var_110], rcx
0x140030e2c  mov     [rbp+0A0h+Context], rcx
0x140030e30  mov     [rbp+0A0h+HashValue], ecx
0x140030e33  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x140030e37  mov     [rbp+0A0h+var_B8], rdx
0x140030e3b  xor     edx, edx; SourceString
0x140030e3d  mov     [rbp+0A0h+var_90], rax
0x140030e41  mov     [rbp+0A0h+FltObject], rbx
0x140030e45  mov     [rbp+0A0h+var_D8], rsi
0x140030e49  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x140030e4d  movups  [rbp+0A0h+var_A0], xmm0
0x140030e51  movups  [rbp+0A0h+FileInformation], xmm0
0x140030e55  call    cs:__imp_RtlInitUnicodeString
0x140030e5c  nop     dword ptr [rax+rax+00h]
0x140030e61  lea     r9, [rbp+0A0h+var_110]
0x140030e65  mov     rdx, rsi; FileObject
0x140030e68  lea     r8, [rbp+0A0h+Context]
0x140030e6c  mov     rcx, rbx; Instance
0x140030e6f  call    WcGetContextFileObject
0x140030e74  mov     [rsp+1A0h+LengthReturned], r14; LengthReturned
0x140030e79  lea     r9d, [r14+10h]; Length
0x140030e7d  mov     [rsp+1A0h+RestartScan], 1; RestartScan
0x140030e82  lea     r8, [rbp+0A0h+FileInformation]; FileInformation
0x140030e86  mov     [rsp+1A0h+FileName], r15; FileName
0x140030e8b  mov     rdx, rsi; FileObject
0x140030e8e  mov     [rsp+1A0h+ReturnSingleEntry], 1; ReturnSingleEntry
0x140030e93  mov     rcx, rbx; Instance
0x140030e96  mov     [rsp+1A0h+FileInformationClass], 0Ch; FileInformationClass
0x140030e9e  call    cs:__imp_FltQueryDirectoryFile
0x140030ea5  nop     dword ptr [rax+rax+00h]
0x140030eaa  mov     edx, 80000000h
0x140030eaf  lea     ecx, [rax+rdx]
0x140030eb2  test    edx, ecx
0x140030eb4  jnz     loc_1400317DA
0x140030eba  cmp     eax, 80000005h
0x140030ebf  jz      loc_1400317DA
0x140030ec5  mov     rbx, [rbp+0A0h+var_110]
0x140030ec9  xor     r9d, r9d; Alertable
0x140030ecc  xor     r8d, r8d; WaitMode
0x140030ecf  mov     qword ptr [rsp+1A0h+FileInformationClass], r14; Timeout
0x140030ed4  xor     edx, edx; WaitReason
0x140030ed6  lea     rsi, [rbx+0E8h]
0x140030edd  mov     rcx, rsi; Object
0x140030ee0  call    cs:__imp_KeWaitForSingleObject
0x140030ee7  nop     dword ptr [rax+rax+00h]
0x140030eec  mov     rax, [rbx+100h]
0x140030ef3  xor     ecx, ecx
0x140030ef5  test    rax, rax
0x140030ef8  jz      loc_140030FE3
0x140030efe  cmp     [rax+14h], ecx
0x140030f01  jz      loc_140030FE3
0x140030f07  mov     r8b, 1; AllocateDestinationString
0x140030f0a  mov     [rsp+1A0h+var_130], 1
0x140030f0f  mov     rdx, r15; SourceString
0x140030f12  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x140030f16  call    cs:__imp_RtlDowncaseUnicodeString
0x140030f1d  nop     dword ptr [rax+rax+00h]
0x140030f22  mov     ebx, eax
0x140030f24  test    eax, eax
0x140030f26  js      loc_140031838
0x140030f2c  lea     r9, [rbp+0A0h+HashValue]; HashValue
0x140030f30  xor     r8d, r8d; HashAlgorithm
0x140030f33  mov     dl, 1; CaseInSensitive
0x140030f35  lea     rcx, [rbp+0A0h+DestinationString]; String
0x140030f39  call    cs:__imp_RtlHashUnicodeString
0x140030f40  nop     dword ptr [rax+rax+00h]
0x140030f45  mov     ebx, eax
0x140030f47  test    eax, eax
0x140030f49  js      loc_140031838
0x140030f4f  mov     rcx, [rbp+0A0h+var_110]
0x140030f53  xor     r8d, r8d; Context
0x140030f56  mov     edx, [rbp+0A0h+HashValue]; Signature
0x140030f59  mov     rcx, [rcx+100h]; HashTable
0x140030f60  call    cs:__imp_RtlLookupEntryHashTable
0x140030f67  nop     dword ptr [rax+rax+00h]
0x140030f6c  xor     ecx, ecx
0x140030f6e  test    rax, rax
0x140030f71  jz      short loc_140030FE3
0x140030f73  mov     ebx, 0C000022Dh
0x140030f78  lea     rax, WPP_RECORDER_INITIALIZED
0x140030f7f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140030f86  jz      loc_140031838
0x140030f8c  mov     rax, cs:wil_details_featureDescriptors_a
0x140030f93  cmp     [rax+48h], cx
0x140030f97  jz      loc_140031838
0x140030f9d  mov     dword ptr [rsp+1A0h+LengthReturned], ebx
0x140030fa1  lea     r9d, [r14+1Bh]
0x140030fa5  mov     qword ptr [rsp+1A0h+RestartScan], r15
0x140030faa  mov     dword ptr [rsp+1A0h+FileName], 969h
0x140030fb2  mov     rcx, cs:_WcVerboseRecorder
0x140030fb9  mov     r8d, 0Ah
0x140030fbf  mov     dl, 5
0x140030fc1  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x140030fc8  mov     qword ptr [rsp+1A0h+ReturnSingleEntry], rax
0x140030fcd  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x140030fd4  mov     qword ptr [rsp+1A0h+FileInformationClass], rax
0x140030fd9  call    WPP_RECORDER_SF_sDZd
0x140030fde  jmp     loc_140031838
0x140030fe3  xor     r8d, r8d; Wait
0x140030fe6  xor     edx, edx; Increment
0x140030fe8  mov     rcx, rsi; Event
0x140030feb  call    cs:__imp_KeSetEvent
0x140030ff2  nop     dword ptr [rax+rax+00h]
0x140030ff7  xor     esi, esi
0x140030ff9  lea     r8, [rbp+0A0h+Destination]
0x140030ffd  mov     rdx, r13
0x140031000  mov     [rsp+1A0h+var_130], sil
0x140031005  mov     rcx, r15; FileName
0x140031008  call    WcLocateSourceDirectory
0x14003100d  mov     ebx, eax
0x14003100f  test    eax, eax
0x140031011  js      loc_140031838
0x140031017  mov     r13, qword ptr [rbp+0A0h+Destination.Length]
0x14003101b  lea     rcx, [rsp+1A0h+var_12F]
0x140031020  mov     rax, [rbp+0A0h+Context]
0x140031024  mov     [rsp+1A0h+var_140], rcx
0x140031029  lea     rcx, [rsp+1A0h+var_12C]
0x14003102e  mov     [rsp+1A0h+var_148], rcx
0x140031033  lea     rcx, [rsp+1A0h+var_12E]
0x140031038  mov     rdx, [r13+18h]
0x14003103c  mov     rax, [rax+40h]
0x140031040  mov     [rsp+1A0h+var_150], rcx
0x140031045  lea     rcx, [rsp+1A0h+var_12D]
0x14003104a  mov     [rsp+1A0h+var_158], rcx
0x14003104f  lea     rcx, [rsp+1A0h+var_12B]
0x140031054  mov     r9, [rdx]
0x140031057  mov     eax, [rax]
0x140031059  mov     r8, [rdx+10h]
0x14003105d  mov     rdx, [rdx+8]
0x140031061  mov     [rsp+1A0h+LengthReturned], rcx
0x140031066  lea     rcx, [rbp+0A0h+var_120]
0x14003106a  mov     qword ptr [rsp+1A0h+RestartScan], rcx
0x14003106f  lea     rcx, [rbp+0A0h+FileHandle]
0x140031073  mov     [rsp+1A0h+FileName], rcx
0x140031078  mov     rcx, r15
0x14003107b  mov     dword ptr [rsp+1A0h+ReturnSingleEntry], eax
0x14003107f  mov     [rsp+1A0h+FileInformationClass], 120088h
0x140031087  call    WcOpenAsReparsePoint
0x14003108c  xor     r10d, r10d
0x14003108f  mov     ebx, eax
0x140031091  test    eax, eax
0x140031093  js      loc_140031838
0x140031099  cmp     [rbp+0A0h+arg_38], r10b
0x1400310a0  jz      short loc_1400310E7
0x1400310a2  mov     ebx, 0C0000034h
0x1400310a7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400310ae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400310b5  jz      loc_140031838
0x1400310bb  mov     rax, cs:wil_details_featureDescriptors_a
0x1400310c2  cmp     [rax+48h], r10w
0x1400310c7  jz      loc_140031838
0x1400310cd  mov     dword ptr [rsp+1A0h+LengthReturned], ebx
0x1400310d1  lea     r9d, [rsi+1Ch]
0x1400310d5  mov     qword ptr [rsp+1A0h+RestartScan], r15
0x1400310da  mov     dword ptr [rsp+1A0h+FileName], 99Bh
0x1400310e2  jmp     loc_140030FB2
0x1400310e7  cmp     [rsp+1A0h+var_12F], r10b
0x1400310ec  jz      short loc_1400310F8
0x1400310ee  mov     ebx, 0C0000034h
0x1400310f3  jmp     loc_140031838
0x1400310f8  cmp     [rbp+0A0h+arg_30], r10b
0x1400310ff  jz      loc_140031217
0x140031105  mov     rdx, [r13+18h]
0x140031109  lea     r9, [rbp+0A0h+FileNameInformation]; FileNameInformation
0x14003110d  mov     rcx, [rbp+0A0h+var_120]; FileObject
0x140031111  mov     r8d, 101h; NameOptions
0x140031117  mov     rdx, [rdx]; Instance
0x14003111a  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140031121  nop     dword ptr [rax+rax+00h]
0x140031126  mov     ebx, eax
0x140031128  test    eax, eax
0x14003112a  js      loc_140031838
0x140031130  mov     rcx, [rbp+0A0h+FileNameInformation]; FileNameInformation
0x140031134  call    cs:__imp_FltParseFileNameInformation
0x14003113b  nop     dword ptr [rax+rax+00h]
0x140031140  xor     r10d, r10d
0x140031143  mov     ebx, eax
0x140031145  test    eax, eax
0x140031147  js      loc_140031838
0x14003114d  mov     rax, [rbp+0A0h+FileNameInformation]
0x140031151  movzx   ecx, word ptr [rax+48h]
0x140031155  lea     rsi, [rax+58h]
0x140031159  test    cx, cx
0x14003115c  jz      short loc_140031161
0x14003115e  sub     [rsi], cx
0x140031161  cmp     word ptr [r15], 18h
0x140031166  ja      loc_14003121A
0x14003116c  mov     r8b, 1; CaseInSensitive
0x14003116f  mov     rdx, r15; String2
0x140031172  mov     rcx, rsi; String1
0x140031175  call    cs:__imp_RtlCompareUnicodeString
0x14003117c  nop     dword ptr [rax+rax+00h]
0x140031181  xor     r10d, r10d
0x140031184  test    eax, eax
0x140031186  jz      loc_14003121A
0x14003118c  lea     r9, [rbp+0A0h+var_114]; HashValue
0x140031190  xor     r8d, r8d; HashAlgorithm
0x140031193  mov     dl, 1; CaseInSensitive
0x140031195  mov     rcx, rsi; String
0x140031198  call    cs:__imp_RtlHashUnicodeString
0x14003119f  nop     dword ptr [rax+rax+00h]
0x1400311a4  mov     eax, cs:dword_14000E060
0x1400311aa  cmp     eax, 5
0x1400311ad  jbe     loc_1400310EE
0x1400311b3  mov     rdx, 400000000000h
0x1400311bd  lea     rcx, dword_14000E060
0x1400311c4  call    _tlgKeywordOn
0x1400311c9  test    al, al
0x1400311cb  jz      loc_1400310EE
0x1400311d1  mov     eax, [rbp+0A0h+var_114]
0x1400311d4  lea     rdx, byte_14000B591
0x1400311db  mov     qword ptr [rbp+0A0h+Destination.Length], rax
0x1400311df  lea     rcx, dword_14000E060
0x1400311e6  lea     rax, [rbp+0A0h+Destination]
0x1400311ea  mov     [rbp+0A0h+var_50], 8
0x1400311f2  mov     [rbp+0A0h+var_58], rax
0x1400311f6  xor     r9d, r9d
0x1400311f9  lea     rax, [rbp+0A0h+var_78]
0x1400311fd  xor     r8d, r8d
0x140031200  mov     qword ptr [rsp+1A0h+ReturnSingleEntry], rax
0x140031205  mov     [rsp+1A0h+FileInformationClass], 3
0x14003120d  call    _tlgWriteTransfer_EtwWriteTransfer
0x140031212  jmp     loc_1400310EE
0x140031217  mov     rsi, r15
0x14003121a  mov     rax, [rbp+0A0h+var_B8]
0x14003121e  mov     rax, [rax]
0x140031221  mov     [rbp+0A0h+var_B8], rax
0x140031225  cmp     [rsp+1A0h+var_12E], r10b
0x14003122a  jnz     loc_140031733
0x140031230  cmp     [rsp+1A0h+var_12D], r10b
0x140031235  jnz     loc_140031733
0x14003123b  cmp     [rsp+1A0h+var_12C], r10b
0x140031240  jz      short loc_140031262
0x140031242  mov     dword ptr [rbp+0A0h+var_A0], 80000020h
0x140031249  lea     rdi, [rbp+0A0h+var_A0]
0x14003124d  mov     word ptr [rbp+0A0h+var_A0+4], r10w
0x140031252  mov     r15d, 8
0x140031258  mov     [rsp+1A0h+var_12A], 1
0x14003125d  jmp     loc_1400314F1
0x140031262  cmp     [rsp+1A0h+var_12B], r10b
0x140031267  jz      loc_140031398
0x14003126d  mov     rcx, [r13+18h]
0x140031271  lea     rax, [rsp+1A0h+var_128]
0x140031276  mov     rdx, [rbp+0A0h+var_120]; FileObject
0x14003127a  lea     r9, [rbp+0A0h+SourceString]
0x14003127e  mov     r8d, 200h
0x140031284  mov     qword ptr [rsp+1A0h+FileInformationClass], rax; __int64
0x140031289  mov     rcx, [rcx]; Instance
0x14003128c  call    WcGetReparseData
0x140031291  mov     ebx, eax
0x140031293  test    eax, eax
0x140031295  jns     short loc_1400312F0
0x140031297  lea     rax, WPP_RECORDER_INITIALIZED
0x14003129e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400312a5  jz      short loc_1400312E7
0x1400312a7  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400312ae  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x1400312b5  mov     dword ptr [rsp+1A0h+RestartScan], ebx
0x1400312b9  mov     r9d, 1Eh
0x1400312bf  mov     dword ptr [rsp+1A0h+FileName], 0A39h
0x1400312c7  mov     dl, 2
0x1400312c9  mov     qword ptr [rsp+1A0h+ReturnSingleEntry], rax
  ... truncated ...
```
