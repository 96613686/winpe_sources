# UnionFs::HandleQueryEa(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsUnionCtx &,bool *,UnionFs::StackEventTracer &)

- ea: `0x14001cbd0`
- end: `0x14001d529`
- name: `?HandleQueryEa@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsStreamHandleCtx@1@AEAVUfsUnionCtx@1@PEA_NAEAVStackEventTracer@1@@Z`
- size: `2393`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, struct _FLT_CALLBACK_DATA *@<rdx>, const struct _FLT_RELATED_OBJECTS *@<r8>, struct UnionFs::UfsStreamHandleCtx *@<r9>, struct UnionFs::UfsUnionCtx *, bool *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x14001e8b0`

## callees

- `0x140006064`
- `0x14000f7fc`
- `0x14001012c`
- `0x14001c7e8`
- `0x14001c858`
- `0x14001c90c`
- `0x14001cbd0`
- `0x14001f0d0`
- `0x140021f80`
- `0x140023970`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14006e1a4`
- `0x14007b8b0`
- `0x14007bc00`
- `0x1400a7008`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001ce53`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001ce53`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cef4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cfa3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d0cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d18c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d280`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d3f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d4c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cef4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cfa3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d0cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d18c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d280`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d3f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d4c0`
- `ntoskrnl!KeSetEvent` at `0x14001d16c`
- `ntoskrnl!KeSetEvent` at `0x14001d260`
- `ntoskrnl!KeSetEvent` at `0x14001d3cc`
- `ntoskrnl!KeSetEvent` at `0x14001d4a0`
- `ntoskrnl!KeSetEvent` at `0x14001d16c`
- `ntoskrnl!KeSetEvent` at `0x14001d260`
- `ntoskrnl!KeSetEvent` at `0x14001d3cc`
- `ntoskrnl!KeSetEvent` at `0x14001d4a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cd66`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d236`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d3a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d476`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cd66`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d236`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d3a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d476`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cd72`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d242`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d3ae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d482`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cd72`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d242`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d3ae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d482`
- `FLTMGR!FltLockUserBuffer` at `0x14001cdb8`
- `FLTMGR!FltLockUserBuffer` at `0x14001cdb8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001cc79`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001ce1a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001cfd5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d0fd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d1c2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d2b6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d42c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d4f6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001cc79`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001ce1a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001cfd5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d0fd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d1c2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d2b6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d42c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d4f6`

## string_xrefs

- `0x14001d315`: `PUSH: Copying EAs to buffer`
- `0x14001d360`: `ORIGIN: Copy EAs into user buffer`

## pseudocode

