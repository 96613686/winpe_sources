# MpHardenPathOnRenameLink

- ea: `0x140046090`
- end: `0x140046e30`
- name: `MpHardenPathOnRenameLink`
- size: `3488`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400459c0`

## callees

- `0x140002450`
- `0x1400051bc`
- `0x1400068fc`
- `0x1400118d0`
- `0x140011bc0`
- `0x140030060`
- `0x14003ee80`
- `0x140040388`
- `0x140046090`
- `0x140046e30`
- `0x1400471ac`
- `0x1400479fc`
- `0x1400484fc`
- `0x140048908`
- `0x140048c98`
- `0x140066180`
- `0x1400704f8`
- `0x1400732c0`
- `0x140088da4`
- `0x14008ab44`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x1400461bc`
- `ntoskrnl!PsGetProcessId` at `0x1400461bc`
- `ntoskrnl!PsInitialSystemProcess` at `0x140046136`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400461aa`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400461aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046259`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046d94`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046259`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046d94`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004624d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046d88`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004624d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046d88`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400461ef`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400461ef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400461dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400461dd`
- `ntoskrnl!IoThreadToProcess` at `0x140046166`
- `ntoskrnl!IoThreadToProcess` at `0x140046192`
- `ntoskrnl!IoThreadToProcess` at `0x140046166`
- `ntoskrnl!IoThreadToProcess` at `0x140046192`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140046cc6`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140046d39`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140046cc6`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140046d39`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x1400463a6`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x1400463a6`
- `FLTMGR!FltReleaseContext` at `0x140046a47`
- `FLTMGR!FltReleaseContext` at `0x140046a47`
- `FLTMGR!FltGetFileNameInformation` at `0x140046744`
- `FLTMGR!FltGetFileNameInformation` at `0x140046744`
- `FLTMGR!FltGetStreamHandleContext` at `0x140046a2b`
- `FLTMGR!FltGetStreamHandleContext` at `0x140046a2b`
- `FLTMGR!FltGetFileSystemType` at `0x14004626e`
- `FLTMGR!FltGetFileSystemType` at `0x14004626e`
- `FLTMGR!FltIsDirectory` at `0x14004642a`
- `FLTMGR!FltIsDirectory` at `0x1400467e3`
- `FLTMGR!FltIsDirectory` at `0x14004642a`
- `FLTMGR!FltIsDirectory` at `0x1400467e3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140046504`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400466e3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140046504`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400466e3`

## string_xrefs

- `0x140046d5a`: `[Mini-filter] Denied rename/hardlink to file [%wZ] from process [%wZ][Pid:%u]. DynamicFsHardeningEnabled[%d].`

## pseudocode

```c
__int64 __fastcall MpHardenPathOnRenameLink(struct _FLT_CALLBACK_DATA *a1, __int64 a2)
{
  PFLT_CALLBACK_DATA v3; // r15
  __int64 v4; // rbx
  char IsAMPath; // r13
  NTSTATUS IsLoopbackByObj; // esi
  int v7; // eax
  struct _KPROCESS *RequestorProcess; // rdi
  struct _KPROCESS *v9; // rbx
  struct _KPROCESS *v10; // rbx
  LONGLONG TimeQuadPart; // r14
  volatile signed __int32 *v12; // rbx
  unsigned __int64 ProcessId; // rsi
  char *v14; // rbx
  _QWORD *v15; // r8
  _QWORD *i; // rax
  volatile signed __int32 *v17; // rdi
  char v18; // r14
  int v19; // eax
  bool v20; // r15
  FLT_FILE_NAME_OPTIONS v21; // edx
  PFLT_CALLBACK_DATA v22; // rbx
  ULONG Options; // ecx
  PFLT_FILE_NAME_INFORMATION *p_FileNameInformation; // rdx
  PFLT_IO_PARAMETER_BLOCK Iopb; // r8
  ULONG v26; // eax
  __int64 EaBuffer; // r8
  ULONG v28; // eax
  WCHAR *v29; // r9
  NTSTATUS RenameParentTargetSymLinkNameInformation; // eax
  __int64 v31; // rax
  struct _FLT_FILE_NAME_INFORMATION *v32; // rbx
  unsigned __int8 v33; // r14
  char v34; // r13
  PCUNICODE_STRING v35; // r15
  unsigned __int8 v36; // al
  __int64 v37; // rbx
  __int64 *v38; // rax
  __int64 *v39; // rcx
  __int64 *v40; // rax
  __int64 *v41; // rcx
  __int64 v42; // rdx
  int v44; // r9d
  struct _FLT_INSTANCE *v45; // rdx
  struct _FILE_OBJECT *v46; // rcx
  __int64 v47; // r9
  PFLT_FILE_NAME_INFORMATION v48; // rdx
  __int64 v49; // rcx
  FLT_FILE_NAME_OPTIONS v50; // ecx
  __int64 v51; // rdx
  struct _FILE_OBJECT *v52; // rdx
  struct _FLT_INSTANCE *v53; // rcx
  int v54; // ebx
  int v55; // eax
  PFLT_FILE_NAME_INFORMATION v56; // rdx
  _QWORD *v57; // r9
  char CurrentProcessId; // al
  PFLT_CALLBACK_DATA v59; // r14
  int v60; // r15d
  __int64 v61; // rbx
  unsigned int v62; // eax
  ULONG FileNameLength[2]; // [rsp+20h] [rbp-E0h]
  _QWORD *NameOptions; // [rsp+28h] [rbp-D8h]
  char v65; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v66; // [rsp+51h] [rbp-AFh] BYREF
  bool v67; // [rsp+52h] [rbp-AEh]
  PFLT_CALLBACK_DATA CallbackData; // [rsp+58h] [rbp-A8h]
  FLT_FILE_NAME_OPTIONS v69; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v70; // [rsp+68h] [rbp-98h] BYREF
  int v71; // [rsp+70h] [rbp-90h]
  __int64 v72; // [rsp+78h] [rbp-88h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+80h] [rbp-80h] BYREF
  PCUNICODE_STRING String2; // [rsp+88h] [rbp-78h] BYREF
  __int64 v75; // [rsp+90h] [rbp-70h] BYREF
  PFLT_CONTEXT Context; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 IsDirectory[4]; // [rsp+A0h] [rbp-60h] BYREF
  enum _FLT_FILESYSTEM_TYPE FileSystemType[3]; // [rsp+A4h] [rbp-5Ch] BYREF
  _QWORD v79[16]; // [rsp+B0h] [rbp-50h] BYREF

  v72 = a2;
  v3 = a1;
  CallbackData = a1;
  FileNameInformation = 0;
  memset(v79, 0, 0x78u);
  v4 = 0;
  FileSystemType[0] = FLT_FSTYPE_UNKNOWN;
  String2 = 0;
  IsAMPath = 0;
  v75 = 0;
  IsLoopbackByObj = 0;
  v7 = *(_DWORD *)(MpData + 868) & 0x4000;
  v70 = 0;
  v71 = v7;
  v66 = 0;
  v69 = 257;
  v65 = 0;
  RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(v3);
  if ( !RequestorProcess || PsInitialSystemProcess == RequestorProcess )
    goto LABEL_103;
  v9 = *(struct _KPROCESS **)(MpData + 232);
  if ( RequestorProcess == v9 )
    goto LABEL_102;
  if ( IoThreadToProcess(KeGetCurrentThread()) == v9 )
    goto LABEL_102;
  v10 = *(struct _KPROCESS **)(MpData + 256);
  if ( IoThreadToProcess(KeGetCurrentThread()) == v10 )
    goto LABEL_102;
  TimeQuadPart = PsGetProcessCreateTimeQuadPart(RequestorProcess);
  v12 = 0;
  ProcessId = (unsigned __int64)PsGetProcessId(RequestorProcess);
  if ( !ProcessId )
  {
LABEL_209:
    IsLoopbackByObj = -1073741275;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        36,
        WPP_ea3e370748bf3721894065c090fd2405_Traceguids,
        v3->Thread,
        -1073741275);
    }
    goto LABEL_98;
  }
  v14 = (char *)MpProcessTable;
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)(v14 + 8), 1u);
  v15 = (_QWORD *)(*((_QWORD *)MpProcessTable + 48) + 16 * ((ProcessId >> 2) & 0x7F));
  for ( i = (_QWORD *)*v15; ; i = (_QWORD *)*i )
  {
    if ( i == v15 )
    {
      ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
      KeLeaveCriticalRegion();
      v12 = 0;
      goto LABEL_209;
    }
    v17 = (volatile signed __int32 *)(i - 1);
    if ( ProcessId == i[2] && TimeQuadPart == *((_QWORD *)v17 + 4) )
      break;
  }
  _InterlockedIncrement(v17 + 12);
  ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
  KeLeaveCriticalRegion();
  IsLoopbackByObj = FltGetFileSystemType(*(PVOID *)(a2 + 24), FileSystemType);
  v18 = MpCheckForAmHardening((_DWORD)v3, a2, 0, (_DWORD)v17, FileSystemType[0] == FLT_FSTYPE_MUP);
  if ( (*(_DWORD *)(MpData + 864) & 8) != 0 )
  {
    if ( (v17[13] & 8) != 0 )
    {
      v20 = 0;
    }
    else
    {
      v19 = *((_DWORD *)v17 + 14);
      v20 = (v19 & 0x20000) != 0 && (v19 & 0x100000) == 0;
    }
  }
  else
  {
    v20 = 0;
  }
  v67 = v20;
  if ( !v18 )
  {
    v12 = v17;
    if ( !v20 )
      goto LABEL_64;
  }
  if ( FileSystemType[0] == FLT_FSTYPE_MUP )
  {
    IsLoopbackByObj = MpIsLoopbackByObj(a2, 0, &v66);
    if ( IsLoopbackByObj >= 0 )
    {
      v12 = v17;
      if ( v66 )
      {
        v21 = 258;
        v69 = 258;
        goto LABEL_19;
      }
      goto LABEL_100;
    }
    v12 = v17;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v51 = 37;
LABEL_150:
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v51,
        WPP_ea3e370748bf3721894065c090fd2405_Traceguids,
        KeGetCurrentThread(),
        IsLoopbackByObj);
    }
