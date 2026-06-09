# UnionFs::UnionFsFilter::PostRead(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)

- ea: `0x140054200`
- end: `0x140054424`
- name: `?PostRead@UnionFsFilter@UnionFs@@SA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z`
- size: `548`
- prototype: `FLT_POSTOP_CALLBACK_STATUS __stdcall(PFLT_CALLBACK_DATA Data, PCFLT_RELATED_OBJECTS FltObjects, PVOID CompletionContext, FLT_POST_OPERATION_FLAGS Flags)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000110c`
- `0x140054200`
- `0x140079a24`
- `0x140079da0`
- `0x140079df4`
- `0x14007af90`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14005422d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005429b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005422d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005429b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400543fd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400543fd`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x140054269`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x140054269`

## string_xrefs

- `0x1400542bb`: `onecore\base\fs\unionfs\sys\read.cpp`
- `0x140054281`: `Failed to post read completion processing`
- `0x1400542c6`: `UnionFs::UnionFsFilter::PostRead`
- `0x140054383`: `!shadowFileObject->PrivateCacheMap || (shadowFileObject->PrivateCacheMap == backingFileObject->PrivateCacheMap)`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PostRead(
        PFLT_CALLBACK_DATA Data,
        struct _FLT_RELATED_OBJECTS *FltObjects,
        PVOID CompletionContext,
        FLT_POST_OPERATION_FLAGS Flags)
{
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  PFILE_OBJECT FileObject; // rsi
  _QWORD *FsContext2; // rbx
  __int64 v14; // rbx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  __int64 Information_low; // r14
  int v17; // r12d
  enum _FLT_POSTOP_CALLBACK_STATUS IrpFlags; // ecx
  char v19; // r15
  bool v20; // r15
  SECTION_OBJECT_POINTERS *v21; // rax
  PVOID PrivateCacheMap; // rax
  __int64 v23; // rcx
  int v24; // [rsp+50h] [rbp-20h] BYREF
  const char *v25; // [rsp+58h] [rbp-18h] BYREF
  const char *v26; // [rsp+60h] [rbp-10h] BYREF
  const char *v27; // [rsp+68h] [rbp-8h] BYREF
  FsFltWil::Details *QuadPart; // [rsp+C0h] [rbp+50h] BYREF
  enum _FLT_POSTOP_CALLBACK_STATUS RetPostOperationStatus; // [rsp+C8h] [rbp+58h] BYREF

  if ( (Flags & 1) == 0 )
  {
    if ( KeGetCurrentIrql() >= 2u )
    {
      RetPostOperationStatus = FLT_POSTOP_FINISHED_PROCESSING;
      if ( FltDoCompletionProcessingWhenSafe(
             Data,
             FltObjects,
             CompletionContext,
             Flags,
             UnionFs::UnionFsFilter::PostRead,
             &RetPostOperationStatus) )
      {
        return (unsigned int)RetPostOperationStatus;
      }
      MicrosoftTelemetryAssertTriggeredMsgKM("Failed to post read completion processing");
      if ( (unsigned int)dword_14009E178 > 2 )
      {
        v24 = 160;
        LODWORD(QuadPart) = KeGetCurrentIrql();
        v25 = "onecore\\base\\fs\\unionfs\\sys\\read.cpp";
        v26 = "UnionFs::UnionFsFilter::PostRead";
        v27 = "Failed to post read completion processing";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v9,
          (unsigned int)byte_1400985D9,
          v10,
          v11,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&QuadPart);
      }
    }
    FileObject = FltObjects->FileObject;
    FsContext2 = FileObject->FsContext2;
    FsFltWil::AcquirePushLockShared(&QuadPart, FsContext2 + 4);
    v14 = FsContext2[3];
    if ( QuadPart )
      FsFltWil::Details::ReleasePushLockShared(QuadPart, (unsigned __int64 *)&FltObjects->Size);
    if ( v14 )
    {
      Iopb = Data->Iopb;
      Information_low = LODWORD(Data->IoStatus.Information);
      v17 = FileObject->Flags & 2;
      IrpFlags = Iopb->IrpFlags;
      v19 = Iopb->IrpFlags;
      QuadPart = (FsFltWil::Details *)Iopb->Parameters.Read.ByteOffset.QuadPart;
      v20 = (v19 & 1) == 0;
      v21 = *(SECTION_OBJECT_POINTERS **)(v14 + 40);
      RetPostOperationStatus = IrpFlags;
      if ( FileObject->SectionObjectPointer != v21 )
        MicrosoftTelemetryAssertTriggeredMsgKM("shadowFileObject->SectionObjectPointer == backingFileObject->SectionObjectPointer");
      PrivateCacheMap = FileObject->PrivateCacheMap;
      if ( PrivateCacheMap && PrivateCacheMap != *(PVOID *)(v14 + 48) )
        MicrosoftTelemetryAssertTriggeredMsgKM(
          "!shadowFileObject->PrivateCacheMap || (shadowFileObject->PrivateCacheMap == backingFileObject->PrivateCacheMap)");
      if ( v20 && (FileObject->Flags & 0x4000) == 0 )
        FileObject->PrivateCacheMap = *(PVOID *)(v14 + 48);
      if ( Data->IoStatus.Status >= 0 && v17 && (RetPostOperationStatus & 2) == 0 && (_DWORD)Information_low )
        FileObject->CurrentByteOffset.QuadPart = (LONGLONG)QuadPart + Information_low;
    }
  }
  if ( CompletionContext )
  {
    FsFltWil::Details::ReleaseRundownProtectionCacheAware(
      (FsFltWil::Details *)CompletionContext,
      (struct FsFltWil::Details::RundownRefCacheAware *)FltObjects);
    v23 = *((_QWORD *)CompletionContext + 16);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), CompletionContext);
  }
  return 0;
}

```