```c
__int64 __fastcall UnionFs::HandleQueryEa(
        PFLT_CALLBACK_DATA CallbackData,
        struct _FLT_CALLBACK_DATA *a2,
        const struct _FLT_RELATED_OBJECTS *a3,
        struct UnionFs::UfsStreamHandleCtx *a4,
        struct UnionFs::UfsUnionCtx *a5,
        struct UnionFs::StackEventTracer *a6)
{
  void *v9; // r15
  struct UnionFs::StackEventTracer *v10; // rsi
  int v11; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v12; // rcx
  UnionFs::UfsEaTable *v14; // rcx
  utl::_RefCountBase *v15; // rbx
  utl::_RefCountBase *v16; // r12
  struct _ERESOURCE *Length; // rcx
  PFLT_IO_PARAMETER_BLOCK Iopb; // r14
  unsigned int v19; // edi
  struct _FLT_FILE_NAME_INFORMATION *v20; // rcx
  LARGE_INTEGER AllocationSize; // rcx
  PVOID v22; // rax
  const char *v23; // rax
  __int64 v24; // r8
  unsigned __int64 v25; // rax
  PVOID EaBuffer; // r9
  void **v27; // rax
  void *v28; // rdi
  int v29; // edx
  unsigned int v30; // esi
  struct _FLT_FILE_NAME_INFORMATION *v31; // rcx
  PVOID EaList; // rcx
  int v33; // edx
  int EaInfoBuffer; // r12d
  struct _FLT_FILE_NAME_INFORMATION *v35; // rcx
  const struct _FLT_RELATED_OBJECTS *v36; // r13
  ULONG EaLength; // eax
  struct _FLT_FILE_NAME_INFORMATION *v38; // rcx
  ULONG FileObject; // eax
  int v40; // edx
  struct _ERESOURCE *v41; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v42; // rcx
  int EAs; // eax
  unsigned int v44; // r13d
  struct _ERESOURCE *v45; // rcx
  bool v46; // zf
  struct _FLT_FILE_NAME_INFORMATION *v47; // rcx
  const char *Priority; // [rsp+28h] [rbp-C0h]
  const char *Prioritya; // [rsp+28h] [rbp-C0h]
  const char *Priorityb; // [rsp+28h] [rbp-C0h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+40h] [rbp-A8h] BYREF
  UCHAR OperationFlags; // [rsp+48h] [rbp-A0h]
  char v53[15]; // [rsp+49h] [rbp-9Fh] BYREF
  utl::_RefCountBase *v54[2]; // [rsp+58h] [rbp-90h] BYREF
  PERESOURCE Resource; // [rsp+68h] [rbp-80h]
  __m128i si128; // [rsp+70h] [rbp-78h] BYREF
  __int64 Pointer; // [rsp+80h] [rbp-68h]
  PVOID P[2]; // [rsp+90h] [rbp-58h] BYREF
  unsigned __int64 v59; // [rsp+A0h] [rbp-48h] BYREF
  PVOID v60; // [rsp+A8h] [rbp-40h]
  PVOID v61; // [rsp+B0h] [rbp-38h]
  utl::_RefCountBase *v62; // [rsp+B8h] [rbp-30h]
  ULONG v63; // [rsp+F8h] [rbp+10h] BYREF
  const struct _FLT_RELATED_OBJECTS *v64; // [rsp+100h] [rbp+18h]

  v64 = a3;
  v9 = 0;
  *(_BYTE *)a5 = 0;
  FileNameInformation = 0;
  si128.m128i_i64[0] = 0;
  si128.m128i_i64[1] = a2->IoStatus.Information;
  Pointer = (__int64)a2->IoStatus.Pointer;
  v10 = a6;
  v11 = UnionFs::Utils::GetFileNameInformation(&si128, 16777473, &FileNameInformation, a6);
  if ( v11 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v11,
      (int)v10,
      (struct UnionFs::StackEventTracer *)0x53500050075LL,
      (unsigned __int64)"UnionFs::HandleQueryEa",
      "PUSH: Getting source file name information",
      Priority);
LABEL_3:
    v12 = FileNameInformation;
    FileNameInformation = 0;
    if ( v12 )
      FltReleaseFileNameInformation(v12);
    return (unsigned int)v11;
  }
  *(_OWORD *)v54 = 0;
  Resource = 0;
  if ( *((_DWORD *)a4 + 7) == 2 )
    v14 = *(UnionFs::UfsEaTable **)(*((_QWORD *)a4 + 4) + 24LL);
  else
    v14 = (UnionFs::UfsEaTable *)*((_QWORD *)UnionFs::g_FilterState + 11);
  v11 = UnionFs::UfsEaTable::LookupEaEntry(
          v14,
          (const struct _FLT_INSTANCE *)a2->IoStatus.Pointer,
          FileNameInformation,
          0,
          (struct UnionFs::LookupEaResults *)v54,
          v10);
  if ( v11 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v11,
      (int)v10,
      (struct UnionFs::StackEventTracer *)0x5600005007FLL,
      (unsigned __int64)"UnionFs::HandleQueryEa",
      "PUSH: EA table lookup",
      Prioritya);
    UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v54);
    goto LABEL_3;
  }
  v15 = v54[1];
  v62 = v54[1];
  if ( v54[1] )
    _InterlockedIncrement((volatile signed __int32 *)v54[1] + 2);
  v16 = v54[0];
  if ( !v54[0] )
  {
    if ( v15 )
      utl::_RefCountBase::_DecStrong(v15);
LABEL_92:
    UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v54);
    v42 = FileNameInformation;
    FileNameInformation = 0;
    if ( v42 )
      FltReleaseFileNameInformation(v42);
    return 0;
  }
  Length = Resource;
  Resource = 0;
  if ( Length )
  {
    ExReleaseResourceLite(Length);
    KeLeaveCriticalRegion();
  }
  Iopb = CallbackData->Iopb;
  OperationFlags = Iopb->OperationFlags;
  LOBYTE(Length) = (OperationFlags & 2) != 0;
  v53[1] = (char)Length;
  LOBYTE(v63) = OperationFlags & 4;
  v53[0] = (OperationFlags & 4) != 0;
  v61 = 0;
  if ( Iopb->Parameters.Create.AllocationSize.QuadPart )
  {
    v19 = FltLockUserBuffer(CallbackData);
    if ( (v19 & 0x80000000) != 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)v19,
        (int)v10,
        (struct UnionFs::StackEventTracer *)0x5360005009DLL,
        (unsigned __int64)"UnionFs::HandleQueryEa",
        "API: FltLockUserBuffer",
        Prioritya);
LABEL_22:
      if ( v15 )
        utl::_RefCountBase::_DecStrong(v15);
      UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v54);
      v20 = FileNameInformation;
      FileNameInformation = 0;
      if ( v20 )
        FltReleaseFileNameInformation(v20);
      return v19;
    }
    AllocationSize = Iopb->Parameters.Create.AllocationSize;
    if ( (*(_BYTE *)(AllocationSize.QuadPart + 10) & 5) != 0 )
      v22 = *(PVOID *)(AllocationSize.QuadPart + 24);
    else
      v22 = MmMapLockedPagesSpecifyCache((PMDL)AllocationSize.QuadPart, 0, MmCached, 0, 0, 0x40000010u);
    if ( v22 )
    {
      v23 = "ORIGIN: MmGetSystemAddressForMdlSafe";
      v24 = 0x537000500A6LL;
      v19 = -1073741801;
LABEL_32:
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)v19,
        (int)v10,
        (struct UnionFs::StackEventTracer *)v24,
        (unsigned __int64)"UnionFs::HandleQueryEa",
        v23,
        Prioritya);
      goto LABEL_22;
    }
    Length = (struct _ERESOURCE *)Iopb->Parameters.Read.Length;
    if ( !(_DWORD)Length )
    {
      v59 = Iopb->Parameters.Read.Length;
      v60 = 0;
      v25 = 0;
      EaBuffer = 0;
LABEL_44:
      v28 = 0;
      goto LABEL_45;
    }
    goto LABEL_113;
  }
  v25 = Iopb->Parameters.Read.Length;
  if ( !CallbackData->RequestorMode )
  {
    EaBuffer = Iopb->Parameters.Create.EaBuffer;
    if ( EaBuffer || !(_DWORD)v25 )
    {
      v59 = Iopb->Parameters.Read.Length;
      v60 = EaBuffer;
      LODWORD(Length) = v25;
      goto LABEL_44;
    }
LABEL_113:
    gsl::details::terminate((gsl::details *)Length);
    JUMPOUT(0x14001D529LL);
  }
  v27 = (void **)utl::make_unique_pool<enum gsl::byte [0],256,1634027093,0>(P, (unsigned int)v25);
  v9 = *v27;
  *v27 = 0;
  v61 = v9;
  if ( P[0] )
    ExFreePoolWithTag(P[0], 0);
  if ( !v9 )
  {
    v23 = "ORIGIN: Allocating EA double buffer";
    v24 = 0x641000500B7LL;
    v19 = -1073741670;
    goto LABEL_32;
  }
  v25 = Iopb->Parameters.Read.Length;
  v59 = v25;
  v60 = v9;
  v28 = v9;
  LODWORD(Length) = v25;
  EaBuffer = v9;
LABEL_45:
  if ( v25 < 0xC )
  {
    v29 = (int)v10;
    v30 = -1073741820;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000004LL,
      v29,
      (struct UnionFs::StackEventTracer *)0x539000500C6LL,
      (unsigned __int64)"UnionFs::HandleQueryEa",
      "ORIGIN: Provided buffer too small",
      Prioritya);
LABEL_47:
    if ( v28 )
      ExFreePoolWithTag(v28, 0);
    if ( v15 )
      utl::_RefCountBase::_DecStrong(v15);
    UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v54);
    v31 = FileNameInformation;
    FileNameInformation = 0;
    if ( v31 )
      FltReleaseFileNameInformation(v31);
    return v30;
  }
  memset(EaBuffer, 0, (unsigned int)Length);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  Pointer = -1;
  if ( Iopb->Parameters.Read.ByteOffset.LowPart )
  {
    EaList = Iopb->Parameters.QueryEa.EaList;
    if ( !EaList )
    {
      v33 = (int)v10;
      v30 = -2147483628;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0x80000014LL,
        v33,
        (struct UnionFs::StackEventTracer *)0x53A000500D3LL,
        (unsigned __int64)"UnionFs::HandleQueryEa",
        "ORIGIN: EaList is null",
        Prioritya);
      utl::vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(&si128);
      goto LABEL_47;
    }
    P[0] = (PVOID)Iopb->Parameters.Read.ByteOffset.LowPart;
    P[1] = EaList;
    EaInfoBuffer = UnionFs::GetNamesFromGetEaInfoBuffer(P, &si128, v10);
    if ( EaInfoBuffer < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)EaInfoBuffer,
        (int)v10,
        (struct UnionFs::StackEventTracer *)0x53C000500DCLL,
        (unsigned __int64)"UnionFs::HandleQueryEa",
        "PUSH: Getting EA names from ea list buffer",
        Prioritya);
      utl::vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(&si128);
      if ( v28 )
        ExFreePoolWithTag(v28, 0);
      if ( v15 )
        utl::_RefCountBase::_DecStrong(v15);
      UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v54);
      v35 = FileNameInformation;
      FileNameInformation = 0;
      if ( v35 )
        FltReleaseFileNameInformation(v35);
      return (unsigned int)EaInfoBuffer;
    }
    v16 = v54[0];
  }
  v36 = v64;
  UnionFs::UfsStreamHandleCtx::SynchronizeQueryEa(v64, P);
  if ( (si128.m128i_i64[1] - si128.m128i_i64[0]) >> 4 )
  {
LABEL_81:
    FileObject = 0;
    goto LABEL_83;
  }
  if ( !(_BYTE)v63 )
  {
    if ( (OperationFlags & 1) == 0 )
    {
      FileObject = (ULONG)v36[15].FileObject;
      goto LABEL_83;
    }
    LODWORD(v36[15].FileObject) = 0;
    goto LABEL_81;
  }
  EaLength = Iopb->Parameters.Create.EaLength;
  if ( !EaLength )
  {
    if ( P[0] )
      KeSetEvent((PRKEVENT)P[0], 0, 0);
    utl::vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(&si128);
    if ( v28 )
      ExFreePoolWithTag(v28, 0);
    if ( v15 )
      utl::_RefCountBase::_DecStrong(v15);
    UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v54);
    v38 = FileNameInformation;
    FileNameInformation = 0;
    if ( v38 )
      FltReleaseFileNameInformation(v38);
    return 3221225553LL;
  }
  FileObject = EaLength - 1;
LABEL_83:
  v63 = FileObject;
  (*(void (__fastcall **)(utl::_RefCountBase *, char *))(*(_QWORD *)v16 + 8LL))(v16, &v53[7]);
  if ( !*((_BYTE *)v16 + 8) )
  {
    v41 = *(struct _ERESOURCE **)&v53[7];
    *(_QWORD *)&v53[7] = 0;
    if ( v41 )
    {
      ExReleaseResourceLite(v41);
      KeLeaveCriticalRegion();
    }
    if ( P[0] )
      KeSetEvent((PRKEVENT)P[0], 0, 0);
    utl::vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(&si128);
    if ( v28 )
      ExFreePoolWithTag(v28, 0);
    if ( v15 )
      utl::_RefCountBase::_DecStrong(v15);
    goto LABEL_92;
  }
  LOBYTE(v40) = v53[1];
  EAs = UnionFs::UfsEaPayload::GetEAs(
          (_DWORD)v16,
          v40,
          (unsigned int)&v59,
          (unsigned int)&v63,
          (__int64)&si128,
          v53[0],
          0);
  v44 = EAs;
  if ( EAs == -2147483630 || (unsigned int)(EAs + 1073741743) <= 1 || EAs >= 0 )
  {
    if ( v28 )
      RtlCopyToUser(Iopb->Parameters.Create.EaBuffer, v28, Iopb->Parameters.Read.Length);
    LODWORD(v64[15].FileObject) = v63;
    *(_BYTE *)a5 = 1;
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)EAs,
      (int)v10,
      (struct UnionFs::StackEventTracer *)0x5630005010CLL,
      (unsigned __int64)"UnionFs::HandleQueryEa",
      "PUSH: Copying EAs to buffer",
      Priorityb);
  }
  v45 = *(struct _ERESOURCE **)&v53[7];
  v46 = *(_QWORD *)&v53[7] == 0;
  *(_QWORD *)&v53[7] = 0;
  if ( !v46 )
  {
    ExReleaseResourceLite(v45);
    KeLeaveCriticalRegion();
  }
  if ( P[0] )
    KeSetEvent((PRKEVENT)P[0], 0, 0);
  utl::vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(&si128);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  if ( v15 )
    utl::_RefCountBase::_DecStrong(v15);
  UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v54);
  v47 = FileNameInformation;
  v46 = FileNameInformation == 0;
  FileNameInformation = 0;
  if ( !v46 )
    FltReleaseFileNameInformation(v47);
  return v44;
}

```