LABEL_64:
    v3 = CallbackData;
    goto LABEL_98;
  }
  v21 = 257;
LABEL_19:
  v22 = CallbackData;
  Options = CallbackData->Iopb->Parameters.Create.Options;
  if ( Options == 11 || Options == 72 )
  {
    IsLoopbackByObj = FltGetFileNameInformation(CallbackData, v21, &FileNameInformation);
    if ( IsLoopbackByObj < 0 )
    {
      if ( IsLoopbackByObj == -1073741612 || IsLoopbackByObj == -1073741766 )
      {
        v12 = v17;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          goto LABEL_64;
        v51 = 38;
      }
      else
      {
        v12 = v17;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_64;
        v51 = 39;
      }
      goto LABEL_150;
    }
    if ( !v66 )
    {
LABEL_116:
      if ( !v18 )
        goto LABEL_215;
      if ( (*(_DWORD *)(MpData + 868) & 0x4000) != 0 )
      {
        v45 = *(struct _FLT_INSTANCE **)(a2 + 24);
        v46 = *(struct _FILE_OBJECT **)(a2 + 32);
        IsDirectory[0] = 0;
        IsLoopbackByObj = FltIsDirectory(v46, v45, IsDirectory);
        if ( IsLoopbackByObj < 0 )
          IsDirectory[0] = 0;
        if ( String2 )
        {
          v47 = v75;
          v48 = 0;
          v49 = 0;
        }
        else
        {
          v49 = *(_QWORD *)(a2 + 24);
          v47 = 0;
          v48 = FileNameInformation;
        }
        LODWORD(NameOptions) = 0;
        IsAMPath = (unsigned __int8)MpFsHardeningAccessCheck(v17, v48, String2, v47, v49) == 0;
      }
      else
      {
        v56 = FileNameInformation;
        if ( String2 )
          v56 = 0;
        IsAMPath = MpIsAMPath(v17, v56);
      }
      if ( !IsAMPath )
      {
LABEL_215:
        if ( !v20 )
          goto LABEL_21;
        _mm_lfence();
        v44 = (int)String2;
        if ( !String2 )
          v44 = (_DWORD)FileNameInformation + 8;
        IsAMPath = MpApplyFolderGuard((_DWORD)v22, a2, (_DWORD)v17, v44, 0);
        if ( !IsAMPath )
          goto LABEL_21;
      }
LABEL_58:
      v22->IoStatus.Status = -1073741790;
      v22->IoStatus.Information = 0;
      IsLoopbackByObj = 1835009;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
      {
        v60 = v71;
        v59 = CallbackData;
      }
      else
      {
        if ( v17 )
          v37 = *((_QWORD *)v17 + 16);
        else
          v37 = 0;
        CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
        v59 = CallbackData;
        v60 = v71;
        WPP_SF_ZZDd(
          WPP_GLOBAL_Control->AttachedDevice,
          44,
          (unsigned int)WPP_ea3e370748bf3721894065c090fd2405_Traceguids,
          &CallbackData->Iopb->TargetFileObject->FileName,
          v37,
          CurrentProcessId,
          v71 != 0);
      }
      if ( v17 )
        v61 = *((_QWORD *)v17 + 16);
      else
        v61 = 0;
      v62 = (unsigned int)PsGetCurrentProcessId();
      FileNameLength[0] = v60 != 0;
      MpLogPrintfW(
        L"[Mini-filter] Denied rename/hardlink to file [%wZ] from process [%wZ][Pid:%u]. DynamicFsHardeningEnabled[%d].",
        &v59->Iopb->TargetFileObject->FileName,
        v61,
        v62,
        *(_QWORD *)FileNameLength);
      v12 = v17;
      goto LABEL_100;
    }
    v52 = *(struct _FILE_OBJECT **)(a2 + 32);
    v53 = *(struct _FLT_INSTANCE **)(a2 + 24);
    Context = 0;
    if ( FltGetStreamHandleContext(v53, v52, &Context) >= 0 && Context )
    {
      v54 = *((_DWORD *)Context + 22);
      FltReleaseContext(Context);
      if ( (v54 & 8) != 0 )
      {
        v55 = MpQueryLoopbackLocalPathByFileObject(a2, *(_QWORD *)(a2 + 32), &String2, &v75);
        v22 = CallbackData;
        goto LABEL_167;
      }
      v22 = CallbackData;
    }
    v55 = MpQueryLoopbackLocalPathByName(a2, FileNameInformation, &String2, &v75);
LABEL_167:
    IsLoopbackByObj = v55;
    if ( v55 >= 0 )
      goto LABEL_116;
    v12 = v17;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v51 = 40;
      goto LABEL_150;
    }
    goto LABEL_64;
  }
