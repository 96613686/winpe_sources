# UdfCommonWrite

- ea: `0x1400010f0`
- end: `0x1400030d6`
- name: `UdfCommonWrite`
- size: `8166`
- prototype: `__int64 __fastcall(PVOID Entry, PVOID Context2)`
- caller_count: `2`
- callee_count: `41`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400010f0`
- `0x1400030e0`
- `0x1400039fc`
- `0x140004380`
- `0x1400050d8`
- `0x140005e80`
- `0x1400062c0`
- `0x14000653c`
- `0x140007b90`
- `0x140009014`
- `0x14000b648`
- `0x14000c728`
- `0x14000ca10`
- `0x14000ca54`
- `0x14000cad4`
- `0x14000cb6c`
- `0x14000eb04`
- `0x14000ed4c`
- `0x14001093c`
- `0x140010c5c`
- `0x140014c08`
- `0x140015638`
- `0x14001758c`
- `0x1400193f0`
- `0x1400195a4`
- `0x14001978c`
- `0x14001980c`
- `0x140019894`
- `0x14001bd80`
- `0x14001c080`
- `0x14002dc10`
- `0x14002dc50`
- `0x140044860`
- `0x140045f10`
- `0x140046750`
- `0x1400472e0`
- `0x14004ce50`
- `0x1400543e0`
- `0x140054460`
- `0x140056cb8`
- `0x1400591e0`

## import_xrefs

- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140002a84`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140002a84`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400029a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003038`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000305c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c90b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c92d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400029a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003038`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000305c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c90b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001c92d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140001c9a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000260f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140001c9a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000260f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140001ce0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140001d13`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000265a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140001ce0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140001d13`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000265a`
- `ntoskrnl!CcSetFileSizes` at `0x140001c76`
- `ntoskrnl!CcSetFileSizes` at `0x140001c76`
- `ntoskrnl!ExAcquireFastMutex` at `0x140001a21`
- `ntoskrnl!ExAcquireFastMutex` at `0x140001fdf`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002e2c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002e65`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002f1a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c744`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c778`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c836`
- `ntoskrnl!ExAcquireFastMutex` at `0x140001a21`
- `ntoskrnl!ExAcquireFastMutex` at `0x140001fdf`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002e2c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002e65`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002f1a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c744`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c778`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001c836`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001de9`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001f92`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002042`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002286`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002ee2`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003017`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c803`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c8f1`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c995`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c9ef`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001de9`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001f92`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002042`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002286`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002ee2`
- `ntoskrnl!ExReleaseFastMutex` at `0x140003017`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c803`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c8f1`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c995`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001c9ef`
- `ntoskrnl!CcFlushCache` at `0x140001789`
- `ntoskrnl!CcFlushCache` at `0x140001789`
- `ntoskrnl!FsRtlCheckOplock` at `0x14000198f`
- `ntoskrnl!FsRtlCheckOplock` at `0x14000198f`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x1400019fa`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x1400019fa`
- `ntoskrnl!CcInitializeCacheMap` at `0x14000200e`
- `ntoskrnl!CcInitializeCacheMap` at `0x14000200e`
- `ntoskrnl!CcPurgeCacheSection` at `0x1400017c2`
- `ntoskrnl!CcPurgeCacheSection` at `0x1400017c2`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140002b63`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140002b63`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x140002065`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x140002065`
- `ntoskrnl!IofCompleteRequest` at `0x140001496`
- `ntoskrnl!IofCompleteRequest` at `0x140001496`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1400020db`
- `ntoskrnl!CcPrepareMdlWrite` at `0x1400020db`
- `ntoskrnl!CcCanIWrite` at `0x14000159d`
- `ntoskrnl!CcCanIWrite` at `0x14000159d`
- `ntoskrnl!CcDeferWrite` at `0x140001628`
- `ntoskrnl!CcDeferWrite` at `0x140001628`
- `ntoskrnl!CcSetDirtyPageThreshold` at `0x140002032`
- `ntoskrnl!CcSetDirtyPageThreshold` at `0x140002032`
- `ntoskrnl!CcCopyWrite` at `0x140002199`
- `ntoskrnl!CcCopyWrite` at `0x1400028d5`
- `ntoskrnl!CcCopyWrite` at `0x140002199`
- `ntoskrnl!CcCopyWrite` at `0x1400028d5`

## pseudocode

