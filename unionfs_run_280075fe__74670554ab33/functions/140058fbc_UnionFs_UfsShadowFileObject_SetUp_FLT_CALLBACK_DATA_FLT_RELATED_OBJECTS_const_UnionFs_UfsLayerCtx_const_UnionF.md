# UnionFs::UfsShadowFileObject::SetUp(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsLayerCtx const &,UnionFs::UfsPathCachePayload &,UnionFs::ShareAccessCaller,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x140058fbc`
- end: `0x140059e77`
- name: `?SetUp@UfsShadowFileObject@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsLayerCtx@2@AEAVUfsPathCachePayload@2@W4ShareAccessCaller@2@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `3771`
- prototype: `__int64 __usercall@<rax>(struct _FILE_OBJECT *@<rcx>, struct _FLT_CALLBACK_DATA *@<rdx>, UnionFs::UfsPathCachePayload *, struct UnionFs::StackEventTracer *, __int64, struct UnionFs::Utils::CheckOplockHParams *)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140013bb0`
- `0x1400156a8`

## callees

- `0x140001008`
- `0x14000110c`
- `0x14000f7fc`
- `0x140010148`
- `0x140024bd8`
- `0x140025b80`
- `0x1400276c4`
- `0x140028450`
- `0x14002a210`
- `0x1400414c8`
- `0x1400420e8`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140057894`
- `0x1400578fc`
- `0x140058fbc`
- `0x14005a228`
- `0x1400696ac`
- `0x1400699dc`
- `0x140069cf8`
- `0x140069eec`
- `0x140079a6c`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!IoSetShadowFileInformation` at `0x140059b70`
- `ntoskrnl!IoSetShadowFileInformation` at `0x140059b70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059278`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059545`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400597e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059d5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059278`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059545`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400597e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059d5c`
- `ntoskrnl!ZwClose` at `0x140059196`
- `ntoskrnl!ZwClose` at `0x1400592b1`
- `ntoskrnl!ZwClose` at `0x14005957e`
- `ntoskrnl!ZwClose` at `0x14005981c`
- `ntoskrnl!ZwClose` at `0x140059d95`
- `ntoskrnl!ZwClose` at `0x140059e39`
- `ntoskrnl!ZwClose` at `0x140059196`
- `ntoskrnl!ZwClose` at `0x1400592b1`
- `ntoskrnl!ZwClose` at `0x14005957e`
- `ntoskrnl!ZwClose` at `0x14005981c`
- `ntoskrnl!ZwClose` at `0x140059d95`
- `ntoskrnl!ZwClose` at `0x140059e39`
- `ntoskrnl!ObfReferenceObject` at `0x1400591a8`
- `ntoskrnl!ObfReferenceObject` at `0x1400591a8`
- `ntoskrnl!ObfDereferenceObject` at `0x14005929b`
- `ntoskrnl!ObfDereferenceObject` at `0x140059568`
- `ntoskrnl!ObfDereferenceObject` at `0x140059806`
- `ntoskrnl!ObfDereferenceObject` at `0x140059d7f`
- `ntoskrnl!ObfDereferenceObject` at `0x140059e23`
- `ntoskrnl!ObfDereferenceObject` at `0x14005929b`
- `ntoskrnl!ObfDereferenceObject` at `0x140059568`
- `ntoskrnl!ObfDereferenceObject` at `0x140059806`
- `ntoskrnl!ObfDereferenceObject` at `0x140059d7f`
- `ntoskrnl!ObfDereferenceObject` at `0x140059e23`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059392`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005951b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059601`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400597b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059d32`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059df4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059392`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005951b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059601`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400597b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059d32`
- `ntoskrnl!ExReleaseResourceLite` at `0x140059df4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005939e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059527`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005960d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400597c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059d3e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059e00`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005939e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059527`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005960d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400597c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059d3e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140059e00`
- `FLTMGR!FltOplockFsctrl` at `0x140059a64`
- `FLTMGR!FltOplockFsctrl` at `0x140059b03`
- `FLTMGR!FltOplockFsctrl` at `0x140059a64`
- `FLTMGR!FltOplockFsctrl` at `0x140059b03`
- `FLTMGR!FltObjectReference` at `0x140059c51`
- `FLTMGR!FltObjectReference` at `0x140059c51`
- `FLTMGR!FltReferenceContext` at `0x14005903b`
- `FLTMGR!FltReferenceContext` at `0x14005903b`
- `FLTMGR!FltReleaseContext` at `0x1400590a8`
- `FLTMGR!FltReleaseContext` at `0x140059134`
- `FLTMGR!FltReleaseContext` at `0x1400592c5`
- `FLTMGR!FltReleaseContext` at `0x140059413`
- `FLTMGR!FltReleaseContext` at `0x1400594fc`
- `FLTMGR!FltReleaseContext` at `0x140059596`
- `FLTMGR!FltReleaseContext` at `0x1400595de`
- `FLTMGR!FltReleaseContext` at `0x14005979a`
- `FLTMGR!FltReleaseContext` at `0x140059830`
- `FLTMGR!FltReleaseContext` at `0x140059d13`
- `FLTMGR!FltReleaseContext` at `0x140059da9`
- `FLTMGR!FltReleaseContext` at `0x140059dd5`
- `FLTMGR!FltReleaseContext` at `0x140059e4d`
- `FLTMGR!FltReleaseContext` at `0x1400590a8`
- `FLTMGR!FltReleaseContext` at `0x140059134`
- `FLTMGR!FltReleaseContext` at `0x1400592c5`
- `FLTMGR!FltReleaseContext` at `0x140059413`
- `FLTMGR!FltReleaseContext` at `0x1400594fc`
- `FLTMGR!FltReleaseContext` at `0x140059596`
- `FLTMGR!FltReleaseContext` at `0x1400595de`
- `FLTMGR!FltReleaseContext` at `0x14005979a`
- `FLTMGR!FltReleaseContext` at `0x140059830`
- `FLTMGR!FltReleaseContext` at `0x140059d13`
- `FLTMGR!FltReleaseContext` at `0x140059da9`
- `FLTMGR!FltReleaseContext` at `0x140059dd5`
- `FLTMGR!FltReleaseContext` at `0x140059e4d`

