# WfpCreateProcessNotifyRoutine

- ea: `0x1400bd1a0`
- end: `0x1400bdcb0`
- name: `WfpCreateProcessNotifyRoutine`
- size: `2832`
- prototype: `__int64 __fastcall(PEPROCESS Process)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400bcfe0`

## callees

- `0x140052870`
- `0x140053bb0`
- `0x1400540a4`
- `0x1400541c0`
- `0x140055a20`
- `0x14008b220`
- `0x1400bd1a0`
- `0x1400bdcc0`
- `0x1400bdd7c`
- `0x1400be528`
- `0x1400be58c`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400bd711`
- `ntoskrnl!ObfReferenceObject` at `0x1400bd711`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400bd589`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400bd589`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400bd28e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400bd40f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400bd28e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400bd40f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bd534`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bd5b9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bd534`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bd5b9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bd4fa`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bd4fa`
- `ntoskrnl!ZwCreateFile` at `0x1400bd829`
- `ntoskrnl!ZwCreateFile` at `0x1400bd829`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400bd6ad`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400bd6ad`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x1400bd2dd`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x1400bd2dd`
- `ntoskrnl!ZwClose` at `0x1400bd67a`
- `ntoskrnl!ZwClose` at `0x1400bd67a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bd86e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bd86e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd4d2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd975`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd4d2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd975`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd665`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd665`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400bdad9`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400bdad9`
- `ntoskrnl!ObCloseHandle` at `0x1400bdac5`
- `ntoskrnl!ObCloseHandle` at `0x1400bdac5`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400bda9b`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400bdb5f`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400bdbb2`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400bda9b`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400bdb5f`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400bdbb2`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400bda6d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400bda6d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400bda39`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400bda39`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd398`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd83d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd89c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bdaf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd398`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd83d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd89c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bdaf2`
- `ntoskrnl!ExAllocatePool2` at `0x1400bdb84`
- `ntoskrnl!ExAllocatePool2` at `0x1400bdb84`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400bd517`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400bd517`
- `NDIS!NdisReleaseRWLock` at `0x1400bd5ec`
- `NDIS!NdisReleaseRWLock` at `0x1400bd5ec`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400bd224`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400bd224`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400bd349`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400bd349`

## string_xrefs

- `0x1400bd307`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400bd784`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400bd98c`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400bd9fd`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400bdc23`: `RtlCreateHashTable`
- `0x1400bd94f`: `RtlStringCbCopyW`
- `0x1400bd6c4`: `WfpCreateProcessNotifyRoutine`
- `0x1400bdb3a`: `WfpCapturePackageSid`
- `0x1400bdbf2`: `WfpCapturePackageSid`
- `0x1400bdc09`: `WfpCapturePackageSid`

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
0x1400bd1a0  mov     rax, rsp
0x1400bd1a3  mov     [rax+10h], rdx
0x1400bd1a7  mov     [rax+8], rcx
0x1400bd1ab  push    rbp
0x1400bd1ac  lea     rbp, [rax-48h]
0x1400bd1b0  sub     rsp, 140h
0x1400bd1b7  mov     [rax-10h], rbx
0x1400bd1bb  xorps   xmm0, xmm0
0x1400bd1be  mov     [rax-18h], rsi
0x1400bd1c2  xor     esi, esi
0x1400bd1c4  mov     [rax-20h], rdi
0x1400bd1c8  mov     edi, 200h
0x1400bd1cd  mov     [rax-28h], r12
0x1400bd1d1  mov     r12, rcx
0x1400bd1d4  mov     rcx, [r8+28h]; FileObject
0x1400bd1d8  mov     [rax-30h], r13
0x1400bd1dc  mov     r13d, esi
0x1400bd1df  mov     [rax-38h], r14
0x1400bd1e3  mov     [rax-40h], r15
0x1400bd1e7  mov     r15d, esi
0x1400bd1ea  mov     [rbp+40h+var_C0], rsi
0x1400bd1ee  mov     [rbp+40h+Handle], rsi
0x1400bd1f2  mov     [rbp+40h+Object], rsi
0x1400bd1f6  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x1400bd1fa  test    rcx, rcx
0x1400bd1fd  jz      loc_1400BD690
0x1400bd203  test    dword ptr [rcx+50h], 4000h
0x1400bd20a  jnz     loc_1400BD690
0x1400bd210  lea     r9, [rbp+40h+FileNameInformation]; FileNameInformation
0x1400bd214  mov     [rbp+40h+SourceString], rsi
0x1400bd218  xor     edx, edx; Instance
0x1400bd21a  mov     [rbp+40h+FileNameInformation], rsi
0x1400bd21e  mov     r8d, 101h; NameOptions
0x1400bd224  call    cs:__imp_FltGetFileNameInformationUnsafe
0x1400bd22b  nop     dword ptr [rax+rax+00h]
0x1400bd230  lea     r14, WPP_GLOBAL_Control
0x1400bd237  mov     ebx, eax
0x1400bd239  test    eax, eax
0x1400bd23b  jnz     loc_1400BD3A9
0x1400bd241  mov     rsi, [rbp+40h+FileNameInformation]
0x1400bd245  cmp     [rsi+8], r13w
0x1400bd24a  jz      loc_1400BD8D3
0x1400bd250  movzx   eax, word ptr [rsi+0Ah]
0x1400bd254  cmp     ax, di
0x1400bd257  ja      loc_1400BD7A5
0x1400bd25d  mov     eax, gs:1A4h
0x1400bd265  mov     rcx, cs:processPathLookasideListLarge
0x1400bd26c  lea     ebx, [rax+1]
0x1400bd26f  shl     rbx, 7
0x1400bd273  add     rbx, rcx
0x1400bd276  movzx   eax, byte ptr [rbx+0B0h]
0x1400bd27d  test    al, al
0x1400bd27f  jnz     short loc_1400BD28A
0x1400bd281  lea     rdx, [rbx+40h]
0x1400bd285  call    PplpLazyInitializeLookasideList
0x1400bd28a  lea     rcx, [rbx+40h]; Lookaside
0x1400bd28e  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400bd295  nop     dword ptr [rax+rax+00h]
0x1400bd29a  mov     rbx, rax
0x1400bd29d  test    rax, rax
0x1400bd2a0  jz      short loc_1400BD301
0x1400bd2a2  xor     edi, edi
0x1400bd2a4  mov     r15, cs:processPathLookasideListLarge
0x1400bd2ab  xor     edx, edx; Val
0x1400bd2ad  mov     r8d, 202h; Size
0x1400bd2b3  mov     [rbp+40h+var_C0], r15
0x1400bd2b7  mov     rcx, rbx; void *
0x1400bd2ba  call    memset
0x1400bd2bf  movzx   eax, word ptr [rsi+0Ah]
0x1400bd2c3  lea     rdx, [rsi+8]; SourceString
0x1400bd2c7  xorps   xmm0, xmm0
0x1400bd2ca  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x1400bd2ce  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x1400bd2d2  xor     r8d, r8d; AllocateDestinationString
0x1400bd2d5  mov     [rbp+40h+DestinationString.MaximumLength], ax
0x1400bd2d9  mov     [rbp+40h+DestinationString.Buffer], rbx
0x1400bd2dd  call    cs:__imp_RtlDowncaseUnicodeString
0x1400bd2e4  nop     dword ptr [rax+rax+00h]
0x1400bd2e9  test    eax, eax
0x1400bd2eb  jz      short loc_1400BD341
0x1400bd2ed  mov     r8d, eax
0x1400bd2f0  lea     rdx, aRtldowncaseuni; "RtlDowncaseUnicodeString"
0x1400bd2f7  call    WfpReportSysErrorAsNtStatus
0x1400bd2fc  mov     rdi, rax
0x1400bd2ff  jmp     short loc_1400BD341
0x1400bd301  mov     r8d, 0C0000017h
0x1400bd307  lea     rdx, aWfpallocatefro; "WfpAllocateFromPerProcessorLookasideLis"...
0x1400bd30e  call    WfpReportSysErrorAsNtStatus
0x1400bd313  mov     rdi, rax
0x1400bd316  test    rax, rax
0x1400bd319  jz      short loc_1400BD338
0x1400bd31b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bd322  lea     rax, WPP_GLOBAL_Control
0x1400bd329  cmp     rcx, rax
0x1400bd32c  jz      short loc_1400BD338
0x1400bd32e  cmp     byte ptr [rcx+29h], 2
0x1400bd332  jnb     loc_1400BD773
0x1400bd338  test    rdi, rdi
0x1400bd33b  jz      loc_1400BD2A4
0x1400bd341  test    rsi, rsi
0x1400bd344  jz      short loc_1400BD355
0x1400bd346  mov     rcx, rsi; FileNameInformation
0x1400bd349  call    cs:__imp_FltReleaseFileNameInformation
0x1400bd350  nop     dword ptr [rax+rax+00h]
0x1400bd355  lea     r14, WPP_GLOBAL_Control
0x1400bd35c  xor     esi, esi
0x1400bd35e  test    rdi, rdi
0x1400bd361  jz      loc_1400BDA1B
0x1400bd367  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bd36e  cmp     rcx, r14
0x1400bd371  jz      short loc_1400BD37D
0x1400bd373  cmp     byte ptr [rcx+29h], 2
0x1400bd377  jnb     loc_1400BD741
0x1400bd37d  mov     rax, [rbp+40h+DestinationString.Buffer]
0x1400bd381  test    rax, rax
0x1400bd384  jnz     loc_1400BD892
0x1400bd38a  test    r13, r13
0x1400bd38d  jz      loc_1400BD624
0x1400bd393  xor     edx, edx; Tag
0x1400bd395  mov     rcx, r13; P
0x1400bd398  call    cs:__imp_ExFreePoolWithTag
0x1400bd39f  nop     dword ptr [rax+rax+00h]
0x1400bd3a4  jmp     loc_1400BD624
0x1400bd3a9  mov     r8d, ebx
0x1400bd3ac  lea     rdx, aFltgetfilename; "FltGetFileNameInformationUnsafe"
0x1400bd3b3  call    WfpReportSysErrorAsNtStatus
0x1400bd3b8  mov     r8d, ebx
0x1400bd3bb  lea     rdx, aWfpalequerynor; "WfpAleQueryNormalizedImageFileName"
0x1400bd3c2  call    WfpReportSysErrorAsNtStatus
0x1400bd3c7  mov     rdi, rax
0x1400bd3ca  jmp     short loc_1400BD35E
0x1400bd3cc  mov     rax, [rbp+40h+DestinationString.Buffer]
0x1400bd3d0  xor     ecx, ecx
0x1400bd3d2  mov     word ptr [rbp+40h+FileNameInformation], cx
0x1400bd3d6  mov     byte ptr [rbp+40h+FileNameInformation+2], cl
0x1400bd3d9  mov     rcx, cs:processTableLookasideList
0x1400bd3e0  mov     [rsp+140h+var_C8], rax
0x1400bd3e5  mov     eax, gs:1A4h
0x1400bd3ed  lea     ebx, [rax+1]
0x1400bd3f0  shl     rbx, 7
0x1400bd3f4  add     rbx, rcx
0x1400bd3f7  movzx   eax, byte ptr [rbx+0B0h]
0x1400bd3fe  test    al, al
0x1400bd400  jnz     short loc_1400BD40B
0x1400bd402  lea     rdx, [rbx+40h]
0x1400bd406  call    PplpLazyInitializeLookasideList
0x1400bd40b  lea     rcx, [rbx+40h]; Lookaside
0x1400bd40f  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400bd416  nop     dword ptr [rax+rax+00h]
0x1400bd41b  mov     [rsp+140h+var_D0], rax
0x1400bd420  mov     rbx, rax
0x1400bd423  test    rax, rax
0x1400bd426  jz      loc_1400BD986
0x1400bd42c  movzx   edi, [rbp+40h+arg_1]
0x1400bd430  lea     rcx, [rbx+8]; void *
0x1400bd434  movzx   esi, byte ptr [rbp+40h+arg_2]
0x1400bd438  xor     edx, edx; Val
0x1400bd43a  movzx   r14d, byte ptr [rbp+40h+arg_2+1]
0x1400bd43f  mov     r8d, 78h ; 'x'; Size
0x1400bd445  movzx   r15d, byte ptr [rbp+40h+arg_2+2]
0x1400bd44a  movzx   r12d, byte ptr [rbp+40h+arg_2+3]
0x1400bd44f  movzx   r13d, [rbp+40h+arg_6]
0x1400bd454  call    memset
0x1400bd459  mov     r8, [rbp+50h]
0x1400bd45d  movzx   eax, r8b
0x1400bd461  imul    rcx, rax, 25h ; '%'
0x1400bd465  mov     rax, [rsp+140h+var_D0]
0x1400bd46a  add     rcx, rdi
0x1400bd46d  imul    rdx, rcx, 25h ; '%'
0x1400bd471  mov     [rax+1], dil
0x1400bd475  mov     rdi, rax
0x1400bd478  add     rdx, rsi
0x1400bd47b  mov     [rax], r8b
0x1400bd47e  imul    rcx, rdx, 25h ; '%'
0x1400bd482  mov     [rax+2], sil
0x1400bd486  add     rcx, r14
0x1400bd489  mov     [rax+3], r14b
0x1400bd48d  imul    rdx, rcx, 25h ; '%'
0x1400bd491  mov     [rax+4], r15b
0x1400bd495  add     rdx, r15
0x1400bd498  mov     [rax+5], r12b
0x1400bd49c  imul    rcx, rdx, 25h ; '%'
0x1400bd4a0  mov     [rax+6], r13b
0x1400bd4a4  add     rcx, r12
0x1400bd4a7  imul    rdx, rcx, 25h ; '%'
0x1400bd4ab  mov     ecx, cs:gAleNumHashEntryBits
0x1400bd4b1  add     rdx, r13
0x1400bd4b4  imul    rbx, rdx, 25h ; '%'
0x1400bd4b8  movzx   edx, [rbp+40h+arg_7]
0x1400bd4bc  add     rbx, rdx
0x1400bd4bf  mov     [rax+7], dl
0x1400bd4c2  mov     rdx, [rsp+140h+var_C8]; SourceString
0x1400bd4c7  shl     rbx, cl
0x1400bd4ca  lea     rcx, [rax+8]; DestinationString
0x1400bd4ce  or      rbx, 3
0x1400bd4d2  call    cs:__imp_RtlInitUnicodeString
0x1400bd4d9  nop     dword ptr [rax+rax+00h]
0x1400bd4de  mov     rax, [rbp+40h+arg_8]
0x1400bd4e2  mov     r15, [rbp+40h+var_C0]
0x1400bd4e6  mov     r13, [rbp+40h+var_90]
0x1400bd4ea  mov     [rdi+20h], rax
0x1400bd4ee  mov     [rdi+18h], r15
0x1400bd4f2  mov     [rdi+30h], r13
0x1400bd4f6  mov     [rdi+78h], rbx
0x1400bd4fa  call    cs:__imp_KeGetCurrentIrql
0x1400bd501  nop     dword ptr [rax+rax+00h]
0x1400bd506  mov     rcx, cs:gAleHashtableLock; Lock
0x1400bd50d  lea     rdx, [rbp+40h+FileNameInformation]; LockState
0x1400bd511  xor     r8d, r8d; Flags
0x1400bd514  movzx   ebx, al
0x1400bd517  call    cs:__imp_NdisAcquireRWLockWrite
0x1400bd51e  nop     dword ptr [rax+rax+00h]
0x1400bd523  cmp     bl, 2
0x1400bd526  jz      short loc_1400BD565
0x1400bd528  cmp     cs:gWfpPerProContext, 0
0x1400bd530  jz      short loc_1400BD565
0x1400bd532  xor     ecx, ecx; ProcNumber
0x1400bd534  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400bd53b  nop     dword ptr [rax+rax+00h]
0x1400bd540  lea     ecx, [rax+rax*8]
0x1400bd543  mov     rax, cs:gWfpPerProContext
0x1400bd54a  shl     ecx, 3
0x1400bd54d  mov     rcx, [rcx+rax]
0x1400bd551  mov     rax, ds:0FFFFF78000000008h
0x1400bd55b  mov     [rcx+8], rax
0x1400bd55f  mov     dword ptr [rcx], 4
0x1400bd565  mov     r8, [rdi+78h]
0x1400bd569  lea     rdx, [rdi+68h]; Entry
0x1400bd56d  xor     edi, edi
0x1400bd56f  test    r8, r8
0x1400bd572  jnz     short loc_1400BD57F
0x1400bd574  mov     r8, 0FFFFFFFFFFFFFFFFh; Signature
0x1400bd57b  mov     [rdx+10h], r8
0x1400bd57f  xor     r9d, r9d; Context
0x1400bd582  lea     rcx, gAleMasterHashTable; HashTable
0x1400bd589  call    cs:__imp_RtlInsertEntryHashTable
0x1400bd590  nop     dword ptr [rax+rax+00h]
0x1400bd595  test    al, al
0x1400bd597  jz      loc_1400BDC1D
0x1400bd59d  xor     ebx, ebx
0x1400bd59f  test    rdi, rdi
0x1400bd5a2  jz      loc_1400BD6DE
0x1400bd5a8  mov     rsi, [rsp+140h+var_D0]
0x1400bd5ad  cmp     cs:gWfpPerProContext, 0
0x1400bd5b5  jz      short loc_1400BD5E1
0x1400bd5b7  xor     ecx, ecx; ProcNumber
0x1400bd5b9  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400bd5c0  nop     dword ptr [rax+rax+00h]
0x1400bd5c5  lea     ecx, [rax+rax*8]
0x1400bd5c8  mov     rax, cs:gWfpPerProContext
0x1400bd5cf  shl     ecx, 3
0x1400bd5d2  mov     rcx, [rcx+rax]
0x1400bd5d6  cmp     dword ptr [rcx], 4
0x1400bd5d9  jnz     short loc_1400BD5E1
0x1400bd5db  mov     dword ptr [rcx], 0
0x1400bd5e1  mov     rcx, cs:gAleHashtableLock; Lock
0x1400bd5e8  lea     rdx, [rbp+40h+FileNameInformation]; LockState
0x1400bd5ec  call    cs:__imp_NdisReleaseRWLock
0x1400bd5f3  nop     dword ptr [rax+rax+00h]
0x1400bd5f8  test    rdi, rdi
0x1400bd5fb  jnz     loc_1400BDC90
0x1400bd601  mov     rcx, [rbx+30h]
0x1400bd605  lea     rax, [rbx+40h]
0x1400bd609  lea     r9, [rbx+38h]
0x1400bd60d  mov     [rsp+140h+AllocationSize], rax
0x1400bd612  lea     rdx, [rbx+8]
0x1400bd616  call    WfpAppTriggerCheckProcessCreate
0x1400bd61b  lea     rcx, [rbx+48h]
0x1400bd61f  call    WfpAleDecrementWaitRef
0x1400bd624  mov     rcx, [rbp+40h+Object]; Object
0x1400bd628  mov     r15, [rsp+140h+var_38]
0x1400bd630  mov     r14, [rsp+140h+var_30]
0x1400bd638  mov     r13, [rsp+140h+var_28]
0x1400bd640  mov     r12, [rsp+140h+var_20]
0x1400bd648  mov     rdi, [rsp+140h+var_18]
0x1400bd650  mov     rsi, [rsp+140h+var_10]
0x1400bd658  mov     rbx, [rsp+138h]
0x1400bd660  test    rcx, rcx
0x1400bd663  jz      short loc_1400BD671
0x1400bd665  call    cs:__imp_ObfDereferenceObject
0x1400bd66c  nop     dword ptr [rax+rax+00h]
0x1400bd671  mov     rcx, [rbp+40h+Handle]; Handle
0x1400bd675  test    rcx, rcx
0x1400bd678  jz      short loc_1400BD686
0x1400bd67a  call    cs:__imp_ZwClose
0x1400bd681  nop     dword ptr [rax+rax+00h]
0x1400bd686  add     rsp, 140h
0x1400bd68d  pop     rbp
0x1400bd68e  retn
0x1400bd690  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x1400bd694  xor     eax, eax
0x1400bd696  mov     [rbp+40h+pImageFileName], rsi
0x1400bd69a  lea     rdx, [rbp+40h+pImageFileName]; pImageFileName
0x1400bd69e  mov     rcx, r12; Process
0x1400bd6a1  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x1400bd6a5  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x1400bd6a9  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x1400bd6ad  call    cs:__imp_SeLocateProcessImageName
0x1400bd6b4  nop     dword ptr [rax+rax+00h]
0x1400bd6b9  test    eax, eax
  ... truncated ...
```