```c
__int64 __fastcall UdfCommonWrite(PVOID Entry, unsigned int *Context2)
{
  int v4; // eax
  __int64 v5; // r11
  int v6; // r10d
  int v7; // ebx
  __int64 v8; // rdx
  bool v9; // r14
  __int64 v10; // r9
  __int64 v11; // rcx
  bool v12; // r15
  int v13; // r13d
  char *v15; // rdi
  __int64 v16; // r12
  __int64 v17; // r8
  __int64 v18; // rdx
  char v19; // al
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rcx
  union _LARGE_INTEGER v23; // rbx
  __int64 v24; // rcx
  PFILE_OBJECT v25; // rax
  char v26; // r11
  __int64 v27; // r8
  PIRP *v28; // rbx
  BOOLEAN v29; // r8
  BOOLEAN v30; // di
  char v31; // cl
  char v32; // al
  char v33; // r10
  union _LARGE_INTEGER *p_FileOffset; // rdx
  __int64 v35; // rbx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // r9
  int v39; // eax
  _QWORD *v40; // rax
  int v41; // ecx
  FILE_LOCK *v42; // rcx
  char v43; // cl
  char v44; // al
  void *v45; // r9
  union _LARGE_INTEGER v46; // rdx
  _DWORD *v47; // r10
  int v48; // edx
  int v49; // r8d
  int v50; // r11d
  unsigned __int64 v51; // rdx
  unsigned int v52; // eax
  unsigned int v53; // ecx
  __int64 v54; // rdx
  signed __int64 v55; // rax
  struct _CC_FILE_SIZES *v56; // rdx
  PFILE_OBJECT v57; // rax
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rcx
  unsigned int v59; // eax
  union _LARGE_INTEGER v60; // rcx
  unsigned int v61; // r8d
  int v62; // ecx
  unsigned __int64 v63; // r11
  unsigned __int64 v64; // r9
  __int64 v65; // rcx
  int v66; // eax
  ULONG v67; // r12d
  PVOID v68; // rax
  int v69; // ecx
  __int64 v70; // r8
  PVOID v71; // rdx
  __int64 v72; // rdx
  char v73; // r9
  size_t v74; // r10
  _QWORD *v75; // rdx
  __int64 v76; // rcx
  int v77; // eax
  __int64 v78; // rax
  __int64 v79; // rcx
  unsigned int *v80; // rdx
  __int64 v81; // r8
  int v82; // eax
  bool v83; // zf
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // r8
  unsigned int v87; // r10d
  int v88; // ecx
  unsigned __int64 v89; // r13
  unsigned __int64 v90; // rbx
  int v91; // r9d
  unsigned int *v92; // rax
  unsigned int *v93; // r11
  __int64 v94; // rcx
  unsigned int v95; // eax
  unsigned int v96; // ecx
  unsigned int v97; // ecx
  unsigned __int64 v98; // r9
  unsigned __int64 v99; // rdx
  unsigned int v100; // eax
  PFILE_OBJECT v101; // r12
  bool v102; // zf
  char v103; // r14
  struct _KTHREAD *CurrentThread; // r15
  __int64 v105; // rcx
  __int64 v106; // rax
  __int64 v107; // rcx
  _QWORD *SharedCacheMap; // r8
  PSECTION_OBJECT_POINTERS v109; // rax
  int BytesToWrite; // [rsp+20h] [rbp-1A8h]
  int Retrying; // [rsp+28h] [rbp-1A0h]
  int v112; // [rsp+30h] [rbp-198h]
  char v113; // [rsp+50h] [rbp-178h]
  char v114; // [rsp+51h] [rbp-177h]
  BOOLEAN v115; // [rsp+53h] [rbp-175h]
  char v116; // [rsp+54h] [rbp-174h]
  unsigned int v117; // [rsp+5Ch] [rbp-16Ch] BYREF
  char v118; // [rsp+60h] [rbp-168h] BYREF
  PVOID Context1; // [rsp+68h] [rbp-160h]
  char v120; // [rsp+70h] [rbp-158h]
  int v121; // [rsp+74h] [rbp-154h]
  int v122; // [rsp+78h] [rbp-150h]
  bool v123; // [rsp+7Ch] [rbp-14Ch]
  ULONG Length[2]; // [rsp+80h] [rbp-148h]
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-140h]
  unsigned int v126; // [rsp+90h] [rbp-138h] BYREF
  bool v127; // [rsp+94h] [rbp-134h]
  union _LARGE_INTEGER FileOffset; // [rsp+98h] [rbp-130h] BYREF
  void *Src; // [rsp+A0h] [rbp-128h]
  bool v130; // [rsp+A8h] [rbp-120h]
  size_t Size; // [rsp+B0h] [rbp-118h] BYREF
  unsigned int *v132; // [rsp+B8h] [rbp-110h] BYREF
  __int64 v133; // [rsp+C0h] [rbp-108h]
  PVOID LazyWriteContext; // [rsp+C8h] [rbp-100h] BYREF
  __int64 v135; // [rsp+D0h] [rbp-F8h] BYREF
  char v136; // [rsp+D8h] [rbp-F0h]
  char v137; // [rsp+D9h] [rbp-EFh]
  _QWORD v138[2]; // [rsp+E0h] [rbp-E8h] BYREF
  int v139; // [rsp+F0h] [rbp-D8h]
  int v140; // [rsp+F4h] [rbp-D4h]
  __int64 v141; // [rsp+F8h] [rbp-D0h]
  _OWORD v142[2]; // [rsp+100h] [rbp-C8h] BYREF
  __int64 v143; // [rsp+120h] [rbp-A8h]
  unsigned int *v144; // [rsp+128h] [rbp-A0h]
  _QWORD v145[19]; // [rsp+130h] [rbp-98h] BYREF
  unsigned int *v146; // [rsp+1D0h] [rbp+8h]
  unsigned __int8 v147; // [rsp+1E0h] [rbp+18h] BYREF
  char v148; // [rsp+1E8h] [rbp+20h]

  Context1 = Entry;
  LazyWriteContext = 0;
  v138[0] = 0;
  v147 = 0;
  LOBYTE(v126) = 0;
  memset(v145, 0, 0x54u);
  FileOffset.QuadPart = 0;
  v132 = 0;
  LODWORD(Size) = 0;
  memset(v142, 0, sizeof(v142));
  v143 = 0;
  *((_QWORD *)Context2 + 7) = 0;
  v135 = *((_QWORD *)Context2 + 23);
  FileObject = *(PFILE_OBJECT *)(v135 + 48);
  v4 = UdfDecodeFileObject(FileObject, &LazyWriteContext, v138);
  v6 = v4;
  v121 = v4;
  v7 = *((_DWORD *)Entry + 7) & 4;
  LOBYTE(v8) = v7 != 0;
  v115 = v7 != 0;
  v10 = Context2[4];
  v9 = (v10 & 2) != 0;
  v127 = v9;
  LOBYTE(v10) = v10 & 1;
  v117 = v10;
  v12 = (*(_BYTE *)(v11 + 80) & 2) != 0;
  v130 = v12;
  if ( v4 != 4 && (v4 != 1 || !(_BYTE)v10 || !v9) && v4 != 2 )
  {
    v13 = -1073741808;
    UdfCompleteRequest(Context1, Context2, 3221225488LL);
    return (unsigned int)v13;
  }
  v15 = (char *)LazyWriteContext;
  v16 = *(_QWORD *)(*((_QWORD *)LazyWriteContext + 17) + 8LL);
  v123 = (*((_DWORD *)LazyWriteContext + 53) & 0x80u) != 0
      || LazyWriteContext == *(PVOID *)(v16 + 296)
      || LazyWriteContext == *(PVOID *)(v16 + 280)
      || LazyWriteContext == *(PVOID *)(v16 + 320)
      || LazyWriteContext == *(PVOID *)(v16 + 328);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
  {
    v17 = 89;
    v18 = 89;
    if ( !v7 )
      v18 = 78;
    v19 = 89;
    if ( !(_BYTE)v10 )
      v19 = 78;
    if ( !v9 )
      v17 = 78;
    WPP_SF_qqdccc(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      v18,
      v17,
      Context2,
      LazyWriteContext,
      v6,
      (_BYTE)v17,
      v19,
      (_BYTE)v18);
    v10 = v117;
    v5 = v135;
    v8 = v115;
    v6 = v121;
  }
  v20 = *(_DWORD *)(v16 + 48);
  if ( (v20 & 0x10000000) != 0 )
  {
    UdfCompleteRequest(Entry, Context2, 3221225865LL);
    return 3221225865LL;
  }
  if ( (v20 & 0x10) != 0 && v6 != 2 )
  {
    if ( (*(_DWORD *)(v16 + 48) & 0x4080) == 0x80 )
    {
      v21 = -1073741662;
    }
    else if ( v9 )
    {
      v21 = -1073741672;
    }
    else
    {
      v21 = -1073741790;
      if ( (v20 & 0x20) != 0 )
        v21 = -1073739770;
    }
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 13, WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids);
    }
    goto LABEL_37;
  }
  if ( !v7 )
  {
    if ( !v9 )
      goto LABEL_42;
    *((_DWORD *)Entry + 7) |= 4u;
    LOBYTE(v8) = 1;
  }
  v115 = v8;
LABEL_42:
  if ( v6 == 2 )
  {
    if ( *(_DWORD *)(*(_QWORD *)(v16 + 24) + 72LL) != 7
      || (*(_DWORD *)(v16 + 48) & 1) != 0
      || (*(_BYTE *)(v5 + 2) & 0x10) != 0 )
    {
      v22 = v138[0];
    }
    else
    {
      v22 = v138[0];
      if ( (*(_DWORD *)(v138[0] + 4LL) & 8) == 0 )
      {
        v21 = -1073741790;
LABEL_37:
        UdfCompleteRequest(Entry, Context2, v21);
        return v21;
      }
    }
    if ( (*(_DWORD *)(v16 + 84) & 0x10) != 0 )
      *(_DWORD *)(v22 + 4) |= 8u;
    LOBYTE(v10) = 1;
    v117 = v10;
    if ( (*(_DWORD *)(v22 + 4) & 0x1000) != 0 )
      *((_DWORD *)Entry + 7) |= 0x2000u;
  }
  v23 = *(union _LARGE_INTEGER *)(v5 + 24);
  FileOffset = v23;
  v24 = *(unsigned int *)(v5 + 8);
  *(_QWORD *)Length = v24;
  v141 = v24;
  if ( v23.QuadPart >= 0 )
  {
    v118 = 0;
    if ( 0x7FFFFFFFFFFFFFFFLL - v23.QuadPart < v24 )
    {
      UdfCleanupIrpContext(Entry);
      if ( (Context2[4] & 0x40) != 0 )
        *((_QWORD *)Context2 + 7) = 0;
      v13 = -1073741811;
      Context2[12] = -1073741811;
      IofCompleteRequest((PIRP)Context2, 1);
      return (unsigned int)v13;
    }
  }
  else
  {
    v118 = 1;
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qq)(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      14,
      WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids,
      (union _LARGE_INTEGER)v23.QuadPart,
      v24);
    v24 = *(_QWORD *)Length;
    v10 = v117;
    v8 = v115;
    v6 = v121;
  }
  if ( !(_DWORD)v24 )
  {
    UdfCompleteRequest(Entry, Context2, 0);
    return 0;
  }
  v25 = FileObject;
  v138[1] = FileObject;
  v13 = 0;
  v122 = 0;
  v26 = 0;
  v113 = 0;
  v114 = 0;
  v148 = 0;
  v120 = 0;
  v116 = 0;
  v27 = v24 + v23.QuadPart;
  Src = (void *)(v24 + v23.QuadPart);
  *(_DWORD *)(v16 + 2132) = 0;
  v28 = (PIRP *)Context1;
  if ( (_BYTE)v10 )
  {
LABEL_75:
    if ( (_BYTE)v10 )
    {
      UdfAllocIoContext(Context1, v145);
      v24 = *(_QWORD *)Length;
      v10 = v117;
      v6 = v121;
      v25 = FileObject;
      v26 = 0;
    }
    if ( v6 == 2 )
    {
      v13 = UdfDasdWrite((_DWORD)Context1, (_DWORD)v15, v138[0], FileOffset.LowPart, v24, (__int64)v25);
      v122 = v13;
      v31 = 0;
      if ( v13 == 259 )
        Context2 = 0;
      v32 = 0;
      v33 = 0;
      goto LABEL_348;
    }
    if ( v9 )
    {
      v35 = *(_QWORD *)Length;
    }
    else
    {
      if ( (_BYTE)v10 && v25->SectionObjectPointer->DataSectionObject )
      {
        UdfAcquireResource(Context1, *(_QWORD *)(*((_QWORD *)v15 + 17) + 80LL) + 8LL, 0, 0);
        v113 = 1;
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
        {
          WPP_SF_(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            16,
            WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids);
        }
        p_FileOffset = (union _LARGE_INTEGER *)(v15 + 32);
        if ( !v118 )
          p_FileOffset = &FileOffset;
        v133 = (__int64)(Context2 + 12);
        v35 = *(_QWORD *)Length;
        CcFlushCache(
          (PSECTION_OBJECT_POINTERS)(*((_QWORD *)v15 + 53) + 8LL),
          p_FileOffset,
          Length[0],
          (PIO_STATUS_BLOCK)Context2 + 3);
        v37 = Context2[12];
        if ( (int)v37 < 0 )
        {
          LOBYTE(v36) = 1;
          UdfRaiseStatusEx(Context1, v37, v36);
        }
        if ( !CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*((_QWORD *)v15 + 53) + 8LL), &FileOffset, Length[0], 0)
          && *((_DWORD *)v15 + 124) )
        {
          *(_DWORD *)v133 = -1073740747;
          LOBYTE(v27) = 1;
          UdfRaiseStatusEx(Context1, 3221226549LL, v27);
        }
        v26 = 1;
      }
      else
      {
        if ( (*((_DWORD *)v15 + 53) & 2) != 0 || (_BYTE)v10 )
        {
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
          {
            WPP_SF_(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
              17,
              WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids);
          }
          v38 = 0;
        }
        else
        {
          v38 = 1;
        }
        UdfAcquireResource(Context1, *(_QWORD *)(*((_QWORD *)v15 + 17) + 80LL) + 8LL, 0, v38);
        v26 = 1;
        v113 = 1;
        v35 = *(_QWORD *)Length;
      }
      v10 = v117;
      v6 = v121;
    }
    if ( !v138[0] || (*(_DWORD *)(v138[0] + 4LL) & 8) == 0 )
    {
      UdfVerifyScbOperation(Context1, v15, v138[0]);
      v10 = v117;
      v6 = v121;
      v26 = v113;
    }
    v39 = *(_DWORD *)(v16 + 2128);
    if ( (v39 & 4) != 0
      || *(_QWORD *)(v16 + 352)
      && ((v39 & 0x80u) == 0
       || (v8 = (unsigned int)(*(_DWORD *)(v16 + 668) - *(_DWORD *)(v16 + 672)),
           (unsigned int)v8 <= 0x500000u >> *(_DWORD *)(v16 + 72))) )
    {
      v40 = Context1;
      v41 = *((_DWORD *)Context1 + 7);
      if ( (v41 & 0x8000) != 0 )
        goto LABEL_116;
      *((_DWORD *)Context1 + 7) = v41 | 0x8000;
      _InterlockedIncrement((volatile signed __int32 *)(v40[2] + 2016LL));
    }
    else
    {
      UdfMarkVolumeOpenAndQueueCloseDpc(Context1, v8, v27, v10);
      LOBYTE(v10) = v117;
      v6 = v121;
      v26 = v113;
    }
    v40 = Context1;
LABEL_116:
    if ( (_BYTE)v10 && v26 )
    {
      *(_QWORD *)(v40[5] + 32LL) = *((_QWORD *)v15 + 1);
      v40 = Context1;
    }
    if ( !v9 && v6 == 4 )
    {
      v13 = FsRtlCheckOplock((POPLOCK)v15 + 11, (PIRP)Context2, v40, UdfOplockComplete, UdfPrePostIrp);
      v122 = v13;
      if ( v13 )
      {
        Context2 = 0;
        v28 = 0;
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
        {
          WPP_SF_(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            18,
            WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids);
        }
        v33 = 0;
        goto LABEL_346;
      }
      v42 = (FILE_LOCK *)*((_QWORD *)v15 + 63);
      if ( v42 )
      {
        if ( !FsRtlCheckLockForWriteAccess(v42, (PIRP)Context2) )
        {
          v13 = -1073741740;
          v122 = -1073741740;
          v33 = 0;
LABEL_345:
          v28 = (PIRP *)Context1;
LABEL_346:
          v31 = v116;
          goto LABEL_347;
        }
      }
    }
    ExAcquireFastMutex(*((PFAST_MUTEX *)v15 + 6));
    v43 = 1;
    v114 = 1;
    if ( v9 )
    {
      v60 = *(union _LARGE_INTEGER *)(v15 + 32);
      if ( FileOffset.QuadPart >= v60.QuadPart )
        goto LABEL_344;
      if ( v35 + FileOffset.QuadPart > v60.QuadPart )
      {
        v35 = v60.QuadPart - FileOffset.QuadPart;
        *(_QWORD *)Length = v60.QuadPart - FileOffset.QuadPart;
        v141 = v60.QuadPart - FileOffset.QuadPart;
      }
    }
    else
    {
      v44 = v118;
      v45 = Src;
      v33 = v118 || (__int64)Src > *((_QWORD *)v15 + 5);
      v148 = v33;
      v120 = v33;
      if ( v33 && v15[4] < 0 )
      {
        v33 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))UdfWaitForIoAtEof)(
                v15,
                (union _LARGE_INTEGER)FileOffset.QuadPart,
                (unsigned int)v35);
        v148 = v33;
        v120 = v33;
        v43 = 1;
        v44 = v118;
        v45 = Src;
      }
      if ( v44 )
      {
        v46 = *(union _LARGE_INTEGER *)(v15 + 32);
        FileOffset = v46;
        if ( 0x7FFFFFFFFFFFFFFFLL - v46.QuadPart < v35 )
        {
          v13 = -1073741811;
          v122 = -1073741811;
          goto LABEL_345;
        }
        v45 = (void *)(v46.QuadPart + v35);
        Src = (void *)(v46.QuadPart + v35);
        v43 = 1;
      }
      if ( !v33 )
      {
        v47 = Context1;
        v57 = FileObject;
        goto LABEL_179;
      }
      if ( !(_BYTE)v117 || v115 )
      {
        v47 = Context1;
      }
      else
      {
        v115 = 1;
        v137 = 1;
        v47 = Context1;
        *((_DWORD *)Context1 + 7) |= 4u;
      }
      v15[4] |= 0x80u;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
      {
        WPP_SF_q(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          19,
          WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids,
          *((_QWORD *)v15 + 4));
        v47 = Context1;
        v45 = Src;
      }
      v48 = *((_DWORD *)v15 + 53);
      v49 = v48 & 2;
      LOBYTE(v50) = v126;
      if ( (v48 & 2) != 0 )
      {
        v50 = (unsigned __int8)v126;
        if ( (__int64)v45 > (unsigned int)(*(_DWORD *)(v16 + 68) - *((_DWORD *)v15 + 56)) )
          v50 = 1;
        v126 = v50;
        v118 = v50;
      }
      if ( !*(_QWORD *)(v16 + 352) && (*(_DWORD *)(v16 + 48) & 0x20000000) == 0 && (v48 & 0x2000) == 0 )
      {
        if ( (v51 = (unsigned __int64)(v35 + FileOffset.QuadPart - 1) >> *(_DWORD *)(v16 + 72), !v49)
          && (unsigned int)(v51 + 1) > *((_DWORD *)v15 + 74)
          || (_BYTE)v50 )
        {
          v52 = v51 - *((_DWORD *)v15 + 74) + 2;
          LODWORD(Size) = v52;
          v53 = *((_DWORD *)v15 + 82);
          if ( v52 >= v53 )
          {
            LODWORD(Size) = v52 - v53;
            if ( v52 != v53 )
            {
              ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v16 + 1584));
              *(_QWORD *)(v16 + 1640) = KeGetCurrentThread();
              v59 = UdfAvailableFreeBlocks(v16, 0);
              if ( (unsigned int)Size > v59 )
              {
                *(_QWORD *)(v16 + 1640) = 0;
                ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v16 + 1584));
                v13 = -1073741697;
LABEL_343:
                v122 = v13;
                goto LABEL_344;
              }
              *(_DWORD *)(v16 + 672) += Size;
              *(_QWORD *)(v16 + 1640) = 0;
              ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v16 + 1584));
              *((_DWORD *)v15 + 82) += Size;
              if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) == 0 )
              {
                v47 = Context1;
              }
              else
              {
                WPP_SF_d(
                  *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                  20,
                  WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids);
                v47 = Context1;
              }
            }
          }
          else
          {
            LODWORD(Size) = 0;
          }
        }
      }
      v54 = v35 + FileOffset.QuadPart;
      *((_QWORD *)v15 + 4) = v35 + FileOffset.QuadPart;
      v55 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v16 + 68) - 1)
          & (v54 + (unsigned int)(*(_DWORD *)(v16 + 68) - 1));
      v56 = (struct _CC_FILE_SIZES *)(v15 + 24);
      if ( *((_QWORD *)v15 + 3) < v55 )
        v56->AllocationSize.QuadPart = v55;
      v116 = 1;
      v57 = FileObject;
      SectionObjectPointer = FileObject->SectionObjectPointer;
      if ( !SectionObjectPointer || !SectionObjectPointer->SharedCacheMap )
      {
LABEL_178:
        v43 = 1;
LABEL_179:
        LOBYTE(v61) = v117;
        if ( !(_BYTE)v117 )
        {
          ExReleaseFastMutex(*((PFAST_MUTEX *)v15 + 6));
          v43 = 0;
          v114 = 0;
          LOBYTE(v61) = 0;
          v47 = Context1;
          v57 = FileObject;
        }
        v133 = v35 + FileOffset.QuadPart;
        if ( v9 )
        {
LABEL_200:
          if ( !(_BYTE)v61 )
          {
            if ( !v57->PrivateCacheMap )
            {
              if ( !v43 )
              {
                ExAcquireFastMutex(*((PFAST_MUTEX *)v15 + 6));
                v57 = FileObject;
              }
              CcInitializeCacheMap(v57, (PCC_FILE_SIZES)v15 + 1, 0, &Callbacks, v15);
              if ( (*(_DWORD *)(v16 + 48) & 0x102) != 0 )
                CcSetDirtyPageThreshold(FileObject, 0x400u);
              ExReleaseFastMutex(*((PFAST_MUTEX *)v15 + 6));
              v114 = 0;
              CcSetReadAheadGranularity(FileObject, 0x10000u);
            }
            if ( (*((_BYTE *)Context1 + 57) & 2) != 0 )
            {
              if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
              {
                WPP_SF_(
                  *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                  21,
                  WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids);
              }
              v67 = Length[0];
              CcPrepareMdlWrite(
                FileObject,
                &FileOffset,
                Length[0],
                (PMDL *)Context2 + 1,
                (PIO_STATUS_BLOCK)Context2 + 3);
              v13 = Context2[12];
              v122 = v13;
              if ( v13 < 0 )
              {
                v28 = (PIRP *)Context1;
                v32 = v113;
                v33 = v148;
                v31 = v116;
              }
              else
              {
                v31 = 0;
                v116 = 0;
                v28 = (PIRP *)Context1;
                v32 = v113;
                v33 = v148;
              }
              goto LABEL_349;
            }
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
            {
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qq)(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                22,
                WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids,
                (union _LARGE_INTEGER)FileOffset.QuadPart,
                v35);
            }
            v68 = UdfMapUserBuffer((__int64)Context1, (__int64)Context2);
            if ( CcCopyWrite(FileObject, &FileOffset, v35, v115, v68) )
            {
              v31 = 0;
              v116 = 0;
              v28 = (PIRP *)Context1;
              v33 = v148;
LABEL_347:
              v32 = v113;
LABEL_348:
              v67 = Length[0];
LABEL_349:
              LOBYTE(v72) = v147;
LABEL_350:
              if ( Context2 )
              {
                *((_QWORD *)Context2 + 7) = v67;
                Context2[12] = v13;
                v32 = v113;
              }
              v101 = FileObject;
              if ( v13 < 0 )
              {
                v103 = v114;
LABEL_368:
                if ( v33 )
                {
                  if ( !v103 )
                  {
                    ExAcquireFastMutex(*((PFAST_MUTEX *)v15 + 6));
                    v103 = 1;
                    LOBYTE(v72) = v147;
                    v32 = v113;
                    v31 = v116;
                  }
                  if ( v31 )
                  {
                    v107 = *((_QWORD *)v15 + 5);
                    *((_QWORD *)v15 + 4) = v107;
                    SharedCacheMap = v101->SectionObjectPointer->SharedCacheMap;
                    v32 = v113;
                    if ( SharedCacheMap )
                      SharedCacheMap[1] = v107;
                  }
                  else if ( v13 >= 0 )
                  {
                    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
                    {
                      WPP_SF_qq(
                        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                        29,
                        WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids,
                        *((_QWORD *)v15 + 5),
                        *((_QWORD *)v15 + 4));
                      LOBYTE(v72) = v147;
                    }
                    *((_QWORD *)v15 + 5) = *((_QWORD *)v15 + 4);
                    v109 = v101->SectionObjectPointer;
                    if ( v109 && v109->SharedCacheMap )
                    {
                      UdfUpdateValidDataLength(v101, v15);
                      LOBYTE(v72) = v147;
                    }
                    v32 = v113;
                  }
                  if ( v13 != 259 )
                  {
                    UdfFinishIoAtEof(v15);
                    LOBYTE(v72) = v147;
                    v32 = v113;
                  }
                }
                if ( v103 )
                {
                  ExReleaseFastMutex(*((PFAST_MUTEX *)v15 + 6));
                  LOBYTE(v72) = v147;
                  v32 = v113;
                }
                if ( (_BYTE)v72 )
                {
                  ExReleaseResourceLite(*((PERESOURCE *)v15 + 2));
                  v32 = v113;
                }
                if ( v32 )
                  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*((_QWORD *)v15 + 17) + 80LL) + 8LL));
                if ( v13 == -1073741608 )
                  v13 = UdfFsdPostRequest(v28, Context2);
                else
                  UdfCompleteRequest(v28, Context2, (unsigned int)v13);
                if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
                {
                  WPP_SF_d(
                    *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                    30,
                    WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids);
                }
                return (unsigned int)v13;
              }
              if ( Context2 )
              {
                v102 = !v9;
                if ( v9 )
                  goto LABEL_360;
                FileObject->Flags |= 0x1000u;
                if ( v33 )
                  v101->Flags |= 0x2000u;
                v32 = v113;
                if ( v12 )
                {
                  v101->CurrentByteOffset.QuadPart = FileOffset.QuadPart + *((_QWORD *)Context2 + 7);
                  v31 = v116;
                }
              }
              v102 = !v9;
LABEL_360:
              v103 = v114;
              if ( v102 )
              {
                if ( !v114 )
                {
                  ExAcquireFastMutex(*((PFAST_MUTEX *)v15 + 6));
                  v103 = 1;
                }
                CurrentThread = KeGetCurrentThread();
                v105 = *((_QWORD *)v15 + 17);
                if ( CurrentThread != *(struct _KTHREAD **)(v105 + 64) )
                {
                  ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v105 + 80) + 216LL));
                  *(_QWORD *)(*((_QWORD *)v15 + 17) + 64LL) = CurrentThread;
                }
                ++*(_DWORD *)(*((_QWORD *)v15 + 17) + 72LL);
                *((_DWORD *)v15 + 53) |= 0x10000u;
                *((_DWORD *)v15 + 55) |= 0x20u;
                UdfUpdateScbTimeStamps(v105, v15, v138[0]);
                --*(_DWORD *)(*((_QWORD *)v15 + 17) + 72LL);
                v106 = *((_QWORD *)v15 + 17);
                if ( !*(_DWORD *)(v106 + 72) )
                {
                  *(_QWORD *)(v106 + 64) = 0;
                  ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*((_QWORD *)v15 + 17) + 80LL) + 216LL));
                  v33 = v148;
                }
                v31 = v116;
                v32 = v113;
                LOBYTE(v72) = v147;
              }
              goto LABEL_368;
            }
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
            {
              WPP_SF_(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                23,
                WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids);
            }
            v13 = -1073741608;
            goto LABEL_343;
          }
          v69 = *(_DWORD *)(v16 + 68) - 1;
          v126 = ~v69 & (v35 + v69);
          if ( !v9
            && ((v69 & FileOffset.LowPart) != 0
             || (~v69 & ((_DWORD)v35 + v69)) != v35 && v35 + FileOffset.QuadPart < *((_QWORD *)v15 + 5)) )
          {
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
            {
              WPP_SF_(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                24,
                WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids);
            }
            v13 = -1073741808;
            goto LABEL_343;
          }
          v132 = (unsigned int *)*((_QWORD *)v15 + 4);
          ExReleaseFastMutex(*((PFAST_MUTEX *)v15 + 6));
          v114 = 0;
          UdfLockUserBuffer((__int64)Context1, *(_DWORD *)(v135 + 8), v70, IoReadAccess);
          v71 = UdfMapUserBuffer((__int64)Context1, (__int64)Context2);
          Src = v71;
          v121 = -1;
          LODWORD(v135) = -1;
          v117 = 0;
          if ( v123 || (*(_WORD *)(*(_QWORD *)(v16 + 16) + 6LL) & 2) != 0 || (*(_DWORD *)(v16 + 48) & 0x20000000) != 0 )
            goto LABEL_262;
          if ( (*((_DWORD *)v15 + 53) & 0x2002) == 0
            && *((_DWORD *)v15 + 74) < (unsigned int)((~(unsigned __int64)(unsigned int)(*(_DWORD *)(v16 + 68) - 1)
                                                     & ((unsigned int)(*(_DWORD *)(v16 + 68) - 1) + v133)) >> *(_DWORD *)(v16 + 72)) )
          {
            UdfAcquireResource(Context1, *((_QWORD *)v15 + 2), 0, 0);
            LOBYTE(v72) = 1;
            v147 = 1;
            if ( !v115 )
            {
              v13 = -1073741608;
              v122 = -1073741608;
              v67 = Length[0];
              v28 = (PIRP *)Context1;
              v32 = v113;
              v33 = v148;
              v31 = v116;
              goto LABEL_350;
            }
            UdfGetBlocksNeeded(v16, (_DWORD)v15, (unsigned int)&v132, (unsigned int)&Size, 0, 0, 0, (__int64)&v118);
            if ( (_DWORD)Size )
            {
              UdfAllocateAtFileTail(Context1, v15, (unsigned int)Size, &v132);
              if ( v133 > *((_QWORD *)v15 + 38) )
                *((_QWORD *)v15 + 38) = v132;
            }
            v71 = Src;
          }
          if ( (*((_DWORD *)v15 + 53) & 0x2000) != 0 )
          {
            v13 = UdfProcessHolesInFileRegion(
                    (_DWORD)Context1,
                    (_DWORD)v15,
                    (unsigned __int64)FileOffset.QuadPart >> *(_DWORD *)(v16 + 72),
                    (~(unsigned __int64)(unsigned int)(*(_DWORD *)(v16 + 68) - 1)
                   & ((unsigned int)(*(_DWORD *)(v16 + 68) - 1)
                    + (unsigned __int64)(FileOffset.LowPart & (*(_DWORD *)(v16 + 68) - 1))
                    + v126)) >> *(_DWORD *)(v16 + 72),
                    0,
                    1,
                    (__int64)&v132,
                    (__int64)&v147);
            v122 = v13;
            if ( v13 < 0 )
            {
              if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
              {
                WPP_SF_d(
                  *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                  25,
                  WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids);
              }
              goto LABEL_344;
            }
            v73 = v147;
            if ( !v147 )
            {
              UdfAcquireResource(Context1, *((_QWORD *)v15 + 2), 0, 0);
              v73 = 1;
              v147 = 1;
            }
            if ( (__int64)v132 > *((_QWORD *)v15 + 38) )
              *((_QWORD *)v15 + 38) = v132;
            v71 = Src;
          }
          else
          {
LABEL_262:
            v73 = v147;
          }
          v74 = (unsigned int)v35;
          Size = (unsigned int)v35;
          *((_QWORD *)Context2 + 7) = (unsigned int)v35;
          if ( (*((_DWORD *)v15 + 53) & 2) != 0 )
          {
            if ( *(_QWORD *)(v16 + 352) || (*(_DWORD *)(v16 + 48) & 0x20000000) != 0 )
            {
              v126 = 0;
              LOBYTE(BytesToWrite) = 0;
              v28 = (PIRP *)Context1;
              v126 = UdfSeqCacheUnReserveFileRegion(Context1, v15, 0, *(unsigned int *)(v16 + 80), BytesToWrite);
              v75 = (_QWORD *)(v16 + 320);
              if ( (*(_DWORD *)(v16 + 48) & 0x20000000) == 0 )
                v75 = (_QWORD *)(v16 + 352);
              LOBYTE(v112) = (*((_DWORD *)v28 + 7) & 0x10) != 0;
              LOBYTE(Retrying) = 0;
              UdfSeqCacheReserveFileRegion(
                v28,
                *v75,
                (unsigned int)(*(_DWORD *)(v16 + 76) & *((_DWORD *)v15 + 46)),
                *(unsigned int *)(v16 + 80),
                &v126,
                Retrying,
                v112);
              if ( v126 )
              {
                ExAcquireFastMutexUnsafe((PFAST_MUTEX)(&v28[2][7].Tail.CompletionKey + 1));
                v28[2][7].Tail.Overlay.CurrentStackLocation = (struct _IO_STACK_LOCATION *)KeGetCurrentThread();
                v28[2][3].IoStatus.Status -= v126;
                v28[2][7].Tail.Overlay.CurrentStackLocation = 0;
                ExReleaseFastMutexUnsafe((PFAST_MUTEX)(&v28[2][7].Tail.CompletionKey + 1));
              }
              v71 = Src;
              v74 = Size;
            }
            else
            {
              v28 = (PIRP *)Context1;
            }
            if ( v15 != *(char **)(v16 + 344) )
            {
              v144 = 0;
              *((_QWORD *)&v142[0] + 1) = 0;
              UdfPrepareModifyIcbForScb(v28, v15, v142);
              v133 = *(_QWORD *)&v142[0];
              memmove((void *)(FileOffset.QuadPart + *(_QWORD *)&v142[0] + *((unsigned int *)v15 + 56)), Src, Size);
              v78 = *((_QWORD *)v15 + 4);
              v79 = v133;
              v80 = (unsigned int *)(v78 - *(_QWORD *)(v133 + 56));
              v133 = (__int64)v80;
              v144 = v80;
              *(_QWORD *)(v79 + 56) = v78;
              v81 = 266;
              v82 = *((_DWORD *)v15 + 8);
              v83 = *(_WORD *)v79 == 266;
              if ( *(_WORD *)v79 == 266 )
                *(_DWORD *)(v79 + 212) = v82;
              else
                *(_DWORD *)(v79 + 172) = v82;
              if ( v83 )
                *(_QWORD *)(v79 + 64) += v80;
              LOBYTE(v81) = 1;
              UdfFinishModifyIcb(v28, v142, v81, v15);
              UdfUnpinView(v28, v142);
              v31 = 0;
              v116 = 0;
              if ( v133 )
              {
                if ( (*((_DWORD *)v15 + 53) & 0x10) != 0 )
                {
                  v84 = *(_QWORD *)(*((_QWORD *)v15 + 17) + 16LL);
                  if ( v84 != *(_QWORD *)(v16 + 304) )
                  {
                    UdfPrepareModifyIcbForScb(v28, v84, v142);
                    *(_QWORD *)(*(_QWORD *)&v142[0] + 64LL) += v133;
                    LOBYTE(v85) = 1;
                    UdfFinishModifyIcb(v28, v142, v85, *(_QWORD *)(*((_QWORD *)v15 + 17) + 16LL));
                    v31 = 0;
                  }
                }
              }
              *((_DWORD *)v15 + 53) |= 0x2000000u;
              v33 = v148;
              goto LABEL_347;
            }
            memmove((void *)(FileOffset.QuadPart + *(_QWORD *)(v16 + 464) + *((unsigned int *)v15 + 56)), v71, v74);
            *(_QWORD *)(*(_QWORD *)(v16 + 464) + 56LL) = *((_QWORD *)v15 + 4);
            v76 = *(_QWORD *)(v16 + 464);
            v77 = *((_DWORD *)v15 + 8);
            if ( *(_WORD *)v76 == 266 )
              *(_DWORD *)(v76 + 212) = v77;
            else
              *(_DWORD *)(v76 + 172) = v77;
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
            {
              WPP_SF_(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                26,
                WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids);
            }
            v33 = v148;
            goto LABEL_346;
          }
          if ( (*(_BYTE *)(*(_QWORD *)(v16 + 16) + 6LL) & 2) != 0 )
            goto LABEL_285;
          if ( v15 == *(char **)(v16 + 320) && (*(_DWORD *)(v16 + 48) & 0x8000000) != 0 )
          {
            CcCopyWrite(*(PFILE_OBJECT *)(*(_QWORD *)(v16 + 328) + 504LL), &FileOffset, v35, 1u, v71);
            v73 = v147;
            v74 = Size;
            v71 = Src;
          }
          *(_DWORD *)(*((_QWORD *)Context1 + 5) + 56LL) = v35;
          if ( (*(_DWORD *)(v16 + 48) & 0x20000000) != 0 )
          {
LABEL_285:
            v88 = *(_DWORD *)(v16 + 72);
            v89 = (unsigned __int64)FileOffset.QuadPart >> v88;
            v90 = (~(unsigned __int64)(unsigned int)(*(_DWORD *)(v16 + 68) - 1)
                 & ((unsigned int)(*(_DWORD *)(v16 + 68) - 1) + v74 + (FileOffset.LowPart & (*(_DWORD *)(v16 + 68) - 1)))) >> v88;
            if ( v73 )
            {
              ExReleaseResourceLite(*((PERESOURCE *)v15 + 2));
              v147 = 0;
            }
            v91 = v90;
            v28 = (PIRP *)Context1;
            v13 = UdfSeqCacheWriteBlocksForFile(
                    (_DWORD)Context1,
                    (_DWORD)v15,
                    v89,
                    v91,
                    (__int64)&v132,
                    (__int64)Src,
                    0);
            v122 = v13;
            v31 = v116;
            if ( v13 >= 0 )
              v31 = 0;
            v116 = v31;
            v87 = v121;
          }
          else
          {
            v28 = (PIRP *)Context1;
            v13 = UdfNonCachedIo((int)Context1, v71, (__int64)&v135, (__int64)&v117);
            v122 = v13;
            v87 = v135;
            v121 = v135;
            v31 = v116;
          }
          if ( v13 == 259 )
          {
            Context2 = 0;
            v32 = 0;
            v113 = 0;
            LOBYTE(v72) = 0;
            v147 = 0;
          }
          else
          {
            if ( v13 < 0 )
            {
              *((_QWORD *)Context2 + 7) = 0;
              if ( (unsigned int)(v13 + 1073741662) <= 1
                || (unsigned int)(v13 + 1073741806) <= 2
                || v13 == -2147483626
                || v13 == -1073741643 )
              {
                IoSetHardErrorOrVerifyDevice(v28[1], *(PDEVICE_OBJECT *)(*(_QWORD *)(v16 + 8) + 16LL));
                UdfRaiseStatusEx(v28, (unsigned int)v13, 0);
              }
              v13 = FsRtlNormalizeNtstatus(v13, -1073741591);
              v122 = v13;
              v87 = v121;
              v31 = v116;
            }
            v32 = v113;
            v72 = v147;
          }
          if ( Context2 && !v123 )
          {
            if ( (*(_WORD *)(*(_QWORD *)(v16 + 16) + 6LL) & 2) == 0
              && (*(_DWORD *)(v16 + 48) & 0x20000000) == 0
              && v13 >= 0 )
            {
              if ( !(_BYTE)v72 )
              {
                *((_DWORD *)v28 + 7) |= 4u;
                UdfAcquireResource(v28, *((_QWORD *)v15 + 2), 0, 0);
                LOBYTE(v72) = 1;
                v147 = 1;
                v87 = v121;
              }
              if ( v87 == -1 && *((_DWORD *)v15 + 74) <= *((_DWORD *)v15 + 75) )
              {
                v92 = (unsigned int *)*((_QWORD *)v15 + 38);
                v93 = v132;
                if ( v92 == v132 || v133 < (__int64)v92 )
                {
LABEL_340:
                  v31 = 0;
                  v116 = 0;
                  v67 = Length[0];
                  v32 = v113;
                  v33 = v148;
                  goto LABEL_350;
                }
              }
              else
              {
                v93 = v132;
              }
              if ( v87 != -1 )
              {
                v94 = *(_QWORD *)&WPP_GLOBAL_Control;
                if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
                {
                  WPP_SF_qDDDD(
                    *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                    v72,
                    v86,
                    v15,
                    v87,
                    v117,
                    *((_DWORD *)v15 + 74),
                    *((_DWORD *)v15 + 75));
                  v87 = v121;
                }
                UdfMarkRegionRecorded(v94, v15, v87, v117);
                v93 = v132;
                LOBYTE(v72) = v147;
                v87 = v121;
              }
              v95 = *((_DWORD *)v15 + 75);
              v96 = *((_DWORD *)v15 + 74);
              if ( v96 <= v95 )
                goto LABEL_325;
              if ( v95 < v87 )
              {
                if ( v95 )
                  v87 = v95 - 1;
                else
                  v87 = 0;
                v121 = v87;
                LODWORD(v135) = v87;
              }
              if ( v96 <= v117 + 1 )
              {
LABEL_325:
                v97 = v117;
              }
              else
              {
                v97 = v96 - 1;
                v117 = v97;
              }
              v146 = (unsigned int *)*((_QWORD *)v15 + 38);
              if ( v146 != v93 )
              {
                v98 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v16 + 68) - 1);
                if ( (unsigned int)((v98 & ((unsigned __int64)v93 + (unsigned int)(*(_DWORD *)(v16 + 68) - 1))) >> *(_DWORD *)(v16 + 72)) == (unsigned int)((v98 & ((unsigned __int64)v146 + (unsigned int)(*(_DWORD *)(v16 + 68) - 1))) >> *(_DWORD *)(v16 + 72)) )
                {
                  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
                  {
                    WPP_SF_dd(
                      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                      28,
                      WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids,
                      v87,
                      v117);
                    v93 = v132;
                    v87 = v121;
                  }
                  v99 = ((unsigned __int64)v93 - 1) >> *(_DWORD *)(v16 + 72);
                  v100 = v99;
                  if ( v117 > (unsigned int)v99 )
                    v100 = v117;
                  v97 = v100;
                  v117 = v100;
                  if ( v87 < (unsigned int)v99 )
                    LODWORD(v99) = v87;
                  v87 = v99;
                  LODWORD(v135) = v99;
                }
                else
                {
                  v97 = v117;
                }
                *((_QWORD *)v15 + 38) = v93;
                LOBYTE(v72) = v147;
              }
              if ( v87 != -1 )
              {
                UdfUpdateAdsFromScb(v28, v15, v87, v97);
                *((_DWORD *)v15 + 53) |= 0x2000000u;
                LOBYTE(v72) = v147;
              }
              goto LABEL_340;
            }
            v31 = v116;
            v32 = v113;
          }
          v67 = Length[0];
          v33 = v148;
          goto LABEL_350;
        }
        v62 = *(_DWORD *)(v16 + 72);
        v63 = (unsigned __int64)FileOffset.QuadPart >> v62;
        v139 = (unsigned __int64)FileOffset.QuadPart >> v62;
        v64 = (~(unsigned __int64)(unsigned int)(*(_DWORD *)(v16 + 68) - 1)
             & ((unsigned int)(*(_DWORD *)(v16 + 68) - 1)
              + (unsigned __int64)(FileOffset.LowPart & (*(_DWORD *)(v16 + 68) - 1))
              + (unsigned int)v35)) >> v62;
        v140 = v64;
        v65 = *((unsigned int *)v15 + 53);
        if ( (v65 & 0x2000) != 0 )
        {
          v66 = UdfProcessHolesInFileRegion((_DWORD)v47, (_DWORD)v15, v63, v64, 0, 0, 0, 0);
        }
        else
        {
          if ( !*(_QWORD *)(v16 + 352) && (*(_DWORD *)(v16 + 48) & 0x20000000) == 0 )
          {
LABEL_191:
            if ( v13 >= 0 )
            {
              if ( (_BYTE)v126
                && (Src = (void *)*((_QWORD *)v15 + 5),
                    LOBYTE(v64) = Src != 0,
                    UdfDeEmbedFileData(v65, v15, FileObject, v64),
                    v61 = v117,
                    (_BYTE)v117)
                && Src
                && FileOffset.QuadPart < 4096 )
              {
                LOBYTE(v61) = 0;
                v117 = v61;
                v136 = 0;
                v43 = v114;
                if ( v114 )
                {
                  ExReleaseFastMutex(*((PFAST_MUTEX *)v15 + 6));
                  v43 = 0;
                  v114 = 0;
                  LOBYTE(v61) = v117;
                }
              }
              else
              {
                v43 = v114;
              }
              v57 = FileObject;
              goto LABEL_200;
            }
LABEL_344:
            v33 = v148;
            goto LABEL_345;
          }
          if ( (v65 & 2) != 0 && !(_BYTE)v126 )
          {
            LODWORD(v63) = 0;
            v139 = 0;
            v64 = *(unsigned int *)(v16 + 80);
            v140 = *(_DWORD *)(v16 + 80);
          }
          LOBYTE(v112) = (v47[7] & 0x10) != 0;
          LOBYTE(Retrying) = 1;
          v66 = UdfSeqCacheReserveFileRegion(v47, v15, (unsigned int)v63, v64, 0, Retrying, v112);
        }
        v122 = v66;
        LOBYTE(v61) = v117;
        v13 = v66;
        goto LABEL_191;
      }
      CcSetFileSizes(FileObject, v56);
    }
    v47 = Context1;
    v57 = FileObject;
    goto LABEL_178;
  }
  v29 = (_BYTE)v8 && (*((_DWORD *)Context1 + 7) & 0x40) == 0;
  if ( CcCanIWrite(v25, v24, v29, (*((_DWORD *)Context1 + 7) & 0x400) != 0) )
  {
    v24 = *(_QWORD *)Length;
    v10 = v117;
    v6 = v121;
    v25 = FileObject;
    v26 = 0;
    goto LABEL_75;
  }
  v30 = (*((_DWORD *)Context1 + 7) & 0x400) != 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
  {
    WPP_SF_q(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      15,
      WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids,
      Context2);
  }
  UdfPrePostIrp(Context1, (PIRP)Context2);
  *((_DWORD *)Context1 + 7) |= 0x400u;
  CcDeferWrite(FileObject, UdfAddToWorkque, v28, Context2, Length[0], v30);
  return 259;
}

```