## string_xrefs

- `0x1400598b1`: `ORIGIN: Filter oplock request on directory`
- `0x1400598ee`: `ORIGIN: Filter oplock request with existing opens`
- `0x140059104`: `PUSH: Checking caller access from cache`
- `0x140059000`: `ORIGIN: FILE_DIRECTORY_FILE and FILE_NON_DIRECTORY_FILE both set`
- `0x140059070`: `ORIGIN: Attempt to open a file as a directory.`
- `0x1400590cd`: `ORIGIN: Attempt to open a directory as a file.`
- `0x14005986b`: `PUSH: CheckShareAccess`
- `0x140059a77`: `API: Setting up atomic create-with-oplock`
- `0x140059660`: `PUSH: Checking share access of SFO`
- `0x140059671`: `UnionFs::UfsShadowFileObject::CheckShareAccess`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsShadowFileObject::SetUp(
        struct _FILE_OBJECT *a1,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_CALLBACK_DATA *a3,
        __int64 a4,
        PFLT_CONTEXT *a5,
        struct UnionFs::StackEventTracer *a6,
        __int64 *a7,
        struct UnionFs::Utils::CheckOplockHParams *a8)
{
  unsigned int v10; // esi
  PFLT_CONTEXT *v12; // rdi
  _QWORD *v13; // rbx
  ULONG Options; // edx
  _QWORD *v15; // rcx
  const char *v16; // rax
  __int64 v17; // r8
  unsigned int v18; // edi
  struct UnionFs::UfsFsContext *v19; // r15
  int DuplicateBackingFileHandle; // r14d
  volatile signed __int32 *v21; // rcx
  utl::_RefCountBase **v22; // r12
  utl::_RefCountBase *v23; // r14
  utl::_RefCountBase *v24; // rax
  __int64 v25; // rcx
  int ShadowFsContext2; // r12d
  UnionFs::UfsFsContext2 *v27; // rdi
  struct _FLT_RELATED_OBJECTS *v28; // rax
  int v29; // r8d
  int v30; // r9d
  char *v31; // rdx
  PVOID *v32; // rax
  PFLT_CONTEXT v33; // rcx
  const char *v34; // rax
  __int64 v35; // r8
  int v36; // r12d
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  PIO_SECURITY_CONTEXT SecurityContext; // rax
  int v39; // r8d
  int v40; // r9d
  const char *v41; // rax
  __int64 v42; // r8
  ULONG Flags; // eax
  struct _FLT_RELATED_OBJECTS *v44; // rcx
  __int64 v45; // r8
  char *v46; // rdx
  int v47; // r8d
  int v48; // r9d
  PFLT_CONTEXT v49; // r12
  NTSTATUS v50; // eax
  int v51; // r13d
  struct UnionFs::StackEventTracer *v52; // [rsp+28h] [rbp-E0h]
  struct UnionFs::StackEventTracer *v53; // [rsp+30h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v54; // [rsp+30h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v55; // [rsp+30h] [rbp-D8h]
  PVOID *p_P; // [rsp+38h] [rbp-D0h]
  _WORD v57[2]; // [rsp+58h] [rbp-B0h] BYREF
  int v58; // [rsp+5Ch] [rbp-ACh] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-A8h] BYREF
  PVOID Object; // [rsp+68h] [rbp-A0h] BYREF
  PERESOURCE Resource; // [rsp+70h] [rbp-98h] BYREF
  PFLT_CONTEXT Context; // [rsp+78h] [rbp-90h]
  int v63; // [rsp+80h] [rbp-88h] BYREF
  PVOID P; // [rsp+88h] [rbp-80h] BYREF
  struct _FLT_RELATED_OBJECTS *v65; // [rsp+90h] [rbp-78h] BYREF
  char v66[8]; // [rsp+98h] [rbp-70h] BYREF
  char *v67; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v68[6]; // [rsp+A8h] [rbp-60h] BYREF
  char v69; // [rsp+D8h] [rbp-30h]
  void *p_PreviouslyGrantedAccess; // [rsp+E0h] [rbp-28h] BYREF
  utl::_RefCountBase *v71; // [rsp+E8h] [rbp-20h]
  int v72; // [rsp+F0h] [rbp-18h]
  _QWORD v73[5]; // [rsp+F8h] [rbp-10h] BYREF
  char v74; // [rsp+120h] [rbp+18h]
  char v75; // [rsp+170h] [rbp+68h] BYREF
  struct _FLT_CALLBACK_DATA *v76; // [rsp+178h] [rbp+70h]
  __int64 v77; // [rsp+180h] [rbp+78h]

  v77 = a4;
  v76 = a3;
  if ( ((__int64)a2->Iopb->Parameters.QueryEa.EaList & 0x41) == 0x41 )
  {
    v10 = -1073741811;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000000DLL,
      (int)a8,
      (struct UnionFs::StackEventTracer *)0x127001D01D4LL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "ORIGIN: FILE_DIRECTORY_FILE and FILE_NON_DIRECTORY_FILE both set",
      (const char *)v53);
    return v10;
  }
  v12 = a5;
  FltReferenceContext(a5[9]);
  v13 = v12[9];
  Options = a2->Iopb->Parameters.Create.Options;
  v15 = (_QWORD *)v13[4];
  Context = v15;
  if ( (Options & 1) != 0 && !*(_BYTE *)(v15[18] + 96LL) )
  {
    v16 = "ORIGIN: Attempt to open a file as a directory.";
    v17 = 0x128001D01E1LL;
    v18 = -1073741565;
LABEL_7:
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)v18,
      (int)a8,
      (struct UnionFs::StackEventTracer *)v17,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      v16,
      (const char *)v53);
    if ( v13 )
      FltReleaseContext(v13);
    return v18;
  }
  if ( (Options & 0x40) != 0 && *(_BYTE *)(v15[18] + 96LL) )
  {
    v16 = "ORIGIN: Attempt to open a directory as a file.";
    v17 = 0x195001D01E9LL;
    v18 = -1073741638;
    goto LABEL_7;
  }
  v19 = a8;
  DuplicateBackingFileHandle = UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess(
                                 (UnionFs::UfsPathCachePayload *)v12,
                                 a2,
                                 a8,
                                 0);
  if ( DuplicateBackingFileHandle < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)DuplicateBackingFileHandle,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x22F001D01EFLL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Checking caller access from cache",
      (const char *)v53);