## disassembly

```asm
0x140054200  mov     [rsp-38h+arg_0], rbx
0x140054205  push    rbp
0x140054206  push    rsi
0x140054207  push    rdi
0x140054208  push    r12
0x14005420a  push    r13
0x14005420c  push    r14
0x14005420e  push    r15
0x140054210  mov     rbp, rsp
0x140054213  sub     rsp, 70h
0x140054217  mov     ebx, r9d
0x14005421a  mov     rdi, r8
0x14005421d  mov     rsi, rdx
0x140054220  mov     r13, rcx
0x140054223  test    r9b, 1
0x140054227  jnz     loc_1400543C7
0x14005422d  call    cs:__imp_KeGetCurrentIrql
0x140054234  nop     dword ptr [rax+rax+00h]
0x140054239  cmp     al, 2
0x14005423b  jb      loc_140054307
0x140054241  lea     rax, [rbp+arg_18]
0x140054245  mov     [rbp+arg_18], 0
0x14005424c  mov     [rsp+70h+RetPostOperationStatus], rax; RetPostOperationStatus
0x140054251  mov     r9d, ebx; Flags
0x140054254  lea     rax, ?PostRead@UnionFsFilter@UnionFs@@SA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z; UnionFs::UnionFsFilter::PostRead(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)
0x14005425b  mov     r8, rdi; CompletionContext
0x14005425e  mov     rdx, rsi; FltObjects
0x140054261  mov     [rsp+70h+SafePostCallback], rax; SafePostCallback
0x140054266  mov     rcx, r13; Data
0x140054269  call    cs:__imp_FltDoCompletionProcessingWhenSafe
0x140054270  nop     dword ptr [rax+rax+00h]
0x140054275  test    al, al
0x140054277  jz      short loc_140054281
0x140054279  mov     eax, [rbp+arg_18]
0x14005427c  jmp     loc_14005440B
0x140054281  lea     rbx, aFailedToPostRe; "Failed to post read completion processi"...
0x140054288  mov     rcx, rbx
0x14005428b  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140054290  mov     eax, cs:dword_14009E178
0x140054296  cmp     eax, 2
0x140054299  jbe     short loc_140054307
0x14005429b  call    cs:__imp_KeGetCurrentIrql
0x1400542a2  nop     dword ptr [rax+rax+00h]
0x1400542a7  lea     rdx, byte_1400985D9
0x1400542ae  mov     [rbp+var_20], 0A0h
0x1400542b5  movzx   eax, al
0x1400542b8  mov     dword ptr [rbp+arg_10], eax
0x1400542bb  lea     rax, aOnecoreBaseFsU_22; "onecore\\base\\fs\\unionfs\\sys\\read.c"...
0x1400542c2  mov     [rbp+var_18], rax
0x1400542c6  lea     rax, aUnionfsUnionfs_67; "UnionFs::UnionFsFilter::PostRead"
0x1400542cd  mov     [rbp+var_10], rax
0x1400542d1  lea     rax, [rbp+arg_10]
0x1400542d5  mov     [rsp+70h+var_30], rax
0x1400542da  lea     rax, [rbp+var_20]
0x1400542de  mov     [rsp+70h+var_38], rax
0x1400542e3  lea     rax, [rbp+var_18]
0x1400542e7  mov     [rsp+70h+var_40], rax
0x1400542ec  lea     rax, [rbp+var_10]
0x1400542f0  mov     [rsp+70h+RetPostOperationStatus], rax
0x1400542f5  lea     rax, [rbp+var_8]
0x1400542f9  mov     [rsp+70h+SafePostCallback], rax
0x1400542fe  mov     [rbp+var_8], rbx
0x140054302  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140054307  mov     rsi, [rsi+20h]
0x14005430b  lea     rcx, [rbp+arg_10]
0x14005430f  mov     rbx, [rsi+20h]
0x140054313  lea     rdx, [rbx+20h]
0x140054317  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14005431c  mov     rcx, [rbp+arg_10]; this
0x140054320  mov     rbx, [rbx+18h]
0x140054324  test    rcx, rcx
0x140054327  jz      short loc_14005432E
0x140054329  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14005432e  test    rbx, rbx
0x140054331  jz      loc_1400543C7
0x140054337  mov     rax, [r13+10h]
0x14005433b  mov     r12d, [rsi+50h]
0x14005433f  mov     r14d, [r13+20h]
0x140054343  and     r12d, 2
0x140054347  mov     ecx, [rax]
0x140054349  mov     r15b, cl
0x14005434c  mov     rax, [rax+28h]
0x140054350  not     r15b
0x140054353  mov     [rbp+arg_10], rax
0x140054357  and     r15b, 1
0x14005435b  mov     rax, [rbx+28h]
0x14005435f  mov     [rbp+arg_18], ecx
0x140054362  cmp     [rsi+28h], rax
0x140054366  jz      short loc_140054374
0x140054368  lea     rcx, aShadowfileobje; "shadowFileObject->SectionObjectPointer "...
0x14005436f  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140054374  mov     rax, [rsi+30h]
0x140054378  test    rax, rax
0x14005437b  jz      short loc_14005438F
0x14005437d  cmp     rax, [rbx+30h]
0x140054381  jz      short loc_14005438F
0x140054383  lea     rcx, aShadowfileobje_0; "!shadowFileObject->PrivateCacheMap || ("...
0x14005438a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14005438f  test    r15b, r15b
0x140054392  jz      short loc_1400543A5
0x140054394  test    dword ptr [rsi+50h], 4000h
0x14005439b  jnz     short loc_1400543A5
0x14005439d  mov     rax, [rbx+30h]
0x1400543a1  mov     [rsi+30h], rax
0x1400543a5  cmp     dword ptr [r13+18h], 0
0x1400543aa  jl      short loc_1400543C7
0x1400543ac  test    r12d, r12d
0x1400543af  jz      short loc_1400543C7
0x1400543b1  test    byte ptr [rbp+arg_18], 2
0x1400543b5  jnz     short loc_1400543C7
0x1400543b7  test    r14d, r14d
0x1400543ba  jz      short loc_1400543C7
0x1400543bc  mov     rax, r14
0x1400543bf  add     rax, [rbp+arg_10]
0x1400543c3  mov     [rsi+68h], rax
0x1400543c7  test    rdi, rdi
0x1400543ca  jz      short loc_140054409
0x1400543cc  mov     rcx, rdi; this
0x1400543cf  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x1400543d4  mov     rcx, [rdi+80h]
0x1400543db  test    rcx, rcx
0x1400543de  jz      short loc_1400543EC
0x1400543e0  mov     rax, [rcx]
0x1400543e3  mov     rax, [rax+18h]
0x1400543e7  call    _guard_dispatch_icall
0x1400543ec  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400543f3  mov     rdx, rdi; Entry
0x1400543f6  add     rcx, 380h; Lookaside
0x1400543fd  call    cs:__imp_ExFreeToLookasideListEx
0x140054404  nop     dword ptr [rax+rax+00h]
0x140054409  xor     eax, eax
0x14005440b  mov     rbx, [rsp+70h+arg_0]
0x140054413  add     rsp, 70h
0x140054417  pop     r15
0x140054419  pop     r14
0x14005441b  pop     r13
0x14005441d  pop     r12
0x14005441f  pop     rdi
0x140054420  pop     rsi
0x140054421  pop     rbp
0x140054422  retn
```
