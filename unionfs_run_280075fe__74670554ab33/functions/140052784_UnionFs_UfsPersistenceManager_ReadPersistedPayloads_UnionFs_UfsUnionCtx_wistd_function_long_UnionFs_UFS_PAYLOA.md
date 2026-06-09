# UnionFs::UfsPersistenceManager::ReadPersistedPayloads(UnionFs::UfsUnionCtx &,wistd::function<long (UnionFs::UFS_PAYLOAD_INFORMATION const &,UnionFs::UFS_PAYLOAD_VERSION_HEADER const &,UnionFs::StackEventTracer &)>,ulong *,UnionFs::StackEventTracer &)

- ea: `0x140052784`
- end: `0x140052fd3`
- name: `?ReadPersistedPayloads@UfsPersistenceManager@UnionFs@@QEBAJAEAVUfsUnionCtx@2@V?$function@$$A6AJAEBUUFS_PAYLOAD_INFORMATION@UnionFs@@AEBUUFS_PAYLOAD_VERSION_HEADER@2@AEAVStackEventTracer@2@@Z@wistd@@PEAKAEAVStackEventTracer@2@@Z`
- size: `2127`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1400204a0`
- `0x14005c250`
- `0x140066978`

## callees

- `0x140001008`
- `0x14000f7fc`
- `0x14003daf4`
- `0x14004fd64`
- `0x140050684`
- `0x140051df4`
- `0x140052784`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140079a24`
- `0x140079da0`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140052d8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052df3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052e3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052d8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052df3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052e3e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400528d9`
- `ntoskrnl!ObfDereferenceObject` at `0x14005296b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400528d9`
- `ntoskrnl!ObfDereferenceObject` at `0x14005296b`
- `FLTMGR!FltReadFile` at `0x140052b7f`
- `FLTMGR!FltReadFile` at `0x140052b7f`
- `FLTMGR!FltClose` at `0x1400528ee`
- `FLTMGR!FltClose` at `0x140052980`
- `FLTMGR!FltClose` at `0x1400528ee`
- `FLTMGR!FltClose` at `0x140052980`
- `FLTMGR!FltQueryInformationFile` at `0x1400529ef`
- `FLTMGR!FltQueryInformationFile` at `0x1400529ef`

## string_xrefs

- `0x1400528a5`: `PUSH: Opening payload file`
- `0x1400527da`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x14005290b`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052a1f`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052bf9`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052dcc`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052e17`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052e60`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052f13`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052f49`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052f77`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x1400528fa`: `PUSH: Opening file to read`
- `0x140052f38`: `API: Reading chunks from payload file`
- `0x140052c04`: `Could not read entire payload chunk, may be old version or corrupt`
- `0x140052e4f`: `PUSH: Applying ReadPersistedPayloadsCallback`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPersistenceManager::ReadPersistedPayloads(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        __int64 a5)
{
  __int64 v7; // r13
  __int64 *v8; // r12
  __int64 v9; // r8
  const char *v10; // r9
  struct _FILE_OBJECT *v11; // r15
  NTSTATUS v12; // ebx
  PVOID v13; // rcx
  __int64 v14; // rcx
  void (*v15)(void); // rax
  __int64 v16; // rax
  PVOID v17; // rcx
  unsigned __int64 *v18; // rdx
  __int64 *v19; // rax
  volatile signed __int32 *v20; // rbx
  __int64 v21; // rdi
  NTSTATUS v22; // edi
  __int64 v23; // rcx
  __int64 v25; // r15
  unsigned __int64 *v26; // rdx
  __int64 *v27; // rax
  volatile signed __int32 *v28; // rbx
  __int64 v29; // rdi
  _QWORD *v30; // rdx
  __int64 *v31; // rdi
  ULONG v32; // eax
  char v33; // cl
  unsigned int v34; // r15d
  unsigned __int64 *v35; // rdx
  __int64 *v36; // rax
  volatile signed __int32 *v37; // r15
  __int64 v38; // rbx
  FsFltWil::Details *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  unsigned int *v42; // r13
  int v43; // eax
  __int64 v44; // rcx
  unsigned int v45; // ecx
  const char *v46; // rax
  __int64 v47; // r8
  __int64 v48; // rcx
  __int64 v49; // rcx
  const char *LengthReturned; // [rsp+28h] [rbp-B9h]
  const char *LengthReturneda; // [rsp+28h] [rbp-B9h]
  const char *LengthReturnedb; // [rsp+28h] [rbp-B9h]
  const char *LengthReturnedc; // [rsp+28h] [rbp-B9h]
  char v54; // [rsp+50h] [rbp-91h]
  ULONG Length; // [rsp+54h] [rbp-8Dh]
  PVOID Buffer; // [rsp+58h] [rbp-89h] BYREF
  ULONG BytesRead; // [rsp+60h] [rbp-81h] BYREF
  unsigned int v58; // [rsp+64h] [rbp-7Dh] BYREF
  PFILE_OBJECT FileObject; // [rsp+68h] [rbp-79h] BYREF
  PVOID Object[2]; // [rsp+70h] [rbp-71h] BYREF
  const char *v61; // [rsp+80h] [rbp-61h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+88h] [rbp-59h] BYREF
  __int64 v63; // [rsp+90h] [rbp-51h] BYREF
  __int64 *v64; // [rsp+98h] [rbp-49h]
  __int64 v65; // [rsp+A0h] [rbp-41h]
  const char *v66; // [rsp+A8h] [rbp-39h] BYREF
  char v67[8]; // [rsp+B0h] [rbp-31h] BYREF
  const char *v68; // [rsp+B8h] [rbp-29h] BYREF
  _DWORD *v69; // [rsp+C0h] [rbp-21h]
  __int64 v70; // [rsp+C8h] [rbp-19h]
  __int128 FileInformation; // [rsp+D0h] [rbp-11h] BYREF
  __int64 v72; // [rsp+E0h] [rbp-1h]

  v70 = a2;
  v7 = a2;
  v69 = a4;
  v8 = a1;
  v64 = a1;
  v9 = 0x8000;
  v10 = "onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp";
  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x8000) != 0
    && (qword_14009E190 & 0x8000) == qword_14009E190 )
  {
    Buffer = (PVOID)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads";
    v61 = "ENTER";
    BytesRead = 173;
    FileObject = (PFILE_OBJECT)"onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      qword_14009E190,
      (unsigned int)&dword_1400982BC,
      0x8000,
      (unsigned int)"onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp",
      (__int64)&v61,
      (__int64)&Buffer,
      (__int64)&FileObject,
      (__int64)&BytesRead);
  }
  *a4 = 0;
  FileObject = (PFILE_OBJECT)(*(__int64 (__fastcall **)(__int64 *, __int64, __int64, const char *))(*v8 + 96))(
                               v8,
                               v7,
                               v9,
                               v10);
  v11 = FileObject;
  if ( !FileObject )
  {
    *(_OWORD *)Object = 0;
    v12 = UnionFs::UfsPersistenceManager::OpenPersistentPayloadFile(v8, v7, Object, a5, 3);
    if ( v12 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v12,
        a5,
        (struct UnionFs::StackEventTracer *)0x7B60017009DLL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::GetPayloadFileObject",
        "PUSH: Opening payload file",
        LengthReturned);
      v13 = Object[1];
      Object[1] = 0;
      if ( v13 )
        ObfDereferenceObject(v13);
      if ( Object[0] )
        FltClose(Object[0]);
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v12,
        a5,
        (struct UnionFs::StackEventTracer *)0x32B001700BBLL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
        "PUSH: Opening file to read",
        LengthReturneda);
LABEL_12:
      lambda_fd806375622af003ca3a1e8511b068d0_::operator()();
      v14 = *(_QWORD *)(a3 + 112);
      if ( v14 )
      {
        v15 = *(void (**)(void))(*(_QWORD *)v14 + 24LL);
        goto LABEL_92;
      }
      return (unsigned int)v12;
    }
    v16 = *v8;
    v11 = (struct _FILE_OBJECT *)Object[1];
    FileObject = (PFILE_OBJECT)Object[1];
    (*(void (__fastcall **)(__int64 *, __int64, PVOID *))(v16 + 104))(v8, v7, Object);
    v17 = Object[1];
    Object[1] = 0;
    if ( v17 )
      ObfDereferenceObject(v17);
    if ( Object[0] )
      FltClose(Object[0]);
  }
  FileInformation = 0;
  v72 = 0;
  FsFltWil::AcquirePushLockShared(&Buffer, v7 + 72);
  v19 = *(__int64 **)(v7 + 48);
  v20 = (volatile signed __int32 *)v19[1];
  v21 = *v19;
  if ( v20 )
    _InterlockedIncrement(v20 + 2);
  if ( Buffer )
    FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Buffer, v18);
  v22 = FltQueryInformationFile(**(PFLT_INSTANCE **)(v21 + 8), v11, &FileInformation, 0x18u, FileStandardInformation, 0);
  if ( v20 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
  if ( v22 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v22,
      a5,
      (struct UnionFs::StackEventTracer *)0x2C5001700C8LL,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
      "API: Querying standard info",
      LengthReturnedb);
    lambda_fd806375622af003ca3a1e8511b068d0_::operator()();
    v23 = *(_QWORD *)(a3 + 112);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23);
    return (unsigned int)v22;
  }
  if ( !*((_QWORD *)&FileInformation + 1) )
  {
LABEL_72:
    lambda_fd806375622af003ca3a1e8511b068d0_::operator()();
    v48 = *(_QWORD *)(a3 + 112);
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 24LL))(v48);
    return 0;
  }
  v25 = *(unsigned int *)(v7 + 300);
  Length = *(_DWORD *)(v7 + 300);
  ByteOffset.QuadPart = 0;
  FsFltWil::AcquirePushLockShared(&Buffer, v7 + 72);
  v27 = *(__int64 **)(v7 + 48);
  v28 = (volatile signed __int32 *)v27[1];
  v29 = *v27;
  if ( v28 )
    _InterlockedIncrement(v28 + 2);
  if ( Buffer )
    FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Buffer, v26);
  v30 = *(_QWORD **)(v29 + 8);
  v65 = v25;
  utl::make_unique_aligned_pool<enum gsl::byte [0],1,1836074581,0>(&Buffer, *v30, v25);
  if ( v28 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v28);
  v31 = (__int64 *)Buffer;
  if ( !Buffer )
  {
    v12 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a5,
      (struct UnionFs::StackEventTracer *)0x4A4001700E2LL,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
      "ORIGIN: Allocating payload info buffer",
      LengthReturnedb);
    goto LABEL_90;
  }
  v32 = Length;
  v33 = 1;
  v34 = 0;
  v54 = 1;
  v63 = 0;
  while ( 1 )
  {
    if ( !v33 )
    {
      if ( v34 != v32 )
        goto LABEL_57;
      ByteOffset.QuadPart += v65;
    }
    BytesRead = 0;
    FsFltWil::AcquirePushLockShared(&Buffer, v7 + 72);
    v36 = *(__int64 **)(v7 + 48);
    v37 = (volatile signed __int32 *)v36[1];
    v38 = *v36;
    if ( v37 )
      _InterlockedIncrement(v37 + 2);
    v39 = (FsFltWil::Details *)Buffer;
    Buffer = 0;
    if ( v39 )
      FsFltWil::Details::ReleasePushLockShared(v39, v35);
    v12 = FltReadFile(**(PFLT_INSTANCE **)(v38 + 8), FileObject, &ByteOffset, Length, v31, 0, &BytesRead, 0, 0);
    if ( v37 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v37);
    if ( v12 < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v12,
        a5,
        (struct UnionFs::StackEventTracer *)0x2BC00170104LL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
        "API: Reading chunks from payload file",
        LengthReturnedb);
LABEL_76:
      if ( v31 )
        ExFreePoolWithTag(v31, 0);
      goto LABEL_12;
    }
    if ( BytesRead != Length
      && (unsigned int)dword_14009E178 > 3
      && (qword_14009E188 & 0x8000) != 0
      && (qword_14009E190 & 0x8000) == qword_14009E190 )
    {
      LODWORD(v61) = 266;
      v66 = "onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp";
      *(_QWORD *)v67 = "UnionFs::UfsPersistenceManager::ReadPersistedPayloads";
      v68 = "Could not read entire payload chunk, may be old version or corrupt";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        qword_14009E190,
        (unsigned int)byte_1400980F5,
        v40,
        v41,
        (__int64)&v68,
        (__int64)v67,
        (__int64)&v66,
        (__int64)&v61);
    }
    v34 = 0;
    if ( v54 )
    {
      v63 = *v31;
      if ( (*(unsigned __int8 (__fastcall **)(__int64 *, __int64 *))(*v8 + 152))(v8, &v63) )
        v34 = 8;
      else
        (*(void (__fastcall **)(__int64 *, __int64))(*v8 + 24))(v8, v7);
      v54 = 0;
    }
LABEL_57:
    if ( Length - v34 < 0x14 )
      break;
    v42 = (unsigned int *)((char *)v31 + v34);
    v58 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, unsigned int *, __int64))(*v64 + 128))(
            v64,
            v42,
            &v58,
            a5);
    if ( v12 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v12,
        a5,
        (struct UnionFs::StackEventTracer *)0x663001705B8LL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ValidatePayloadInfo",
        "PUSH: Getting payload size",
        LengthReturnedb);
      goto LABEL_87;
    }
    if ( v58 > Length - v34 )
    {
      v46 = "ORIGIN: Entry size is greater than remaining chunk size";
      v47 = 0x69B001705BFLL;
      goto LABEL_86;
    }
    if ( *v42 && v58 > *v42 )
    {
      v46 = "ORIGIN: Entry size is greater than NextEntryOffset";
      v47 = 0x7E001705C8LL;
      goto LABEL_86;
    }
    v8 = v64;
    v43 = (*(__int64 (__fastcall **)(__int64 *, char *, __int64))(*v64 + 120))(v64, (char *)v31 + v34, a5);
    v12 = v43;
    if ( v43 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v43,
        a5,
        (struct UnionFs::StackEventTracer *)0x68B001705CELL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ValidatePayloadInfo",
        "PUSH: Validating payload info",
        LengthReturnedb);
      goto LABEL_87;
    }
    v44 = *(_QWORD *)(a3 + 112);
    if ( !v44 )
      wistd::__throw_bad_function_call(0);
    v12 = (*(__int64 (__fastcall **)(__int64, char *, __int64 *, __int64))(*(_QWORD *)v44 + 32LL))(
            v44,
            (char *)v31 + v34,
            &v63,
            a5);
    if ( v12 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v12,
        a5,
        (struct UnionFs::StackEventTracer *)0x22A00170139LL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
        "PUSH: Applying ReadPersistedPayloadsCallback",
        LengthReturnedb);
      goto LABEL_76;
    }
    v45 = v34 + *v42;
    if ( v45 < v34 )
    {
      v12 = -1073741675;
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)0xC0000095LL,
        a5,
        (struct UnionFs::StackEventTracer *)0x49E0017013ELL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
        "API: Adding NextEntryOffset to bufferOffset",
        LengthReturnedb);
      goto LABEL_79;
    }
    v32 = Length;
    v34 += *v42;
    if ( v45 > Length )
    {
      v12 = -1073741566;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000102LL,
        a5,
        (struct UnionFs::StackEventTracer *)0x4AF00170145LL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
        "ORIGIN: Payload record extends beyond buffer",
        LengthReturnedb);
      goto LABEL_76;
    }
    ++*v69;
    if ( !*v42 )
    {
      if ( v31 )
        ExFreePoolWithTag(v31, 0);
      goto LABEL_72;
    }
    v7 = v70;
    v33 = v54;
  }
  v46 = "ORIGIN: RemainingChunkSize less than the size of payload info";
  v47 = 0x4B9001705B1LL;
LABEL_86:
  v12 = -1073741566;
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC0000102LL,
    a5,
    (struct UnionFs::StackEventTracer *)v47,
    (unsigned __int64)"UnionFs::UfsPersistenceManager::ValidatePayloadInfo",
    v46,
    LengthReturnedb);
LABEL_87:
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v12,
    a5,
    (struct UnionFs::StackEventTracer *)0x69A00170134LL,
    (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
    "PUSH: Validating payload info",
    LengthReturnedc);
LABEL_79:
  if ( v31 )
    ExFreePoolWithTag(v31, 0);
LABEL_90:
  lambda_fd806375622af003ca3a1e8511b068d0_::operator()();
  v49 = *(_QWORD *)(a3 + 112);
  if ( v49 )
  {
    v15 = *(void (**)(void))(*(_QWORD *)v49 + 24LL);
LABEL_92:
    v15();
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140052784  push    rbp
0x140052786  push    rbx
0x140052787  push    rsi
0x140052788  push    rdi
0x140052789  push    r12
0x14005278b  push    r13
0x14005278d  push    r14
0x14005278f  push    r15
0x140052791  lea     rbp, [rsp-17h]
0x140052796  sub     rsp, 0F8h
0x14005279d  mov     rax, cs:__security_cookie
0x1400527a4  xor     rax, rsp
0x1400527a7  mov     [rbp+4Fh+var_48], rax
0x1400527ab  mov     eax, cs:dword_14009E178
0x1400527b1  mov     rbx, r9
0x1400527b4  mov     rsi, qword ptr [rbp+4Fh+arg_20]
0x1400527b8  mov     r14, r8
0x1400527bb  mov     [rbp+4Fh+var_68], rdx
0x1400527bf  mov     r13, rdx
0x1400527c2  mov     [rbp+4Fh+var_70], rbx
0x1400527c6  mov     r12, rcx
0x1400527c9  mov     [rbp+4Fh+var_98], rcx
0x1400527cd  mov     r8d, 8000h
0x1400527d3  lea     r9, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x1400527da  lea     rdx, aUnionfsUfspers_5; "UnionFs::UfsPersistenceManager::ReadPer"...
0x1400527e1  cmp     eax, 5
0x1400527e4  jbe     short loc_140052852
0x1400527e6  mov     rcx, cs:qword_14009E190
0x1400527ed  mov     rax, cs:qword_14009E188
0x1400527f4  test    r8, rax
0x1400527f7  jz      short loc_140052852
0x1400527f9  mov     rax, rcx
0x1400527fc  and     rax, r8
0x1400527ff  cmp     rax, rcx
0x140052802  jnz     short loc_140052852
0x140052804  lea     rax, aEnter; "ENTER"
0x14005280b  mov     [rsp+130h+Buffer], rdx
0x140052810  mov     [rbp+4Fh+var_B0], rax
0x140052814  lea     rdx, dword_1400982BC
0x14005281b  lea     rax, [rsp+130h+var_D0]
0x140052820  mov     [rsp+130h+var_D0], 0ADh
0x140052828  mov     [rsp+130h+CallbackRoutine], rax
0x14005282d  lea     rax, [rbp+4Fh+FileObject]
0x140052831  mov     [rsp+130h+BytesRead], rax
0x140052836  lea     rax, [rsp+130h+Buffer]
0x14005283b  mov     [rsp+130h+LengthReturned], rax; char *
0x140052840  lea     rax, [rbp+4Fh+var_B0]
0x140052844  mov     qword ptr [rsp+130h+FileInformationClass], rax
0x140052849  mov     [rbp+4Fh+FileObject], r9
0x14005284d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140052852  xor     edi, edi
0x140052854  mov     rdx, r13
0x140052857  mov     [rbx], edi
0x140052859  mov     rcx, r12
0x14005285c  mov     rax, [r12]
0x140052860  mov     rax, [rax+60h]
0x140052864  call    _guard_dispatch_icall
0x140052869  mov     [rbp+4Fh+FileObject], rax
0x14005286d  mov     r15, rax
0x140052870  test    rax, rax
0x140052873  jnz     loc_14005298C
0x140052879  xorps   xmm0, xmm0
0x14005287c  mov     [rsp+130h+FileInformationClass], 3
0x140052884  mov     r9, rsi
0x140052887  lea     r8, [rbp+4Fh+Object]
0x14005288b  mov     rdx, r13
0x14005288e  mov     rcx, r12
0x140052891  movdqu  xmmword ptr [rbp+4Fh+Object], xmm0
0x140052896  call    ?OpenPersistentPayloadFile@UfsPersistenceManager@UnionFs@@IEBAJAEBVUfsUnionCtx@2@AEAU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@utl@@AEAVStackEventTracer@2@W4OpenOrCreateDisposition@Utils@2@@Z; UnionFs::UfsPersistenceManager::OpenPersistentPayloadFile(UnionFs::UfsUnionCtx const &,utl::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>> &,UnionFs::StackEventTracer &,UnionFs::Utils::OpenOrCreateDisposition)
0x14005289b  mov     ebx, eax
0x14005289d  test    eax, eax
0x14005289f  jns     loc_14005293F
0x1400528a5  lea     rax, aPushOpeningPay; "PUSH: Opening payload file"
0x1400528ac  mov     r8, 7B60017009Dh; struct UnionFs::StackEventTracer *
0x1400528b6  lea     r9, aUnionfsUfspers_7; "UnionFs::UfsPersistenceManager::GetPayl"...
0x1400528bd  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x1400528c2  mov     rdx, rsi; int
0x1400528c5  mov     ecx, ebx; this
0x1400528c7  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400528cc  mov     rcx, [rbp+4Fh+Object+8]; Object
0x1400528d0  mov     [rbp+4Fh+Object+8], rdi
0x1400528d4  test    rcx, rcx
0x1400528d7  jz      short loc_1400528E5
0x1400528d9  call    cs:__imp_ObfDereferenceObject
0x1400528e0  nop     dword ptr [rax+rax+00h]
0x1400528e5  mov     rcx, [rbp+4Fh+Object]; FileHandle
0x1400528e9  test    rcx, rcx
0x1400528ec  jz      short loc_1400528FA
0x1400528ee  call    cs:__imp_FltClose
0x1400528f5  nop     dword ptr [rax+rax+00h]
0x1400528fa  lea     rax, aPushOpeningFil; "PUSH: Opening file to read"
0x140052901  mov     r8, 32B001700BBh; struct UnionFs::StackEventTracer *
0x14005290b  lea     r9, aUnionfsUfspers_5; "UnionFs::UfsPersistenceManager::ReadPer"...
0x140052912  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x140052917  mov     rdx, rsi; int
0x14005291a  mov     ecx, ebx; this
0x14005291c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140052921  call    _lambda_fd806375622af003ca3a1e8511b068d0___operator__
0x140052926  mov     rcx, [r14+70h]
0x14005292a  test    rcx, rcx
0x14005292d  jz      loc_140052FAA
0x140052933  mov     rax, [rcx]
0x140052936  mov     rax, [rax+18h]
0x14005293a  jmp     loc_140052FA5
0x14005293f  mov     rax, [r12]
0x140052943  lea     r8, [rbp+4Fh+Object]
0x140052947  mov     r15, [rbp+4Fh+Object+8]
0x14005294b  mov     rdx, r13
0x14005294e  mov     rcx, r12
0x140052951  mov     [rbp+4Fh+FileObject], r15
0x140052955  mov     rax, [rax+68h]
0x140052959  call    _guard_dispatch_icall
0x14005295e  mov     rcx, [rbp+4Fh+Object+8]; Object
0x140052962  mov     [rbp+4Fh+Object+8], rdi
0x140052966  test    rcx, rcx
0x140052969  jz      short loc_140052977
0x14005296b  call    cs:__imp_ObfDereferenceObject
0x140052972  nop     dword ptr [rax+rax+00h]
0x140052977  mov     rcx, [rbp+4Fh+Object]; FileHandle
0x14005297b  test    rcx, rcx
0x14005297e  jz      short loc_14005298C
0x140052980  call    cs:__imp_FltClose
0x140052987  nop     dword ptr [rax+rax+00h]
0x14005298c  xorps   xmm0, xmm0
0x14005298f  lea     rdx, [r13+48h]
0x140052993  xor     eax, eax
0x140052995  lea     rcx, [rsp+130h+Buffer]
0x14005299a  movups  [rbp+4Fh+FileInformation], xmm0
0x14005299e  mov     [rbp+4Fh+var_50], rax
0x1400529a2  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x1400529a7  mov     rax, [r13+30h]
0x1400529ab  mov     rbx, [rax+8]
0x1400529af  mov     rdi, [rax]
0x1400529b2  test    rbx, rbx
0x1400529b5  jz      short loc_1400529BB
0x1400529b7  lock inc dword ptr [rbx+8]
0x1400529bb  mov     rcx, [rsp+130h+Buffer]; this
0x1400529c0  test    rcx, rcx
0x1400529c3  jz      short loc_1400529CA
0x1400529c5  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400529ca  mov     rcx, [rdi+8]
0x1400529ce  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x1400529d2  mov     [rsp+130h+LengthReturned], 0; char *
0x1400529db  mov     r9d, 18h; Length
0x1400529e1  mov     rdx, r15; FileObject
0x1400529e4  mov     [rsp+130h+FileInformationClass], 5; FileInformationClass
0x1400529ec  mov     rcx, [rcx]; Instance
0x1400529ef  call    cs:__imp_FltQueryInformationFile
0x1400529f6  nop     dword ptr [rax+rax+00h]
0x1400529fb  mov     edi, eax
0x1400529fd  test    rbx, rbx
0x140052a00  jz      short loc_140052A0A
0x140052a02  mov     rcx, rbx; this
0x140052a05  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140052a0a  test    edi, edi
0x140052a0c  jns     short loc_140052A56
0x140052a0e  lea     rax, aApiQueryingSta; "API: Querying standard info"
0x140052a15  mov     r8, 2C5001700C8h; struct UnionFs::StackEventTracer *
0x140052a1f  lea     r9, aUnionfsUfspers_5; "UnionFs::UfsPersistenceManager::ReadPer"...
0x140052a26  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x140052a2b  mov     rdx, rsi; int
0x140052a2e  mov     ecx, edi; this
0x140052a30  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140052a35  call    _lambda_fd806375622af003ca3a1e8511b068d0___operator__
0x140052a3a  mov     rcx, [r14+70h]
0x140052a3e  test    rcx, rcx
0x140052a41  jz      short loc_140052A4F
0x140052a43  mov     rax, [rcx]
0x140052a46  mov     rax, [rax+18h]
0x140052a4a  call    _guard_dispatch_icall
0x140052a4f  mov     eax, edi
0x140052a51  jmp     loc_140052FAC
0x140052a56  cmp     qword ptr [rbp+4Fh+FileInformation+8], 0
0x140052a5b  jz      loc_140052D98
0x140052a61  mov     r15d, [r13+12Ch]
0x140052a68  lea     rdx, [r13+48h]
0x140052a6c  lea     rcx, [rsp+130h+Buffer]
0x140052a71  mov     [rsp+130h+Length], r15d
0x140052a76  mov     qword ptr [rbp+4Fh+ByteOffset], 0
0x140052a7e  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140052a83  mov     rax, [r13+30h]
0x140052a87  mov     rbx, [rax+8]
0x140052a8b  mov     rdi, [rax]
0x140052a8e  test    rbx, rbx
0x140052a91  jz      short loc_140052A97
0x140052a93  lock inc dword ptr [rbx+8]
0x140052a97  mov     rcx, [rsp+130h+Buffer]; this
0x140052a9c  test    rcx, rcx
0x140052a9f  jz      short loc_140052AA6
0x140052aa1  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140052aa6  mov     rdx, [rdi+8]
0x140052aaa  lea     rcx, [rsp+130h+Buffer]
0x140052aaf  mov     r8, r15
0x140052ab2  mov     [rbp+4Fh+var_90], r15
0x140052ab6  mov     rdx, [rdx]
0x140052ab9  call    ??$make_unique_aligned_pool@$$BY0A@W4byte@gsl@@$00$0GNHAEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@PEAU_FLT_INSTANCE@@_K@Z; utl::make_unique_aligned_pool<gsl::byte [0],1,1836074581,0>(_FLT_INSTANCE *,unsigned __int64)
0x140052abe  test    rbx, rbx
0x140052ac1  jz      short loc_140052ACB
0x140052ac3  mov     rcx, rbx; this
0x140052ac6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140052acb  mov     rdi, [rsp+130h+Buffer]
0x140052ad0  test    rdi, rdi
0x140052ad3  jz      loc_140052F64
0x140052ad9  mov     eax, [rsp+130h+Length]
0x140052add  mov     cl, 1
0x140052adf  xor     r15d, r15d
0x140052ae2  mov     [rsp+130h+var_E0], cl
0x140052ae6  mov     [rbp+4Fh+var_A0], r15
0x140052aea  test    cl, cl
0x140052aec  jnz     short loc_140052AFF
0x140052aee  cmp     r15d, eax
0x140052af1  jnz     loc_140052C85
0x140052af7  mov     rax, [rbp+4Fh+var_90]
0x140052afb  add     qword ptr [rbp+4Fh+ByteOffset], rax
0x140052aff  lea     rdx, [r13+48h]
0x140052b03  mov     [rsp+130h+var_D0], 0
0x140052b0b  lea     rcx, [rsp+130h+Buffer]
0x140052b10  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140052b15  mov     rax, [r13+30h]
0x140052b19  mov     r15, [rax+8]
0x140052b1d  mov     rbx, [rax]
0x140052b20  test    r15, r15
0x140052b23  jz      short loc_140052B2A
0x140052b25  lock inc dword ptr [r15+8]
0x140052b2a  mov     rcx, [rsp+130h+Buffer]; this
0x140052b2f  mov     [rsp+130h+Buffer], 0
0x140052b38  test    rcx, rcx
0x140052b3b  jz      short loc_140052B42
0x140052b3d  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140052b42  mov     rcx, [rbx+8]
0x140052b46  lea     rax, [rsp+130h+var_D0]
0x140052b4b  mov     r9d, [rsp+130h+Length]; Length
0x140052b50  lea     r8, [rbp+4Fh+ByteOffset]; ByteOffset
0x140052b54  mov     rdx, [rbp+4Fh+FileObject]; FileObject
0x140052b58  mov     [rsp+130h+CallbackContext], 0; CallbackContext
0x140052b61  mov     rcx, [rcx]; InitiatingInstance
0x140052b64  mov     [rsp+130h+CallbackRoutine], 0; CallbackRoutine
0x140052b6d  mov     [rsp+130h+BytesRead], rax; BytesRead
0x140052b72  mov     dword ptr [rsp+130h+LengthReturned], 0; char *
0x140052b7a  mov     qword ptr [rsp+130h+FileInformationClass], rdi; Buffer
0x140052b7f  call    cs:__imp_FltReadFile
0x140052b86  nop     dword ptr [rax+rax+00h]
0x140052b8b  mov     ebx, eax
0x140052b8d  test    r15, r15
0x140052b90  jz      short loc_140052B9A
0x140052b92  mov     rcx, r15; this
0x140052b95  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140052b9a  test    ebx, ebx
0x140052b9c  js      loc_140052F38
0x140052ba2  mov     r15d, [rsp+130h+Length]
0x140052ba7  cmp     [rsp+130h+var_D0], r15d
0x140052bac  jz      loc_140052C38
0x140052bb2  mov     eax, cs:dword_14009E178
0x140052bb8  cmp     eax, 3
0x140052bbb  jbe     short loc_140052C38
0x140052bbd  mov     rcx, cs:qword_14009E190
0x140052bc4  mov     edx, 8000h
0x140052bc9  mov     rax, cs:qword_14009E188
0x140052bd0  test    rdx, rax
0x140052bd3  jz      short loc_140052C38
0x140052bd5  mov     rax, rcx
0x140052bd8  and     rax, rdx
0x140052bdb  cmp     rax, rcx
0x140052bde  jnz     short loc_140052C38
0x140052be0  lea     rax, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x140052be7  mov     dword ptr [rbp+4Fh+var_B0], 10Ah
0x140052bee  mov     [rbp+4Fh+var_88], rax
0x140052bf2  lea     rdx, byte_1400980F5
0x140052bf9  lea     rax, aUnionfsUfspers_5; "UnionFs::UfsPersistenceManager::ReadPer"...
0x140052c00  mov     qword ptr [rbp+4Fh+var_80], rax
0x140052c04  lea     rax, aCouldNotReadEn; "Could not read entire payload chunk, ma"...
0x140052c0b  mov     [rbp+4Fh+var_78], rax
0x140052c0f  lea     rax, [rbp+4Fh+var_B0]
0x140052c13  mov     [rsp+130h+CallbackRoutine], rax
0x140052c18  lea     rax, [rbp+4Fh+var_88]
0x140052c1c  mov     [rsp+130h+BytesRead], rax
0x140052c21  lea     rax, [rbp+4Fh+var_80]
0x140052c25  mov     [rsp+130h+LengthReturned], rax; char *
0x140052c2a  lea     rax, [rbp+4Fh+var_78]
0x140052c2e  mov     qword ptr [rsp+130h+FileInformationClass], rax
0x140052c33  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140052c38  xor     r15d, r15d
0x140052c3b  cmp     [rsp+130h+var_E0], r15b
0x140052c40  jz      short loc_140052C85
0x140052c42  mov     rax, [rdi]
0x140052c45  lea     rdx, [rbp+4Fh+var_A0]
0x140052c49  mov     [rbp+4Fh+var_A0], rax
0x140052c4d  mov     rcx, r12
0x140052c50  mov     rax, [r12]
0x140052c54  mov     rax, [rax+98h]
0x140052c5b  call    _guard_dispatch_icall
0x140052c60  test    al, al
0x140052c62  jnz     short loc_140052C79
0x140052c64  mov     rax, [r12]
0x140052c68  mov     rdx, r13
0x140052c6b  mov     rcx, r12
0x140052c6e  mov     rax, [rax+18h]
0x140052c72  call    _guard_dispatch_icall
0x140052c77  jmp     short loc_140052C7F
0x140052c79  mov     r15d, 8
  ... truncated ...
```