LABEL_15:
    if ( v13 )
      FltReleaseContext(v13);
    return (unsigned int)DuplicateBackingFileHandle;
  }
  Handle = 0;
  DuplicateBackingFileHandle = UnionFs::UfsPathCachePayload::GetDuplicateBackingFileHandle(v12, &Handle, v19);
  if ( DuplicateBackingFileHandle < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)DuplicateBackingFileHandle,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x23C001D01F6LL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Getting duplicate layer handle",
      (const char *)v53);
    if ( Handle )
      ZwClose(Handle);
    goto LABEL_15;
  }
  ObfReferenceObject(v12[8]);
  v21 = (volatile signed __int32 *)v12[5];
  v22 = (utl::_RefCountBase **)v12[4];
  v67 = (char *)v12[8];
  Object = v67;
  if ( v21 )
    _InterlockedIncrement(v21 + 2);
  _InterlockedIncrement((volatile signed __int32 *)*v22 + 2);
  v23 = *v22;
  v71 = *v22;
  p_PreviouslyGrantedAccess = v22;
  if ( v21 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v21);
  v24 = v22[1];
  P = 0;
  v25 = *a7;
  *(_QWORD *)v66 = *(_QWORD *)v24;
  ShadowFsContext2 = UnionFs::UfsStreamHandleCtx::CreateShadowFsContext2(
                       v25,
                       (unsigned int)&p_PreviouslyGrantedAccess,
                       (unsigned int)&Handle,
                       (unsigned int)&Object,
                       (__int64)&P,
                       (_DWORD)v19);
  if ( ShadowFsContext2 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)ShadowFsContext2,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x12D001D020DLL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Creating shadow FsContext2",
      (const char *)v54);
LABEL_27:
    v27 = (UnionFs::UfsFsContext2 *)P;
LABEL_28:
    if ( v27 )
    {
      UnionFs::UfsFsContext2::~UfsFsContext2(v27);
      ExFreePoolWithTag(v27, 0);
    }
    if ( v23 )
      utl::_RefCountBase::_DecStrong(v23);
    if ( Object )
      ObfDereferenceObject(Object);
    if ( Handle )
      ZwClose(Handle);
    if ( v13 )
      FltReleaseContext(v13);
    return (unsigned int)ShadowFsContext2;
  }
  v28 = (struct _FLT_RELATED_OBJECTS *)Context;
  a1->FsContext = Context;
  v65 = v28;
  FsFltWil::AcquireResourceExclusive(&Resource, (char *)v28[2].Instance + 56);
  v68[0] = a1;
  v68[3] = v57;
  v57[0] = 0;
  v75 = 0;
  v68[4] = (char *)v57 + 1;
  v68[1] = &v75;
  v68[5] = &v65;
  v68[2] = v77;
  v69 = 1;
  ShadowFsContext2 = UnionFs::UfsStreamHandleCtx::FltSet(**(PFLT_INSTANCE **)(v77 + 8), a1);
  if ( ShadowFsContext2 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)ShadowFsContext2,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x12E001D024BLL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Attaching handle context to SFO",
      (const char *)v54);
LABEL_41:
    wil::details::lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___::_lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___(v68);
    if ( Resource )
    {
      ExReleaseResourceLite(Resource);
      KeLeaveCriticalRegion();
    }
    goto LABEL_27;
  }
  v75 = 1;
  Context = 0;
  ShadowFsContext2 = UnionFs::UfsInstanceCtx::FltGet(**(PFLT_INSTANCE **)(v77 + 8));
  if ( ShadowFsContext2 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)ShadowFsContext2,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x12F001D0256LL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Getting scratch instance ctx",
      (const char *)v54);
    if ( Context )
      FltReleaseContext(Context);
    goto LABEL_41;
  }
  v27 = (UnionFs::UfsFsContext2 *)P;
  a1->FsContext2 = P;
  v58 = 0;
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    v58 = UnionFs::Utils::BreakBatchAndHOplocks((UnionFs::Utils *)a2, v76, v65, v19, v52);
    ShadowFsContext2 = v58;
    if ( v58 == 259 )
    {
      if ( (unsigned int)dword_14009E178 <= 4
        || (qword_14009E188 & 0x202200) == 0
        || (qword_14009E190 & 0x202200) != qword_14009E190 )
      {
        goto LABEL_53;
      }
      v63 = 625;
      P = "onecore\\base\\fs\\unionfs\\sys\\sfosupport.cpp";
      v31 = byte_140098A91;
      v67 = "Oplock break";
      p_P = &P;
      v32 = (PVOID *)&v67;
LABEL_52:
      *(_QWORD *)v66 = "UnionFs::UfsShadowFileObject::SetUp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        2105856,
        (_DWORD)v31,
        v29,
        v30,
        (__int64)v32,
        (__int64)v66,
        (__int64)p_P,
        (__int64)&v63);
LABEL_53:
      v10 = v58;
      goto LABEL_54;
    }
    if ( v58 < 0 )
    {
      v34 = "PUSH: Breaking oplocks";
      v35 = 0x6EE001D0276LL;
LABEL_70:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)ShadowFsContext2,
        (int)v19,
        (struct UnionFs::StackEventTracer *)v35,
        (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
        v34,
        (const char *)v54);
