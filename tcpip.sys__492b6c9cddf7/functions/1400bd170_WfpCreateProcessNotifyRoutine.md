# WfpCreateProcessNotifyRoutine

- ea: `0x1400bd170`
- end: `0x1400bdc80`
- name: `WfpCreateProcessNotifyRoutine`
- size: `2832`
- prototype: `__int64 __fastcall(PEPROCESS Process)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400bcfb0`

## callees

- `0x1400525d0`
- `0x140053910`
- `0x140053e04`
- `0x140053f20`
- `0x140055780`
- `0x14008a370`
- `0x1400bd170`
- `0x1400bdc90`
- `0x1400bdd4c`
- `0x1400be4f8`
- `0x1400be55c`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400bd6e1`
- `ntoskrnl!ObfReferenceObject` at `0x1400bd6e1`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400bd559`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400bd559`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400bd25e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400bd3df`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400bd25e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400bd3df`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bd504`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bd589`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bd504`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bd589`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bd4ca`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bd4ca`
- `ntoskrnl!ZwCreateFile` at `0x1400bd7f9`
- `ntoskrnl!ZwCreateFile` at `0x1400bd7f9`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400bd67d`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400bd67d`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x1400bd2ad`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x1400bd2ad`
- `ntoskrnl!ZwClose` at `0x1400bd64a`
- `ntoskrnl!ZwClose` at `0x1400bd64a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bd83e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bd83e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd4a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd945`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd4a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd945`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd635`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd635`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400bdaa9`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400bdaa9`
- `ntoskrnl!ObCloseHandle` at `0x1400bda95`
- `ntoskrnl!ObCloseHandle` at `0x1400bda95`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400bda6b`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400bdb2f`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400bdb82`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400bda6b`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400bdb2f`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400bdb82`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400bda3d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400bda3d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400bda09`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400bda09`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd368`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd80d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd86c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bdac2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd368`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd80d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd86c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bdac2`
- `ntoskrnl!ExAllocatePool2` at `0x1400bdb54`
- `ntoskrnl!ExAllocatePool2` at `0x1400bdb54`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400bd4e7`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400bd4e7`
- `NDIS!NdisReleaseRWLock` at `0x1400bd5bc`
- `NDIS!NdisReleaseRWLock` at `0x1400bd5bc`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400bd1f4`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400bd1f4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400bd319`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400bd319`

## string_xrefs

- `0x1400bd2d7`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400bd754`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400bd95c`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400bd9cd`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400bdbf3`: `RtlCreateHashTable`
- `0x1400bd91f`: `RtlStringCbCopyW`
- `0x1400bd694`: `WfpCreateProcessNotifyRoutine`
- `0x1400bdb0a`: `WfpCapturePackageSid`
- `0x1400bdbc2`: `WfpCapturePackageSid`
- `0x1400bdbd9`: `WfpCapturePackageSid`

## pseudocode

