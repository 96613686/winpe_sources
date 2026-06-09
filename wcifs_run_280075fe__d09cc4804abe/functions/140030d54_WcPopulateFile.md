# WcPopulateFile

- ea: `0x140030d54`
- end: `0x1400318e6`
- name: `WcPopulateFile`
- size: `2962`
- prototype: `__int64 __usercall@<rax>(PUNICODE_STRING FileName@<rcx>, __int64, PFILE_OBJECT FileObject, char, char)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140018b9c`
- `0x14002ef40`

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
- `0x140029d34`
- `0x14002cae8`
- `0x14002da54`
- `0x14002ee78`
- `0x14002f994`
- `0x140030d54`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x140030f10`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140030f10`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400314c0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400314c0`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140030ec6`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140030ec6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400317ec`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400317ec`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400318b7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400318b7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003146e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003146e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140030e90`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003161b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140030e90`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003161b`
- `ntoskrnl!KeSetEvent` at `0x140030f9b`
- `ntoskrnl!KeSetEvent` at `0x140031810`
- `ntoskrnl!KeSetEvent` at `0x140030f9b`
- `ntoskrnl!KeSetEvent` at `0x140031810`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140031125`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140031125`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003144d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003144d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140030e05`
- `ntoskrnl!RtlInitUnicodeString` at `0x140030e05`
- `ntoskrnl!RtlHashUnicodeString` at `0x140030ee9`
- `ntoskrnl!RtlHashUnicodeString` at `0x140031148`
- `ntoskrnl!RtlHashUnicodeString` at `0x140030ee9`
- `ntoskrnl!RtlHashUnicodeString` at `0x140031148`
- `ntoskrnl!ObfDereferenceObject` at `0x140031870`
- `ntoskrnl!ObfDereferenceObject` at `0x140031870`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003148b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003148b`
- `ntoskrnl!KeInitializeEvent` at `0x14003155b`
- `ntoskrnl!KeInitializeEvent` at `0x14003155b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031831`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031831`
- `ntoskrnl!ExAllocatePool2` at `0x14003138a`
- `ntoskrnl!ExAllocatePool2` at `0x14003138a`
- `FLTMGR!FltQueueGenericWorkItem` at `0x1400315be`
- `FLTMGR!FltQueueGenericWorkItem` at `0x1400315be`
- `FLTMGR!FltQueryDirectoryFile` at `0x140030e4e`
- `FLTMGR!FltQueryDirectoryFile` at `0x140030e4e`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400310ca`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400310ca`
- `FLTMGR!FltClose` at `0x14003185b`
- `FLTMGR!FltClose` at `0x14003185b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031846`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140031846`
- `FLTMGR!FltParseFileNameInformation` at `0x1400310e4`
- `FLTMGR!FltParseFileNameInformation` at `0x1400310e4`
- `FLTMGR!FltFreeGenericWorkItem` at `0x1400315d3`
- `FLTMGR!FltFreeGenericWorkItem` at `0x1400315d3`
- `FLTMGR!FltReleaseContext` at `0x140031888`
- `FLTMGR!FltReleaseContext` at `0x14003189c`
- `FLTMGR!FltReleaseContext` at `0x140031888`
- `FLTMGR!FltReleaseContext` at `0x14003189c`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140031567`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140031567`

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
  NTSTATUS v13; // eax
  unsigned int v14; // edx
  struct _KEVENT *v15; // rsi
  __int64 v16; // rax
  int SourceDirectory; // ebx
  int v18; // edx
  int v19; // r9d
  PVOID DeviceExtension; // rcx
  int v21; // r8d
  __int64 v22; // r13
  USHORT Length; // cx
  UNICODE_STRING *p_FinalComponent; // rsi
  _QWORD *v25; // rax
  unsigned int v26; // r15d
  int v27; // edx
  int v28; // edx
  int v29; // r9d
  int v30; // r15d
  int v31; // eax
  __int64 Pool2; // rax
  USHORT *v33; // r8
  USHORT v34; // r9
  _QWORD *v35; // r12
  int v36; // eax
  struct _KEVENT *v37; // rax
  struct _LIST_ENTRY *v38; // rbx
  struct _LIST_ENTRY *v39; // rcx
  PFILE_OBJECT v40; // rax
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rax
  struct _FLT_GENERIC_WORKITEM *v42; // r15
  PFLT_CONTEXT v43; // rsi
  char FileNamea; // [rsp+30h] [rbp-D0h]
  char FileNameb; // [rsp+30h] [rbp-D0h]
  PUNICODE_STRING RestartScan; // [rsp+38h] [rbp-C8h]
  char RestartScana; // [rsp+38h] [rbp-C8h]
  char LengthReturned; // [rsp+40h] [rbp-C0h]
  char v50; // [rsp+70h] [rbp-90h]
  bool v51; // [rsp+71h] [rbp-8Fh] BYREF
  bool v52; // [rsp+72h] [rbp-8Eh] BYREF
  bool v53; // [rsp+73h] [rbp-8Dh] BYREF
  char v54; // [rsp+74h] [rbp-8Ch] BYREF
  bool v55; // [rsp+75h] [rbp-8Bh] BYREF
  char v56; // [rsp+76h] [rbp-8Ah]
  __int64 v57; // [rsp+78h] [rbp-88h] BYREF
  PFILE_OBJECT v58; // [rsp+80h] [rbp-80h] BYREF
  ULONG HashValue; // [rsp+88h] [rbp-78h] BYREF
  ULONG v60; // [rsp+8Ch] [rbp-74h] BYREF
  PFLT_CONTEXT v61; // [rsp+90h] [rbp-70h]
  HANDLE FileHandle; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+A0h] [rbp-60h] BYREF
  UNICODE_STRING SourceString; // [rsp+B0h] [rbp-50h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+C0h] [rbp-40h] BYREF
  PFILE_OBJECT v66; // [rsp+C8h] [rbp-38h]
  struct _LIST_ENTRY *v67; // [rsp+D0h] [rbp-30h]
  PVOID FltObject; // [rsp+D8h] [rbp-28h]
  PFLT_CONTEXT Context; // [rsp+E0h] [rbp-20h]
  _QWORD *v70; // [rsp+E8h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v72; // [rsp+100h] [rbp+0h] BYREF
  __int64 v73; // [rsp+110h] [rbp+10h]
  __int128 FileInformation; // [rsp+118h] [rbp+18h] BYREF
  char v75[32]; // [rsp+128h] [rbp+28h] BYREF
  struct _UNICODE_STRING *p_Destination; // [rsp+148h] [rbp+48h]
  __int64 v77; // [rsp+150h] [rbp+50h]

  v67 = a5;
  *(_QWORD *)&Destination.Length = 0;
  FileHandle = 0;
  v9 = 0;
  v58 = 0;
  v10 = 0;
  *(_QWORD *)&SourceString.Length = 0;
  v56 = 0;
  LODWORD(v57) = 0;
  v55 = 0;
  v53 = 0;
  v52 = 0;
  v54 = 0;
  v51 = 0;
  FileNameInformation = 0;
  v60 = 0;
  v61 = 0;
  Context = 0;
  HashValue = 0;
  v70 = a2;
  v73 = 0;
  FltObject = a4;
  v66 = FileObject;
  DestinationString = 0;
  v72 = 0;
  FileInformation = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  WcGetContextFileObject((PFLT_INSTANCE)a4, FileObject);
  v13 = FltQueryDirectoryFile(
          (PFLT_INSTANCE)a4,
          FileObject,
          &FileInformation,
          0x10u,
          FileNamesInformation,
          1u,
          FileName,
          1u,
          0);
  v14 = 0x80000000;
  if ( (int)(v13 + 0x80000000) < 0 || v13 == -2147483643 )
  {
    SourceDirectory = 0;
    v50 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v14) = 5;
      WPP_RECORDER_SF_sDZ(
        WcVerboseRecorder,
        v14,
        10,
        26,
        (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
        47,
        (__int64)FileName);
    }
    goto LABEL_84;
  }
  v15 = (struct _KEVENT *)((char *)v61 + 232);
  KeWaitForSingleObject((char *)v61 + 232, Executive, 0, 0, 0);
  v16 = *((_QWORD *)v61 + 32);
  if ( v16 && *(_DWORD *)(v16 + 20) )
  {
    v50 = 1;
    SourceDirectory = RtlDowncaseUnicodeString(&DestinationString, FileName, 1u);
    if ( SourceDirectory < 0 )
      goto LABEL_84;
    SourceDirectory = RtlHashUnicodeString(&DestinationString, 1u, 0, &HashValue);
    if ( SourceDirectory < 0 )
      goto LABEL_84;
    if ( RtlLookupEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)v61 + 32), HashValue, 0) )
    {
      SourceDirectory = -1073741267;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LengthReturned = 45;
        v19 = 27;
        RestartScan = FileName;
        FileNamea = 105;
LABEL_11:
        LODWORD(DeviceExtension) = WcVerboseRecorder;
        v21 = 10;
        LOBYTE(v18) = 5;
LABEL_12:
        WPP_RECORDER_SF_sDZd(
          (_DWORD)DeviceExtension,
          v18,
          v21,
          v19,
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
  KeSetEvent(v15, 0, 0);
  v50 = 0;
  SourceDirectory = WcLocateSourceDirectory(FileName);
  if ( SourceDirectory < 0 )
    goto LABEL_84;
  v22 = *(_QWORD *)&Destination.Length;
  SourceDirectory = WcOpenAsReparsePoint(
                      FileName,
                      *(void **)(*(_QWORD *)(*(_QWORD *)&Destination.Length + 24LL) + 8LL),
                      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&Destination.Length + 24LL) + 16LL),
                      **(struct _FLT_INSTANCE ***)(*(_QWORD *)&Destination.Length + 24LL),
                      0x120088u,
                      **((_DWORD **)Context + 8),
                      &FileHandle,
                      &v58,
                      &v55,
                      &v53,
                      &v52,
                      &v54,
                      &v51);
  if ( SourceDirectory < 0 )
    goto LABEL_84;
  if ( a8 )
  {
    SourceDirectory = -1073741772;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LengthReturned = 52;
      v19 = 28;
      RestartScan = FileName;
      FileNamea = -101;
      goto LABEL_11;
    }
    goto LABEL_84;
  }
  if ( v51 )
  {
LABEL_20:
    SourceDirectory = -1073741772;
    goto LABEL_84;
  }
  if ( a7 )
  {
    SourceDirectory = FltGetFileNameInformationUnsafe(v58, **(PFLT_INSTANCE **)(v22 + 24), 0x101u, &FileNameInformation);
    if ( SourceDirectory < 0 )
      goto LABEL_84;
    SourceDirectory = FltParseFileNameInformation(FileNameInformation);
    if ( SourceDirectory < 0 )
      goto LABEL_84;
    Length = FileNameInformation->Stream.Length;
    p_FinalComponent = &FileNameInformation->FinalComponent;
    if ( Length )
      p_FinalComponent->Length -= Length;
    if ( FileName->Length <= 0x18u && RtlCompareUnicodeString(p_FinalComponent, FileName, 1u) )
    {
      RtlHashUnicodeString(p_FinalComponent, 1u, 0, &v60);
      if ( (unsigned int)dword_14000E060 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
      {
        *(_QWORD *)&Destination.Length = v60;
        v77 = 8;
        p_Destination = &Destination;
        tlgWriteTransfer_EtwWriteTransfer(&dword_14000E060, byte_14000B591, 0, 0, 3, v75);
      }
      goto LABEL_20;
    }
  }
  else
  {
    p_FinalComponent = FileName;
  }
  v25 = (_QWORD *)*v70;
  v70 = (_QWORD *)*v70;
  if ( v52 || v53 )
  {
    SourceDirectory = WcCopyFile(
                        (__int64)FileHandle,
                        v58,
                        **(struct _FLT_INSTANCE ***)(v22 + 24),
                        p_FinalComponent,
                        (struct _FLT_INSTANCE *)FltObject,
                        v67,
                        (__int64)v66,
                        0,
                        *(_DWORD *)(*(_QWORD *)(v25[3] + 32LL) + 16LL));
    if ( SourceDirectory >= 0 )
      goto LABEL_84;
    if ( SourceDirectory == -1073741771 || SourceDirectory == -1073739511 )
    {
      SourceDirectory = 0;
      goto LABEL_84;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_84;
    LengthReturned = SourceDirectory;
    v19 = 29;
    RestartScan = p_FinalComponent;
    FileNamea = 26;
    v21 = 10;
    goto LABEL_79;
  }
  if ( v54 )
  {
    LODWORD(v72) = -2147483616;
    v9 = &v72;
    WORD2(v72) = 0;
    v26 = 8;
    v56 = 1;
    goto LABEL_57;
  }
  if ( v55 )
  {
    SourceDirectory = WcGetReparseData(**(PFLT_INSTANCE **)(v22 + 24), v58, (__int64)&v57);
    if ( SourceDirectory < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v27,
          15,
          30,
          (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
          57,
          SourceDirectory);
      }
      v9 = *(__int128 **)&SourceString.Length;
      goto LABEL_84;
    }
    v9 = *(__int128 **)&SourceString.Length;
    v26 = v57;
    SourceDirectory = WcValidateWcReparseInfo(*(_QWORD *)&SourceString.Length, (unsigned int)v57);
    if ( SourceDirectory < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_84;
      RestartScana = SourceDirectory;
      v29 = 31;
      FileNameb = 64;
      goto LABEL_44;
    }
    if ( *((_QWORD *)v9 + 2) == *(_QWORD *)&GUID_NULL.Data1 && *((_QWORD *)v9 + 3) == *(_QWORD *)GUID_NULL.Data4 )
      v9[1] = *(_OWORD *)*(_QWORD *)(*(_QWORD *)(v22 + 24) + 32LL);
    *((_DWORD *)v9 + 3) &= 0xFFFFFFF1;
    goto LABEL_57;
  }
  v30 = *(unsigned __int16 *)(a3 + 32) + 34;
  v31 = (*(_WORD *)(a3 + 32) != 0 ? 2 : 0) + p_FinalComponent->Length;
  LODWORD(v57) = *(_WORD *)(a3 + 32) != 0 ? 2 : 0;
  v26 = v31 + v30;
  Destination = 0;
  SourceString = 0;
  Pool2 = ExAllocatePool2(256, v26, 1769096023);
  v9 = (__int128 *)Pool2;
  if ( !Pool2 )
  {
    SourceDirectory = -1073741670;
    goto LABEL_84;
  }
  *(_QWORD *)(Pool2 + 8) = 1;
  *(_OWORD *)(Pool2 + 16) = *(_OWORD *)*(_QWORD *)(*(_QWORD *)(v22 + 24) + 32LL);
  SourceDirectory = RtlUShortAdd(p_FinalComponent->Length, *(_WORD *)(a3 + 32), (USHORT *)(Pool2 + 32));
  if ( SourceDirectory >= 0 )
  {
    SourceDirectory = RtlUShortAdd(*((_WORD *)v9 + 16), v57, v33);
    if ( SourceDirectory >= 0 )
    {
      *(_DWORD *)v9 = *(_DWORD *)a3;
      SourceDirectory = RtlUShortAdd(0x1Au, *((_WORD *)v9 + 16), (USHORT *)v9 + 2);
      if ( SourceDirectory >= 0 )
      {
        Destination.MaximumLength = *((_WORD *)v9 + 16);
        Destination.Length = v34;
        Destination.Buffer = (PWSTR)v9 + 17;
        SourceString.MaximumLength = *(_WORD *)(a3 + 32);
        SourceString.Length = SourceString.MaximumLength;
        SourceString.Buffer = (PWSTR)(a3 + 34);
        RtlCopyUnicodeString(&Destination, &SourceString);
        if ( !*(_WORD *)(a3 + 32)
          || (SourceDirectory = RtlAppendUnicodeToString(&Destination, L"\\"), SourceDirectory >= 0) )
        {
          SourceDirectory = RtlAppendUnicodeStringToString(&Destination, p_FinalComponent);
          if ( SourceDirectory >= 0 )
          {
LABEL_57:
            v35 = v70;
            v36 = *(_DWORD *)(*(_QWORD *)(v70[3] + 32LL) + 16LL);
            if ( (v36 & 0x20) != 0 )
            {
              v37 = (struct _KEVENT *)ExAllocateFromNPagedLookasideList(&stru_14000E600);
              v10 = v37;
              if ( !v37 )
              {
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  goto LABEL_84;
                RestartScana = SourceDirectory;
                v29 = 32;
                FileNameb = -86;
                goto LABEL_44;
              }
              v38 = (struct _LIST_ENTRY *)FltObject;
              *(_QWORD *)&v37->Header.Lock = FileHandle;
              v37->Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v58;
              v39 = **(struct _LIST_ENTRY ***)(v22 + 24);
              v37[1].Header.WaitListHead.Blink = v67;
              v40 = v66;
              v10->Header.WaitListHead.Blink = v39;
              *(_QWORD *)&v10[2].Header.Lock = v40;
              *(_QWORD *)&v10[1].Header.Lock = p_FinalComponent;
              v10[1].Header.WaitListHead.Flink = v38;
              v10[2].Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v9;
              LODWORD(v10[2].Header.WaitListHead.Blink) = v26;
              v10[4].Header.LockNV = 0;
              v10[4].Header.SignalState = *(_DWORD *)(*(_QWORD *)(v35[3] + 32LL) + 16LL);
              KeInitializeEvent(v10 + 3, NotificationEvent, 0);
              GenericWorkItem = FltAllocateGenericWorkItem();
              v42 = GenericWorkItem;
              if ( !GenericWorkItem )
              {
                SourceDirectory = -1073741670;
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  goto LABEL_84;
                RestartScana = -102;
                v29 = 33;
                FileNameb = -63;
                goto LABEL_44;
              }
              SourceDirectory = FltQueueGenericWorkItem(
                                  GenericWorkItem,
                                  v38,
                                  WcCopyAsPlaceHolderWorker,
                                  CriticalWorkQueue,
                                  v10);
              if ( SourceDirectory < 0 )
              {
                FltFreeGenericWorkItem(v42);
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  goto LABEL_84;
                RestartScana = SourceDirectory;
                v29 = 34;
                FileNameb = -50;
LABEL_44:
                LOBYTE(v28) = 2;
                WPP_RECORDER_SF_sDd(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v28,
                  15,
                  v29,
                  (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
                  (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
                  FileNameb,
                  RestartScana);
                goto LABEL_84;
              }
              KeWaitForSingleObject(&v10[3], Executive, 0, 0, 0);
              SourceDirectory = v10[4].Header.Lock;
              if ( SourceDirectory >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_84;
              LengthReturned = v10[4].Header.LockNV;
              v19 = 35;
              RestartScan = p_FinalComponent;
              FileNamea = -37;
            }
            else
            {
              SourceDirectory = WcCopyAsPlaceHolder(
                                  (__int64)FileHandle,
                                  v58,
                                  **(struct _FLT_INSTANCE ***)(v22 + 24),
                                  p_FinalComponent,
                                  (struct _FLT_INSTANCE *)FltObject,
                                  v67,
                                  (__int64)v66,
                                  (__int64)v9,
                                  v26,
                                  v36);
              if ( SourceDirectory >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_84;
              LengthReturned = SourceDirectory;
              v19 = 36;
              RestartScan = p_FinalComponent;
              FileNamea = -19;
            }
            v21 = 15;
LABEL_79:
            LOBYTE(v18) = 2;
            DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
            goto LABEL_12;
          }
        }
      }
    }
  }
LABEL_84:
  RtlFreeUnicodeString(&DestinationString);
  v43 = v61;
  if ( v50 )
    KeSetEvent((PRKEVENT)((char *)v61 + 232), 0, 0);
  if ( v9 && !v56 )
    ExFreePoolWithTag(v9, 0x69724357u);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v58 )
    ObfDereferenceObject(v58);
  if ( Context )
    FltReleaseContext(Context);
  if ( v43 )
    FltReleaseContext(v43);
  if ( v10 )
    ExFreeToNPagedLookasideList(&stru_14000E600, v10);
  return (unsigned int)SourceDirectory;
}

```