LABEL_71:
      if ( Context )
        FltReleaseContext(Context);
      wil::details::lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___::_lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___(v68);
      if ( Resource )
      {
        ExReleaseResourceLite(Resource);
        KeLeaveCriticalRegion();
      }
      goto LABEL_28;
    }
  }
  LODWORD(v54) = (_DWORD)a6;
  v36 = UnionFs::Utils::CheckShareAccess(
          *(unsigned int *)(*(_QWORD *)(a2->Iopb->Parameters.WMI.ProviderId + 8) + 20LL),
          a2->Iopb->Parameters.Create.ShareAccess,
          a1,
          a1->FsContext,
          1);
  if ( v36 >= 0 )
    v36 = 0;
  else
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v36,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x627001D05B2LL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::CheckShareAccess",
      "PUSH: Checking share access of SFO",
      (const char *)v54);
  v58 = v36;
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v58 == -1073741757 )
    {
      Iopb = a2->Iopb;
      if ( (Iopb->Parameters.Create.Options & 0x100) == 0 )
      {
        SecurityContext = Iopb->Parameters.Create.SecurityContext;
        v72 = 128;
        p_PreviouslyGrantedAccess = &SecurityContext->AccessState->PreviouslyGrantedAccess;
        v71 = (utl::_RefCountBase *)((char *)&Iopb->Parameters.WMI.BufferSize + 2);
        ShadowFsContext2 = UnionFs::Utils::CheckOplockH(
                             a2,
                             v76,
                             (struct _FLT_RELATED_OBJECTS *)((char *)v65 + 88),
                             (unsigned int **)&p_PreviouslyGrantedAccess,
                             v19);
        if ( ShadowFsContext2 == 259 )
        {
          if ( (unsigned int)dword_14009E178 > 4
            && (qword_14009E188 & 0x202200) != 0
            && (qword_14009E190 & 0x202200) == qword_14009E190 )
          {
            v63 = 663;
            v67 = "onecore\\base\\fs\\unionfs\\sys\\sfosupport.cpp";
            *(_QWORD *)v66 = "UnionFs::UfsShadowFileObject::SetUp";
            P = "H oplock break for sharing violation";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              2105856,
              (unsigned int)byte_140098B19,
              v39,
              v40,
              (__int64)&P,
              (__int64)v66,
              (__int64)&v67,
              (__int64)&v63);
          }
          if ( Context )
            FltReleaseContext(Context);
          wil::details::lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___::_lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___(v68);
          if ( Resource )
          {
            ExReleaseResourceLite(Resource);
            KeLeaveCriticalRegion();
          }
          if ( v27 )
          {
            UnionFs::UfsFsContext2::~UfsFsContext2(v27);
            ExFreePoolWithTag(v27, 0);
          }
          if ( v23 )
            utl::_RefCountBase::_DecStrong(v23);
          if ( Object )
            ObfDereferenceObject(Object);
          if ( Handle )
            ZwClose(Handle);
          if ( v13 )
            FltReleaseContext(v13);
          return 259;
        }
        if ( ShadowFsContext2 < 0 )
        {
          v34 = "PUSH: CheckOplockH";
          v35 = 0x3DE001D029CLL;
          goto LABEL_70;
        }
      }
    }
  }
  ShadowFsContext2 = v58;
  if ( v58 < 0 )
  {
    v34 = "PUSH: CheckShareAccess";
    v35 = 0x22E001D02A0LL;
    goto LABEL_70;
  }
  LOBYTE(v57[0]) = 1;
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( (a2->Iopb->Parameters.Create.Options & 0x100000) != 0 )
    {
      if ( *(_BYTE *)(*(_QWORD *)&v65[3].Size + 96LL) )
      {
        v41 = "ORIGIN: Filter oplock request on directory";
        v42 = 0x6EF001D02AFLL;
        v10 = -1073741811;
LABEL_109:
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)v10,
          (int)v19,
          (struct UnionFs::StackEventTracer *)v42,
          (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
          v41,
          (const char *)v54);
LABEL_54:
        v33 = Context;
        if ( !Context )
        {
LABEL_56:
          wil::details::lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___::_lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___(v68);
          if ( Resource )
          {
            ExReleaseResourceLite(Resource);
            KeLeaveCriticalRegion();
          }
          if ( v27 )
          {
            UnionFs::UfsFsContext2::~UfsFsContext2(v27);
            ExFreePoolWithTag(v27, 0);
          }
          if ( v23 )
            utl::_RefCountBase::_DecStrong(v23);
          if ( Object )
            ObfDereferenceObject(Object);
          if ( Handle )
            ZwClose(Handle);
          if ( v13 )
            FltReleaseContext(v13);
          return v10;
        }
LABEL_55:
        FltReleaseContext(v33);
        goto LABEL_56;
      }
      if ( LODWORD(v65[4].Volume) > 1 )
      {
        v41 = "ORIGIN: Filter oplock request with existing opens";
        v42 = 0x6F0001D02B5LL;
        v10 = -1073741598;
        goto LABEL_109;
      }
    }
    v58 = UnionFs::Utils::CheckOplock(a2, (__int64)v76, (PVOID *)&v65[1].Transaction, (int)v19, 0);
    ShadowFsContext2 = v58;
    if ( v58 == 259 )
    {
      if ( (unsigned int)dword_14009E178 <= 4
        || (qword_14009E188 & 0x202200) == 0
        || (qword_14009E190 & 0x202200) != qword_14009E190 )
      {
        goto LABEL_53;
      }
      v63 = 705;
      v67 = "onecore\\base\\fs\\unionfs\\sys\\sfosupport.cpp";
      v31 = &byte_140098B57;
      P = "Oplock break";
      p_P = (PVOID *)&v67;
      v32 = &P;
      goto LABEL_52;
    }
    if ( v58 < 0 )
    {
      v34 = "PUSH: Checking oplock";
      v35 = 0x6F1001D02C6LL;
      goto LABEL_70;
    }
    ShadowFsContext2 = UnionFs::Utils::CheckOplock(a2, (__int64)v76, (PVOID *)&v65[1].Transaction, (int)v19, 2);
    if ( ShadowFsContext2 < 0 )
    {
      v34 = "PUSH: Oplock key check";
      v35 = 0x6F2001D02D1LL;
      goto LABEL_70;
    }
  }
  Flags = a1->Flags;
  v44 = v65;
  _InterlockedIncrement((volatile signed __int32 *)&v65[4].Volume);
  if ( (Flags & 8) != 0 )
    _InterlockedIncrement((volatile signed __int32 *)&v44[4].Volume + 1);
  HIBYTE(v57[0]) = 1;
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( (a2->Iopb->Parameters.Create.Options & 0x10000) != 0 )
    {
      ShadowFsContext2 = FltOplockFsctrl((POPLOCK)&v65[1].Transaction, a2, (ULONG)v65[4].Volume);
      if ( ShadowFsContext2 < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)ShadowFsContext2,
          (int)v19,
          (struct UnionFs::StackEventTracer *)0x6F3001D02E2LL,
          (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
          "API: Setting up atomic create-with-oplock",
          (const char *)v54);
        goto LABEL_71;
      }
    }
  }
  v73[0] = a2;
  v73[1] = &v58;
  v73[2] = v76;
  v73[3] = &v65;
  v73[4] = v19;
  v74 = 1;
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( (a2->Iopb->Parameters.Create.Options & 0x100000) != 0 && !*(_BYTE *)(*(_QWORD *)&v65[3].Size + 96LL) )
    {
      ShadowFsContext2 = FltOplockFsctrl((POPLOCK)&v65[1].Transaction, a2, (ULONG)v65[4].Volume);
      if ( ShadowFsContext2 < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)ShadowFsContext2,
          (int)v19,
          (struct UnionFs::StackEventTracer *)0x6F4001D0306LL,
          (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
          "API: Setting up reserve opfilter",
          (const char *)v54);
        wil::details::lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___::_lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___(v73);
        goto LABEL_71;
      }
    }
  }
  v45 = *(_QWORD *)v66;
  v46 = v67;
  a1->LockOperation = v67[72];
  a1->DeletePending = v46[73];
  a1->SectionObjectPointer = (PSECTION_OBJECT_POINTERS)*((_QWORD *)v46 + 5);
  v58 = IoSetShadowFileInformation(a1, v46, v45);
  if ( v58 < 0
    && (unsigned int)dword_14009E178 > 3
    && (qword_14009E188 & 0x2000) != 0
    && (qword_14009E190 & 0x2000) == qword_14009E190 )
  {
    v63 = v58;
    v67 = "onecore\\base\\fs\\unionfs\\sys\\sfosupport.cpp";
    p_PreviouslyGrantedAccess = "Failed to set shadow file information";
    LODWORD(P) = 800;
    *(_QWORD *)v66 = "UnionFs::UfsShadowFileObject::SetUp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_14009E190,
      (unsigned int)&byte_140098ACF,
      v47,
      v48,
      (__int64)&p_PreviouslyGrantedAccess,
      (__int64)v66,
      (__int64)&v67,
      (__int64)&P,
      (__int64)&v63);
  }
  v49 = Context;
  a1->Vpb = (PVPB)*((_QWORD *)Context + 4);
  UnionFs::UfsShadowFileObject::UpdateFileSizesFromBFO((UnionFs::UfsShadowFileObject *)a1);
  if ( a1->CurrentByteOffset.QuadPart )
    MicrosoftTelemetryAssertTriggeredMsgKM("this->CurrentByteOffset.QuadPart == 0");
  v50 = FltObjectReference(*(PVOID *)v49);
  LODWORD(P) = v50;
  if ( v50 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v50,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x6000A017BLL,
      (unsigned __int64)"UnionFs::UfsInstanceCtx::IncrementActiveShadowFileCount",
      "API: Referencing FLT_INSTANCE",
      (const char *)v54);
    v10 = (unsigned int)P;
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)P,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x92001D0337LL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Incrementing active SFO count",
      (const char *)v55);
    wil::details::lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___::_lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___(v73);
    v33 = v49;
    goto LABEL_55;
  }
  _InterlockedIncrement((volatile signed __int32 *)v49 + 28);
  v51 = UnionFs::UfsStreamCtx::RememberSFO((UnionFs::UfsStreamCtx *)v13, a1, v19);
  if ( v51 >= 0 )
  {
    *((_DWORD *)v27 + 10) |= 1u;
    v69 = 0;
    v74 = 0;
    wil::details::lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___::_lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___(v73);
    FltReleaseContext(v49);
    wil::details::lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___::_lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___(v68);
    if ( Resource )
    {
      ExReleaseResourceLite(Resource);
      KeLeaveCriticalRegion();
    }
    if ( v23 )
      utl::_RefCountBase::_DecStrong(v23);
    if ( Object )
      ObfDereferenceObject(Object);
    if ( Handle )
      ZwClose(Handle);
    if ( v13 )
      FltReleaseContext(v13);
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v51,
      (int)v19,
      (struct UnionFs::StackEventTracer *)0x46B001D033ELL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::SetUp",
      "PUSH: Remembering new SFO",
      (const char *)v54);
    wil::details::lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___::_lambda_call__lambda_390da0a41ac4a99ff8a61140577dc3a3___(v73);
    FltReleaseContext(v49);
    wil::details::lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___::_lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___(v68);
    if ( Resource )
    {
      ExReleaseResourceLite(Resource);
      KeLeaveCriticalRegion();
    }
    if ( v27 )
    {
      UnionFs::UfsFsContext2::~UfsFsContext2(v27);
      ExFreePoolWithTag(v27, 0);
    }
    if ( v23 )
      utl::_RefCountBase::_DecStrong(v23);
    if ( Object )
      ObfDereferenceObject(Object);
    if ( Handle )
      ZwClose(Handle);
    if ( v13 )
      FltReleaseContext(v13);
    return (unsigned int)v51;
  }
}

