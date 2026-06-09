# WfpCreateProcessNotifyRoutine

- ea: `0x1400c68c0`
- end: `0x1400c73d0`
- name: `WfpCreateProcessNotifyRoutine`
- size: `2832`
- prototype: `__int64 __fastcall(PEPROCESS Process)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400c6700`

## callees

- `0x140013140`
- `0x140014480`
- `0x140014974`
- `0x140014a90`
- `0x1400162f0`
- `0x1400ad6a0`
- `0x1400c68c0`
- `0x1400c73e0`
- `0x1400c749c`
- `0x1400c7c48`
- `0x1400c7cac`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400c6e31`
- `ntoskrnl!ObfReferenceObject` at `0x1400c6e31`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400c6ca9`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400c6ca9`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400c69ae`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400c6b2f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400c69ae`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400c6b2f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c6c54`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c6cd9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c6c54`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c6cd9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c6c1a`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c6c1a`
- `ntoskrnl!ZwCreateFile` at `0x1400c6f49`
- `ntoskrnl!ZwCreateFile` at `0x1400c6f49`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400c6dcd`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400c6dcd`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x1400c69fd`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x1400c69fd`
- `ntoskrnl!ZwClose` at `0x1400c6d9a`
- `ntoskrnl!ZwClose` at `0x1400c6d9a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400c6f8e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400c6f8e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c6bf2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c7095`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c6bf2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c7095`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c6d85`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c6d85`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400c71f9`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400c71f9`
- `ntoskrnl!ObCloseHandle` at `0x1400c71e5`
- `ntoskrnl!ObCloseHandle` at `0x1400c71e5`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400c71bb`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400c727f`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400c72d2`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400c71bb`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400c727f`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400c72d2`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400c718d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400c718d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400c7159`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400c7159`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c6ab8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c6f5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c6fbc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c7212`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c6ab8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c6f5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c6fbc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c7212`
- `ntoskrnl!ExAllocatePool2` at `0x1400c72a4`
- `ntoskrnl!ExAllocatePool2` at `0x1400c72a4`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400c6c37`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400c6c37`
- `NDIS!NdisReleaseRWLock` at `0x1400c6d0c`
- `NDIS!NdisReleaseRWLock` at `0x1400c6d0c`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400c6944`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400c6944`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400c6a69`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400c6a69`

## string_xrefs