## disassembly

```asm
0x140030d54  push    rbp
0x140030d56  push    rbx
0x140030d57  push    rsi
0x140030d58  push    rdi
0x140030d59  push    r12
0x140030d5b  push    r13
0x140030d5d  push    r14
0x140030d5f  push    r15
0x140030d61  lea     rbp, [rsp-68h]
0x140030d66  sub     rsp, 168h
0x140030d6d  mov     rax, cs:__security_cookie
0x140030d74  xor     rax, rsp
0x140030d77  mov     [rbp+0A0h+var_48], rax
0x140030d7b  mov     rax, [rbp+0A0h+arg_20]
0x140030d82  xorps   xmm0, xmm0
0x140030d85  mov     rsi, [rbp+0A0h+FileObject]
0x140030d8c  mov     r15, rcx
0x140030d8f  xor     ecx, ecx
0x140030d91  mov     [rbp+0A0h+var_D0], rax
0x140030d95  mov     qword ptr [rbp+0A0h+Destination.Length], rcx
0x140030d99  xor     eax, eax
0x140030d9b  mov     [rbp+0A0h+FileHandle], rcx
0x140030d9f  mov     edi, ecx
0x140030da1  mov     [rbp+0A0h+var_120], rcx
0x140030da5  mov     r14d, ecx
0x140030da8  mov     qword ptr [rbp+0A0h+SourceString.Length], rcx
0x140030dac  mov     rbx, r9
0x140030daf  mov     [rsp+1A0h+var_12A], cl
0x140030db3  mov     r13, rdx
0x140030db6  mov     dword ptr [rsp+1A0h+var_128], ecx
0x140030dba  mov     r12, r8
0x140030dbd  mov     [rsp+1A0h+var_12B], cl
0x140030dc1  mov     [rsp+1A0h+var_12D], cl
0x140030dc5  mov     [rsp+1A0h+var_12E], cl
0x140030dc9  mov     [rsp+1A0h+var_12C], cl
0x140030dcd  mov     [rsp+1A0h+var_12F], cl
0x140030dd1  mov     [rbp+0A0h+FileNameInformation], rcx
0x140030dd5  mov     [rbp+0A0h+var_114], ecx
0x140030dd8  mov     [rbp+0A0h+var_110], rcx
0x140030ddc  mov     [rbp+0A0h+Context], rcx
0x140030de0  mov     [rbp+0A0h+HashValue], ecx
0x140030de3  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x140030de7  mov     [rbp+0A0h+var_B8], rdx
0x140030deb  xor     edx, edx; SourceString
0x140030ded  mov     [rbp+0A0h+var_90], rax
0x140030df1  mov     [rbp+0A0h+FltObject], rbx
0x140030df5  mov     [rbp+0A0h+var_D8], rsi
0x140030df9  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x140030dfd  movups  [rbp+0A0h+var_A0], xmm0
0x140030e01  movups  [rbp+0A0h+FileInformation], xmm0
0x140030e05  call    cs:__imp_RtlInitUnicodeString
0x140030e0c  nop     dword ptr [rax+rax+00h]
0x140030e11  lea     r9, [rbp+0A0h+var_110]
0x140030e15  mov     rdx, rsi; FileObject
0x140030e18  lea     r8, [rbp+0A0h+Context]
0x140030e1c  mov     rcx, rbx; Instance
0x140030e1f  call    WcGetContextFileObject
0x140030e24  mov     [rsp+1A0h+LengthReturned], r14; LengthReturned
0x140030e29  lea     r9d, [r14+10h]; Length
0x140030e2d  mov     [rsp+1A0h+RestartScan], 1; RestartScan
0x140030e32  lea     r8, [rbp+0A0h+FileInformation]; FileInformation
0x140030e36  mov     [rsp+1A0h+FileName], r15; FileName
0x140030e3b  mov     rdx, rsi; FileObject
0x140030e3e  mov     [rsp+1A0h+ReturnSingleEntry], 1; ReturnSingleEntry
0x140030e43  mov     rcx, rbx; Instance
0x140030e46  mov     [rsp+1A0h+FileInformationClass], 0Ch; FileInformationClass
0x140030e4e  call    cs:__imp_FltQueryDirectoryFile
0x140030e55  nop     dword ptr [rax+rax+00h]
0x140030e5a  mov     edx, 80000000h
0x140030e5f  lea     ecx, [rax+rdx]
0x140030e62  test    edx, ecx
0x140030e64  jnz     loc_14003178A
0x140030e6a  cmp     eax, 80000005h
0x140030e6f  jz      loc_14003178A
0x140030e75  mov     rbx, [rbp+0A0h+var_110]
0x140030e79  xor     r9d, r9d; Alertable
0x140030e7c  xor     r8d, r8d; WaitMode
0x140030e7f  mov     qword ptr [rsp+1A0h+FileInformationClass], r14; Timeout
0x140030e84  xor     edx, edx; WaitReason
0x140030e86  lea     rsi, [rbx+0E8h]
0x140030e8d  mov     rcx, rsi; Object
0x140030e90  call    cs:__imp_KeWaitForSingleObject
0x140030e97  nop     dword ptr [rax+rax+00h]
0x140030e9c  mov     rax, [rbx+100h]
0x140030ea3  xor     ecx, ecx
0x140030ea5  test    rax, rax
0x140030ea8  jz      loc_140030F93
0x140030eae  cmp     [rax+14h], ecx
0x140030eb1  jz      loc_140030F93
0x140030eb7  mov     r8b, 1; AllocateDestinationString
0x140030eba  mov     [rsp+1A0h+var_130], 1
0x140030ebf  mov     rdx, r15; SourceString
0x140030ec2  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x140030ec6  call    cs:__imp_RtlDowncaseUnicodeString
0x140030ecd  nop     dword ptr [rax+rax+00h]
0x140030ed2  mov     ebx, eax
0x140030ed4  test    eax, eax
0x140030ed6  js      loc_1400317E8
0x140030edc  lea     r9, [rbp+0A0h+HashValue]; HashValue
0x140030ee0  xor     r8d, r8d; HashAlgorithm
0x140030ee3  mov     dl, 1; CaseInSensitive
0x140030ee5  lea     rcx, [rbp+0A0h+DestinationString]; String
0x140030ee9  call    cs:__imp_RtlHashUnicodeString
0x140030ef0  nop     dword ptr [rax+rax+00h]
0x140030ef5  mov     ebx, eax
0x140030ef7  test    eax, eax
0x140030ef9  js      loc_1400317E8
0x140030eff  mov     rcx, [rbp+0A0h+var_110]
0x140030f03  xor     r8d, r8d; Context
0x140030f06  mov     edx, [rbp+0A0h+HashValue]; Signature
0x140030f09  mov     rcx, [rcx+100h]; HashTable
0x140030f10  call    cs:__imp_RtlLookupEntryHashTable
0x140030f17  nop     dword ptr [rax+rax+00h]
0x140030f1c  xor     ecx, ecx
0x140030f1e  test    rax, rax
0x140030f21  jz      short loc_140030F93
0x140030f23  mov     ebx, 0C000022Dh
0x140030f28  lea     rax, WPP_RECORDER_INITIALIZED
0x140030f2f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140030f36  jz      loc_1400317E8
0x140030f3c  mov     rax, cs:WPP_GLOBAL_Control
0x140030f43  cmp     [rax+48h], cx
0x140030f47  jz      loc_1400317E8
0x140030f4d  mov     dword ptr [rsp+1A0h+LengthReturned], ebx
0x140030f51  lea     r9d, [r14+1Bh]
0x140030f55  mov     qword ptr [rsp+1A0h+RestartScan], r15
0x140030f5a  mov     dword ptr [rsp+1A0h+FileName], 969h
0x140030f62  mov     rcx, cs:_WcVerboseRecorder
0x140030f69  mov     r8d, 0Ah
0x140030f6f  mov     dl, 5
0x140030f71  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x140030f78  mov     qword ptr [rsp+1A0h+ReturnSingleEntry], rax
0x140030f7d  lea     rax, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x140030f84  mov     qword ptr [rsp+1A0h+FileInformationClass], rax
0x140030f89  call    WPP_RECORDER_SF_sDZd
0x140030f8e  jmp     loc_1400317E8
0x140030f93  xor     r8d, r8d; Wait
0x140030f96  xor     edx, edx; Increment
0x140030f98  mov     rcx, rsi; Event
0x140030f9b  call    cs:__imp_KeSetEvent
0x140030fa2  nop     dword ptr [rax+rax+00h]
0x140030fa7  xor     esi, esi
0x140030fa9  lea     r8, [rbp+0A0h+Destination]
0x140030fad  mov     rdx, r13
0x140030fb0  mov     [rsp+1A0h+var_130], sil
0x140030fb5  mov     rcx, r15; FileName
0x140030fb8  call    WcLocateSourceDirectory
0x140030fbd  mov     ebx, eax
0x140030fbf  test    eax, eax
0x140030fc1  js      loc_1400317E8
0x140030fc7  mov     r13, qword ptr [rbp+0A0h+Destination.Length]
0x140030fcb  lea     rcx, [rsp+1A0h+var_12F]
0x140030fd0  mov     rax, [rbp+0A0h+Context]
0x140030fd4  mov     [rsp+1A0h+var_140], rcx
0x140030fd9  lea     rcx, [rsp+1A0h+var_12C]
0x140030fde  mov     [rsp+1A0h+var_148], rcx
0x140030fe3  lea     rcx, [rsp+1A0h+var_12E]
0x140030fe8  mov     rdx, [r13+18h]
0x140030fec  mov     rax, [rax+40h]
0x140030ff0  mov     [rsp+1A0h+var_150], rcx
0x140030ff5  lea     rcx, [rsp+1A0h+var_12D]
0x140030ffa  mov     [rsp+1A0h+var_158], rcx
0x140030fff  lea     rcx, [rsp+1A0h+var_12B]
0x140031004  mov     r9, [rdx]
0x140031007  mov     eax, [rax]
0x140031009  mov     r8, [rdx+10h]
0x14003100d  mov     rdx, [rdx+8]
0x140031011  mov     [rsp+1A0h+LengthReturned], rcx
0x140031016  lea     rcx, [rbp+0A0h+var_120]
0x14003101a  mov     qword ptr [rsp+1A0h+RestartScan], rcx
0x14003101f  lea     rcx, [rbp+0A0h+FileHandle]
0x140031023  mov     [rsp+1A0h+FileName], rcx
0x140031028  mov     rcx, r15
0x14003102b  mov     dword ptr [rsp+1A0h+ReturnSingleEntry], eax
0x14003102f  mov     [rsp+1A0h+FileInformationClass], 120088h
0x140031037  call    WcOpenAsReparsePoint
0x14003103c  xor     r10d, r10d
0x14003103f  mov     ebx, eax
0x140031041  test    eax, eax
0x140031043  js      loc_1400317E8
0x140031049  cmp     [rbp+0A0h+arg_38], r10b
0x140031050  jz      short loc_140031097
0x140031052  mov     ebx, 0C0000034h
0x140031057  lea     rax, WPP_RECORDER_INITIALIZED
0x14003105e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031065  jz      loc_1400317E8
0x14003106b  mov     rax, cs:WPP_GLOBAL_Control
0x140031072  cmp     [rax+48h], r10w
0x140031077  jz      loc_1400317E8
0x14003107d  mov     dword ptr [rsp+1A0h+LengthReturned], ebx
0x140031081  lea     r9d, [rsi+1Ch]
0x140031085  mov     qword ptr [rsp+1A0h+RestartScan], r15
0x14003108a  mov     dword ptr [rsp+1A0h+FileName], 99Bh
0x140031092  jmp     loc_140030F62
0x140031097  cmp     [rsp+1A0h+var_12F], r10b
0x14003109c  jz      short loc_1400310A8
0x14003109e  mov     ebx, 0C0000034h
0x1400310a3  jmp     loc_1400317E8
0x1400310a8  cmp     [rbp+0A0h+arg_30], r10b
0x1400310af  jz      loc_1400311C7
0x1400310b5  mov     rdx, [r13+18h]
0x1400310b9  lea     r9, [rbp+0A0h+FileNameInformation]; FileNameInformation
0x1400310bd  mov     rcx, [rbp+0A0h+var_120]; FileObject
0x1400310c1  mov     r8d, 101h; NameOptions
0x1400310c7  mov     rdx, [rdx]; Instance
0x1400310ca  call    cs:__imp_FltGetFileNameInformationUnsafe
0x1400310d1  nop     dword ptr [rax+rax+00h]
0x1400310d6  mov     ebx, eax
0x1400310d8  test    eax, eax
0x1400310da  js      loc_1400317E8
0x1400310e0  mov     rcx, [rbp+0A0h+FileNameInformation]; FileNameInformation
0x1400310e4  call    cs:__imp_FltParseFileNameInformation
0x1400310eb  nop     dword ptr [rax+rax+00h]
0x1400310f0  xor     r10d, r10d
0x1400310f3  mov     ebx, eax
0x1400310f5  test    eax, eax
0x1400310f7  js      loc_1400317E8
0x1400310fd  mov     rax, [rbp+0A0h+FileNameInformation]
0x140031101  movzx   ecx, word ptr [rax+48h]
0x140031105  lea     rsi, [rax+58h]
0x140031109  test    cx, cx
0x14003110c  jz      short loc_140031111
0x14003110e  sub     [rsi], cx
0x140031111  cmp     word ptr [r15], 18h
0x140031116  ja      loc_1400311CA
0x14003111c  mov     r8b, 1; CaseInSensitive
0x14003111f  mov     rdx, r15; String2
0x140031122  mov     rcx, rsi; String1
0x140031125  call    cs:__imp_RtlCompareUnicodeString
0x14003112c  nop     dword ptr [rax+rax+00h]
0x140031131  xor     r10d, r10d
0x140031134  test    eax, eax
0x140031136  jz      loc_1400311CA
0x14003113c  lea     r9, [rbp+0A0h+var_114]; HashValue
0x140031140  xor     r8d, r8d; HashAlgorithm
0x140031143  mov     dl, 1; CaseInSensitive
0x140031145  mov     rcx, rsi; String
0x140031148  call    cs:__imp_RtlHashUnicodeString
0x14003114f  nop     dword ptr [rax+rax+00h]
0x140031154  mov     eax, cs:dword_14000E060
0x14003115a  cmp     eax, 5
0x14003115d  jbe     loc_14003109E
0x140031163  mov     rdx, 400000000000h
0x14003116d  lea     rcx, dword_14000E060
0x140031174  call    _tlgKeywordOn
0x140031179  test    al, al
0x14003117b  jz      loc_14003109E
0x140031181  mov     eax, [rbp+0A0h+var_114]
0x140031184  lea     rdx, byte_14000B591
0x14003118b  mov     qword ptr [rbp+0A0h+Destination.Length], rax
0x14003118f  lea     rcx, dword_14000E060
0x140031196  lea     rax, [rbp+0A0h+Destination]
0x14003119a  mov     [rbp+0A0h+var_50], 8
0x1400311a2  mov     [rbp+0A0h+var_58], rax
0x1400311a6  xor     r9d, r9d
0x1400311a9  lea     rax, [rbp+0A0h+var_78]
0x1400311ad  xor     r8d, r8d
0x1400311b0  mov     qword ptr [rsp+1A0h+ReturnSingleEntry], rax
0x1400311b5  mov     [rsp+1A0h+FileInformationClass], 3
0x1400311bd  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400311c2  jmp     loc_14003109E
0x1400311c7  mov     rsi, r15
0x1400311ca  mov     rax, [rbp+0A0h+var_B8]
0x1400311ce  mov     rax, [rax]
0x1400311d1  mov     [rbp+0A0h+var_B8], rax
0x1400311d5  cmp     [rsp+1A0h+var_12E], r10b
0x1400311da  jnz     loc_1400316E3
0x1400311e0  cmp     [rsp+1A0h+var_12D], r10b
0x1400311e5  jnz     loc_1400316E3
0x1400311eb  cmp     [rsp+1A0h+var_12C], r10b
0x1400311f0  jz      short loc_140031212
0x1400311f2  mov     dword ptr [rbp+0A0h+var_A0], 80000020h
0x1400311f9  lea     rdi, [rbp+0A0h+var_A0]
0x1400311fd  mov     word ptr [rbp+0A0h+var_A0+4], r10w
0x140031202  mov     r15d, 8
0x140031208  mov     [rsp+1A0h+var_12A], 1
0x14003120d  jmp     loc_1400314A1
0x140031212  cmp     [rsp+1A0h+var_12B], r10b
0x140031217  jz      loc_140031348
0x14003121d  mov     rcx, [r13+18h]
0x140031221  lea     rax, [rsp+1A0h+var_128]
0x140031226  mov     rdx, [rbp+0A0h+var_120]; FileObject
0x14003122a  lea     r9, [rbp+0A0h+SourceString]
0x14003122e  mov     r8d, 200h
0x140031234  mov     qword ptr [rsp+1A0h+FileInformationClass], rax; __int64
0x140031239  mov     rcx, [rcx]; Instance
0x14003123c  call    WcGetReparseData
0x140031241  mov     ebx, eax
0x140031243  test    eax, eax
0x140031245  jns     short loc_1400312A0
0x140031247  lea     rax, WPP_RECORDER_INITIALIZED
0x14003124e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140031255  jz      short loc_140031297
0x140031257  mov     rcx, cs:WPP_GLOBAL_Control
0x14003125e  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x140031265  mov     dword ptr [rsp+1A0h+RestartScan], ebx
0x140031269  mov     r9d, 1Eh
0x14003126f  mov     dword ptr [rsp+1A0h+FileName], 0A39h
0x140031277  mov     dl, 2
0x140031279  mov     qword ptr [rsp+1A0h+ReturnSingleEntry], rax
  ... truncated ...
```