## disassembly

```asm
0x14001cbd0  mov     r11, rsp
0x14001cbd3  mov     [r11+8], rbx
0x14001cbd7  mov     [r11+20h], rsi
0x14001cbdb  mov     [r11+18h], r8
0x14001cbdf  push    rdi
0x14001cbe0  push    r12
0x14001cbe2  push    r13
0x14001cbe4  push    r14
0x14001cbe6  push    r15
0x14001cbe8  sub     rsp, 0C0h
0x14001cbef  mov     rdi, r9
0x14001cbf2  mov     r14, rdx
0x14001cbf5  mov     r13, rcx
0x14001cbf8  xor     r15d, r15d
0x14001cbfb  mov     rax, [rsp+0E8h+arg_20]
0x14001cc03  mov     [rax], r15b
0x14001cc06  mov     [rsp+0E8h+FileNameInformation], r15
0x14001cc0b  mov     [r11-78h], r15
0x14001cc0f  mov     rax, [rdx+20h]
0x14001cc13  mov     [r11-70h], rax
0x14001cc17  mov     rax, [rdx+18h]
0x14001cc1b  mov     [r11-68h], rax
0x14001cc1f  mov     rsi, [rsp+0E8h+arg_28]
0x14001cc27  mov     r9, rsi
0x14001cc2a  lea     r8, [rsp+0E8h+FileNameInformation]
0x14001cc2f  mov     edx, 1000101h
0x14001cc34  lea     rcx, [r11-78h]
0x14001cc38  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x14001cc3d  mov     ebx, eax
0x14001cc3f  test    eax, eax
0x14001cc41  jns     short loc_14001CC8C
0x14001cc43  lea     rax, aPushGettingSou_0; "PUSH: Getting source file name informat"...
0x14001cc4a  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001cc4f  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001cc56  mov     r8, 53500050075h; struct UnionFs::StackEventTracer *
0x14001cc60  mov     rdx, rsi; int
0x14001cc63  mov     ecx, ebx; this
0x14001cc65  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001cc6a  mov     rcx, [rsp+0E8h+FileNameInformation]; FileNameInformation
0x14001cc6f  mov     [rsp+0E8h+FileNameInformation], r15
0x14001cc74  test    rcx, rcx
0x14001cc77  jz      short loc_14001CC85
0x14001cc79  call    cs:__imp_FltReleaseFileNameInformation
0x14001cc80  nop     dword ptr [rax+rax+00h]
0x14001cc85  mov     eax, ebx
0x14001cc87  jmp     loc_14001D505
0x14001cc8c  xorps   xmm0, xmm0
0x14001cc8f  movdqu  xmmword ptr [rsp+0E8h+var_90], xmm0
0x14001cc95  mov     [rsp+0E8h+Resource], r15
0x14001cc9a  cmp     dword ptr [rdi+1Ch], 2
0x14001cc9e  jnz     short loc_14001CCAA
0x14001cca0  mov     rax, [rdi+20h]
0x14001cca4  mov     rcx, [rax+18h]
0x14001cca8  jmp     short loc_14001CCB5
0x14001ccaa  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001ccb1  mov     rcx, [rax+58h]; this
0x14001ccb5  mov     qword ptr [rsp+0E8h+Priority], rsi; char *
0x14001ccba  lea     rax, [rsp+0E8h+var_90]
0x14001ccbf  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; struct UnionFs::LookupEaResults *
0x14001ccc4  xor     r9d, r9d; bool
0x14001ccc7  mov     r8, [rsp+0E8h+FileNameInformation]; struct _FLT_FILE_NAME_INFORMATION *
0x14001cccc  mov     rdx, [r14+18h]; struct _FLT_INSTANCE *
0x14001ccd0  call    ?LookupEaEntry@UfsEaTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@_NAEAULookupEaResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsEaTable::LookupEaEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,bool,UnionFs::LookupEaResults &,UnionFs::StackEventTracer &)
0x14001ccd5  mov     ebx, eax
0x14001ccd7  test    eax, eax
0x14001ccd9  jns     short loc_14001CD11
0x14001ccdb  lea     rax, aPushEaTableLoo; "PUSH: EA table lookup"
0x14001cce2  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001cce7  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001ccee  mov     r8, 5600005007Fh; struct UnionFs::StackEventTracer *
0x14001ccf8  mov     rdx, rsi; int
0x14001ccfb  mov     ecx, ebx; this
0x14001ccfd  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001cd02  lea     rcx, [rsp+0E8h+var_90]; this
0x14001cd07  call    ??1LookupEaResults@UnionFs@@QEAA@XZ; UnionFs::LookupEaResults::~LookupEaResults(void)
0x14001cd0c  jmp     loc_14001CC6A
0x14001cd11  mov     rbx, [rsp+0E8h+var_90+8]
0x14001cd16  mov     [rsp+0E8h+var_30], rbx
0x14001cd1e  test    rbx, rbx
0x14001cd21  jz      short loc_14001CD27
0x14001cd23  lock inc dword ptr [rbx+8]
0x14001cd27  mov     r12, [rsp+0E8h+var_90]
0x14001cd2c  test    r12, r12
0x14001cd2f  jnz     short loc_14001CD57
0x14001cd31  test    rbx, rbx
0x14001cd34  jz      short loc_14001CD3E
0x14001cd36  mov     rcx, rbx; this
0x14001cd39  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001cd3e  lea     rcx, [rsp+0E8h+var_90]; this
0x14001cd43  call    ??1LookupEaResults@UnionFs@@QEAA@XZ; UnionFs::LookupEaResults::~LookupEaResults(void)
0x14001cd48  mov     rcx, [rsp+0E8h+FileNameInformation]
0x14001cd4d  mov     [rsp+0E8h+FileNameInformation], r15
0x14001cd52  jmp     loc_14001D2B1
0x14001cd57  mov     rcx, [rsp+0E8h+Resource]; Resource
0x14001cd5c  mov     [rsp+0E8h+Resource], r15
0x14001cd61  test    rcx, rcx
0x14001cd64  jz      short loc_14001CD7E
0x14001cd66  call    cs:__imp_ExReleaseResourceLite
0x14001cd6d  nop     dword ptr [rax+rax+00h]
0x14001cd72  call    cs:__imp_KeLeaveCriticalRegion
0x14001cd79  nop     dword ptr [rax+rax+00h]
0x14001cd7e  mov     r14, [r13+10h]
0x14001cd82  mov     al, [r14+6]
0x14001cd86  mov     [rsp+0E8h+var_A0], al
0x14001cd8a  mov     cl, al
0x14001cd8c  shr     cl, 1
0x14001cd8e  and     cl, 1
0x14001cd91  mov     [rsp+0E8h+var_9F+1], cl
0x14001cd95  and     al, 4
0x14001cd97  mov     byte ptr [rsp+0E8h+arg_8], al
0x14001cd9e  setnz   [rsp+0E8h+var_9F]
0x14001cda3  mov     [rsp+0E8h+var_38], r15
0x14001cdab  cmp     [r14+40h], r15
0x14001cdaf  jz      loc_14001CEBB
0x14001cdb5  mov     rcx, r13; CallbackData
0x14001cdb8  call    cs:__imp_FltLockUserBuffer
0x14001cdbf  nop     dword ptr [rax+rax+00h]
0x14001cdc4  mov     edi, eax
0x14001cdc6  xor     r13d, r13d
0x14001cdc9  test    eax, eax
0x14001cdcb  jns     short loc_14001CE2D
0x14001cdcd  lea     rax, aApiFltlockuser; "API: FltLockUserBuffer"
0x14001cdd4  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001cdd9  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001cde0  mov     r8, 5360005009Dh; struct UnionFs::StackEventTracer *
0x14001cdea  mov     rdx, rsi; int
0x14001cded  mov     ecx, edi; this
0x14001cdef  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001cdf4  test    rbx, rbx
0x14001cdf7  jz      short loc_14001CE01
0x14001cdf9  mov     rcx, rbx; this
0x14001cdfc  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001ce01  lea     rcx, [rsp+0E8h+var_90]; this
0x14001ce06  call    ??1LookupEaResults@UnionFs@@QEAA@XZ; UnionFs::LookupEaResults::~LookupEaResults(void)
0x14001ce0b  mov     rcx, [rsp+0E8h+FileNameInformation]; FileNameInformation
0x14001ce10  mov     [rsp+0E8h+FileNameInformation], r13
0x14001ce15  test    rcx, rcx
0x14001ce18  jz      short loc_14001CE26
0x14001ce1a  call    cs:__imp_FltReleaseFileNameInformation
0x14001ce21  nop     dword ptr [rax+rax+00h]
0x14001ce26  mov     eax, edi
0x14001ce28  jmp     loc_14001D505
0x14001ce2d  mov     rcx, [r14+40h]; MemoryDescriptorList
0x14001ce31  test    byte ptr [rcx+0Ah], 5
0x14001ce35  jz      short loc_14001CE3D
0x14001ce37  mov     rax, [rcx+18h]
0x14001ce3b  jmp     short loc_14001CE5F
0x14001ce3d  mov     [rsp+0E8h+Priority], 40000010h; char *
0x14001ce45  mov     [rsp+0E8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14001ce4a  xor     r9d, r9d; RequestedAddress
0x14001ce4d  xor     edx, edx; AccessMode
0x14001ce4f  lea     r8d, [r9+1]; CacheType
0x14001ce53  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001ce5a  nop     dword ptr [rax+rax+00h]
0x14001ce5f  test    rax, rax
0x14001ce62  jz      short loc_14001CE95
0x14001ce64  lea     rax, aOriginMmgetsys; "ORIGIN: MmGetSystemAddressForMdlSafe"
0x14001ce6b  mov     r8, 537000500A6h; struct UnionFs::StackEventTracer *
0x14001ce75  mov     edi, 0C0000017h
0x14001ce7a  mov     rdx, rsi; int
0x14001ce7d  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001ce84  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001ce89  mov     ecx, edi; this
0x14001ce8b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001ce90  jmp     loc_14001CDF4
0x14001ce95  mov     ecx, [r14+18h]; this
0x14001ce99  test    ecx, ecx
0x14001ce9b  jnz     loc_14001D523
0x14001cea1  mov     [rsp+0E8h+var_48], rcx
0x14001cea9  mov     [rsp+0E8h+var_40], r13
0x14001ceb1  mov     eax, ecx
0x14001ceb3  mov     r9, r13
0x14001ceb6  jmp     loc_14001CF64
0x14001cebb  mov     eax, [r14+18h]
0x14001cebf  cmp     [r13+50h], r15b
0x14001cec3  jz      short loc_14001CF3E
0x14001cec5  mov     edx, eax
0x14001cec7  lea     rcx, [rsp+0E8h+P]
0x14001cecf  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GBGFEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1634027093,0>(unsigned __int64)
0x14001ced4  mov     r15, [rax]
0x14001ced7  xor     r13d, r13d
0x14001ceda  mov     [rax], r13
0x14001cedd  mov     [rsp+0E8h+var_38], r15
0x14001cee5  mov     rcx, [rsp+0E8h+P]; P
0x14001ceed  test    rcx, rcx
0x14001cef0  jz      short loc_14001CF00
0x14001cef2  xor     edx, edx; Tag
0x14001cef4  call    cs:__imp_ExFreePoolWithTag
0x14001cefb  nop     dword ptr [rax+rax+00h]
0x14001cf00  test    r15, r15
0x14001cf03  jnz     short loc_14001CF20
0x14001cf05  lea     rax, aOriginAllocati_91; "ORIGIN: Allocating EA double buffer"
0x14001cf0c  mov     r8, 641000500B7h
0x14001cf16  mov     edi, 0C000009Ah
0x14001cf1b  jmp     loc_14001CE7A
0x14001cf20  mov     eax, [r14+18h]
0x14001cf24  mov     [rsp+0E8h+var_48], rax
0x14001cf2c  mov     [rsp+0E8h+var_40], r15
0x14001cf34  mov     rdi, r15
0x14001cf37  mov     ecx, eax
0x14001cf39  mov     r9, r15
0x14001cf3c  jmp     short loc_14001CF67
0x14001cf3e  mov     r9, [r14+38h]
0x14001cf42  xor     r13d, r13d
0x14001cf45  test    r9, r9
0x14001cf48  jnz     short loc_14001CF52
0x14001cf4a  test    eax, eax
0x14001cf4c  jnz     loc_14001D523
0x14001cf52  mov     [rsp+0E8h+var_48], rax
0x14001cf5a  mov     [rsp+0E8h+var_40], r9
0x14001cf62  mov     ecx, eax
0x14001cf64  mov     rdi, r13
0x14001cf67  cmp     rax, 0Ch
0x14001cf6b  jnb     short loc_14001CFE8
0x14001cf6d  lea     rax, aOriginProvided; "ORIGIN: Provided buffer too small"
0x14001cf74  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001cf79  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001cf80  mov     r8, 539000500C6h; struct UnionFs::StackEventTracer *
0x14001cf8a  mov     rdx, rsi; int
0x14001cf8d  mov     esi, 0C0000004h
0x14001cf92  mov     ecx, esi; this
0x14001cf94  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001cf99  test    rdi, rdi
0x14001cf9c  jz      short loc_14001CFAF
0x14001cf9e  xor     edx, edx; Tag
0x14001cfa0  mov     rcx, rdi; P
0x14001cfa3  call    cs:__imp_ExFreePoolWithTag
0x14001cfaa  nop     dword ptr [rax+rax+00h]
0x14001cfaf  test    rbx, rbx
0x14001cfb2  jz      short loc_14001CFBC
0x14001cfb4  mov     rcx, rbx; this
0x14001cfb7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001cfbc  lea     rcx, [rsp+0E8h+var_90]; this
0x14001cfc1  call    ??1LookupEaResults@UnionFs@@QEAA@XZ; UnionFs::LookupEaResults::~LookupEaResults(void)
0x14001cfc6  mov     rcx, [rsp+0E8h+FileNameInformation]; FileNameInformation
0x14001cfcb  mov     [rsp+0E8h+FileNameInformation], r13
0x14001cfd0  test    rcx, rcx
0x14001cfd3  jz      short loc_14001CFE1
0x14001cfd5  call    cs:__imp_FltReleaseFileNameInformation
0x14001cfdc  nop     dword ptr [rax+rax+00h]
0x14001cfe1  mov     eax, esi
0x14001cfe3  jmp     loc_14001D505
0x14001cfe8  mov     r8d, ecx; Size
0x14001cfeb  xor     edx, edx; Val
0x14001cfed  mov     rcx, r9; void *
0x14001cff0  call    memset
0x14001cff5  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14001cffd  movdqu  [rsp+0E8h+var_78], xmm0
0x14001d003  mov     [rsp+0E8h+var_68], 0FFFFFFFFFFFFFFFFh
0x14001d00f  mov     eax, [r14+28h]
0x14001d013  test    eax, eax
0x14001d015  jz      loc_14001D116
0x14001d01b  mov     rcx, [r14+20h]
0x14001d01f  test    rcx, rcx
0x14001d022  jnz     short loc_14001D05F
0x14001d024  lea     rax, aOriginEalistIs; "ORIGIN: EaList is null"
0x14001d02b  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001d030  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001d037  mov     r8, 53A000500D3h; struct UnionFs::StackEventTracer *
0x14001d041  mov     rdx, rsi; int
0x14001d044  mov     esi, 80000014h
0x14001d049  mov     ecx, esi; this
0x14001d04b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001d050  lea     rcx, [rsp+0E8h+var_78]
0x14001d055  call    ??1?$vector@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@@utl@@@utl@@QEAA@XZ; utl::vector<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(void)
0x14001d05a  jmp     loc_14001CF99
0x14001d05f  mov     [rsp+0E8h+P], rax
0x14001d067  mov     [rsp+0E8h+var_50], rcx
0x14001d06f  mov     r8, rsi
0x14001d072  lea     rdx, [rsp+0E8h+var_78]
0x14001d077  lea     rcx, [rsp+0E8h+P]
0x14001d07f  call    ?GetNamesFromGetEaInfoBuffer@UnionFs@@YAJAEAV?$span@W4byte@gsl@@$0?0@gsl@@AEAV?$vector@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@@utl@@@utl@@AEAVStackEventTracer@1@@Z; UnionFs::GetNamesFromGetEaInfoBuffer(gsl::span<gsl::byte,-1> &,utl::vector<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>> &,UnionFs::StackEventTracer &)
0x14001d084  mov     r12d, eax
0x14001d087  test    eax, eax
0x14001d089  jns     loc_14001D111
0x14001d08f  lea     rax, aPushGettingEaN; "PUSH: Getting EA names from ea list buf"...
0x14001d096  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001d09b  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001d0a2  mov     r8, 53C000500DCh; struct UnionFs::StackEventTracer *
0x14001d0ac  mov     rdx, rsi; int
0x14001d0af  mov     ecx, r12d; this
0x14001d0b2  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001d0b7  lea     rcx, [rsp+0E8h+var_78]
0x14001d0bc  call    ??1?$vector@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@@utl@@@utl@@QEAA@XZ; utl::vector<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(void)
0x14001d0c1  test    rdi, rdi
0x14001d0c4  jz      short loc_14001D0D7
0x14001d0c6  xor     edx, edx; Tag
0x14001d0c8  mov     rcx, rdi; P
0x14001d0cb  call    cs:__imp_ExFreePoolWithTag
0x14001d0d2  nop     dword ptr [rax+rax+00h]
0x14001d0d7  test    rbx, rbx
0x14001d0da  jz      short loc_14001D0E4
0x14001d0dc  mov     rcx, rbx; this
0x14001d0df  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001d0e4  lea     rcx, [rsp+0E8h+var_90]; this
0x14001d0e9  call    ??1LookupEaResults@UnionFs@@QEAA@XZ; UnionFs::LookupEaResults::~LookupEaResults(void)
0x14001d0ee  mov     rcx, [rsp+0E8h+FileNameInformation]; FileNameInformation
0x14001d0f3  mov     [rsp+0E8h+FileNameInformation], r13
0x14001d0f8  test    rcx, rcx
0x14001d0fb  jz      short loc_14001D109
  ... truncated ...
```