```c
void __fastcall WfpCreateProcessNotifyRoutine(PEPROCESS Process, __int64 a2, __int64 a3)
{
  PFLT_FILE_NAME_INFORMATION v3; // rsi
  struct _FILE_OBJECT *v5; // rcx
  PFLT_FILE_NAME_INFORMATION v6; // r13
  PVOID v7; // r15
  unsigned int FileNameInformationUnsafe; // eax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  PFLT_FILE_NAME_INFORMATION v11; // rsi
  __int64 MaximumLength; // rax
  char *v13; // rbx
  __int64 v14; // rcx
  WCHAR *v15; // rbx
  __int64 v16; // rdi
  USHORT v17; // ax
  unsigned int v18; // eax
  __int64 v19; // rcx
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rcx
  char *v22; // rbx
  __int64 v23; // rcx
  char *v24; // rbx
  char *v25; // rax
  _QWORD *v26; // rdi
  char v27; // cl
  __int64 v28; // rbx
  __int64 v29; // rcx
  ULONG_PTR v30; // r8
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  PVOID *v35; // rbx
  PVOID *v36; // rsi
  _DWORD *v37; // rcx
  int v38; // r8d
  NTSTATUS v39; // eax
  __int64 v40; // rcx
  __int64 v41; // r8
  WCHAR *v42; // rbx
  const char *v43; // r9
  NTSTATUS v44; // ebx
  const WCHAR *v45; // r10
  const WCHAR *v46; // r8
  WCHAR *v47; // r9
  __int64 v48; // rax
  __int64 v49; // rdx
  WCHAR *v50; // rcx
  __int64 v51; // r8
  __int64 v52; // rax
  __int64 v53; // r14
  PSID *Pool2; // rdi
  PACCESS_TOKEN v55; // rbx
  NTSTATUS InformationToken; // eax
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 TokenInformation; // [rsp+68h] [rbp-A0h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp-98h] BYREF
  char *v61; // [rsp+78h] [rbp-90h]
  WCHAR *Buffer; // [rsp+80h] [rbp-88h]
  PVOID v63; // [rsp+88h] [rbp-80h]
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-78h] BYREF
  PUNICODE_STRING pImageFileName; // [rsp+A0h] [rbp-68h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp-60h] BYREF
  PVOID v67; // [rsp+B0h] [rbp-58h] BYREF
  PFLT_FILE_NAME_INFORMATION v68; // [rsp+B8h] [rbp-50h]
  PVOID Object; // [rsp+C0h] [rbp-48h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-10h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+168h] [rbp+60h] BYREF
  PCWSTR SourceString; // [rsp+170h] [rbp+68h] BYREF

  v3 = 0;
  v5 = *(struct _FILE_OBJECT **)(a3 + 40);
  v6 = 0;
  v7 = 0;
  v63 = 0;
  Handle = 0;
  Object = 0;
  DestinationString = 0;
  if ( !v5 || (v5->Flags & 0x4000) != 0 )
  {
    pImageFileName = 0;
    IoStatusBlock = 0;
    memset(&ObjectAttributes, 0, 44);
    v39 = SeLocateProcessImageName(Process, &pImageFileName);
    if ( v39 >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.ObjectName = pImageFileName;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v44 = ZwCreateFile(&Handle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0, 0, 0);
      ExFreePoolWithTag(pImageFileName, 0);
      if ( v44 < 0 )
      {
        v41 = (unsigned int)v44;
LABEL_50:
        if ( !WfpReportSysErrorAsNtStatus(v40, "WfpCreateProcessNotifyRoutine", v41) )
          goto LABEL_43;
        goto LABEL_23;
      }
      v67 = 0;
      v39 = ObReferenceObjectByHandle(Handle, 0x400u, 0, 0, &v67, 0);
      Object = v67;
      if ( v39 >= 0 )
      {
        v5 = (struct _FILE_OBJECT *)v67;
        goto LABEL_3;
      }
    }
    v41 = (unsigned int)v39;
    goto LABEL_50;
  }
LABEL_3:
  SourceString = 0;
  FileNameInformation = 0;
  FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(v5, 0, 0x101u, &FileNameInformation);
  v10 = FileNameInformationUnsafe;
  if ( FileNameInformationUnsafe )
  {
    WfpReportSysErrorAsNtStatus(v9, "FltGetFileNameInformationUnsafe", FileNameInformationUnsafe);
    v16 = WfpReportSysErrorAsNtStatus(v21, "WfpAleQueryNormalizedImageFileName", v10);
    goto LABEL_20;
  }
  v11 = FileNameInformation;
  if ( !FileNameInformation->Name.Length )
  {
    SourceString = 0;
    v16 = WfpAllocateFromPerProcessorLookasideList(processPathLookasideListSmall, &SourceString);
    if ( !v16 )
    {
      v45 = SourceString;
      v46 = L"Unknown";
      v47 = (WCHAR *)SourceString;
      v48 = 2147483646;
      v49 = 8;
      do
      {
        if ( !v48 )
          break;
        if ( !*v46 )
          break;
        *v47++ = *v46++;
        --v48;
        --v49;
      }
      while ( v49 );
      v50 = v47 - 1;
      v51 = 2147483653LL;
      if ( v49 )
      {
        v50 = v47;
        v51 = 0;
      }
      *v50 = 0;
      if ( v49 )
      {
        v7 = processPathLookasideListSmall;
        v63 = processPathLookasideListSmall;
        RtlInitUnicodeString(&DestinationString, v45);
      }
      else
      {
        v16 = WfpReportSysErrorAsNtStatus(v50, "RtlStringCbCopyW", v51);
      }
    }
    goto LABEL_17;
  }
  MaximumLength = FileNameInformation->Name.MaximumLength;
  if ( (unsigned __int16)MaximumLength > 0x200u )
  {
    v16 = WfpPoolAllocNonPaged(MaximumLength + 2, 1348824129, &SourceString);
    if ( !v16 )
    {
      v15 = (WCHAR *)SourceString;
      v63 = 0;
LABEL_11:
      v17 = v11->Name.MaximumLength;
      *(_QWORD *)&DestinationString.Length = 0;
      DestinationString.MaximumLength = v17;
      DestinationString.Buffer = v15;
      v18 = RtlDowncaseUnicodeString(&DestinationString, &v11->Name, 0);
      if ( v18 )
        v16 = WfpReportSysErrorAsNtStatus(v19, "RtlDowncaseUnicodeString", v18);
    }
  }
  else
  {
    v13 = (char *)processPathLookasideListLarge
        + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v13[176] )
      PplpLazyInitializeLookasideList(processPathLookasideListLarge, v13 + 64);
    v15 = (WCHAR *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v13 + 64));
    if ( v15 )
    {
      v16 = 0;
LABEL_10:
      v7 = processPathLookasideListLarge;
      v63 = processPathLookasideListLarge;
      memset(v15, 0, 0x202u);
      goto LABEL_11;
    }
    v16 = WfpReportSysErrorAsNtStatus(v14, "WfpAllocateFromPerProcessorLookasideList", 3221225495LL);
    if ( v16
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"WfpAllocateFromPerProcessorLookasideList",
        v16);
    }
    else if ( !v16 )
    {
      goto LABEL_10;
    }
  }
LABEL_17:
  if ( v11 )
    FltReleaseFileNameInformation(v11);
  v3 = 0;
LABEL_20:
  if ( !v16 )
  {
    TokenHandle = 0;
    v53 = 0;
    LODWORD(SourceString) = 0;
    Pool2 = 0;
    FileNameInformation = 0;
    LODWORD(TokenInformation) = 0;
    v68 = 0;
    v55 = PsReferencePrimaryToken(Process);
    if ( ObOpenObjectByPointer(v55, 0x200u, 0, 0xF01FFu, 0, 0, &TokenHandle) < 0 )
      goto LABEL_90;
    ZwQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, (PULONG)&SourceString);
    if ( !(_DWORD)TokenInformation )
      goto LABEL_89;
    InformationToken = ZwQueryInformationToken(TokenHandle, TokenAppContainerSid, 0, 0, (PULONG)&SourceString);
    if ( InformationToken != -1073741789 )
      goto LABEL_108;
    Pool2 = (PSID *)ExAllocatePool2(64, (unsigned int)SourceString, 1852864065);
    if ( !Pool2 )
    {
      v53 = WfpReportSysErrorAsNtStatus(v58, "WfpCapturePackageSid", 3221225626LL);
      goto LABEL_90;
    }
    InformationToken = ZwQueryInformationToken(
                         TokenHandle,
                         TokenAppContainerSid,
                         Pool2,
                         (ULONG)SourceString,
                         (PULONG)&SourceString);
    if ( InformationToken >= 0 )
    {
      if ( !*Pool2 )
      {
LABEL_89:
        v6 = v3;
        v68 = v3;
        goto LABEL_90;
      }
      v53 = WfpAppTriggerCopySid(*Pool2);
      if ( !v53 )
      {
        v3 = FileNameInformation;
        goto LABEL_89;
      }
    }
    else
    {
LABEL_108:
      v53 = WfpReportSysErrorAsNtStatus(v57, "WfpCapturePackageSid", (unsigned int)InformationToken);
    }
LABEL_90:
    if ( TokenHandle )
      ObCloseHandle(TokenHandle, 0);
    if ( v55 )
      PsDereferencePrimaryToken(v55);
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0x6E707641u);
    if ( v53 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpCapturePackageSid",
          v53);
      }
      goto LABEL_23;
    }
    LOWORD(FileNameInformation) = 0;
    BYTE2(FileNameInformation) = 0;
    Buffer = DestinationString.Buffer;
    v22 = (char *)processTableLookasideList
        + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v22[176] )
      PplpLazyInitializeLookasideList(processTableLookasideList, v22 + 64);
    v61 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v22 + 64));
    v24 = v61;
    if ( !v61 )
    {
      v52 = WfpReportSysErrorAsNtStatus(v23, "WfpAllocateFromPerProcessorLookasideList", 3221225495LL);
      LOBYTE(v16) = v52;
      if ( v52 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"WfpAllocateFromPerProcessorLookasideList",
            v52);
        }
LABEL_81:
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0 )
        {
          goto LABEL_23;
        }
        v43 = "WfpAleInsertProcessInformation";
        goto LABEL_55;
      }
    }
    memset(v24 + 8, 0, 0x78u);
    v25 = v61;
    v61[1] = BYTE1(Process);
    v26 = v25;
    *v25 = (char)Process;
    *(_DWORD *)(v25 + 2) = *(_DWORD *)((char *)&Process + 2);
    v25[6] = BYTE6(Process);
    v27 = gAleNumHashEntryBits;
    v25[7] = HIBYTE(Process);
    v28 = ((HIBYTE(Process)
          + 37
          * (BYTE6(Process)
           + 37
           * (BYTE5(Process)
            + 37
            * (BYTE4(Process)
             + 37 * (BYTE3(Process) + 37 * (BYTE2(Process) + 37 * (BYTE1(Process) + 37LL * (unsigned __int8)Process))))))) << v27)
        | 3;
    RtlInitUnicodeString((PUNICODE_STRING)(v25 + 8), Buffer);
    v7 = v63;
    v6 = v68;
    v26[4] = a2;
    v26[3] = v7;
    v26[6] = v6;
    v26[15] = v28;
    LOBYTE(v28) = KeGetCurrentIrql();
    NdisAcquireRWLockWrite(gAleHashtableLock, (PLOCK_STATE_EX)&FileNameInformation, 0);
    if ( (_BYTE)v28 != 2 && gWfpPerProContext )
    {
      v29 = *(_QWORD *)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      *(_QWORD *)(v29 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v29 = 4;
    }
    v30 = v26[15];
    v31 = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)(v26 + 13);
    v16 = 0;
    if ( !v30 )
    {
      v30 = -1;
      v31->Signature = -1;
    }
    if ( RtlInsertEntryHashTable(&gAleMasterHashTable, v31, v30, 0)
      || (v16 = WfpReportSysErrorAsNtStatus(v33, "RtlCreateHashTable", 3221225495LL)) == 0
      || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0 )
    {
      v35 = 0;
      if ( !v16 )
      {
        v36 = (PVOID *)v61;
        v42 = (WCHAR *)(v61 + 72);
        WfpAleInitializeWaitRef_0(v61 + 72, v32, v34, v61);
        Buffer = v42;
        *(_DWORD *)v42 = (*(_DWORD *)v42 + 4)
                       ^ ((unsigned __int8)*(_DWORD *)v42
                        ^ (unsigned __int8)(*(_DWORD *)v42 + 4))
                       & 3;
        ObfReferenceObject(*v36);
        Buffer = v42;
        v35 = v36;
        *(_DWORD *)Buffer = (*(_DWORD *)Buffer + 4)
                          ^ ((unsigned __int8)*(_DWORD *)Buffer
                           ^ (unsigned __int8)(*(_DWORD *)Buffer + 4))
                          & 3;
LABEL_38:
        if ( gWfpPerProContext )
        {
          v37 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
          if ( *v37 == 4 )
            *v37 = 0;
        }
        NdisReleaseRWLock(gAleHashtableLock, (PLOCK_STATE_EX)&FileNameInformation);
        if ( !v16 )
        {
          WfpAppTriggerCheckProcessCreate(
            (unsigned int)v35[6],
            (_DWORD)v35 + 8,
            v38,
            (_DWORD)v35 + 56,
            (__int64)(v35 + 8));
          WfpAleDecrementWaitRef(v35 + 9);
          goto LABEL_43;
        }
        if ( v36 )
          PplFreeToLookasideList(processTableLookasideList);
        goto LABEL_81;
      }
    }
    else
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"WfpHashtableInsert",
        v16);
      v35 = 0;
    }
    v36 = (PVOID *)v61;
    goto LABEL_38;
  }
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0 )
  {
    goto LABEL_23;
  }
  v43 = "WfpAleCaptureImageFileName";
LABEL_55:
  WPP_SF_sd(v20->AttachedDevice, 15, (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids, (_DWORD)v43, v16);
LABEL_23:
  if ( DestinationString.Buffer )
  {
    if ( v7 )
    {
      PplFreeToLookasideList(v7);
    }
    else
    {
      ExFreePoolWithTag(DestinationString.Buffer, 0);
      DestinationString.Buffer = (PWSTR)0xBADBADFABADBADFALL;
    }
  }
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
LABEL_43:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( Handle )
    ZwClose(Handle);
}

```