LABEL_21:
  if ( FileNameInformation )
  {
    FltReleaseFileNameInformation(FileNameInformation);
    p_FileNameInformation = 0;
    FileNameInformation = 0;
  }
  else
  {
    p_FileNameInformation = 0;
  }
  if ( String2 )
  {
    MpFreeString(String2);
    p_FileNameInformation = 0;
    String2 = 0;
  }
  if ( v75 )
  {
    MpFreeString(v75);
    p_FileNameInformation = 0;
    v75 = 0;
  }
  Iopb = v22->Iopb;
  v26 = Iopb->Parameters.Create.Options;
  switch ( v26 )
  {
    case 0x41u:
LABEL_28:
      EaBuffer = (__int64)Iopb->Parameters.Create.EaBuffer;
      v28 = *(_DWORD *)(EaBuffer + 16);
      v29 = (WCHAR *)(EaBuffer + 20);
      if ( v28
        && EaBuffer != -20
        && !*(_QWORD *)(EaBuffer + 8)
        && *v29 == 92
        && v28 >= 0xA
        && *(_WORD *)(EaBuffer + 22) == 63
        && *(_WORD *)(EaBuffer + 24) == 63
        && *(_WORD *)(EaBuffer + 26) == 92
        && (v28 < 0x10 || *(_WORD *)(EaBuffer + 30) != 58 || *(_WORD *)(EaBuffer + 32) != 92)
        && (v28 < 0x12
         || *(_WORD *)(EaBuffer + 28) != 85
         || *(_WORD *)(EaBuffer + 30) != 78
         || *(_WORD *)(EaBuffer + 32) != 67
         || *(_WORD *)(EaBuffer + 34) != 92) )
      {
        v65 = 1;
        if ( v66 )
        {
          v38 = &v75;
          v39 = &v70;
        }
        else
        {
          v38 = 0;
          v39 = 0;
          p_FileNameInformation = &FileNameInformation;
        }
        LOBYTE(v29) = 1;
        RenameParentTargetSymLinkNameInformation = MpGetRenameParentTargetSymLinkNameInformation(
                                                     (int)v22,
                                                     a2,
                                                     v66,
                                                     (int)v29,
                                                     EaBuffer,
                                                     v69,
                                                     p_FileNameInformation,
                                                     (__int64)v39,
                                                     (__int64)v38);
        goto LABEL_36;
      }
LABEL_35:
      v65 = 0;
      RenameParentTargetSymLinkNameInformation = FltGetDestinationFileNameInformation(
                                                   *(PFLT_INSTANCE *)(a2 + 24),
                                                   *(PFILE_OBJECT *)(a2 + 32),
                                                   *(HANDLE *)(EaBuffer + 8),
                                                   v29,
                                                   v28,
                                                   v69,
                                                   &FileNameInformation);
      goto LABEL_36;
    case 0xBu:
      goto LABEL_77;
    case 0xAu:
      goto LABEL_28;
    case 0x48u:
LABEL_77:
      EaBuffer = (__int64)Iopb->Parameters.Create.EaBuffer;
      v28 = *(_DWORD *)(EaBuffer + 16);
      v29 = (WCHAR *)(EaBuffer + 20);
      if ( !v28
        || EaBuffer == -20
        || *(_QWORD *)(EaBuffer + 8)
        || *v29 != 92
        || v28 < 0xA
        || *(_WORD *)(EaBuffer + 22) != 63
        || *(_WORD *)(EaBuffer + 24) != 63
        || *(_WORD *)(EaBuffer + 26) != 92
        || v28 >= 0x10 && *(_WORD *)(EaBuffer + 30) == 58 && *(_WORD *)(EaBuffer + 32) == 92
        || v28 >= 0x12
        && *(_WORD *)(EaBuffer + 28) == 85
        && *(_WORD *)(EaBuffer + 30) == 78
        && *(_WORD *)(EaBuffer + 32) == 67
        && *(_WORD *)(EaBuffer + 34) == 92 )
      {
        goto LABEL_35;
      }
      v65 = 1;
      if ( v66 )
      {
        v40 = &v75;
        v41 = &v70;
      }
      else
      {
        v40 = 0;
        v41 = 0;
        p_FileNameInformation = &FileNameInformation;
      }
      RenameParentTargetSymLinkNameInformation = MpGetRenameParentTargetSymLinkNameInformation(
                                                   (int)v22,
                                                   a2,
                                                   v66,
                                                   0,
                                                   EaBuffer,
                                                   v69,
                                                   p_FileNameInformation,
                                                   (__int64)v41,
                                                   (__int64)v40);
LABEL_36:
      IsLoopbackByObj = RenameParentTargetSymLinkNameInformation;
      break;
  }
  if ( IsLoopbackByObj < 0 )
  {
    if ( IsLoopbackByObj == -1073741612 || IsLoopbackByObj == -1073741766 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        goto LABEL_96;
      v42 = 41;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_96;
      v42 = 42;
    }
    goto LABEL_183;
  }
  if ( !v66 )
    goto LABEL_39;
  if ( !v65 )
  {
    _mm_lfence();
    IsLoopbackByObj = MpQueryLoopbackLocalPathByName(v72, FileNameInformation, &String2, &v75);
    if ( IsLoopbackByObj >= 0 )
    {
LABEL_39:
      v31 = v70;
      goto LABEL_40;
    }
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_96;
    v42 = 43;
LABEL_183:
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v42,
      WPP_ea3e370748bf3721894065c090fd2405_Traceguids,
      KeGetCurrentThread(),
      IsLoopbackByObj);
    goto LABEL_96;
  }
  v31 = v70;
  if ( v70 )
  {
    NameOptions = &v79[13];
    *(_OWORD *)&v79[1] = *(_OWORD *)v70;
    IsLoopbackByObj = MpParseFileName(v70, 0, &v79[7], &v79[9], &v79[11]);
    goto LABEL_39;
  }
