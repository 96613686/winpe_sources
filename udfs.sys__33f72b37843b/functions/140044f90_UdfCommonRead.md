# UdfCommonRead

- ea: `0x140044f90`
- end: `0x140045eff`
- name: `UdfCommonRead`
- size: `3951`
- prototype: `__int64 __fastcall(_QWORD *Entry, IRP *Context2)`
- caller_count: `2`
- callee_count: `24`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x1400039fc`
- `0x140004380`
- `0x14000653c`
- `0x140009014`
- `0x14000c640`
- `0x14000ca10`
- `0x14000ca54`
- `0x14000cad4`
- `0x140010c5c`
- `0x140012cc8`
- `0x1400149d0`
- `0x140014c08`
- `0x140015638`
- `0x14001bd80`
- `0x14001c080`
- `0x140044860`
- `0x140044f90`
- `0x140045f10`
- `0x140046750`
- `0x1400472e0`
- `0x14004d45c`
- `0x1400537b0`
- `0x1400543e0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140045425`
- `ntoskrnl!ExRaiseStatus` at `0x140045479`
- `ntoskrnl!ExRaiseStatus` at `0x140045728`
- `ntoskrnl!ExRaiseStatus` at `0x14004583e`
- `ntoskrnl!ExRaiseStatus` at `0x140045858`
- `ntoskrnl!ExRaiseStatus` at `0x140045425`
- `ntoskrnl!ExRaiseStatus` at `0x140045479`
- `ntoskrnl!ExRaiseStatus` at `0x140045728`
- `ntoskrnl!ExRaiseStatus` at `0x14004583e`
- `ntoskrnl!ExRaiseStatus` at `0x140045858`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140045ab9`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140045ab9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140045193`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140045193`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045b67`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045ea9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a07f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045b67`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045ea9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a07f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400455b4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400455b4`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140045607`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140045607`
- `ntoskrnl!ExAcquireFastMutex` at `0x140045220`
- `ntoskrnl!ExAcquireFastMutex` at `0x140045220`
- `ntoskrnl!ExReleaseFastMutex` at `0x140045242`
- `ntoskrnl!ExReleaseFastMutex` at `0x140045242`
- `ntoskrnl!CcFlushCache` at `0x1400455e0`
- `ntoskrnl!CcFlushCache` at `0x1400455e0`
- `ntoskrnl!FsRtlCheckOplock` at `0x1400451f2`
- `ntoskrnl!FsRtlCheckOplock` at `0x1400451f2`
- `ntoskrnl!CcInitializeCacheMap` at `0x140045ae6`
- `ntoskrnl!CcInitializeCacheMap` at `0x140045ae6`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x1400457d6`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x1400457d6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140045457`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140045706`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140045457`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140045706`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x14004580a`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x14004580a`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x140045afb`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x140045afb`
- `ntoskrnl!CcCopyRead` at `0x1400452e5`
- `ntoskrnl!CcCopyRead` at `0x1400452e5`
- `ntoskrnl!CcMdlRead` at `0x1400456ce`
- `ntoskrnl!CcMdlRead` at `0x1400456ce`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x140045404`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x140045404`

## pseudocode