- `0x1400c6a27`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400c6ea4`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400c70ac`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400c711d`: `WfpAllocateFromPerProcessorLookasideList`
- `0x1400c7343`: `RtlCreateHashTable`
- `0x1400c706f`: `RtlStringCbCopyW`
- `0x1400c6de4`: `WfpCreateProcessNotifyRoutine`
- `0x1400c725a`: `WfpCapturePackageSid`
- `0x1400c7312`: `WfpCapturePackageSid`
- `0x1400c7329`: `WfpCapturePackageSid`

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
0x1400c68c0  mov     rax, rsp
0x1400c68c3  mov     [rax+10h], rdx
0x1400c68c7  mov     [rax+8], rcx
0x1400c68cb  push    rbp
0x1400c68cc  lea     rbp, [rax-48h]
0x1400c68d0  sub     rsp, 140h
0x1400c68d7  mov     [rax-10h], rbx
0x1400c68db  xorps   xmm0, xmm0
0x1400c68de  mov     [rax-18h], rsi
0x1400c68e2  xor     esi, esi
0x1400c68e4  mov     [rax-20h], rdi
0x1400c68e8  mov     edi, 200h
0x1400c68ed  mov     [rax-28h], r12
0x1400c68f1  mov     r12, rcx
0x1400c68f4  mov     rcx, [r8+28h]; FileObject
0x1400c68f8  mov     [rax-30h], r13
0x1400c68fc  mov     r13d, esi
0x1400c68ff  mov     [rax-38h], r14
0x1400c6903  mov     [rax-40h], r15
0x1400c6907  mov     r15d, esi
0x1400c690a  mov     [rbp+40h+var_C0], rsi
0x1400c690e  mov     [rbp+40h+Handle], rsi
0x1400c6912  mov     [rbp+40h+Object], rsi
0x1400c6916  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x1400c691a  test    rcx, rcx
0x1400c691d  jz      loc_1400C6DB0
0x1400c6923  test    dword ptr [rcx+50h], 4000h
0x1400c692a  jnz     loc_1400C6DB0
0x1400c6930  lea     r9, [rbp+40h+FileNameInformation]; FileNameInformation
0x1400c6934  mov     [rbp+40h+SourceString], rsi
0x1400c6938  xor     edx, edx; Instance
0x1400c693a  mov     [rbp+40h+FileNameInformation], rsi
0x1400c693e  mov     r8d, 101h; NameOptions
0x1400c6944  call    cs:__imp_FltGetFileNameInformationUnsafe
0x1400c694b  nop     dword ptr [rax+rax+00h]
0x1400c6950  lea     r14, WPP_GLOBAL_Control
0x1400c6957  mov     ebx, eax
0x1400c6959  test    eax, eax
0x1400c695b  jnz     loc_1400C6AC9
0x1400c6961  mov     rsi, [rbp+40h+FileNameInformation]
0x1400c6965  cmp     [rsi+8], r13w
0x1400c696a  jz      loc_1400C6FF3
0x1400c6970  movzx   eax, word ptr [rsi+0Ah]
0x1400c6974  cmp     ax, di
0x1400c6977  ja      loc_1400C6EC5
0x1400c697d  mov     eax, gs:1A4h
0x1400c6985  mov     rcx, cs:processPathLookasideListLarge
0x1400c698c  lea     ebx, [rax+1]
0x1400c698f  shl     rbx, 7
0x1400c6993  add     rbx, rcx
0x1400c6996  movzx   eax, byte ptr [rbx+0B0h]
0x1400c699d  test    al, al
0x1400c699f  jnz     short loc_1400C69AA
0x1400c69a1  lea     rdx, [rbx+40h]
0x1400c69a5  call    PplpLazyInitializeLookasideList
0x1400c69aa  lea     rcx, [rbx+40h]; Lookaside
0x1400c69ae  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400c69b5  nop     dword ptr [rax+rax+00h]
0x1400c69ba  mov     rbx, rax
0x1400c69bd  test    rax, rax
0x1400c69c0  jz      short loc_1400C6A21
0x1400c69c2  xor     edi, edi
0x1400c69c4  mov     r15, cs:processPathLookasideListLarge
0x1400c69cb  xor     edx, edx; Val
0x1400c69cd  mov     r8d, 202h; Size
0x1400c69d3  mov     [rbp+40h+var_C0], r15
0x1400c69d7  mov     rcx, rbx; void *
0x1400c69da  call    memset
0x1400c69df  movzx   eax, word ptr [rsi+0Ah]
0x1400c69e3  lea     rdx, [rsi+8]; SourceString
0x1400c69e7  xorps   xmm0, xmm0
0x1400c69ea  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x1400c69ee  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x1400c69f2  xor     r8d, r8d; AllocateDestinationString
0x1400c69f5  mov     [rbp+40h+DestinationString.MaximumLength], ax
0x1400c69f9  mov     [rbp+40h+DestinationString.Buffer], rbx
0x1400c69fd  call    cs:__imp_RtlDowncaseUnicodeString
0x1400c6a04  nop     dword ptr [rax+rax+00h]
0x1400c6a09  test    eax, eax
0x1400c6a0b  jz      short loc_1400C6A61
0x1400c6a0d  mov     r8d, eax
0x1400c6a10  lea     rdx, aRtldowncaseuni; "RtlDowncaseUnicodeString"
0x1400c6a17  call    WfpReportSysErrorAsNtStatus
0x1400c6a1c  mov     rdi, rax
0x1400c6a1f  jmp     short loc_1400C6A61
0x1400c6a21  mov     r8d, 0C0000017h
0x1400c6a27  lea     rdx, aWfpallocatefro; "WfpAllocateFromPerProcessorLookasideLis"...
0x1400c6a2e  call    WfpReportSysErrorAsNtStatus
0x1400c6a33  mov     rdi, rax
0x1400c6a36  test    rax, rax
0x1400c6a39  jz      short loc_1400C6A58
0x1400c6a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c6a42  lea     rax, WPP_GLOBAL_Control
0x1400c6a49  cmp     rcx, rax
0x1400c6a4c  jz      short loc_1400C6A58
0x1400c6a4e  cmp     byte ptr [rcx+29h], 2
0x1400c6a52  jnb     loc_1400C6E93
0x1400c6a58  test    rdi, rdi
0x1400c6a5b  jz      loc_1400C69C4
0x1400c6a61  test    rsi, rsi
0x1400c6a64  jz      short loc_1400C6A75
0x1400c6a66  mov     rcx, rsi; FileNameInformation
0x1400c6a69  call    cs:__imp_FltReleaseFileNameInformation
0x1400c6a70  nop     dword ptr [rax+rax+00h]
0x1400c6a75  lea     r14, WPP_GLOBAL_Control
0x1400c6a7c  xor     esi, esi
0x1400c6a7e  test    rdi, rdi
0x1400c6a81  jz      loc_1400C713B
0x1400c6a87  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c6a8e  cmp     rcx, r14
0x1400c6a91  jz      short loc_1400C6A9D
0x1400c6a93  cmp     byte ptr [rcx+29h], 2
0x1400c6a97  jnb     loc_1400C6E61
0x1400c6a9d  mov     rax, [rbp+40h+DestinationString.Buffer]
0x1400c6aa1  test    rax, rax
0x1400c6aa4  jnz     loc_1400C6FB2
0x1400c6aaa  test    r13, r13
0x1400c6aad  jz      loc_1400C6D44
0x1400c6ab3  xor     edx, edx; Tag
0x1400c6ab5  mov     rcx, r13; P
0x1400c6ab8  call    cs:__imp_ExFreePoolWithTag
0x1400c6abf  nop     dword ptr [rax+rax+00h]
0x1400c6ac4  jmp     loc_1400C6D44
0x1400c6ac9  mov     r8d, ebx
0x1400c6acc  lea     rdx, aFltgetfilename; "FltGetFileNameInformationUnsafe"
0x1400c6ad3  call    WfpReportSysErrorAsNtStatus
0x1400c6ad8  mov     r8d, ebx
0x1400c6adb  lea     rdx, aWfpalequerynor; "WfpAleQueryNormalizedImageFileName"
0x1400c6ae2  call    WfpReportSysErrorAsNtStatus
0x1400c6ae7  mov     rdi, rax
0x1400c6aea  jmp     short loc_1400C6A7E
0x1400c6aec  mov     rax, [rbp+40h+DestinationString.Buffer]
0x1400c6af0  xor     ecx, ecx
0x1400c6af2  mov     word ptr [rbp+40h+FileNameInformation], cx
0x1400c6af6  mov     byte ptr [rbp+40h+FileNameInformation+2], cl
0x1400c6af9  mov     rcx, cs:processTableLookasideList
0x1400c6b00  mov     [rsp+140h+var_C8], rax
0x1400c6b05  mov     eax, gs:1A4h
0x1400c6b0d  lea     ebx, [rax+1]
0x1400c6b10  shl     rbx, 7
0x1400c6b14  add     rbx, rcx
0x1400c6b17  movzx   eax, byte ptr [rbx+0B0h]
0x1400c6b1e  test    al, al
0x1400c6b20  jnz     short loc_1400C6B2B
0x1400c6b22  lea     rdx, [rbx+40h]
0x1400c6b26  call    PplpLazyInitializeLookasideList
0x1400c6b2b  lea     rcx, [rbx+40h]; Lookaside
0x1400c6b2f  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400c6b36  nop     dword ptr [rax+rax+00h]
0x1400c6b3b  mov     [rsp+140h+var_D0], rax
0x1400c6b40  mov     rbx, rax
0x1400c6b43  test    rax, rax
0x1400c6b46  jz      loc_1400C70A6
0x1400c6b4c  movzx   edi, [rbp+40h+arg_1]
0x1400c6b50  lea     rcx, [rbx+8]; void *
0x1400c6b54  movzx   esi, byte ptr [rbp+40h+arg_2]
0x1400c6b58  xor     edx, edx; Val
0x1400c6b5a  movzx   r14d, byte ptr [rbp+40h+arg_2+1]
0x1400c6b5f  mov     r8d, 78h ; 'x'; Size
0x1400c6b65  movzx   r15d, byte ptr [rbp+40h+arg_2+2]
0x1400c6b6a  movzx   r12d, byte ptr [rbp+40h+arg_2+3]
0x1400c6b6f  movzx   r13d, [rbp+40h+arg_6]
0x1400c6b74  call    memset
0x1400c6b79  mov     r8, [rbp+50h]
0x1400c6b7d  movzx   eax, r8b
0x1400c6b81  imul    rcx, rax, 25h ; '%'
0x1400c6b85  mov     rax, [rsp+140h+var_D0]
0x1400c6b8a  add     rcx, rdi
0x1400c6b8d  imul    rdx, rcx, 25h ; '%'
0x1400c6b91  mov     [rax+1], dil
0x1400c6b95  mov     rdi, rax
0x1400c6b98  add     rdx, rsi
0x1400c6b9b  mov     [rax], r8b
0x1400c6b9e  imul    rcx, rdx, 25h ; '%'
0x1400c6ba2  mov     [rax+2], sil
0x1400c6ba6  add     rcx, r14
0x1400c6ba9  mov     [rax+3], r14b
0x1400c6bad  imul    rdx, rcx, 25h ; '%'
0x1400c6bb1  mov     [rax+4], r15b
0x1400c6bb5  add     rdx, r15
0x1400c6bb8  mov     [rax+5], r12b
0x1400c6bbc  imul    rcx, rdx, 25h ; '%'
0x1400c6bc0  mov     [rax+6], r13b
0x1400c6bc4  add     rcx, r12
0x1400c6bc7  imul    rdx, rcx, 25h ; '%'
0x1400c6bcb  mov     ecx, cs:gAleNumHashEntryBits
0x1400c6bd1  add     rdx, r13
0x1400c6bd4  imul    rbx, rdx, 25h ; '%'
0x1400c6bd8  movzx   edx, [rbp+40h+arg_7]
0x1400c6bdc  add     rbx, rdx
0x1400c6bdf  mov     [rax+7], dl
0x1400c6be2  mov     rdx, [rsp+140h+var_C8]; SourceString
0x1400c6be7  shl     rbx, cl
0x1400c6bea  lea     rcx, [rax+8]; DestinationString
0x1400c6bee  or      rbx, 3
0x1400c6bf2  call    cs:__imp_RtlInitUnicodeString
0x1400c6bf9  nop     dword ptr [rax+rax+00h]
0x1400c6bfe  mov     rax, [rbp+40h+arg_8]
0x1400c6c02  mov     r15, [rbp+40h+var_C0]
0x1400c6c06  mov     r13, [rbp+40h+var_90]
0x1400c6c0a  mov     [rdi+20h], rax
0x1400c6c0e  mov     [rdi+18h], r15
0x1400c6c12  mov     [rdi+30h], r13
0x1400c6c16  mov     [rdi+78h], rbx
0x1400c6c1a  call    cs:__imp_KeGetCurrentIrql
0x1400c6c21  nop     dword ptr [rax+rax+00h]
0x1400c6c26  mov     rcx, cs:gAleHashtableLock; Lock
0x1400c6c2d  lea     rdx, [rbp+40h+FileNameInformation]; LockState
0x1400c6c31  xor     r8d, r8d; Flags
0x1400c6c34  movzx   ebx, al
0x1400c6c37  call    cs:__imp_NdisAcquireRWLockWrite
0x1400c6c3e  nop     dword ptr [rax+rax+00h]
0x1400c6c43  cmp     bl, 2
0x1400c6c46  jz      short loc_1400C6C85
0x1400c6c48  cmp     cs:gWfpPerProContext, 0
0x1400c6c50  jz      short loc_1400C6C85
0x1400c6c52  xor     ecx, ecx; ProcNumber
0x1400c6c54  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400c6c5b  nop     dword ptr [rax+rax+00h]
0x1400c6c60  lea     ecx, [rax+rax*8]
0x1400c6c63  mov     rax, cs:gWfpPerProContext
0x1400c6c6a  shl     ecx, 3
0x1400c6c6d  mov     rcx, [rcx+rax]
0x1400c6c71  mov     rax, ds:0FFFFF78000000008h
0x1400c6c7b  mov     [rcx+8], rax
0x1400c6c7f  mov     dword ptr [rcx], 4
0x1400c6c85  mov     r8, [rdi+78h]
0x1400c6c89  lea     rdx, [rdi+68h]; Entry
0x1400c6c8d  xor     edi, edi
0x1400c6c8f  test    r8, r8
0x1400c6c92  jnz     short loc_1400C6C9F
0x1400c6c94  mov     r8, 0FFFFFFFFFFFFFFFFh; Signature
0x1400c6c9b  mov     [rdx+10h], r8
0x1400c6c9f  xor     r9d, r9d; Context
0x1400c6ca2  lea     rcx, gAleMasterHashTable; HashTable
0x1400c6ca9  call    cs:__imp_RtlInsertEntryHashTable
0x1400c6cb0  nop     dword ptr [rax+rax+00h]
0x1400c6cb5  test    al, al
0x1400c6cb7  jz      loc_1400C733D
0x1400c6cbd  xor     ebx, ebx
0x1400c6cbf  test    rdi, rdi
0x1400c6cc2  jz      loc_1400C6DFE
0x1400c6cc8  mov     rsi, [rsp+140h+var_D0]
0x1400c6ccd  cmp     cs:gWfpPerProContext, 0
0x1400c6cd5  jz      short loc_1400C6D01
0x1400c6cd7  xor     ecx, ecx; ProcNumber
0x1400c6cd9  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400c6ce0  nop     dword ptr [rax+rax+00h]
0x1400c6ce5  lea     ecx, [rax+rax*8]
0x1400c6ce8  mov     rax, cs:gWfpPerProContext
0x1400c6cef  shl     ecx, 3
0x1400c6cf2  mov     rcx, [rcx+rax]
0x1400c6cf6  cmp     dword ptr [rcx], 4
0x1400c6cf9  jnz     short loc_1400C6D01
0x1400c6cfb  mov     dword ptr [rcx], 0
0x1400c6d01  mov     rcx, cs:gAleHashtableLock; Lock
0x1400c6d08  lea     rdx, [rbp+40h+FileNameInformation]; LockState
0x1400c6d0c  call    cs:__imp_NdisReleaseRWLock
0x1400c6d13  nop     dword ptr [rax+rax+00h]
0x1400c6d18  test    rdi, rdi
0x1400c6d1b  jnz     loc_1400C73B0
0x1400c6d21  mov     rcx, [rbx+30h]
0x1400c6d25  lea     rax, [rbx+40h]
0x1400c6d29  lea     r9, [rbx+38h]
0x1400c6d2d  mov     [rsp+140h+AllocationSize], rax
0x1400c6d32  lea     rdx, [rbx+8]
0x1400c6d36  call    WfpAppTriggerCheckProcessCreate
0x1400c6d3b  lea     rcx, [rbx+48h]
0x1400c6d3f  call    WfpAleDecrementWaitRef
0x1400c6d44  mov     rcx, [rbp+40h+Object]; Object
0x1400c6d48  mov     r15, [rsp+140h+var_38]
0x1400c6d50  mov     r14, [rsp+140h+var_30]
0x1400c6d58  mov     r13, [rsp+140h+var_28]
0x1400c6d60  mov     r12, [rsp+140h+var_20]
0x1400c6d68  mov     rdi, [rsp+140h+var_18]
0x1400c6d70  mov     rsi, [rsp+140h+var_10]
0x1400c6d78  mov     rbx, [rsp+138h]
0x1400c6d80  test    rcx, rcx
0x1400c6d83  jz      short loc_1400C6D91
0x1400c6d85  call    cs:__imp_ObfDereferenceObject
0x1400c6d8c  nop     dword ptr [rax+rax+00h]
0x1400c6d91  mov     rcx, [rbp+40h+Handle]; Handle
0x1400c6d95  test    rcx, rcx
0x1400c6d98  jz      short loc_1400C6DA6
0x1400c6d9a  call    cs:__imp_ZwClose
0x1400c6da1  nop     dword ptr [rax+rax+00h]
0x1400c6da6  add     rsp, 140h
0x1400c6dad  pop     rbp
0x1400c6dae  retn
0x1400c6db0  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x1400c6db4  xor     eax, eax
0x1400c6db6  mov     [rbp+40h+pImageFileName], rsi
0x1400c6dba  lea     rdx, [rbp+40h+pImageFileName]; pImageFileName
0x1400c6dbe  mov     rcx, r12; Process
0x1400c6dc1  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x1400c6dc5  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x1400c6dc9  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x1400c6dcd  call    cs:__imp_SeLocateProcessImageName
0x1400c6dd4  nop     dword ptr [rax+rax+00h]
0x1400c6dd9  test    eax, eax
  ... truncated ...
```