LABEL_40:
  if ( v18 )
  {
    if ( String2 )
    {
      v32 = 0;
    }
    else
    {
      v32 = (struct _FLT_FILE_NAME_INFORMATION *)v79;
      if ( !v31 )
        v32 = FileNameInformation;
    }
    if ( v71 )
    {
      _mm_lfence();
      IsDirectory[0] = 0;
      IsLoopbackByObj = FltIsDirectory(*(PFILE_OBJECT *)(v72 + 32), *(PFLT_INSTANCE *)(v72 + 24), IsDirectory);
      if ( IsLoopbackByObj < 0 )
        IsDirectory[0] = 0;
      if ( !String2 )
        _mm_lfence();
      v33 = 0;
      v34 = IsDirectory[0];
      v35 = String2;
      if ( MpFsHardeningData && v17 && (v32 || String2) )
      {
        v69 = 0;
        v36 = FsHardeningMatch(v32, String2, 0, (int)NameOptions, (__int64)&v69);
        if ( v36 )
        {
          v50 = v69;
          if ( (v69 & 1) != 0 )
            v33 = v36;
          if ( (v69 & 2) != 0 )
          {
            LOBYTE(v50) = 1;
            MpTraceFsHardeningNotification(v50, v33, *((_QWORD *)v17 + 16), (_DWORD)v32, (__int64)v35, v34);
          }
        }
        else
        {
          v33 = 1;
        }
      }
      else
      {
        v33 = 0;
      }
      IsAMPath = v33 == 0;
    }
    else
    {
      IsAMPath = MpIsAMPath(v17, v32);
    }
    if ( IsAMPath )
    {
LABEL_57:
      v22 = CallbackData;
      goto LABEL_58;
    }
    v20 = v67;
  }
  if ( v20 )
  {
    _mm_lfence();
    LODWORD(v57) = (_DWORD)String2;
    if ( !String2 )
    {
      if ( v70 )
        v57 = &v79[1];
      else
        LODWORD(v57) = (_DWORD)FileNameInformation + 8;
    }
    v3 = CallbackData;
    IsAMPath = MpApplyFolderGuard((_DWORD)CallbackData, v72, (_DWORD)v17, (_DWORD)v57, v65);
  }
  else
  {
LABEL_96:
    v3 = CallbackData;
  }
  v12 = v17;
  if ( IsAMPath )
    goto LABEL_57;