```c
__int64 __fastcall UdfCommonRead(_QWORD *Entry, IRP *Context2)
{
  IRP *v2; // r13
  __int64 v3; // r15
  union _LARGE_INTEGER *v4; // rdi
  PFILE_OBJECT FileObject; // r12
  __int64 v6; // r8
  unsigned __int64 FsContext2; // r14
  int v8; // esi
  char *FsContext; // rbx
  unsigned __int64 v10; // r14
  int v11; // edx
  int v12; // r9d
  ULONG Flags; // r11d
  __int64 LowPart; // rdi
  int v15; // r10d
  _DWORD *v16; // rcx
  struct _ERESOURCE *v17; // rcx
  int v18; // eax
  int v19; // r12d
  NTSTATUS Status; // edi
  __int64 QuadPart; // r8
  FILE_LOCK *v22; // rcx
  ULONG v23; // r14d
  union _LARGE_INTEGER v24; // rdi
  struct _IO_STACK_LOCATION *v25; // r14
  struct _FILE_OBJECT *v26; // rsi
  PMDL *p_MdlAddress; // r9
  PMDL v28; // rcx
  PVOID UserBuffer; // rax
  char v30; // si
  union _LARGE_INTEGER v31; // rdx
  int v32; // edx
  int v33; // r9d
  unsigned int v34; // esi
  __int64 v35; // r8
  PMDL MdlAddress; // rcx
  PVOID MappedSystemVa; // rax
  NTSTATUS v38; // eax
  __int64 v39; // rax
  __int64 v40; // rsi
  union _LARGE_INTEGER v41; // rax
  void *v42; // rdi
  __int64 v43; // rdx
  struct _IO_STACK_LOCATION *v45; // rbx
  __int64 v46; // r8
  __int64 v47; // rdx
  char v48; // al
  bool v49; // zf
  LOCK_OPERATION v50; // r9d
  _QWORD *v51; // rax
  char v52; // [rsp+61h] [rbp-127h]
  union _LARGE_INTEGER FileOffset; // [rsp+70h] [rbp-118h] BYREF
  ULONG Length[2]; // [rsp+78h] [rbp-110h]
  __int64 v55; // [rsp+80h] [rbp-108h]
  int v56; // [rsp+88h] [rbp-100h]
  _DWORD *v57; // [rsp+90h] [rbp-F8h]
  ULONG v58; // [rsp+98h] [rbp-F0h]
  __int64 v59; // [rsp+A0h] [rbp-E8h]
  int v60; // [rsp+A8h] [rbp-E0h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+B0h] [rbp-D8h]
  char *v62; // [rsp+B8h] [rbp-D0h]
  _OWORD v63[2]; // [rsp+C0h] [rbp-C8h] BYREF
  __int64 v64; // [rsp+E0h] [rbp-A8h]
  _OWORD v65[5]; // [rsp+F0h] [rbp-98h] BYREF
  int v66; // [rsp+140h] [rbp-48h]
  unsigned __int64 v67; // [rsp+198h] [rbp+10h] BYREF
  int v68; // [rsp+1A0h] [rbp+18h]
  ULONG v69; // [rsp+1A8h] [rbp+20h]

  v2 = Context2;
  v3 = (__int64)Entry;
  CurrentStackLocation = Context2->Tail.Overlay.CurrentStackLocation;
  v4 = (union _LARGE_INTEGER *)CurrentStackLocation;
  FileOffset.QuadPart = 0;
  memset(v63, 0, sizeof(v63));
  v64 = 0;
  memset(v65, 0, sizeof(v65));
  v66 = 0;
  FileObject = CurrentStackLocation->FileObject;
  v6 = Entry[2];
  v59 = v6;
  FsContext2 = (unsigned __int64)FileObject->FsContext2;
  v8 = FsContext2 & 7;
  FileObject->FsContext2 = (PVOID)FsContext2;
  if ( (FsContext2 & 7) != 0 )
  {
    FsContext = (char *)FileObject->FsContext;
    v10 = FsContext2 & 0xFFFFFFFFFFFFFFF8uLL;
  }
  else
  {
    FsContext = 0;
    v10 = 0;
  }
  v62 = FsContext;
  if ( !v8 || v8 == 3 )
  {
    UdfCompleteRequest(Entry, Context2, 3221225488LL);
    return 3221225488LL;
  }
  if ( FsContext == *(char **)(v6 + 296)
    && *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000000) != 0 )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qD)(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      10,
      WPP_3a4bc84a1802361b0ed93f440d80abe7_Traceguids,
      (union _LARGE_INTEGER)v4[3].QuadPart,
      v4[1].LowPart);
    v6 = v59;
  }
  if ( !v4[1].LowPart )
  {
    UdfCompleteRequest(v3, v2, 0);
    return 0;
  }
  v11 = *(_DWORD *)(v3 + 28);
  v12 = v11 & 4;
  v60 = v12;
  LOBYTE(v67) = v12 != 0;
  Flags = v2->Flags;
  v68 = *(_DWORD *)(v4[6].QuadPart + 80);
  FileOffset = v4[3];
  LowPart = v4[1].LowPart;
  *(_QWORD *)Length = LowPart;
  v55 = LowPart + FileOffset.QuadPart;
  if ( 0x7FFFFFFFFFFFFFFFLL - FileOffset.QuadPart < LowPart )
  {
    UdfCompleteRequest(v3, v2, 3221225485LL);
    return 3221225485LL;
  }
  v15 = Flags & 2;
  v56 = v15;
  v68 &= 2u;
  v52 = 0;
  v58 = LowPart;
  v16 = (_DWORD *)(v10 + 4);
  v57 = (_DWORD *)(v10 + 4);
  if ( v8 == 2 )
  {
    LOBYTE(Flags) = 1;
    v69 = Flags;
    if ( (*v16 & 0x1000) != 0 )
      *(_DWORD *)(v3 + 28) = v11 | 0x2000;
    else
      v57 = (_DWORD *)(v10 + 4);
  }
  else
  {
    LOBYTE(Flags) = Flags & 1;
    v69 = Flags;
  }
  if ( v8 == 4
    && (*(_DWORD *)(v6 + 48) & 0x40000000) != 0
    && ((*v16 & 0x4000) != 0 || (*((_DWORD *)FsContext + 53) & 0x10000000) != 0) )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000) != 0 )
    {
      WPP_SF_qq(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        11,
        WPP_3a4bc84a1802361b0ed93f440d80abe7_Traceguids,
        FsContext,
        v10);
      v12 = v60;
      v15 = v56;
      LOBYTE(Flags) = v69;
    }
    *(_DWORD *)(v3 + 28) |= 0x100000u;
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000) != 0 )
  {
    v46 = 89;
    v47 = 89;
    if ( !v12 )
      v47 = 78;
    v48 = 89;
    if ( !(_BYTE)Flags )
      v48 = 78;
    if ( !v15 )
      v46 = 78;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _BYTE, _BYTE, _BYTE))WPP_SF_qqdiDccc)(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      v47,
      v46,
      v2,
      FsContext,
      v8,
      (union _LARGE_INTEGER)FileOffset.QuadPart,
      LowPart,
      (_BYTE)v46,
      v48,
      (_BYTE)v47);
    v15 = v56;
    LOBYTE(Flags) = v69;
  }
  if ( !v15 && (_BYTE)Flags && FileObject->SectionObjectPointer->DataSectionObject )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 13, WPP_3a4bc84a1802361b0ed93f440d80abe7_Traceguids);
    }
    if ( !ExAcquireResourceExclusiveLite(
            (PERESOURCE)(*(_QWORD *)(*((_QWORD *)FsContext + 17) + 80LL) + 8LL),
            (*(_DWORD *)(v3 + 28) & 4) != 0) )
    {
      *(_DWORD *)(v3 + 24) = -1073741608;
      ExRaiseStatus(-1073741608);
    }
    CcFlushCache(FileObject->SectionObjectPointer, &FileOffset, Length[0], &v2->IoStatus);
    Status = v2->IoStatus.Status;
    if ( Status < 0 )
    {
      v30 = 1;
      goto LABEL_140;
    }
    ExConvertExclusiveToSharedLite((PERESOURCE)(*(_QWORD *)(*((_QWORD *)FsContext + 17) + 80LL) + 8LL));
  }
  else
  {
    v17 = (struct _ERESOURCE *)(*(_QWORD *)(*((_QWORD *)FsContext + 17) + 80LL) + 8LL);
    v18 = *(_DWORD *)(v3 + 28);
    if ( v15 )
    {
      if ( !ExAcquireSharedStarveExclusive(v17, (v18 & 4) != 0) )
      {
        *(_DWORD *)(v3 + 24) = -1073741608;
        ExRaiseStatus(-1073741608);
      }
    }
    else if ( !ExAcquireResourceSharedLite(v17, (v18 & 4) != 0) )
    {
      *(_DWORD *)(v3 + 24) = -1073741608;
      ExRaiseStatus(-1073741608);
    }
  }
  if ( v8 != 2 || !v10 || (*v57 & 8) == 0 )
    UdfVerifyScbOperation(v3, FsContext, v10);
  v19 = v56;
  if ( v56 || v8 != 4 )
    goto LABEL_26;
  Status = FsRtlCheckOplock((POPLOCK)FsContext + 11, v2, (PVOID)v3, UdfOplockComplete, UdfPrePostIrp);
  if ( Status )
  {
    v2 = 0;
    v3 = 0;
    v30 = 1;
    goto LABEL_140;
  }
  v22 = (FILE_LOCK *)*((_QWORD *)FsContext + 63);
  if ( !v22 || FsRtlCheckLockForReadAccess(v22, v2) )
  {
LABEL_26:
    ExAcquireFastMutex(*((PFAST_MUTEX *)FsContext + 6));
    if ( v19
      || FsContext[4] >= 0
      || v55 <= *((_QWORD *)FsContext + 5)
      || (v31 = FileOffset, FileOffset.QuadPart >= *((_QWORD *)FsContext + 4)) )
    {
      v23 = Length[0];
    }
    else
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 14, WPP_3a4bc84a1802361b0ed93f440d80abe7_Traceguids);
        v31 = FileOffset;
      }
      v23 = Length[0];
      if ( (unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))UdfWaitForIoAtEof)(
                              FsContext,
                              (union _LARGE_INTEGER)v31.QuadPart,
                              Length[0]) )
        UdfFinishIoAtEof(FsContext);
    }
    v24 = *(union _LARGE_INTEGER *)(FsContext + 32);
    ExReleaseFastMutex(*((PFAST_MUTEX *)FsContext + 6));
    if ( v8 == 2 && (*v57 & 0x10) != 0 )
    {
      QuadPart = FileOffset.QuadPart;
    }
    else
    {
      QuadPart = FileOffset.QuadPart;
      if ( FileOffset.QuadPart >= v24.QuadPart )
      {
        Status = -1073741807;
        v30 = 1;
        goto LABEL_140;
      }
      if ( v55 > v24.QuadPart )
      {
        v23 = v24.LowPart - FileOffset.LowPart;
        *(_QWORD *)Length = v24.LowPart - FileOffset.LowPart;
        v55 = v24.QuadPart;
        v57 = (_DWORD *)v24.QuadPart;
LABEL_32:
        if ( (_BYTE)v69 )
        {
          v32 = *((_DWORD *)FsContext + 53);
          if ( (v32 & 2) != 0 )
          {
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000) != 0 )
            {
              WPP_SF_(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                15,
                WPP_3a4bc84a1802361b0ed93f440d80abe7_Traceguids);
              QuadPart = FileOffset.QuadPart;
            }
            v40 = v59;
            v41.QuadPart = (unsigned int)(*(_DWORD *)(v59 + 68) - *((_DWORD *)FsContext + 56));
            if ( v24.QuadPart > v41.QuadPart )
            {
              v55 = (unsigned int)(*(_DWORD *)(v59 + 68) - *((_DWORD *)FsContext + 56));
              v57 = (_DWORD *)v41.QuadPart;
              if ( v41.QuadPart <= QuadPart )
                v23 = 0;
              else
                v23 = v41.LowPart - QuadPart;
            }
            v42 = (void *)UdfMapUserBuffer(v3, v2);
            if ( v23 )
            {
              if ( FsContext == *(char **)(v40 + 344) && *(_QWORD *)(v40 + 352) )
              {
                if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
                {
                  WPP_SF_(
                    *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                    16,
                    WPP_3a4bc84a1802361b0ed93f440d80abe7_Traceguids);
                }
                v43 = *((unsigned int *)FsContext + 56) + *(_QWORD *)(v40 + 464);
              }
              else
              {
                if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000) != 0 )
                {
                  WPP_SF_d(
                    *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                    17,
                    WPP_3a4bc84a1802361b0ed93f440d80abe7_Traceguids);
                }
                v63[0] = 0;
                v67 = *((_QWORD *)FsContext + 23);
                UdfMapMetadataView(v3, v63, v40, HIDWORD(v67), v67, *(_DWORD *)(v40 + 68), 4);
                v52 = 1;
                v43 = *(_QWORD *)&v63[0] + *((unsigned int *)FsContext + 56);
              }
              memmove(v42, (const void *)(FileOffset.QuadPart + v43), v23);
            }
            v2->IoStatus.Information = v23;
            if ( v68 && !v19 )
              CurrentStackLocation->FileObject->CurrentByteOffset.QuadPart = v55;
            Status = 0;
            goto LABEL_41;
          }
          v33 = *(_DWORD *)(v59 + 68);
          v34 = ~(v33 - 1) & (v23 + v33 - 1);
          if ( (((v33 - 1) & (unsigned int)QuadPart) != 0 || v34 > v58)
            && (!v19 || !*(_QWORD *)(*((_QWORD *)FsContext + 53) + 24LL) || (v32 & 0x2000) != 0) )
          {
            Status = -1073741811;
            v30 = 1;
            goto LABEL_140;
          }
          if ( !v19
            || (v32 & 0x2000) == 0
            || (FsContext[4] & 0x20) == 0
            || (Status = UdfProcessHolesInFileRegion(
                           v3,
                           (_DWORD)FsContext,
                           (unsigned __int64)QuadPart >> *(_DWORD *)(v59 + 72),
                           (~(unsigned __int64)(unsigned int)(v33 - 1)
                          & ((unsigned int)(v33 - 1) + (unsigned __int64)((unsigned int)QuadPart & (v33 - 1)) + v34)) >> *(_DWORD *)(v59 + 72),
                           0,
                           0,
                           0,
                           0),
                Status >= 0) )
          {
            UdfAllocIoContext(v3, v65);
            *(_DWORD *)(*(_QWORD *)(v3 + 40) + 56LL) = v23;
            *(_QWORD *)(*(_QWORD *)(v3 + 40) + 32LL) = *((_QWORD *)FsContext + 1);
            v2->IoStatus.Information = v34;
            UdfLockUserBuffer(v3, v58, v35, IoWriteAccess);
            MdlAddress = v2->MdlAddress;
            if ( MdlAddress )
            {
              if ( (MdlAddress->MdlFlags & 5) != 0 )
                MappedSystemVa = MdlAddress->MappedSystemVa;
              else
                MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
              if ( !MappedSystemVa )
              {
                *(_DWORD *)(v3 + 24) = -1073741670;
                ExRaiseStatus(-1073741670);
              }
            }
            else
            {
              MappedSystemVa = v2->UserBuffer;
            }
            v38 = UdfNonCachedIo(v3, MappedSystemVa, 0, 0);
            Status = v38;
            if ( v38 == 259 )
            {
              v2 = 0;
              v30 = 0;
              goto LABEL_140;
            }
            if ( v38 < 0 )
            {
              v2->IoStatus.Information = 0;
              if ( (unsigned int)(v38 + 1073741662) <= 1
                || (unsigned int)(v38 + 1073741806) <= 2
                || v38 == -2147483626
                || v38 == -1073741643 )
              {
                IoSetHardErrorOrVerifyDevice(*(PIRP *)(v3 + 8), *(PDEVICE_OBJECT *)(*(_QWORD *)(v59 + 8) + 16LL));
                UdfRaiseStatusEx(v3, (unsigned int)Status, 0);
              }
              Status = FsRtlNormalizeNtstatus(v38, -1073741591);
            }
            else if ( v34 != v23 )
            {
              v39 = UdfMapUserBuffer(v3, v2);
              memset((void *)(v23 + v39), 0, v34 - Length[0]);
              v2->IoStatus.Information = v23;
            }
            if ( v68 && !v19 && Status >= 0 )
            {
              v25 = CurrentStackLocation;
LABEL_139:
              v25->FileObject->CurrentByteOffset.QuadPart = v55;
            }
          }
        }
        else
        {
          v25 = CurrentStackLocation;
          v26 = CurrentStackLocation->FileObject;
          if ( !v26->PrivateCacheMap )
          {
            CcInitializeCacheMap(v26, (PCC_FILE_SIZES)FsContext + 1, 0, &Callbacks, FsContext);
            CcSetReadAheadGranularity(v25->FileObject, 0x10000u);
          }
          p_MdlAddress = &v2->MdlAddress;
          if ( (*(_BYTE *)(v3 + 57) & 2) != 0 )
          {
            CcMdlRead(v26, &FileOffset, Length[0], p_MdlAddress, &v2->IoStatus);
            Status = v2->IoStatus.Status;
          }
          else
          {
            v28 = *p_MdlAddress;
            if ( *p_MdlAddress )
            {
              if ( (v28->MdlFlags & 5) != 0 )
                UserBuffer = v28->MappedSystemVa;
              else
                UserBuffer = MmMapLockedPagesSpecifyCache(v28, 0, MmCached, 0, 0, 0x40000010u);
              if ( !UserBuffer )
              {
                *(_DWORD *)(v3 + 24) = -1073741670;
                ExRaiseStatus(-1073741670);
              }
            }
            else
            {
              UserBuffer = v2->UserBuffer;
            }
            if ( !CcCopyRead(v26, &FileOffset, Length[0], v67, UserBuffer, &v2->IoStatus) )
            {
              Status = -1073741608;
              v30 = 1;
              goto LABEL_140;
            }
            Status = v2->IoStatus.Status;
            if ( Status < 0 )
            {
              LOBYTE(QuadPart) = 1;
              UdfRaiseStatusEx(v3, (unsigned int)Status, QuadPart);
            }
          }
          if ( v68 && !v19 && Status >= 0 )
            goto LABEL_139;
        }
LABEL_41:
        v30 = 1;
        goto LABEL_140;
      }
    }
    v24.QuadPart = v55;
    goto LABEL_32;
  }
  Status = -1073741740;
  v30 = 1;
LABEL_140:
  if ( v52 )
    UdfUnpinView(v3, v63);
  if ( v30 )
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*((_QWORD *)FsContext + 17) + 80LL) + 8LL));
  if ( Status == -1073741608 )
  {
    v45 = v2->Tail.Overlay.CurrentStackLocation;
    LOBYTE(v67) = 0;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x1000000) != 0 )
    {
      WPP_SF_q(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        10,
        WPP_3ff9e5ec72f932b5eb1d8b8d4a04988f_Traceguids,
        v2);
    }
    switch ( *(_BYTE *)(v3 + 56) )
    {
      case 0:
        v51 = *(_QWORD **)(v3 + 40);
        if ( v51 && *v51 )
        {
          UdfTeardownStructures(v3, *v51, 0, 0, (__int64)&v67);
          if ( !(_BYTE)v67 )
            ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(**(_QWORD **)(v3 + 40) + 136LL) + 80LL) + 8LL));
          **(_QWORD **)(v3 + 40) = 0;
          *(_QWORD *)(v3 + 40) = 0;
        }
        goto LABEL_155;
      case 3:
        v49 = (*(_BYTE *)(v3 + 57) & 2) == 0;
        break;
      case 4:
        if ( (*(_BYTE *)(v3 + 57) & 2) != 0 )
          goto LABEL_155;
        v50 = IoReadAccess;
        goto LABEL_182;
      case 0xC:
        v49 = *(_BYTE *)(v3 + 57) == 1;
        break;
      default:
LABEL_155:
        *(_DWORD *)(v3 + 28) |= 2u;
        UdfCleanupIrpContext((PVOID)v3);
        v2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        UdfAddToWorkque((PVOID)v3, v2);
        Status = 259;
        goto LABEL_146;
    }
    if ( !v49 )
      goto LABEL_155;
    v50 = IoWriteAccess;
LABEL_182:
    UdfLockUserBuffer(v3, v45->Parameters.Read.Length, QuadPart, v50);
    goto LABEL_155;
  }
  UdfCompleteRequest(v3, v2, (unsigned int)Status);
LABEL_146:
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 18, WPP_3a4bc84a1802361b0ed93f440d80abe7_Traceguids);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140044f90  mov     r11, rsp
0x140044f93  mov     [r11+8], rcx
0x140044f97  push    rbx
0x140044f98  push    rsi
0x140044f99  push    rdi
0x140044f9a  push    r12
0x140044f9c  push    r13
0x140044f9e  push    r14
0x140044fa0  push    r15
0x140044fa2  sub     rsp, 150h
0x140044fa9  mov     r13, rdx
0x140044fac  mov     r15, rcx
0x140044faf  mov     rdi, [rdx+0B8h]
0x140044fb6  mov     [rsp+188h+var_D8], rdi
0x140044fbe  mov     qword ptr [rsp+188h+FileOffset], 0
0x140044fc7  xorps   xmm0, xmm0
0x140044fca  xor     eax, eax
0x140044fcc  movups  [rsp+188h+var_C8], xmm0
0x140044fd4  movups  [rsp+188h+var_B8], xmm0
0x140044fdc  mov     [r11-0A8h], rax
0x140044fe3  movups  [rsp+188h+var_98], xmm0
0x140044feb  movups  [rsp+188h+var_88], xmm0
0x140044ff3  movups  xmmword ptr [r11-78h], xmm0
0x140044ff8  movups  xmmword ptr [r11-68h], xmm0
0x140044ffd  movups  xmmword ptr [r11-58h], xmm0
0x140045002  mov     [r11-48h], eax
0x140045006  mov     r12, [rdi+30h]
0x14004500a  mov     r8, [rcx+10h]
0x14004500e  mov     [rsp+188h+var_E8], r8
0x140045016  mov     r14, [r12+20h]
0x14004501b  mov     esi, r14d
0x14004501e  and     esi, 7
0x140045021  mov     [r12+20h], r14
0x140045026  jz      loc_140045C8D
0x14004502c  mov     rbx, [r12+18h]
0x140045031  and     r14, 0FFFFFFFFFFFFFFF8h
0x140045035  mov     [rsp+188h+var_D0], rbx
0x14004503d  test    esi, esi
0x14004503f  jz      loc_140045EEA
0x140045045  cmp     esi, 3
0x140045048  jz      loc_140045EEA
0x14004504e  cmp     rbx, [r8+128h]
0x140045055  jz      loc_140045C97
0x14004505b  cmp     dword ptr [rdi+8], 0
0x14004505f  jz      loc_140045CE8
0x140045065  mov     edx, [r15+1Ch]
0x140045069  mov     r9d, edx
0x14004506c  and     r9d, 4
0x140045070  mov     [rsp+188h+var_E0], r9d
0x140045078  setnz   byte ptr [rsp+188h+arg_8]
0x140045080  mov     r11d, [r13+10h]
0x140045084  mov     rax, [rdi+30h]
0x140045088  mov     ecx, [rax+50h]
0x14004508b  mov     [rsp+188h+arg_10], ecx
0x140045092  mov     rcx, [rdi+18h]
0x140045096  mov     qword ptr [rsp+188h+FileOffset], rcx
0x14004509b  mov     edi, [rdi+8]
0x14004509e  mov     qword ptr [rsp+188h+Length], rdi
0x1400450a3  lea     rax, [rdi+rcx]
0x1400450a7  mov     [rsp+188h+var_108], rax
0x1400450af  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400450b9  sub     rax, rcx
0x1400450bc  cmp     rax, rdi
0x1400450bf  jl      loc_140045CFD
0x1400450c5  mov     r10d, r11d
0x1400450c8  and     r10d, 2
0x1400450cc  mov     [rsp+188h+var_100], r10d
0x1400450d4  and     [rsp+188h+arg_10], 2
0x1400450dc  mov     [rsp+188h+var_127], 0
0x1400450e1  mov     [rsp+188h+var_128], 0
0x1400450e6  mov     [rsp+188h+var_F0], edi
0x1400450ed  lea     rcx, [r14+4]
0x1400450f1  mov     [rsp+188h+var_F8], rcx
0x1400450f9  cmp     esi, 2
0x1400450fc  jz      loc_140045C3C
0x140045102  and     r11b, 1
0x140045106  mov     [rsp+188h+arg_18], r11d
0x14004510e  cmp     esi, 4
0x140045111  jnz     short loc_140045139
0x140045113  mov     eax, [r8+30h]
0x140045117  bt      eax, 1Eh
0x14004511b  jnb     short loc_140045139
0x14004511d  mov     eax, [rcx]
0x14004511f  bt      eax, 0Eh
0x140045123  jb      loc_140045C60
0x140045129  mov     eax, [rbx+0D4h]
0x14004512f  bt      eax, 1Ch
0x140045133  jb      loc_140045C60
0x140045139  lea     rdx, WPP_GLOBAL_Control
0x140045140  mov     rcx, cs:WPP_GLOBAL_Control
0x140045147  cmp     rcx, rdx
0x14004514a  jz      short loc_140045159
0x14004514c  mov     eax, [rcx+2Ch]
0x14004514f  bt      eax, 10h
0x140045153  jb      loc_140045D65
0x140045159  test    r10d, r10d
0x14004515c  jnz     short loc_140045167
0x14004515e  test    r11b, r11b
0x140045161  jnz     loc_140045572
0x140045167  mov     rax, [rbx+88h]
0x14004516e  mov     rcx, [rax+50h]
0x140045172  add     rcx, 8; Resource
0x140045176  xor     dl, dl
0x140045178  mov     eax, [r15+1Ch]
0x14004517c  test    r10d, r10d
0x14004517f  jnz     loc_1400453F6
0x140045185  mov     [rsp+188h+var_11E], dl
0x140045189  test    al, 4
0x14004518b  jz      short loc_140045193
0x14004518d  mov     dl, 1; Wait
0x14004518f  mov     [rsp+188h+var_11E], dl
0x140045193  call    cs:__imp_ExAcquireResourceSharedLite
0x14004519a  nop     dword ptr [rax+rax+00h]
0x14004519f  test    al, al
0x1400451a1  jz      loc_14004584B
0x1400451a7  mov     [rsp+188h+var_128], 1
0x1400451ac  cmp     esi, 2
0x1400451af  jz      loc_140045698
0x1400451b5  mov     r8, r14
0x1400451b8  mov     rdx, rbx
0x1400451bb  mov     rcx, r15
0x1400451be  call    UdfVerifyScbOperation
0x1400451c3  mov     r12d, [rsp+188h+var_100]
0x1400451cb  test    r12d, r12d
0x1400451ce  jnz     short loc_14004521C
0x1400451d0  cmp     esi, 4
0x1400451d3  jnz     short loc_14004521C
0x1400451d5  lea     rcx, [rbx+58h]; Oplock
0x1400451d9  lea     rax, UdfPrePostIrp
0x1400451e0  mov     [rsp+188h+PostIrpRoutine], rax; PostIrpRoutine
0x1400451e5  lea     r9, UdfOplockComplete; CompletionRoutine
0x1400451ec  mov     r8, r15; Context
0x1400451ef  mov     rdx, r13; Irp
0x1400451f2  call    cs:__imp_FsRtlCheckOplock
0x1400451f9  nop     dword ptr [rax+rax+00h]
0x1400451fe  mov     edi, eax
0x140045200  mov     [rsp+188h+var_124], eax
0x140045204  test    eax, eax
0x140045206  jnz     loc_1400457EF
0x14004520c  mov     rcx, [rbx+1F8h]; FileLock
0x140045213  test    rcx, rcx
0x140045216  jnz     loc_140045807
0x14004521c  mov     rcx, [rbx+30h]; FastMutex
0x140045220  call    cs:__imp_ExAcquireFastMutex
0x140045227  nop     dword ptr [rax+rax+00h]
0x14004522c  test    r12d, r12d
0x14004522f  jz      loc_14004531F
0x140045235  mov     r14, qword ptr [rsp+188h+Length]
0x14004523a  mov     rdi, [rbx+20h]
0x14004523e  mov     rcx, [rbx+30h]; FastMutex
0x140045242  call    cs:__imp_ExReleaseFastMutex
0x140045249  nop     dword ptr [rax+rax+00h]
0x14004524e  cmp     esi, 2
0x140045251  jz      loc_1400453DA
0x140045257  mov     r8, qword ptr [rsp+188h+FileOffset]
0x14004525c  cmp     r8, rdi
0x14004525f  jge     loc_140045655
0x140045265  cmp     [rsp+188h+var_108], rdi
0x14004526d  jg      loc_1400453B8
0x140045273  mov     rdi, [rsp+188h+var_108]
0x14004527b  cmp     byte ptr [rsp+188h+arg_18], 0
0x140045283  jnz     loc_140045486
0x140045289  mov     r14, [rsp+188h+var_D8]
0x140045291  mov     rsi, [r14+30h]
0x140045295  cmp     qword ptr [rsi+30h], 0
0x14004529a  jz      loc_140045AD0
0x1400452a0  lea     r9, [r13+8]; MdlChain
0x1400452a4  movzx   eax, byte ptr [r15+39h]
0x1400452a9  test    al, 2
0x1400452ab  jnz     loc_1400456B8
0x1400452b1  mov     rcx, [r9]; MemoryDescriptorList
0x1400452b4  test    rcx, rcx
0x1400452b7  jnz     loc_140045432
0x1400452bd  mov     rax, [r13+70h]
0x1400452c1  lea     rdi, [r13+30h]
0x1400452c5  mov     [rsp+188h+IoStatus], rdi; IoStatus
0x1400452ca  mov     [rsp+188h+PostIrpRoutine], rax; Buffer
0x1400452cf  movzx   r9d, byte ptr [rsp+188h+arg_8]; Wait
0x1400452d8  mov     r8d, [rsp+188h+Length]; Length
0x1400452dd  lea     rdx, [rsp+188h+FileOffset]; FileOffset
0x1400452e2  mov     rcx, rsi; FileObject
0x1400452e5  call    cs:__imp_CcCopyRead
0x1400452ec  nop     dword ptr [rax+rax+00h]
0x1400452f1  test    al, al
0x1400452f3  jz      loc_1400453A5
0x1400452f9  mov     edi, [rdi]
0x1400452fb  test    edi, edi
0x1400452fd  js      loc_140045B15
0x140045303  mov     [rsp+188h+var_124], edi
0x140045307  cmp     [rsp+188h+arg_10], 0
0x14004530f  jnz     loc_140045B22
0x140045315  movzx   esi, [rsp+188h+var_128]
0x14004531a  jmp     loc_140045B48
0x14004531f  cmp     byte ptr [rbx+4], 0
0x140045323  jge     loc_140045235
0x140045329  mov     rcx, [rsp+188h+var_108]
0x140045331  cmp     rcx, [rbx+28h]
0x140045335  jle     loc_140045235
0x14004533b  mov     rdx, qword ptr [rsp+188h+FileOffset]
0x140045340  cmp     rdx, [rbx+20h]
0x140045344  jge     loc_140045235
0x14004534a  mov     rcx, cs:WPP_GLOBAL_Control
0x140045351  lea     rax, WPP_GLOBAL_Control
0x140045358  cmp     rcx, rax
0x14004535b  jz      short loc_140045380
0x14004535d  test    dword ptr [rcx+2Ch], 10000h
0x140045364  jz      short loc_140045380
0x140045366  mov     edx, 0Eh
0x14004536b  lea     r8, WPP_3a4bc84a1802361b0ed93f440d80abe7_Traceguids
0x140045372  mov     rcx, [rcx+18h]
0x140045376  call    WPP_SF_
0x14004537b  mov     rdx, qword ptr [rsp+188h+FileOffset]
0x140045380  mov     r14, qword ptr [rsp+188h+Length]
0x140045385  mov     r8d, r14d
0x140045388  mov     rcx, rbx
0x14004538b  call    UdfWaitForIoAtEof
0x140045390  test    al, al
0x140045392  jz      loc_14004523A
0x140045398  mov     rcx, rbx
0x14004539b  call    UdfFinishIoAtEof
0x1400453a0  jmp     loc_14004523A
0x1400453a5  mov     edi, 0C00000D8h
0x1400453aa  mov     [rsp+188h+var_124], edi
0x1400453ae  movzx   esi, [rsp+188h+var_128]
0x1400453b3  jmp     loc_140045B48
0x1400453b8  mov     eax, edi
0x1400453ba  sub     eax, r8d
0x1400453bd  mov     r14d, eax
0x1400453c0  mov     qword ptr [rsp+188h+Length], r14
0x1400453c5  mov     [rsp+188h+var_108], rdi
0x1400453cd  mov     [rsp+188h+var_F8], rdi
0x1400453d5  jmp     loc_14004527B
0x1400453da  mov     rax, [rsp+188h+var_F8]
0x1400453e2  mov     eax, [rax]
0x1400453e4  test    al, 10h
0x1400453e6  jz      loc_140045257
0x1400453ec  mov     r8, qword ptr [rsp+188h+FileOffset]
0x1400453f1  jmp     loc_140045273
0x1400453f6  mov     [rsp+188h+var_11F], dl
0x1400453fa  test    al, 4
0x1400453fc  jz      short loc_140045404
0x1400453fe  mov     dl, 1; Wait
0x140045400  mov     [rsp+188h+var_11F], dl
0x140045404  call    cs:__imp_ExAcquireSharedStarveExclusive
0x14004540b  nop     dword ptr [rax+rax+00h]
0x140045410  test    al, al
0x140045412  jnz     loc_1400451A7
0x140045418  mov     dword ptr [r15+18h], 0C00000D8h
0x140045420  mov     ecx, 0C00000D8h; Status
0x140045425  call    cs:__imp_ExRaiseStatus
0x140045432  test    byte ptr [rcx+0Ah], 5
0x140045436  jnz     loc_140045B0C
0x14004543c  mov     dword ptr [rsp+188h+IoStatus], 40000010h; Priority
0x140045444  mov     dword ptr [rsp+188h+PostIrpRoutine], 0; BugCheckOnFailure
0x14004544c  xor     r9d, r9d; RequestedAddress
0x14004544f  xor     edx, edx; AccessMode
0x140045451  mov     r8d, 1; CacheType
0x140045457  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004545e  nop     dword ptr [rax+rax+00h]
0x140045463  test    rax, rax
0x140045466  jnz     loc_1400452C1
0x14004546c  mov     dword ptr [r15+18h], 0C000009Ah
0x140045474  mov     ecx, 0C000009Ah; Status
0x140045479  call    cs:__imp_ExRaiseStatus
0x140045486  mov     edx, [rbx+0D4h]
0x14004548c  test    dl, 2
0x14004548f  jnz     loc_140045865
0x140045495  mov     r10, [rsp+188h+var_E8]
0x14004549d  mov     r9d, [r10+44h]
0x1400454a1  lea     ecx, [r9-1]
0x1400454a5  lea     esi, [r9-1]
0x1400454a9  add     esi, r14d
0x1400454ac  mov     eax, ecx
0x1400454ae  not     eax
0x1400454b0  and     esi, eax
0x1400454b2  test    r8d, ecx
0x1400454b5  jnz     loc_140045668
0x1400454bb  cmp     esi, [rsp+188h+var_F0]
0x1400454c2  ja      loc_140045668
0x1400454c8  test    r12d, r12d
0x1400454cb  jz      short loc_1400454D7
0x1400454cd  bt      edx, 0Dh
0x1400454d1  jb      loc_140045A1C
0x1400454d7  lea     rdx, [rsp+188h+var_98]
0x1400454df  mov     rcx, r15
0x1400454e2  call    UdfAllocIoContext
0x1400454e7  mov     rax, [r15+28h]
0x1400454eb  mov     [rax+38h], r14d
0x1400454ef  mov     rcx, [r15+28h]
0x1400454f3  mov     rax, [rbx+8]
0x1400454f7  mov     [rcx+20h], rax
0x1400454fb  mov     eax, esi
0x1400454fd  mov     [r13+38h], rax
0x140045501  mov     r9d, 1
0x140045507  mov     edx, [rsp+188h+var_F0]
0x14004550e  mov     rcx, r15
0x140045511  call    UdfLockUserBuffer
0x140045516  mov     rcx, [r13+8]; MemoryDescriptorList
0x14004551a  test    rcx, rcx
0x14004551d  jnz     loc_1400456E1
  ... truncated ...
```