## disassembly

```asm
0x1400bd170  mov     rax, rsp
0x1400bd173  mov     [rax+10h], rdx
0x1400bd177  mov     [rax+8], rcx
0x1400bd17b  push    rbp
0x1400bd17c  lea     rbp, [rax-48h]
0x1400bd180  sub     rsp, 140h
0x1400bd187  mov     [rax-10h], rbx
0x1400bd18b  xorps   xmm0, xmm0
0x1400bd18e  mov     [rax-18h], rsi
0x1400bd192  xor     esi, esi
0x1400bd194  mov     [rax-20h], rdi
0x1400bd198  mov     edi, 200h
0x1400bd19d  mov     [rax-28h], r12
0x1400bd1a1  mov     r12, rcx
0x1400bd1a4  mov     rcx, [r8+28h]; FileObject
0x1400bd1a8  mov     [rax-30h], r13
0x1400bd1ac  mov     r13d, esi
0x1400bd1af  mov     [rax-38h], r14
0x1400bd1b3  mov     [rax-40h], r15
0x1400bd1b7  mov     r15d, esi
0x1400bd1ba  mov     [rbp+40h+var_C0], rsi
0x1400bd1be  mov     [rbp+40h+Handle], rsi
0x1400bd1c2  mov     [rbp+40h+Object], rsi
0x1400bd1c6  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x1400bd1ca  test    rcx, rcx
0x1400bd1cd  jz      loc_1400BD660
0x1400bd1d3  test    dword ptr [rcx+50h], 4000h
0x1400bd1da  jnz     loc_1400BD660
0x1400bd1e0  lea     r9, [rbp+40h+FileNameInformation]; FileNameInformation
0x1400bd1e4  mov     [rbp+40h+SourceString], rsi
0x1400bd1e8  xor     edx, edx; Instance
0x1400bd1ea  mov     [rbp+40h+FileNameInformation], rsi
0x1400bd1ee  mov     r8d, 101h; NameOptions
0x1400bd1f4  call    cs:__imp_FltGetFileNameInformationUnsafe
0x1400bd1fb  nop     dword ptr [rax+rax+00h]
0x1400bd200  lea     r14, WPP_GLOBAL_Control
0x1400bd207  mov     ebx, eax
0x1400bd209  test    eax, eax
0x1400bd20b  jnz     loc_1400BD379
0x1400bd211  mov     rsi, [rbp+40h+FileNameInformation]
0x1400bd215  cmp     [rsi+8], r13w
0x1400bd21a  jz      loc_1400BD8A3
0x1400bd220  movzx   eax, word ptr [rsi+0Ah]
0x1400bd224  cmp     ax, di
0x1400bd227  ja      loc_1400BD775
0x1400bd22d  mov     eax, gs:1A4h
0x1400bd235  mov     rcx, cs:processPathLookasideListLarge
0x1400bd23c  lea     ebx, [rax+1]
0x1400bd23f  shl     rbx, 7
0x1400bd243  add     rbx, rcx
0x1400bd246  movzx   eax, byte ptr [rbx+0B0h]
0x1400bd24d  test    al, al
0x1400bd24f  jnz     short loc_1400BD25A
0x1400bd251  lea     rdx, [rbx+40h]
0x1400bd255  call    PplpLazyInitializeLookasideList
0x1400bd25a  lea     rcx, [rbx+40h]; Lookaside
0x1400bd25e  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400bd265  nop     dword ptr [rax+rax+00h]
0x1400bd26a  mov     rbx, rax
0x1400bd26d  test    rax, rax
0x1400bd270  jz      short loc_1400BD2D1
0x1400bd272  xor     edi, edi
0x1400bd274  mov     r15, cs:processPathLookasideListLarge
0x1400bd27b  xor     edx, edx; Val
0x1400bd27d  mov     r8d, 202h; Size
0x1400bd283  mov     [rbp+40h+var_C0], r15
0x1400bd287  mov     rcx, rbx; void *
0x1400bd28a  call    memset
0x1400bd28f  movzx   eax, word ptr [rsi+0Ah]
0x1400bd293  lea     rdx, [rsi+8]; SourceString
0x1400bd297  xorps   xmm0, xmm0
0x1400bd29a  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x1400bd29e  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x1400bd2a2  xor     r8d, r8d; AllocateDestinationString
0x1400bd2a5  mov     [rbp+40h+DestinationString.MaximumLength], ax
0x1400bd2a9  mov     [rbp+40h+DestinationString.Buffer], rbx
0x1400bd2ad  call    cs:__imp_RtlDowncaseUnicodeString
0x1400bd2b4  nop     dword ptr [rax+rax+00h]
0x1400bd2b9  test    eax, eax
0x1400bd2bb  jz      short loc_1400BD311
0x1400bd2bd  mov     r8d, eax
0x1400bd2c0  lea     rdx, aRtldowncaseuni; "RtlDowncaseUnicodeString"
0x1400bd2c7  call    WfpReportSysErrorAsNtStatus
0x1400bd2cc  mov     rdi, rax
0x1400bd2cf  jmp     short loc_1400BD311
0x1400bd2d1  mov     r8d, 0C0000017h
0x1400bd2d7  lea     rdx, aWfpallocatefro; "WfpAllocateFromPerProcessorLookasideLis"...
0x1400bd2de  call    WfpReportSysErrorAsNtStatus
0x1400bd2e3  mov     rdi, rax
0x1400bd2e6  test    rax, rax
0x1400bd2e9  jz      short loc_1400BD308
0x1400bd2eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bd2f2  lea     rax, WPP_GLOBAL_Control
0x1400bd2f9  cmp     rcx, rax
0x1400bd2fc  jz      short loc_1400BD308
0x1400bd2fe  cmp     byte ptr [rcx+29h], 2
0x1400bd302  jnb     loc_1400BD743
0x1400bd308  test    rdi, rdi
0x1400bd30b  jz      loc_1400BD274
0x1400bd311  test    rsi, rsi
0x1400bd314  jz      short loc_1400BD325
0x1400bd316  mov     rcx, rsi; FileNameInformation
0x1400bd319  call    cs:__imp_FltReleaseFileNameInformation
0x1400bd320  nop     dword ptr [rax+rax+00h]
0x1400bd325  lea     r14, WPP_GLOBAL_Control
0x1400bd32c  xor     esi, esi
0x1400bd32e  test    rdi, rdi
0x1400bd331  jz      loc_1400BD9EB
0x1400bd337  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bd33e  cmp     rcx, r14
0x1400bd341  jz      short loc_1400BD34D
0x1400bd343  cmp     byte ptr [rcx+29h], 2
0x1400bd347  jnb     loc_1400BD711
0x1400bd34d  mov     rax, [rbp+40h+DestinationString.Buffer]
0x1400bd351  test    rax, rax
0x1400bd354  jnz     loc_1400BD862
0x1400bd35a  test    r13, r13
0x1400bd35d  jz      loc_1400BD5F4
0x1400bd363  xor     edx, edx; Tag
0x1400bd365  mov     rcx, r13; P
0x1400bd368  call    cs:__imp_ExFreePoolWithTag
0x1400bd36f  nop     dword ptr [rax+rax+00h]
0x1400bd374  jmp     loc_1400BD5F4
0x1400bd379  mov     r8d, ebx
0x1400bd37c  lea     rdx, aFltgetfilename; "FltGetFileNameInformationUnsafe"
0x1400bd383  call    WfpReportSysErrorAsNtStatus
0x1400bd388  mov     r8d, ebx
0x1400bd38b  lea     rdx, aWfpalequerynor; "WfpAleQueryNormalizedImageFileName"
0x1400bd392  call    WfpReportSysErrorAsNtStatus
0x1400bd397  mov     rdi, rax
0x1400bd39a  jmp     short loc_1400BD32E
0x1400bd39c  mov     rax, [rbp+40h+DestinationString.Buffer]
0x1400bd3a0  xor     ecx, ecx
0x1400bd3a2  mov     word ptr [rbp+40h+FileNameInformation], cx
0x1400bd3a6  mov     byte ptr [rbp+40h+FileNameInformation+2], cl
0x1400bd3a9  mov     rcx, cs:processTableLookasideList
0x1400bd3b0  mov     [rsp+140h+var_C8], rax
0x1400bd3b5  mov     eax, gs:1A4h
0x1400bd3bd  lea     ebx, [rax+1]
0x1400bd3c0  shl     rbx, 7
0x1400bd3c4  add     rbx, rcx
0x1400bd3c7  movzx   eax, byte ptr [rbx+0B0h]
0x1400bd3ce  test    al, al
0x1400bd3d0  jnz     short loc_1400BD3DB
0x1400bd3d2  lea     rdx, [rbx+40h]
0x1400bd3d6  call    PplpLazyInitializeLookasideList
0x1400bd3db  lea     rcx, [rbx+40h]; Lookaside
0x1400bd3df  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400bd3e6  nop     dword ptr [rax+rax+00h]
0x1400bd3eb  mov     [rsp+140h+var_D0], rax
0x1400bd3f0  mov     rbx, rax
0x1400bd3f3  test    rax, rax
0x1400bd3f6  jz      loc_1400BD956
0x1400bd3fc  movzx   edi, [rbp+40h+arg_1]
0x1400bd400  lea     rcx, [rbx+8]; void *
0x1400bd404  movzx   esi, byte ptr [rbp+40h+arg_2]
0x1400bd408  xor     edx, edx; Val
0x1400bd40a  movzx   r14d, byte ptr [rbp+40h+arg_2+1]
0x1400bd40f  mov     r8d, 78h ; 'x'; Size
0x1400bd415  movzx   r15d, byte ptr [rbp+40h+arg_2+2]
0x1400bd41a  movzx   r12d, byte ptr [rbp+40h+arg_2+3]
0x1400bd41f  movzx   r13d, [rbp+40h+arg_6]
0x1400bd424  call    memset
0x1400bd429  mov     r8, [rbp+50h]
0x1400bd42d  movzx   eax, r8b
0x1400bd431  imul    rcx, rax, 25h ; '%'
0x1400bd435  mov     rax, [rsp+140h+var_D0]
0x1400bd43a  add     rcx, rdi
0x1400bd43d  imul    rdx, rcx, 25h ; '%'
0x1400bd441  mov     [rax+1], dil
0x1400bd445  mov     rdi, rax
0x1400bd448  add     rdx, rsi
0x1400bd44b  mov     [rax], r8b
0x1400bd44e  imul    rcx, rdx, 25h ; '%'
0x1400bd452  mov     [rax+2], sil
0x1400bd456  add     rcx, r14
0x1400bd459  mov     [rax+3], r14b
0x1400bd45d  imul    rdx, rcx, 25h ; '%'
0x1400bd461  mov     [rax+4], r15b
0x1400bd465  add     rdx, r15
0x1400bd468  mov     [rax+5], r12b
0x1400bd46c  imul    rcx, rdx, 25h ; '%'
0x1400bd470  mov     [rax+6], r13b
0x1400bd474  add     rcx, r12
0x1400bd477  imul    rdx, rcx, 25h ; '%'
0x1400bd47b  mov     ecx, cs:gAleNumHashEntryBits
0x1400bd481  add     rdx, r13
0x1400bd484  imul    rbx, rdx, 25h ; '%'
0x1400bd488  movzx   edx, [rbp+40h+arg_7]
0x1400bd48c  add     rbx, rdx
0x1400bd48f  mov     [rax+7], dl
0x1400bd492  mov     rdx, [rsp+140h+var_C8]; SourceString
0x1400bd497  shl     rbx, cl
0x1400bd49a  lea     rcx, [rax+8]; DestinationString
0x1400bd49e  or      rbx, 3
0x1400bd4a2  call    cs:__imp_RtlInitUnicodeString
0x1400bd4a9  nop     dword ptr [rax+rax+00h]
0x1400bd4ae  mov     rax, [rbp+40h+arg_8]
0x1400bd4b2  mov     r15, [rbp+40h+var_C0]
0x1400bd4b6  mov     r13, [rbp+40h+var_90]
0x1400bd4ba  mov     [rdi+20h], rax
0x1400bd4be  mov     [rdi+18h], r15
0x1400bd4c2  mov     [rdi+30h], r13
0x1400bd4c6  mov     [rdi+78h], rbx
0x1400bd4ca  call    cs:__imp_KeGetCurrentIrql
0x1400bd4d1  nop     dword ptr [rax+rax+00h]
0x1400bd4d6  mov     rcx, cs:gAleHashtableLock; Lock
0x1400bd4dd  lea     rdx, [rbp+40h+FileNameInformation]; LockState
0x1400bd4e1  xor     r8d, r8d; Flags
0x1400bd4e4  movzx   ebx, al
0x1400bd4e7  call    cs:__imp_NdisAcquireRWLockWrite
0x1400bd4ee  nop     dword ptr [rax+rax+00h]
0x1400bd4f3  cmp     bl, 2
0x1400bd4f6  jz      short loc_1400BD535
0x1400bd4f8  cmp     cs:gWfpPerProContext, 0
0x1400bd500  jz      short loc_1400BD535
0x1400bd502  xor     ecx, ecx; ProcNumber
0x1400bd504  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400bd50b  nop     dword ptr [rax+rax+00h]
0x1400bd510  lea     ecx, [rax+rax*8]
0x1400bd513  mov     rax, cs:gWfpPerProContext
0x1400bd51a  shl     ecx, 3
0x1400bd51d  mov     rcx, [rcx+rax]
0x1400bd521  mov     rax, ds:0FFFFF78000000008h
0x1400bd52b  mov     [rcx+8], rax
0x1400bd52f  mov     dword ptr [rcx], 4
0x1400bd535  mov     r8, [rdi+78h]
0x1400bd539  lea     rdx, [rdi+68h]; Entry
0x1400bd53d  xor     edi, edi
0x1400bd53f  test    r8, r8
0x1400bd542  jnz     short loc_1400BD54F
0x1400bd544  mov     r8, 0FFFFFFFFFFFFFFFFh; Signature
0x1400bd54b  mov     [rdx+10h], r8
0x1400bd54f  xor     r9d, r9d; Context
0x1400bd552  lea     rcx, gAleMasterHashTable; HashTable
0x1400bd559  call    cs:__imp_RtlInsertEntryHashTable
0x1400bd560  nop     dword ptr [rax+rax+00h]
0x1400bd565  test    al, al
0x1400bd567  jz      loc_1400BDBED
0x1400bd56d  xor     ebx, ebx
0x1400bd56f  test    rdi, rdi
0x1400bd572  jz      loc_1400BD6AE
0x1400bd578  mov     rsi, [rsp+140h+var_D0]
0x1400bd57d  cmp     cs:gWfpPerProContext, 0
0x1400bd585  jz      short loc_1400BD5B1
0x1400bd587  xor     ecx, ecx; ProcNumber
0x1400bd589  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400bd590  nop     dword ptr [rax+rax+00h]
0x1400bd595  lea     ecx, [rax+rax*8]
0x1400bd598  mov     rax, cs:gWfpPerProContext
0x1400bd59f  shl     ecx, 3
0x1400bd5a2  mov     rcx, [rcx+rax]
0x1400bd5a6  cmp     dword ptr [rcx], 4
0x1400bd5a9  jnz     short loc_1400BD5B1
0x1400bd5ab  mov     dword ptr [rcx], 0
0x1400bd5b1  mov     rcx, cs:gAleHashtableLock; Lock
0x1400bd5b8  lea     rdx, [rbp+40h+FileNameInformation]; LockState
0x1400bd5bc  call    cs:__imp_NdisReleaseRWLock
0x1400bd5c3  nop     dword ptr [rax+rax+00h]
0x1400bd5c8  test    rdi, rdi
0x1400bd5cb  jnz     loc_1400BDC60
0x1400bd5d1  mov     rcx, [rbx+30h]
0x1400bd5d5  lea     rax, [rbx+40h]
0x1400bd5d9  lea     r9, [rbx+38h]
0x1400bd5dd  mov     [rsp+140h+AllocationSize], rax
0x1400bd5e2  lea     rdx, [rbx+8]
0x1400bd5e6  call    WfpAppTriggerCheckProcessCreate
0x1400bd5eb  lea     rcx, [rbx+48h]
0x1400bd5ef  call    WfpAleDecrementWaitRef
0x1400bd5f4  mov     rcx, [rbp+40h+Object]; Object
0x1400bd5f8  mov     r15, [rsp+140h+var_38]
0x1400bd600  mov     r14, [rsp+140h+var_30]
0x1400bd608  mov     r13, [rsp+140h+var_28]
0x1400bd610  mov     r12, [rsp+140h+var_20]
0x1400bd618  mov     rdi, [rsp+140h+var_18]
0x1400bd620  mov     rsi, [rsp+140h+var_10]
0x1400bd628  mov     rbx, [rsp+138h]
0x1400bd630  test    rcx, rcx
0x1400bd633  jz      short loc_1400BD641
0x1400bd635  call    cs:__imp_ObfDereferenceObject
0x1400bd63c  nop     dword ptr [rax+rax+00h]
0x1400bd641  mov     rcx, [rbp+40h+Handle]; Handle
0x1400bd645  test    rcx, rcx
0x1400bd648  jz      short loc_1400BD656
0x1400bd64a  call    cs:__imp_ZwClose
0x1400bd651  nop     dword ptr [rax+rax+00h]
0x1400bd656  add     rsp, 140h
0x1400bd65d  pop     rbp
0x1400bd65e  retn
0x1400bd660  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x1400bd664  xor     eax, eax
0x1400bd666  mov     [rbp+40h+pImageFileName], rsi
0x1400bd66a  lea     rdx, [rbp+40h+pImageFileName]; pImageFileName
0x1400bd66e  mov     rcx, r12; Process
0x1400bd671  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x1400bd675  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x1400bd679  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x1400bd67d  call    cs:__imp_SeLocateProcessImageName
0x1400bd684  nop     dword ptr [rax+rax+00h]
0x1400bd689  test    eax, eax
  ... truncated ...
```