## disassembly

```asm
0x1400010f0  mov     rax, rsp
0x1400010f3  mov     [rax+10h], rdx
0x1400010f7  mov     [rax+8], rcx
0x1400010fb  push    rbx
0x1400010fc  push    rsi
0x1400010fd  push    rdi
0x1400010fe  push    r12
0x140001100  push    r13
0x140001102  push    r14
0x140001104  push    r15
0x140001106  sub     rsp, 190h
0x14000110d  mov     rsi, rdx
0x140001110  mov     r13, rcx
0x140001113  mov     [rsp+1C8h+Context1], rcx
0x140001118  xor     ebx, ebx
0x14000111a  mov     [rax-100h], rbx
0x140001121  mov     [rax-0E8h], rbx
0x140001128  mov     [rax+18h], bl
0x14000112b  mov     byte ptr [rsp+1C8h+var_138], bl
0x140001132  xor     eax, eax
0x140001134  mov     [rsp+1C8h+var_94], eax
0x14000113b  xor     edx, edx; Val
0x14000113d  mov     r8d, 54h ; 'T'; Size
0x140001143  lea     rcx, [rsp+1C8h+var_98]; void *
0x14000114b  call    memset
0x140001150  mov     qword ptr [rsp+1C8h+FileOffset], rbx
0x140001158  mov     [rsp+1C8h+var_110], rbx
0x140001160  mov     dword ptr [rsp+1C8h+Size], ebx
0x140001167  xorps   xmm0, xmm0
0x14000116a  xor     eax, eax
0x14000116c  movups  [rsp+1C8h+var_C8], xmm0
0x140001174  movups  [rsp+1C8h+var_B8], xmm0
0x14000117c  mov     [rsp+1C8h+var_A8], rax
0x140001184  mov     [rsi+38h], rbx
0x140001188  mov     r11, [rsi+0B8h]
0x14000118f  mov     [rsp+1C8h+var_F8], r11
0x140001197  mov     rcx, [r11+30h]
0x14000119b  mov     [rsp+1C8h+FileObject], rcx
0x1400011a3  lea     r8, [rsp+1C8h+var_E8]
0x1400011ab  lea     rdx, [rsp+1C8h+LazyWriteContext]
0x1400011b3  call    UdfDecodeFileObject
0x1400011b8  mov     r10d, eax
0x1400011bb  mov     [rsp+1C8h+var_154], eax
0x1400011bf  mov     ebx, [r13+1Ch]
0x1400011c3  and     ebx, 4
0x1400011c6  setnz   dl
0x1400011c9  mov     [rsp+1C8h+var_175], dl
0x1400011cd  mov     r9d, [rsi+10h]
0x1400011d1  movzx   r14d, r9b
0x1400011d5  shr     r14b, 1
0x1400011d8  and     r14b, 1
0x1400011dc  mov     [rsp+1C8h+var_134], r14b
0x1400011e4  and     r9b, 1
0x1400011e8  mov     dword ptr [rsp+1C8h+var_16C], r9d
0x1400011ed  movzx   r15d, byte ptr [rcx+50h]
0x1400011f2  shr     r15b, 1
0x1400011f5  and     r15b, 1
0x1400011f9  mov     [rsp+1C8h+var_120], r15b
0x140001201  cmp     eax, 4
0x140001204  jz      short loc_14000123A
0x140001206  cmp     eax, 1
0x140001209  jnz     short loc_140001215
0x14000120b  test    r9b, r9b
0x14000120e  jz      short loc_140001215
0x140001210  test    r14b, r14b
0x140001213  jnz     short loc_14000123A
0x140001215  cmp     r10d, 2
0x140001219  jz      short loc_14000123A
0x14000121b  mov     r13d, 0C0000010h
0x140001221  mov     r8d, r13d
0x140001224  mov     rdx, rsi
0x140001227  mov     rcx, [rsp+1C8h+Context1]
0x14000122c  call    UdfCompleteRequest
0x140001231  mov     eax, r13d
0x140001234  jmp     loc_1400030C3
0x14000123a  mov     rdi, [rsp+1C8h+LazyWriteContext]
0x140001242  mov     rax, [rdi+88h]
0x140001249  mov     r12, [rax+8]
0x14000124d  mov     eax, [rdi+0D4h]
0x140001253  test    al, al
0x140001255  js      short loc_140001286
0x140001257  cmp     rdi, [r12+128h]
0x14000125f  jz      short loc_140001286
0x140001261  cmp     rdi, [r12+118h]
0x140001269  jz      short loc_140001286
0x14000126b  cmp     rdi, [r12+140h]
0x140001273  jz      short loc_140001286
0x140001275  cmp     rdi, [r12+148h]
0x14000127d  jz      short loc_140001286
0x14000127f  mov     [rsp+1C8h+var_14C], 0
0x140001284  jmp     short loc_14000128B
0x140001286  mov     [rsp+1C8h+var_14C], 1
0x14000128b  lea     r8, WPP_GLOBAL_Control
0x140001292  mov     rcx, cs:WPP_GLOBAL_Control
0x140001299  cmp     rcx, r8
0x14000129c  jz      short loc_14000130E
0x14000129e  test    dword ptr [rcx+2Ch], 4000000h
0x1400012a5  jz      short loc_14000130E
0x1400012a7  mov     r8d, 59h ; 'Y'
0x1400012ad  mov     edx, r8d
0x1400012b0  mov     r11d, 4Eh ; 'N'
0x1400012b6  test    ebx, ebx
0x1400012b8  cmovz   edx, r11d
0x1400012bc  mov     eax, r8d
0x1400012bf  test    r9b, r9b
0x1400012c2  cmovz   eax, r11d
0x1400012c6  test    r14b, r14b
0x1400012c9  cmovz   r8d, r11d
0x1400012cd  mov     [rsp+1C8h+var_188], dl
0x1400012d1  mov     byte ptr [rsp+1C8h+var_190], al
0x1400012d5  mov     byte ptr [rsp+1C8h+var_198], r8b
0x1400012da  mov     dword ptr [rsp+1C8h+Retrying], r10d
0x1400012df  mov     qword ptr [rsp+1C8h+BytesToWrite], rdi
0x1400012e4  mov     r9, rsi
0x1400012e7  mov     rcx, [rcx+18h]
0x1400012eb  call    WPP_SF_qqdccc
0x1400012f0  mov     r9d, dword ptr [rsp+1C8h+var_16C]
0x1400012f5  mov     r11, [rsp+1C8h+var_F8]
0x1400012fd  movzx   edx, [rsp+1C8h+var_175]
0x140001302  mov     r10d, [rsp+1C8h+var_154]
0x140001307  lea     r8, WPP_GLOBAL_Control
0x14000130e  mov     eax, [r12+30h]
0x140001313  bt      eax, 1Ch
0x140001317  jnb     short loc_140001334
0x140001319  mov     r8d, 0C0000189h
0x14000131f  mov     rdx, rsi
0x140001322  mov     rcx, r13
0x140001325  call    UdfCompleteRequest
0x14000132a  mov     eax, 0C0000189h
0x14000132f  jmp     loc_1400030C3
0x140001334  test    al, 10h
0x140001336  jz      short loc_1400013B2
0x140001338  cmp     r10d, 2
0x14000133c  jz      short loc_1400013B2
0x14000133e  mov     ecx, eax
0x140001340  and     ecx, 4080h
0x140001346  cmp     ecx, 80h
0x14000134c  jnz     short loc_140001355
0x14000134e  mov     ebx, 0C00000A2h
0x140001353  jmp     short loc_140001370
0x140001355  test    r14b, r14b
0x140001358  jz      short loc_140001361
0x14000135a  mov     ebx, 0C0000098h
0x14000135f  jmp     short loc_140001370
0x140001361  test    al, 20h
0x140001363  mov     ebx, 0C0000022h
0x140001368  mov     eax, 0C0000806h
0x14000136d  cmovnz  ebx, eax
0x140001370  mov     rcx, cs:WPP_GLOBAL_Control
0x140001377  cmp     rcx, r8
0x14000137a  jz      short loc_14000139D
0x14000137c  test    dword ptr [rcx+2Ch], 4000000h
0x140001383  jz      short loc_14000139D
0x140001385  mov     edx, 0Dh
0x14000138a  mov     r9d, ebx
0x14000138d  lea     r8, WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids
0x140001394  mov     rcx, [rcx+18h]
0x140001398  call    WPP_SF_d
0x14000139d  mov     r8d, ebx
0x1400013a0  mov     rdx, rsi
0x1400013a3  mov     rcx, r13
0x1400013a6  call    UdfCompleteRequest
0x1400013ab  mov     eax, ebx
0x1400013ad  jmp     loc_1400030C3
0x1400013b2  test    ebx, ebx
0x1400013b4  jnz     short loc_1400013C2
0x1400013b6  test    r14b, r14b
0x1400013b9  jz      short loc_1400013C6
0x1400013bb  or      dword ptr [r13+1Ch], 4
0x1400013c0  mov     dl, 1
0x1400013c2  mov     [rsp+1C8h+var_175], dl
0x1400013c6  cmp     r10d, 2
0x1400013ca  jnz     short loc_14000142B
0x1400013cc  mov     rax, [r12+18h]
0x1400013d1  cmp     dword ptr [rax+48h], 7
0x1400013d5  jnz     short loc_1400013FD
0x1400013d7  mov     eax, [r12+30h]
0x1400013dc  test    al, 1
0x1400013de  jnz     short loc_1400013FD
0x1400013e0  test    byte ptr [r11+2], 10h
0x1400013e5  jnz     short loc_1400013FD
0x1400013e7  mov     rcx, [rsp+1C8h+var_E8]
0x1400013ef  mov     eax, [rcx+4]
0x1400013f2  test    al, 8
0x1400013f4  jnz     short loc_140001405
0x1400013f6  mov     ebx, 0C0000022h
0x1400013fb  jmp     short loc_14000139D
0x1400013fd  mov     rcx, [rsp+1C8h+var_E8]
0x140001405  mov     eax, [r12+54h]
0x14000140a  test    al, 10h
0x14000140c  jz      short loc_140001412
0x14000140e  or      dword ptr [rcx+4], 8
0x140001412  mov     r9b, 1
0x140001415  mov     dword ptr [rsp+1C8h+var_16C], r9d
0x14000141a  test    dword ptr [rcx+4], 1000h
0x140001421  jz      short loc_14000142B
0x140001423  or      dword ptr [r13+1Ch], 2000h
0x14000142b  mov     rbx, [r11+18h]
0x14000142f  mov     qword ptr [rsp+1C8h+FileOffset], rbx
0x140001437  mov     ecx, [r11+8]
0x14000143b  mov     qword ptr [rsp+1C8h+Length], rcx
0x140001443  mov     [rsp+1C8h+var_D0], rcx
0x14000144b  test    rbx, rbx
0x14000144e  jns     short loc_140001457
0x140001450  mov     byte ptr [rsp+1C8h+var_16C+4], 1
0x140001455  jmp     short loc_1400014AE
0x140001457  mov     byte ptr [rsp+1C8h+var_16C+4], 0
0x14000145c  mov     r8, 7FFFFFFFFFFFFFFFh
0x140001466  sub     r8, rbx
0x140001469  cmp     r8, rcx
0x14000146c  jge     short loc_1400014A7
0x14000146e  xor     edx, edx
0x140001470  mov     rcx, r13; Entry
0x140001473  call    UdfCleanupIrpContext
0x140001478  mov     eax, [rsi+10h]
0x14000147b  test    al, 40h
0x14000147d  jz      short loc_140001487
0x14000147f  mov     qword ptr [rsi+38h], 0
0x140001487  mov     r13d, 0C000000Dh
0x14000148d  mov     [rsi+30h], r13d
0x140001491  mov     dl, 1; PriorityBoost
0x140001493  mov     rcx, rsi; Irp
0x140001496  call    cs:__imp_IofCompleteRequest
0x14000149d  nop     dword ptr [rax+rax+00h]
0x1400014a2  jmp     loc_140001231
0x1400014a7  lea     r8, WPP_GLOBAL_Control
0x1400014ae  mov     r11, cs:WPP_GLOBAL_Control
0x1400014b5  cmp     r11, r8
0x1400014b8  jz      short loc_1400014F8
0x1400014ba  test    dword ptr [r11+2Ch], 4000000h
0x1400014c2  jz      short loc_1400014F8
0x1400014c4  mov     edx, 0Eh
0x1400014c9  mov     qword ptr [rsp+1C8h+BytesToWrite], rcx
0x1400014ce  mov     r9, rbx
0x1400014d1  lea     r8, WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids
0x1400014d8  mov     rcx, [r11+18h]
0x1400014dc  call    WPP_SF_qq
0x1400014e1  mov     rcx, qword ptr [rsp+1C8h+Length]
0x1400014e9  mov     r9d, dword ptr [rsp+1C8h+var_16C]
0x1400014ee  movzx   edx, [rsp+1C8h+var_175]
0x1400014f3  mov     r10d, [rsp+1C8h+var_154]
0x1400014f8  test    ecx, ecx
0x1400014fa  jnz     short loc_140001511
0x1400014fc  xor     r8d, r8d
0x1400014ff  mov     rdx, rsi
0x140001502  mov     rcx, r13
0x140001505  call    UdfCompleteRequest
0x14000150a  xor     eax, eax
0x14000150c  jmp     loc_1400030C3
0x140001511  mov     rax, [rsp+1C8h+FileObject]
0x140001519  mov     [rsp+1C8h+var_E0], rax
0x140001521  xor     r13d, r13d
0x140001524  mov     [rsp+1C8h+var_150], r13d
0x140001529  xor     r11b, r11b
0x14000152c  mov     [rsp+1C8h+var_178], r11b
0x140001531  xor     r8b, r8b
0x140001534  mov     [rsp+1C8h+var_177], r8b
0x140001539  mov     [rsp+1C8h+var_176], r8b
0x14000153e  mov     [rsp+1C8h+arg_18], r8b
0x140001546  mov     [rsp+1C8h+var_158], r8b
0x14000154b  mov     [rsp+1C8h+var_174], r8d
0x140001550  mov     [rsp+1C8h+var_170], r8b
0x140001555  lea     r8, [rcx+rbx]
0x140001559  mov     [rsp+1C8h+Src], r8
0x140001561  mov     [r12+854h], r13d
0x140001569  mov     rbx, [rsp+1C8h+Context1]
0x14000156e  test    r9b, r9b
0x140001571  jnz     loc_14000165B
0x140001577  mov     r8d, [rbx+1Ch]
0x14000157b  mov     r9d, r8d
0x14000157e  shr     r9d, 0Ah
0x140001582  and     r9b, 1; Retrying
0x140001586  test    dl, dl
0x140001588  jz      short loc_140001595
0x14000158a  test    r8b, 40h
0x14000158e  jnz     short loc_140001595
0x140001590  mov     r8b, 1
0x140001593  jmp     short loc_140001598
0x140001595  xor     r8d, r8d; Wait
0x140001598  mov     edx, ecx; BytesToWrite
0x14000159a  mov     rcx, rax; FileObject
0x14000159d  call    cs:__imp_CcCanIWrite
0x1400015a4  nop     dword ptr [rax+rax+00h]
0x1400015a9  test    al, al
0x1400015ab  jnz     loc_14000163E
0x1400015b1  mov     edi, [rbx+1Ch]
0x1400015b4  shr     edi, 0Ah
0x1400015b7  and     dil, 1
0x1400015bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400015c2  lea     rax, WPP_GLOBAL_Control
0x1400015c9  cmp     rcx, rax
0x1400015cc  jz      short loc_1400015EF
0x1400015ce  test    dword ptr [rcx+2Ch], 4000000h
0x1400015d5  jz      short loc_1400015EF
0x1400015d7  mov     edx, 0Fh
0x1400015dc  mov     r9, rsi
0x1400015df  lea     r8, WPP_d6a9f59b0e1a34a335a7c145baea7fea_Traceguids
0x1400015e6  mov     rcx, [rcx+18h]
0x1400015ea  call    WPP_SF_q
0x1400015ef  mov     rdx, rsi; Irp
  ... truncated ...
```