```

## disassembly

```asm
0x140058fbc  mov     rax, rsp
0x140058fbf  mov     [rax+8], rbx
0x140058fc3  mov     [rax+20h], r9
0x140058fc7  mov     [rax+18h], r8
0x140058fcb  push    rbp
0x140058fcc  push    rsi
0x140058fcd  push    rdi
0x140058fce  push    r12
0x140058fd0  push    r13
0x140058fd2  push    r14
0x140058fd4  push    r15
0x140058fd6  lea     rbp, [rax-58h]
0x140058fda  sub     rsp, 120h
0x140058fe1  mov     rax, [rdx+10h]
0x140058fe5  mov     rsi, rdx
0x140058fe8  mov     r13, rcx
0x140058feb  mov     r10d, [rax+20h]
0x140058fef  and     r10d, 41h
0x140058ff3  cmp     r10b, 41h ; 'A'
0x140058ff7  jnz     short loc_140059030
0x140058ff9  mov     rdx, [rbp+50h+arg_38]; int
0x140059000  lea     rax, aOriginFileDire; "ORIGIN: FILE_DIRECTORY_FILE and FILE_NO"...
0x140059007  mov     esi, 0C000000Dh
0x14005900c  mov     [rsp+150h+var_130], rax; char *
0x140059011  mov     ecx, esi; this
0x140059013  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x14005901a  mov     r8, 127001D01D4h; struct UnionFs::StackEventTracer *
0x140059024  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140059029  mov     eax, esi
0x14005902b  jmp     loc_140059E5B
0x140059030  mov     rdi, [rbp+50h+arg_20]
0x140059037  mov     rcx, [rdi+48h]; Context
0x14005903b  call    cs:__imp_FltReferenceContext
0x140059042  nop     dword ptr [rax+rax+00h]
0x140059047  mov     rax, [rsi+10h]
0x14005904b  xor     r12d, r12d
0x14005904e  mov     rbx, [rdi+48h]
0x140059052  mov     edx, [rax+20h]
0x140059055  mov     rcx, [rbx+20h]
0x140059059  mov     [rsp+150h+Context], rcx
0x14005905e  test    dl, 1
0x140059061  jz      short loc_1400590BB
0x140059063  mov     rax, [rcx+90h]
0x14005906a  cmp     [rax+60h], r12b
0x14005906e  jnz     short loc_1400590BB
0x140059070  lea     rax, aOriginAttemptT_1; "ORIGIN: Attempt to open a file as a dir"...
0x140059077  mov     r8, 128001D01E1h; struct UnionFs::StackEventTracer *
0x140059081  mov     edi, 0C0000103h
0x140059086  mov     rdx, [rbp+50h+arg_38]; int
0x14005908d  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x140059094  mov     ecx, edi; this
0x140059096  mov     [rsp+150h+var_130], rax; char *
0x14005909b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400590a0  test    rbx, rbx
0x1400590a3  jz      short loc_1400590B4
0x1400590a5  mov     rcx, rbx; Context
0x1400590a8  call    cs:__imp_FltReleaseContext
0x1400590af  nop     dword ptr [rax+rax+00h]
0x1400590b4  mov     eax, edi
0x1400590b6  jmp     loc_140059E5B
0x1400590bb  test    dl, 40h
0x1400590be  jz      short loc_1400590E5
0x1400590c0  mov     rax, [rcx+90h]
0x1400590c7  cmp     [rax+60h], r12b
0x1400590cb  jz      short loc_1400590E5
0x1400590cd  lea     rax, aOriginAttemptT_3; "ORIGIN: Attempt to open a directory as "...
0x1400590d4  mov     r8, 195001D01E9h
0x1400590de  mov     edi, 0C00000BAh
0x1400590e3  jmp     short loc_140059086
0x1400590e5  mov     r15, [rbp+50h+arg_38]
0x1400590ec  xor     r9d, r9d; bool
0x1400590ef  mov     r8, r15; struct UnionFs::StackEventTracer *
0x1400590f2  mov     rdx, rsi; struct _FLT_CALLBACK_DATA *
0x1400590f5  mov     rcx, rdi; this
0x1400590f8  call    ?CheckAndCacheCallerAccess@UfsPathCachePayload@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess(_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &,bool)
0x1400590fd  mov     r14d, eax
0x140059100  test    eax, eax
0x140059102  jns     short loc_140059148
0x140059104  lea     rax, aPushCheckingCa_0; "PUSH: Checking caller access from cache"
0x14005910b  mov     r8, 22F001D01EFh; struct UnionFs::StackEventTracer *
0x140059115  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x14005911c  mov     [rsp+150h+var_130], rax; char *
0x140059121  mov     rdx, r15; int
0x140059124  mov     ecx, r14d; this
0x140059127  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005912c  test    rbx, rbx
0x14005912f  jz      short loc_140059140
0x140059131  mov     rcx, rbx; Context
0x140059134  call    cs:__imp_FltReleaseContext
0x14005913b  nop     dword ptr [rax+rax+00h]
0x140059140  mov     eax, r14d
0x140059143  jmp     loc_140059E5B
0x140059148  mov     r8, r15
0x14005914b  mov     [rsp+150h+Handle], r12
0x140059150  lea     rdx, [rsp+150h+Handle]
0x140059155  mov     rcx, rdi
0x140059158  call    ?GetDuplicateBackingFileHandle@UfsPathCachePayload@UnionFs@@QEBAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::GetDuplicateBackingFileHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,UnionFs::StackEventTracer &)
0x14005915d  mov     r14d, eax
0x140059160  test    eax, eax
0x140059162  jns     short loc_1400591A4
0x140059164  lea     rax, aPushGettingDup; "PUSH: Getting duplicate layer handle"
0x14005916b  mov     r8, 23C001D01F6h; struct UnionFs::StackEventTracer *
0x140059175  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x14005917c  mov     [rsp+150h+var_130], rax; char *
0x140059181  mov     rdx, r15; int
0x140059184  mov     ecx, r14d; this
0x140059187  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005918c  mov     rcx, [rsp+150h+Handle]; Handle
0x140059191  test    rcx, rcx
0x140059194  jz      short loc_14005912C
0x140059196  call    cs:__imp_ZwClose
0x14005919d  nop     dword ptr [rax+rax+00h]
0x1400591a2  jmp     short loc_14005912C
0x1400591a4  mov     rcx, [rdi+40h]; Object
0x1400591a8  call    cs:__imp_ObfReferenceObject
0x1400591af  nop     dword ptr [rax+rax+00h]
0x1400591b4  mov     rax, [rdi+40h]
0x1400591b8  mov     rcx, [rdi+28h]; this
0x1400591bc  mov     r12, [rdi+20h]
0x1400591c0  mov     [rbp+50h+var_B8], rax
0x1400591c4  mov     [rsp+150h+Object], rax
0x1400591c9  test    rcx, rcx
0x1400591cc  jz      short loc_1400591D2
0x1400591ce  lock inc dword ptr [rcx+8]
0x1400591d2  mov     rax, [r12]
0x1400591d6  lock inc dword ptr [rax+8]
0x1400591da  mov     r14, [r12]
0x1400591de  mov     [rbp+50h+var_70], r14
0x1400591e2  mov     [rbp+50h+var_78], r12
0x1400591e6  test    rcx, rcx
0x1400591e9  jz      short loc_1400591F0
0x1400591eb  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400591f0  mov     rax, [r12+8]
0x1400591f5  lea     r9, [rsp+150h+Object]
0x1400591fa  mov     rdi, [rbp+50h+arg_30]
0x140059201  lea     r8, [rsp+150h+Handle]
0x140059206  mov     [rsp+150h+var_128], r15; char *
0x14005920b  lea     rdx, [rbp+50h+var_78]
0x14005920f  mov     [rbp+50h+P], 0
0x140059217  mov     rax, [rax]
0x14005921a  mov     rcx, [rdi]
0x14005921d  mov     qword ptr [rbp+50h+var_C0], rax
0x140059221  lea     rax, [rbp+50h+P]
0x140059225  mov     [rsp+150h+var_130], rax; struct UnionFs::StackEventTracer *
0x14005922a  call    ?CreateShadowFsContext2@UfsStreamHandleCtx@UnionFs@@QEAAJ$$QEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@AEAV?$unique_ptr@VUfsFsContext2@UnionFs@@U?$default_delete@VUfsFsContext2@UnionFs@@@utl@@@4@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::CreateShadowFsContext2(utl::shared_ptr<UnionFs::UfsLayerCtx> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> &&,utl::unique_ptr<UnionFs::UfsFsContext2,utl::default_delete<UnionFs::UfsFsContext2>> &,UnionFs::StackEventTracer &)
0x14005922f  mov     r12d, eax
0x140059232  test    eax, eax
0x140059234  jns     loc_1400592D9
0x14005923a  lea     rax, aPushCreatingSh; "PUSH: Creating shadow FsContext2"
0x140059241  mov     r8, 12D001D020Dh; struct UnionFs::StackEventTracer *
0x14005924b  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x140059252  mov     [rsp+150h+var_130], rax; char *
0x140059257  mov     rdx, r15; int
0x14005925a  mov     ecx, r12d; this
0x14005925d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140059262  mov     rdi, [rbp+50h+P]
0x140059266  test    rdi, rdi
0x140059269  jz      short loc_140059284
0x14005926b  mov     rcx, rdi; this
0x14005926e  call    ??1UfsFsContext2@UnionFs@@QEAA@XZ; UnionFs::UfsFsContext2::~UfsFsContext2(void)
0x140059273  xor     edx, edx; Tag
0x140059275  mov     rcx, rdi; P
0x140059278  call    cs:__imp_ExFreePoolWithTag
0x14005927f  nop     dword ptr [rax+rax+00h]
0x140059284  test    r14, r14
0x140059287  jz      short loc_140059291
0x140059289  mov     rcx, r14; this
0x14005928c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140059291  mov     rcx, [rsp+150h+Object]; Object
0x140059296  test    rcx, rcx
0x140059299  jz      short loc_1400592A7
0x14005929b  call    cs:__imp_ObfDereferenceObject
0x1400592a2  nop     dword ptr [rax+rax+00h]
0x1400592a7  mov     rcx, [rsp+150h+Handle]; Handle
0x1400592ac  test    rcx, rcx
0x1400592af  jz      short loc_1400592BD
0x1400592b1  call    cs:__imp_ZwClose
0x1400592b8  nop     dword ptr [rax+rax+00h]
0x1400592bd  test    rbx, rbx
0x1400592c0  jz      short loc_1400592D1
0x1400592c2  mov     rcx, rbx; Context
0x1400592c5  call    cs:__imp_FltReleaseContext
0x1400592cc  nop     dword ptr [rax+rax+00h]
0x1400592d1  mov     eax, r12d
0x1400592d4  jmp     loc_140059E5B
0x1400592d9  mov     rax, [rsp+150h+Context]
0x1400592de  lea     rcx, [rsp+150h+Resource]
0x1400592e3  mov     [r13+18h], rax
0x1400592e7  mov     [rbp+50h+var_C8], rax
0x1400592eb  mov     rdx, [rax+78h]
0x1400592ef  add     rdx, 38h ; '8'
0x1400592f3  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x1400592f8  xor     eax, eax
0x1400592fa  mov     [rbp+50h+var_B0], r13
0x1400592fe  mov     byte ptr [rsp+150h+var_100+1], al
0x140059302  lea     rcx, [rsp+150h+var_100]
0x140059307  mov     [rbp+50h+var_98], rcx
0x14005930b  mov     r9, r15
0x14005930e  mov     byte ptr [rsp+150h+var_100], al
0x140059312  lea     rcx, [rsp+150h+var_100+1]
0x140059317  mov     [rbp+50h+arg_8], al
0x14005931a  mov     r8, rdi
0x14005931d  mov     [rbp+50h+var_90], rcx
0x140059321  lea     rax, [rbp+50h+arg_8]
0x140059325  mov     [rbp+50h+var_A8], rax
0x140059329  lea     rcx, [rbp+50h+var_C8]
0x14005932d  mov     rax, [rbp+50h+arg_18]
0x140059331  mov     rdx, r13; FileObject
0x140059334  mov     [rbp+50h+var_88], rcx
0x140059338  mov     [rbp+50h+var_A0], rax
0x14005933c  mov     [rbp+50h+var_80], 1
0x140059340  mov     rcx, [rax+8]
0x140059344  mov     rcx, [rcx]; Instance
0x140059347  call    ?FltSet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT const &,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x14005934c  mov     r12d, eax
0x14005934f  test    eax, eax
0x140059351  jns     short loc_1400593AF
0x140059353  lea     rax, aPushAttachingH; "PUSH: Attaching handle context to SFO"
0x14005935a  mov     r8, 12E001D024Bh; struct UnionFs::StackEventTracer *
0x140059364  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x14005936b  mov     [rsp+150h+var_130], rax; char *
0x140059370  mov     rdx, r15; int
0x140059373  mov     ecx, r12d; this
0x140059376  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005937b  lea     rcx, [rbp+50h+var_B0]
0x14005937f  call    wil__details__lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3______lambda_call__lambda_6443d8c1c7a99d04f10d89c27a4118f3___
0x140059384  mov     rcx, [rsp+150h+Resource]; Resource
0x140059389  test    rcx, rcx
0x14005938c  jz      loc_140059262
0x140059392  call    cs:__imp_ExReleaseResourceLite
0x140059399  nop     dword ptr [rax+rax+00h]
0x14005939e  call    cs:__imp_KeLeaveCriticalRegion
0x1400593a5  nop     dword ptr [rax+rax+00h]
0x1400593aa  jmp     loc_140059262
0x1400593af  mov     r9, [rbp+50h+arg_18]
0x1400593b3  lea     r8, [rsp+150h+Context]
0x1400593b8  mov     [rbp+50h+arg_8], 1
0x1400593bc  xor     edx, edx
0x1400593be  mov     [rsp+150h+Context], 0
0x1400593c7  mov     rcx, [r9+8]
0x1400593cb  mov     r9, r15
0x1400593ce  mov     rcx, [rcx]; Instance
0x1400593d1  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x1400593d6  mov     r12d, eax
0x1400593d9  test    eax, eax
0x1400593db  jns     short loc_140059424
0x1400593dd  lea     rax, aPushGettingScr_1; "PUSH: Getting scratch instance ctx"
0x1400593e4  mov     r8, 12F001D0256h; struct UnionFs::StackEventTracer *
0x1400593ee  lea     r9, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
0x1400593f5  mov     [rsp+150h+var_130], rax; char *
0x1400593fa  mov     rdx, r15; int
0x1400593fd  mov     ecx, r12d; this
0x140059400  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140059405  mov     rcx, [rsp+150h+Context]; Context
0x14005940a  test    rcx, rcx
0x14005940d  jz      loc_14005937B
0x140059413  call    cs:__imp_FltReleaseContext
0x14005941a  nop     dword ptr [rax+rax+00h]
0x14005941f  jmp     loc_14005937B
0x140059424  mov     rdi, [rbp+50h+P]
0x140059428  mov     [r13+20h], rdi
0x14005942c  mov     dword ptr [rsp+150h+var_100+4], 0
0x140059434  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140059439  test    eax, eax
0x14005943b  jz      loc_14005961E
0x140059441  mov     r8, [rbp+50h+var_C8]; struct _FLT_RELATED_OBJECTS *
0x140059445  mov     r9, r15; struct UnionFs::UfsFsContext *
0x140059448  mov     rdx, [rbp+50h+arg_10]; struct _FLT_CALLBACK_DATA *
0x14005944c  mov     rcx, rsi; this
0x14005944f  call    ?BreakBatchAndHOplocks@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsFsContext@2@AEAVStackEventTracer@2@@Z; UnionFs::Utils::BreakBatchAndHOplocks(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsFsContext &,UnionFs::StackEventTracer &)
0x140059454  mov     dword ptr [rsp+150h+var_100+4], eax
0x140059458  mov     r12d, eax
0x14005945b  cmp     eax, 103h
0x140059460  jnz     loc_1400595A7
0x140059466  mov     eax, cs:dword_14009E178
0x14005946c  cmp     eax, 4
0x14005946f  jbe     short loc_1400594EE
0x140059471  mov     rdx, cs:qword_14009E190
0x140059478  mov     ecx, 202200h
0x14005947d  mov     rax, cs:qword_14009E188
0x140059484  test    rcx, rax
0x140059487  jz      short loc_1400594EE
0x140059489  mov     rax, rdx
0x14005948c  and     rax, rcx
0x14005948f  cmp     rax, rdx
0x140059492  jnz     short loc_1400594EE
0x140059494  lea     rax, aOnecoreBaseFsU_17; "onecore\\base\\fs\\unionfs\\sys\\sfosup"...
0x14005949b  mov     [rsp+150h+var_D8], 271h
0x1400594a3  mov     [rbp+50h+P], rax
0x1400594a7  lea     rdx, byte_140098A91
0x1400594ae  lea     rax, aOplockBreak; "Oplock break"
0x1400594b5  mov     [rbp+50h+var_B8], rax
0x1400594b9  lea     rax, [rsp+150h+var_D8]
0x1400594be  mov     [rsp+150h+var_118], rax
0x1400594c3  lea     rax, [rbp+50h+P]
0x1400594c7  mov     [rsp+150h+var_120], rax
0x1400594cc  lea     rax, [rbp+50h+var_C0]
0x1400594d0  mov     [rsp+150h+var_128], rax
0x1400594d5  lea     rax, [rbp+50h+var_B8]
0x1400594d9  lea     rsi, aUnionfsUfsshad_3; "UnionFs::UfsShadowFileObject::SetUp"
  ... truncated ...
```