LABEL_98:
  if ( IsLoopbackByObj == -1073741536 || IsLoopbackByObj == -1073741749 )
  {
    v3->IoStatus.Status = IsLoopbackByObj;
    IsLoopbackByObj = 1835009;
    v3->IoStatus.Information = 0;
  }
LABEL_100:
  if ( v12 )
    MpReleaseProcessContext(v12);
LABEL_102:
  v4 = v70;
LABEL_103:
  if ( String2 )
    MpFreeString(String2);
  if ( v75 )
  {
    MpFreeString(v75);
    v75 = 0;
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v4 )
    MpFreeString(v4);
  return (unsigned int)IsLoopbackByObj;
}

```

## disassembly

```asm
0x140046090  mov     [rsp-8+arg_10], rbx
0x140046095  push    rbp
0x140046096  push    rsi
0x140046097  push    rdi
0x140046098  push    r12
0x14004609a  push    r13
0x14004609c  push    r14
0x14004609e  push    r15
0x1400460a0  lea     rbp, [rsp-40h]
0x1400460a5  sub     rsp, 140h
0x1400460ac  mov     rax, cs:__security_cookie
0x1400460b3  xor     rax, rsp
0x1400460b6  mov     [rbp+70h+var_40], rax
0x1400460ba  mov     r12, rdx
0x1400460bd  mov     [rsp+170h+var_F8], rdx
0x1400460c2  mov     r15, rcx
0x1400460c5  mov     [rsp+170h+CallbackData], rcx
0x1400460ca  xor     r14d, r14d
0x1400460cd  lea     rcx, [rbp+70h+var_C0]; void *
0x1400460d1  xor     edx, edx; Val
0x1400460d3  mov     [rbp+70h+FileNameInformation], r14
0x1400460d7  mov     r8d, 78h ; 'x'; Size
0x1400460dd  call    memset
0x1400460e2  mov     rax, cs:MpData
0x1400460e9  mov     ebx, r14d
0x1400460ec  mov     [rbp+70h+FileSystemType], r14d
0x1400460f0  mov     rcx, r15
0x1400460f3  mov     [rbp+70h+String2], r14
0x1400460f7  xor     r13b, r13b
0x1400460fa  mov     [rbp+70h+var_E0], r14
0x1400460fe  mov     esi, r14d
0x140046101  mov     eax, [rax+364h]
0x140046107  and     eax, 4000h
0x14004610c  mov     [rsp+170h+var_108], rbx
0x140046111  mov     [rsp+170h+var_100], eax
0x140046115  mov     [rsp+170h+var_11F], bl
0x140046119  mov     [rsp+170h+var_110], 101h
0x140046121  mov     [rsp+170h+var_120], bl
0x140046125  call    MpGetRequestorProcess
0x14004612a  mov     rdi, rax
0x14004612d  test    rax, rax
0x140046130  jz      loc_1400466C0
0x140046136  mov     rax, cs:__imp_PsInitialSystemProcess
0x14004613d  cmp     [rax], rdi
0x140046140  jz      loc_1400466C0
0x140046146  mov     rax, cs:MpData
0x14004614d  mov     rbx, [rax+0E8h]
0x140046154  cmp     rdi, rbx
0x140046157  jz      loc_1400466BB
0x14004615d  mov     rcx, gs:188h; Thread
0x140046166  call    cs:__imp_IoThreadToProcess
0x14004616d  nop     dword ptr [rax+rax+00h]
0x140046172  cmp     rax, rbx
0x140046175  jz      loc_1400466BB
0x14004617b  mov     rcx, gs:188h; Thread
0x140046184  mov     rax, cs:MpData
0x14004618b  mov     rbx, [rax+100h]
0x140046192  call    cs:__imp_IoThreadToProcess
0x140046199  nop     dword ptr [rax+rax+00h]
0x14004619e  cmp     rax, rbx
0x1400461a1  jz      loc_1400466BB
0x1400461a7  mov     rcx, rdi; Process
0x1400461aa  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x1400461b1  nop     dword ptr [rax+rax+00h]
0x1400461b6  mov     rcx, rdi; Process
0x1400461b9  mov     r14, rax
0x1400461bc  call    cs:__imp_PsGetProcessId
0x1400461c3  nop     dword ptr [rax+rax+00h]
0x1400461c8  xor     ebx, ebx
0x1400461ca  mov     rsi, rax
0x1400461cd  test    rax, rax
0x1400461d0  jz      loc_140046909
0x1400461d6  mov     rbx, cs:MpProcessTable
0x1400461dd  call    cs:__imp_KeEnterCriticalRegion
0x1400461e4  nop     dword ptr [rax+rax+00h]
0x1400461e9  mov     dl, 1; Wait
0x1400461eb  lea     rcx, [rbx+8]; Resource
0x1400461ef  call    cs:__imp_ExAcquireResourceSharedLite
0x1400461f6  nop     dword ptr [rax+rax+00h]
0x1400461fb  mov     rax, cs:MpProcessTable
0x140046202  mov     r8, rsi
0x140046205  shr     r8, 2
0x140046209  and     r8d, 7Fh
0x14004620d  shl     r8, 4
0x140046211  add     r8, [rax+180h]
0x140046218  mov     rax, [r8]
0x14004621b  nop     dword ptr [rax+rax+00h]
0x140046220  cmp     rax, r8
0x140046223  jz      loc_140046D7D
0x140046229  cmp     rsi, [rax+10h]
0x14004622d  lea     rdi, [rax-8]
0x140046231  jz      short loc_140046238
0x140046233  mov     rax, [rax]
0x140046236  jmp     short loc_140046220
0x140046238  cmp     r14, [rdi+20h]
0x14004623c  jnz     short loc_140046233
0x14004623e  lock inc dword ptr [rdi+30h]
0x140046242  mov     rcx, cs:MpProcessTable
0x140046249  add     rcx, 8; Resource
0x14004624d  call    cs:__imp_ExReleaseResourceLite
0x140046254  nop     dword ptr [rax+rax+00h]
0x140046259  call    cs:__imp_KeLeaveCriticalRegion
0x140046260  nop     dword ptr [rax+rax+00h]
0x140046265  mov     rcx, [r12+18h]; FltObject
0x14004626a  lea     rdx, [rbp+70h+FileSystemType]; FileSystemType
0x14004626e  call    cs:__imp_FltGetFileSystemType
0x140046275  nop     dword ptr [rax+rax+00h]
0x14004627a  cmp     [rbp+70h+FileSystemType], 0Dh
0x14004627e  mov     r9, rdi
0x140046281  mov     esi, eax
0x140046283  mov     rdx, r12
0x140046286  setz    al
0x140046289  mov     rcx, r15
0x14004628c  xor     r8d, r8d
0x14004628f  mov     byte ptr [rsp+170h+FileNameLength], al
0x140046293  call    MpCheckForAmHardening
0x140046298  movzx   r14d, al
0x14004629c  mov     rax, cs:MpData
0x1400462a3  mov     ecx, [rax+360h]
0x1400462a9  test    cl, 8
0x1400462ac  jz      loc_140046911
0x1400462b2  mov     eax, [rdi+34h]
0x1400462b5  test    al, 8
0x1400462b7  jnz     loc_14004683C
0x1400462bd  mov     eax, [rdi+38h]
0x1400462c0  bt      eax, 11h
0x1400462c4  jb      loc_14004672B
0x1400462ca  xor     r15b, r15b
0x1400462cd  mov     [rsp+170h+var_11E], r15b
0x1400462d2  test    r14b, r14b
0x1400462d5  jz      loc_14004651B
0x1400462db  cmp     [rbp+70h+FileSystemType], 0Dh
0x1400462df  jz      loc_140046919
0x1400462e5  mov     edx, 101h; NameOptions
0x1400462ea  mov     rbx, [rsp+170h+CallbackData]
0x1400462ef  mov     rax, [rbx+10h]
0x1400462f3  mov     ecx, [rax+20h]
0x1400462f6  cmp     ecx, 0Bh
0x1400462f9  jz      loc_14004673D
0x1400462ff  cmp     ecx, 48h ; 'H'
0x140046302  jz      loc_14004673D
0x140046308  mov     rcx, [rbp+70h+FileNameInformation]; FileNameInformation
0x14004630c  test    rcx, rcx
0x14004630f  jnz     loc_140046504
0x140046315  xor     edx, edx
0x140046317  mov     rcx, [rbp+70h+String2]
0x14004631b  test    rcx, rcx
0x14004631e  jnz     loc_140046AF1
0x140046324  mov     rcx, [rbp+70h+var_E0]
0x140046328  test    rcx, rcx
0x14004632b  jnz     loc_140046B01
0x140046331  mov     r8, [rbx+10h]
0x140046335  mov     eax, [r8+20h]
0x140046339  cmp     eax, 41h ; 'A'
0x14004633c  jnz     loc_1400465A1
0x140046342  mov     r8, [r8+38h]
0x140046346  mov     eax, [r8+10h]
0x14004634a  lea     r9, [r8+14h]; FileName
0x14004634e  test    eax, eax
0x140046350  jz      short loc_14004637E
0x140046352  test    r9, r9
0x140046355  jz      short loc_14004637E
0x140046357  cmp     qword ptr [r8+8], 0
0x14004635c  jnz     short loc_14004637E
0x14004635e  cmp     word ptr [r9], 5Ch ; '\'
0x140046363  jnz     short loc_14004637E
0x140046365  cmp     eax, 0Ah
0x140046368  jb      short loc_14004637E
0x14004636a  cmp     word ptr [r9+2], 3Fh ; '?'
0x140046370  jnz     short loc_14004637E
0x140046372  cmp     word ptr [r9+4], 3Fh ; '?'
0x140046378  jz      loc_140046531
0x14004637e  mov     r8, [r8+8]; RootDirectory
0x140046382  lea     rcx, [rbp+70h+FileNameInformation]
0x140046386  mov     rdx, [r12+20h]; FileObject
0x14004638b  mov     [rsp+170h+RetFileNameInformation], rcx; RetFileNameInformation
0x140046390  mov     ecx, [rsp+170h+var_110]
0x140046394  mov     [rsp+170h+NameOptions], ecx; int
0x140046398  mov     rcx, [r12+18h]; Instance
0x14004639d  mov     [rsp+170h+var_120], 0
0x1400463a2  mov     [rsp+170h+FileNameLength], eax; FileNameLength
0x1400463a6  call    cs:__imp_FltGetDestinationFileNameInformation
0x1400463ad  nop     dword ptr [rax+rax+00h]
0x1400463b2  mov     esi, eax
0x1400463b4  lea     r12, WPP_GLOBAL_Control
0x1400463bb  test    esi, esi
0x1400463bd  js      loc_14004664F
0x1400463c3  cmp     [rsp+170h+var_11F], 0
0x1400463c8  jnz     loc_140046BC4
0x1400463ce  mov     rax, [rsp+170h+var_108]
0x1400463d3  test    r14b, r14b
0x1400463d6  jz      loc_140046678
0x1400463dc  cmp     [rbp+70h+String2], 0
0x1400463e1  jnz     loc_140046722
0x1400463e7  test    rax, rax
0x1400463ea  lea     rbx, [rbp+70h+var_C0]
0x1400463ee  cmovz   rbx, [rbp+70h+FileNameInformation]
0x1400463f3  cmp     [rsp+170h+var_100], 0
0x1400463f8  jnz     short loc_140046412
0x1400463fa  mov     r8, [rbp+70h+String2]
0x1400463fe  mov     rdx, rbx
0x140046401  mov     rcx, rdi
0x140046404  call    MpIsAMPath
0x140046409  movzx   r13d, al
0x14004640d  jmp     loc_1400464B3
0x140046412  lfence
0x140046415  mov     r14, [rsp+170h+var_F8]
0x14004641a  lea     r8, [rbp+70h+IsDirectory]; IsDirectory
0x14004641e  mov     [rbp+70h+IsDirectory], 0
0x140046422  mov     rdx, [r14+18h]; Instance
0x140046426  mov     rcx, [r14+20h]; FileObject
0x14004642a  call    cs:__imp_FltIsDirectory
0x140046431  nop     dword ptr [rax+rax+00h]
0x140046436  mov     esi, eax
0x140046438  test    eax, eax
0x14004643a  js      loc_140046C4E
0x140046440  cmp     [rbp+70h+String2], 0
0x140046445  jnz     loc_140046C57
0x14004644b  lfence
0x14004644e  mov     r9, [r14+18h]
0x140046452  xor     r14d, r14d
0x140046455  cmp     cs:MpFsHardeningData, 0
0x14004645d  movzx   r13d, [rbp+70h+IsDirectory]
0x140046462  mov     r15, [rbp+70h+String2]
0x140046466  jz      loc_1400467B2
0x14004646c  test    rdi, rdi
0x14004646f  jz      loc_1400467B2
0x140046475  test    rbx, rbx
0x140046478  jz      loc_140046C62
0x14004647e  mov     r8, [rbp+70h+var_E0]
0x140046482  lea     rax, [rsp+170h+var_110]
0x140046487  mov     [rsp+170h+RetFileNameInformation], rax; __int64
0x14004648c  mov     rdx, r15; String2
0x14004648f  mov     rcx, rbx; FileNameInformation
0x140046492  mov     qword ptr [rsp+170h+FileNameLength], r14; __int64
0x140046497  mov     [rsp+170h+var_110], r14d
0x14004649c  call    FsHardeningMatch
0x1400464a1  test    al, al
0x1400464a3  jnz     loc_1400468CE
0x1400464a9  mov     r14b, 1
0x1400464ac  test    r14b, r14b
0x1400464af  setz    r13b
0x1400464b3  test    r13b, r13b
0x1400464b6  jz      loc_140046C70
0x1400464bc  mov     rbx, [rsp+170h+CallbackData]
0x1400464c1  xor     r13d, r13d
0x1400464c4  mov     dword ptr [rbx+18h], 0C0000022h
0x1400464cb  mov     [rbx+20h], r13
0x1400464cf  mov     esi, 1C0001h
0x1400464d4  mov     rax, cs:WPP_GLOBAL_Control
0x1400464db  cmp     rax, r12
0x1400464de  jz      loc_140046D1E
0x1400464e4  mov     eax, [rax+2Ch]
0x1400464e7  test    al, 2
0x1400464e9  jz      loc_140046D1E
0x1400464ef  test    rdi, rdi
0x1400464f2  jz      loc_140046CC3
0x1400464f8  mov     rbx, [rdi+80h]
0x1400464ff  jmp     loc_140046CC6
0x140046504  call    cs:__imp_FltReleaseFileNameInformation
0x14004650b  nop     dword ptr [rax+rax+00h]
0x140046510  xor     edx, edx
0x140046512  mov     [rbp+70h+FileNameInformation], rdx
0x140046516  jmp     loc_140046317
0x14004651b  mov     rbx, rdi
0x14004651e  test    r15b, r15b
0x140046521  jnz     loc_1400462DB
0x140046527  mov     r15, [rsp+170h+CallbackData]
0x14004652c  jmp     loc_140046692
0x140046531  cmp     word ptr [r9+6], 5Ch ; '\'
0x140046537  jnz     loc_14004637E
0x14004653d  cmp     eax, 10h
0x140046540  jb      short loc_140046556
0x140046542  cmp     word ptr [r9+0Ah], 3Ah ; ':'
0x140046548  jnz     short loc_140046556
0x14004654a  cmp     word ptr [r9+0Ch], 5Ch ; '\'
0x140046550  jz      loc_14004637E
0x140046556  cmp     eax, 12h
0x140046559  jb      short loc_14004657F
0x14004655b  cmp     word ptr [r9+8], 55h ; 'U'
0x140046561  jnz     short loc_14004657F
0x140046563  cmp     word ptr [r9+0Ah], 4Eh ; 'N'
0x140046569  jnz     short loc_14004657F
0x14004656b  cmp     word ptr [r9+0Ch], 43h ; 'C'
0x140046571  jnz     short loc_14004657F
0x140046573  cmp     word ptr [r9+0Eh], 5Ch ; '\'
0x140046579  jz      loc_14004637E
0x14004657f  movzx   r10d, [rsp+170h+var_11F]
0x140046585  mov     [rsp+170h+var_120], 1
0x14004658a  test    r10b, r10b
0x14004658d  jz      loc_140046B28
0x140046593  lea     rax, [rbp+70h+var_E0]
0x140046597  lea     rcx, [rsp+170h+var_108]
0x14004659c  jmp     loc_140046B32
0x1400465a1  cmp     eax, 0Bh
0x1400465a4  jnz     loc_140046B11
0x1400465aa  mov     r8, [r8+38h]
0x1400465ae  mov     eax, [r8+10h]
0x1400465b2  lea     r9, [r8+14h]
0x1400465b6  test    eax, eax
  ... truncated ...
```
