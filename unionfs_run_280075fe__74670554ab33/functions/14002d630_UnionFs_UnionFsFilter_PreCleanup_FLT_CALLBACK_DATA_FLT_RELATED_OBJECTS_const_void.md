# UnionFs::UnionFsFilter::PreCleanup(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x14002d630`
- end: `0x14002dbcc`
- name: `?PreCleanup@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `1436`
- prototype: `enum _FLT_PREOP_CALLBACK_STATUS __fastcall(struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation`

## callees

- `0x140005574`
- `0x1400056b4`
- `0x140005ff8`
- `0x140006168`
- `0x14000efd0`
- `0x14000f7fc`
- `0x1400279fc`
- `0x140027c18`
- `0x14002b428`
- `0x14002bde4`
- `0x14002d630`
- `0x1400567f4`
- `0x140056afc`
- `0x140057e88`
- `0x140074b3c`
- `0x140079df4`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d9d3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002da97`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d9d3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002da97`
- `FLTMGR!FltReleaseContext` at `0x14002d853`
- `FLTMGR!FltReleaseContext` at `0x14002d9fd`
- `FLTMGR!FltReleaseContext` at `0x14002da3b`
- `FLTMGR!FltReleaseContext` at `0x14002dac1`
- `FLTMGR!FltReleaseContext` at `0x14002db04`
- `FLTMGR!FltReleaseContext` at `0x14002db4b`
- `FLTMGR!FltReleaseContext` at `0x14002d853`
- `FLTMGR!FltReleaseContext` at `0x14002d9fd`
- `FLTMGR!FltReleaseContext` at `0x14002da3b`
- `FLTMGR!FltReleaseContext` at `0x14002dac1`
- `FLTMGR!FltReleaseContext` at `0x14002db04`
- `FLTMGR!FltReleaseContext` at `0x14002db4b`

## string_xrefs

- `0x14002d985`: `PUSH: Preparing for delete`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PreCleanup(
        struct _FLT_CALLBACK_DATA *a1,
        const struct _FLT_RELATED_OBJECTS *a2,
        void **a3)
{
  bool v6; // r8
  int v7; // esi
  struct UnionFs::UfsStreamHandleCtx *v8; // rbx
  __int64 v9; // rdx
  unsigned int v10; // r14d
  PFILE_OBJECT FileObject; // rcx
  _WORD *FsContext; // rax
  int v13; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v14; // rdx
  struct _FILE_OBJECT *v15; // rdx
  int Set; // eax
  int v17; // eax
  __int16 v18; // cx
  int v19; // edi
  __int64 v20; // rcx
  PVOID v21; // rdi
  PVOID v22; // rdi
  PVOID *v23; // rax
  PVOID v24; // rbx
  struct UnionFs::StackEventTracer *v26; // [rsp+28h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v27; // [rsp+28h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v28; // [rsp+28h] [rbp-D8h]
  PVOID Entry; // [rsp+48h] [rbp-B8h] BYREF
  PFLT_CONTEXT v30; // [rsp+50h] [rbp-B0h]
  __int128 v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h]
  struct UnionFs::UfsStreamHandleCtx *v33; // [rsp+70h] [rbp-90h]
  _BYTE v34[8]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v35[14]; // [rsp+80h] [rbp-80h] BYREF
  struct UnionFs::UfsUnionCtx *v36; // [rsp+F0h] [rbp-10h]
  utl::_RefCountBase *v37; // [rsp+F8h] [rbp-8h]
  __int64 v38; // [rsp+100h] [rbp+0h] BYREF
  char v39; // [rsp+108h] [rbp+8h]
  _BYTE v40[112]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v41; // [rsp+180h] [rbp+80h]
  PFLT_CONTEXT Context[3]; // [rsp+188h] [rbp+88h] BYREF
  _QWORD v43[17]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v44[4]; // [rsp+228h] [rbp+128h] BYREF
  _QWORD v45[46]; // [rsp+2A0h] [rbp+1A0h]
  __int16 v46; // [rsp+412h] [rbp+312h]
  __int16 v47; // [rsp+44Ch] [rbp+34Ch]

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v44, 0x2D1000B090DuLL, a1);
  memset(Context, 0, sizeof(Context));
  memset(v43, 0, sizeof(v43));
  v7 = UnionFs::UfsStreamHandleCtx::FltGet(
         a2->Instance,
         a2->FileObject,
         v6,
         (struct UnionFs::HandleCtxAndUnionWithRundown *)Context,
         (struct UnionFs::StackEventTracer *)v44);
  if ( v7 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v7,
      (int)v44,
      (struct UnionFs::StackEventTracer *)0x2D5000B091FLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCleanup",
      "PUSH: Getting handle ctx",
      (const char *)v26);
    UnionFs::StackEventTracer::LogError((UnionFs::StackEventTracer *)v44);
    *(_DWORD *)v44 = 0;
    v47 = 0;
  }
  v8 = (struct UnionFs::UfsStreamHandleCtx *)Context[0];
  v36 = (struct UnionFs::UfsUnionCtx *)Context[1];
  v37 = (utl::_RefCountBase *)Context[2];
  v38 = v43[0];
  v39 = v43[1];
  memset(Context, 0, sizeof(Context));
  wistd::function<void (bool)>::function<void (bool)>(v40, &v43[2]);
  memset(v43, 0, sizeof(v43));
  v10 = 1;
  if ( v8 )
  {
    FileObject = a2->FileObject;
    FsContext = FileObject->FsContext;
    if ( FsContext )
    {
      v9 = 17217;
      if ( *FsContext == 17217 && (*(_BYTE *)v8 & 1) != 0 )
      {
        v13 = UnionFs::UfsShadowFileObject::Cleanup(
                (UnionFs::UfsShadowFileObject *)FileObject,
                a1,
                a2,
                v8,
                v36,
                (struct UnionFs::StackEventTracer *)v44);
        if ( v13 < 0 )
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v13,
            (int)v44,
            (struct UnionFs::StackEventTracer *)0xC1000B093BLL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCleanup",
            "PUSH: Cleaning up SFO",
            (const char *)v27);
        a1->IoStatus.Status = 0;
        a1->IoStatus.Information = 0;
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v38, v14);
        if ( v41 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 24LL))(v41);
        if ( v37 )
          utl::_RefCountBase::_DecStrong(v37);
        FltReleaseContext(v8);
        v10 = 4;
        goto LABEL_48;
      }
    }
    if ( v7 < 0 )
      goto LABEL_27;
    v15 = a2->FileObject;
    v30 = 0;
    Set = UnionFs::UfsFileCtx::FltGetSet(a2->Instance, v15, 0);
    if ( Set < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)Set,
        (int)v44,
        (struct UnionFs::StackEventTracer *)0x2D8000B0952LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCleanup",
        "PUSH: Getting file ctx",
        (const char *)v26);
LABEL_27:
      FsFltWil::Details::ReleaseRundownProtectionCacheAware(
        (FsFltWil::Details *)&v38,
        (struct FsFltWil::Details::RundownRefCacheAware *)v9);
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 24LL))(v41);
      if ( v37 )
        utl::_RefCountBase::_DecStrong(v37);
      FltReleaseContext(v8);
      goto LABEL_48;
    }
    v35[0] = off_14007E900;
    v35[13] = v35;
    UnionFs::StackEventTracer::SetIgnoreStatusCallback(v44, v34);
    Entry = 0;
    v17 = UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded(
            a1,
            (const struct _FLT_CALLBACK_DATA *)a2,
            (struct _FLT_RELATED_OBJECTS *)v8,
            (const struct UnionFs::UfsStreamHandleCtx *)v30,
            (__int64)v36,
            (UnionFs::CleanupContext **)&Entry,
            (UnionFs::StackEventTracer *)v44);
    v18 = v46;
    v19 = v17;
    if ( v46 )
    {
      --v46;
      v9 = 120LL * (unsigned __int16)(v18 - 1);
      v20 = *(_QWORD *)((char *)v45 + v9);
      *(_QWORD *)((char *)v45 + v9) = 0;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
    }
    if ( v19 < 0 )
    {
      if ( v19 != -1073741567 )
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v19,
          (int)v44,
          (struct UnionFs::StackEventTracer *)0x4F6000B096BLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCleanup",
          "PUSH: Preparing for delete",
          (const char *)v28);
      v21 = Entry;
      if ( Entry )
      {
        UnionFs::CleanupContext::~CleanupContext((UnionFs::CleanupContext *)Entry);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 800), v21);
      }
      goto LABEL_27;
    }
    v22 = Entry;
    if ( Entry )
      goto LABEL_36;
    if ( (*(_DWORD *)v8 & 0x40) == 0 )
      goto LABEL_27;
    v32 = 0;
    v33 = v8;
    v31 = 0;
    v23 = (PVOID *)utl::make_unique<UnionFs::CleanupContext,UnionFs::CleanupContext,0>(&Entry, &v31);
    v22 = *v23;
    *v23 = 0;
    v24 = Entry;
    if ( Entry )
    {
      UnionFs::CleanupContext::~CleanupContext((UnionFs::CleanupContext *)Entry);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 800), v24);
    }
    UnionFs::CleanupContext::~CleanupContext((UnionFs::CleanupContext *)&v31);
    if ( v22 )
    {
      v8 = 0;
LABEL_36:
      *a3 = v22;
      FsFltWil::Details::ReleaseRundownProtectionCacheAware(
        (FsFltWil::Details *)&v38,
        (struct FsFltWil::Details::RundownRefCacheAware *)v9);
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 24LL))(v41);
      if ( v37 )
        utl::_RefCountBase::_DecStrong(v37);
      if ( v8 )
        FltReleaseContext(v8);
      v10 = 0;
      goto LABEL_48;
    }
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)0xC000009ALL,
      (int)v44,
      (struct UnionFs::StackEventTracer *)0x28A000B097BLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCleanup",
      "PUSH: Allocating cleanup context",
      (const char *)v28);
  }
  FsFltWil::Details::ReleaseRundownProtectionCacheAware(
    (FsFltWil::Details *)&v38,
    (struct FsFltWil::Details::RundownRefCacheAware *)v9);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 24LL))(v41);
  if ( v37 )
    utl::_RefCountBase::_DecStrong(v37);
LABEL_48:
  UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)Context);
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v44);
  return v10;
}

```

## disassembly

```asm
0x14002d630  mov     [rsp-8+arg_18], rbx
0x14002d635  push    rbp
0x14002d636  push    rsi
0x14002d637  push    rdi
0x14002d638  push    r12
0x14002d63a  push    r13
0x14002d63c  push    r14
0x14002d63e  push    r15
0x14002d640  lea     rbp, [rsp-420h]
0x14002d648  sub     rsp, 520h
0x14002d64f  mov     rax, cs:__security_cookie
0x14002d656  xor     rax, rsp
0x14002d659  mov     [rbp+450h+var_38], rax
0x14002d660  mov     r12, r8
0x14002d663  mov     r15, rdx
0x14002d666  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x14002d669  mov     rdi, rcx
0x14002d66c  lea     rcx, [rbp+450h+var_328]; this
0x14002d673  mov     rdx, 2D1000B090Dh; unsigned __int64
0x14002d67d  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x14002d682  xorps   xmm0, xmm0
0x14002d685  lea     rcx, [rbp+450h+var_3B0]; void *
0x14002d68c  xorps   xmm1, xmm1
0x14002d68f  xor     r13d, r13d
0x14002d692  mov     r14d, 88h
0x14002d698  mov     [rbp+450h+var_3A8], r13b
0x14002d69f  mov     r8d, r14d; Size
0x14002d6a2  mov     [rbp+450h+var_330], r13
0x14002d6a9  xor     edx, edx; Val
0x14002d6ab  movdqu  xmmword ptr [rbp+450h+Context], xmm0
0x14002d6b3  movdqu  xmmword ptr [rbp+98h], xmm1
0x14002d6bb  call    memset
0x14002d6c0  mov     rdx, [r15+20h]; FileObject
0x14002d6c4  lea     rax, [rbp+450h+var_328]
0x14002d6cb  mov     rcx, [r15+18h]; Instance
0x14002d6cf  lea     r9, [rbp+450h+Context]; struct UnionFs::HandleCtxAndUnionWithRundown *
0x14002d6d6  mov     [rsp+550h+var_530], rax; struct UnionFs::StackEventTracer *
0x14002d6db  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAUHandleCtxAndUnionWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,UnionFs::HandleCtxAndUnionWithRundown &,UnionFs::StackEventTracer &)
0x14002d6e0  mov     esi, eax
0x14002d6e2  test    eax, eax
0x14002d6e4  jns     short loc_14002D72C
0x14002d6e6  lea     rax, aPushGettingHan; "PUSH: Getting handle ctx"
0x14002d6ed  mov     r8, 2D5000B091Fh; struct UnionFs::StackEventTracer *
0x14002d6f7  lea     r9, aUnionfsUnionfs_10; "UnionFs::UnionFsFilter::PreCleanup"
0x14002d6fe  mov     [rsp+550h+var_530], rax; char *
0x14002d703  lea     rdx, [rbp+450h+var_328]; int
0x14002d70a  mov     ecx, esi; this
0x14002d70c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002d711  lea     rcx, [rbp+450h+var_328]; this
0x14002d718  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14002d71d  mov     dword ptr [rbp+450h+var_328], r13d
0x14002d724  mov     [rbp+450h+var_104], r13w
0x14002d72c  mov     rax, [rbp+450h+Context+8]
0x14002d733  lea     rdx, [rbp+450h+var_3A0]
0x14002d73a  mov     rbx, [rbp+450h+Context]
0x14002d741  lea     rcx, [rbp+450h+var_440]
0x14002d745  mov     [rbp+450h+var_460], rax
0x14002d749  xorps   xmm0, xmm0
0x14002d74c  mov     rax, [rbp+450h+var_3B8]
0x14002d753  mov     [rbp+450h+var_458], rax
0x14002d757  mov     rax, [rbp+450h+var_3B0]
0x14002d75e  mov     [rbp+450h+var_450], rax
0x14002d762  mov     al, [rbp+450h+var_3A8]
0x14002d768  mov     [rbp+450h+var_448], al
0x14002d76b  mov     [rbp+450h+Context], r13
0x14002d772  movdqu  xmmword ptr [rbp+450h+Context+8], xmm0
0x14002d77a  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14002d77f  mov     r8, r14; Size
0x14002d782  lea     rcx, [rbp+450h+var_3B0]; void *
0x14002d789  xor     edx, edx; Val
0x14002d78b  call    memset
0x14002d790  mov     r14d, 1
0x14002d796  test    rbx, rbx
0x14002d799  jz      loc_14002DB57
0x14002d79f  mov     rcx, [r15+20h]; this
0x14002d7a3  mov     rax, [rcx+18h]
0x14002d7a7  test    rax, rax
0x14002d7aa  jz      loc_14002D86A
0x14002d7b0  mov     edx, 4341h
0x14002d7b5  cmp     [rax], dx
0x14002d7b8  jnz     loc_14002D86A
0x14002d7be  test    [rbx], r14b
0x14002d7c1  jz      loc_14002D86A
0x14002d7c7  mov     rax, [rbp+450h+var_460]
0x14002d7cb  lea     rdx, [rbp+450h+var_328]
0x14002d7d2  mov     [rsp+550h+var_528], rdx; char *
0x14002d7d7  mov     r9, rbx; struct UnionFs::UfsStreamHandleCtx *
0x14002d7da  mov     rdx, rdi; struct _FLT_CALLBACK_DATA *
0x14002d7dd  mov     [rsp+550h+var_530], rax; struct UnionFs::UfsUnionCtx *
0x14002d7e2  mov     r8, r15; struct _FLT_RELATED_OBJECTS *
0x14002d7e5  call    ?Cleanup@UfsShadowFileObject@UnionFs@@QEAAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsStreamHandleCtx@2@AEAVUfsUnionCtx@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsShadowFileObject::Cleanup(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsUnionCtx &,UnionFs::StackEventTracer &)
0x14002d7ea  test    eax, eax
0x14002d7ec  jns     short loc_14002D819
0x14002d7ee  lea     rcx, aPushCleaningUp; "PUSH: Cleaning up SFO"
0x14002d7f5  mov     r8, 0C1000B093Bh; struct UnionFs::StackEventTracer *
0x14002d7ff  mov     [rsp+550h+var_530], rcx; char *
0x14002d804  lea     r9, aUnionfsUnionfs_10; "UnionFs::UnionFsFilter::PreCleanup"
0x14002d80b  mov     ecx, eax; this
0x14002d80d  lea     rdx, [rbp+450h+var_328]; int
0x14002d814  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002d819  lea     rcx, [rbp+450h+var_450]; this
0x14002d81d  mov     [rdi+18h], r13d
0x14002d821  mov     [rdi+20h], r13
0x14002d825  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002d82a  mov     rcx, [rbp+450h+var_3D0]
0x14002d831  test    rcx, rcx
0x14002d834  jz      short loc_14002D842
0x14002d836  mov     rax, [rcx]
0x14002d839  mov     rax, [rax+18h]
0x14002d83d  call    _guard_dispatch_icall
0x14002d842  mov     rcx, [rbp+450h+var_458]; this
0x14002d846  test    rcx, rcx
0x14002d849  jz      short loc_14002D850
0x14002d84b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002d850  mov     rcx, rbx; Context
0x14002d853  call    cs:__imp_FltReleaseContext
0x14002d85a  nop     dword ptr [rax+rax+00h]
0x14002d85f  mov     r14d, 4
0x14002d865  jmp     loc_14002DB86
0x14002d86a  test    esi, esi
0x14002d86c  js      loc_14002DA09
0x14002d872  mov     rdx, rcx; FileObject
0x14002d875  mov     [rsp+550h+var_500], r13
0x14002d87a  mov     rcx, [r15+18h]; Instance
0x14002d87e  lea     r9, [rbp+450h+var_328]
0x14002d885  lea     r8, [rsp+550h+var_500]
0x14002d88a  mov     dword ptr [rsp+550h+var_530], r13d; int
0x14002d88f  call    ?FltGetSet@UfsFileCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsFileCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@K@Z; UnionFs::UfsFileCtx::FltGetSet(_FLT_INSTANCE const &,_FILE_OBJECT &,wistd::unique_ptr<UnionFs::UfsFileCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &,ulong)
0x14002d894  test    eax, eax
0x14002d896  jns     short loc_14002D8D6
0x14002d898  lea     rcx, aPushGettingFil_1; "PUSH: Getting file ctx"
0x14002d89f  mov     r8, 2D8000B0952h; struct UnionFs::StackEventTracer *
0x14002d8a9  mov     [rsp+550h+var_530], rcx; char *
0x14002d8ae  lea     r9, aUnionfsUnionfs_10; "UnionFs::UnionFsFilter::PreCleanup"
0x14002d8b5  mov     ecx, eax; this
0x14002d8b7  lea     rdx, [rbp+450h+var_328]; int
0x14002d8be  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002d8c3  mov     rcx, [rsp+550h+var_500]
0x14002d8c8  test    rcx, rcx
0x14002d8cb  jz      loc_14002DA09
0x14002d8d1  jmp     loc_14002D9FD
0x14002d8d6  lea     rax, off_14007E900
0x14002d8dd  mov     [rbp+450h+var_4D0], rax
0x14002d8e1  lea     rdx, [rsp+550h+var_4D8]
0x14002d8e6  lea     rax, [rbp+450h+var_4D0]
0x14002d8ea  lea     rcx, [rbp+450h+var_328]
0x14002d8f1  mov     [rbp+450h+var_468], rax
0x14002d8f5  call    ?SetIgnoreStatusCallback@StackEventTracer@UnionFs@@QEAAXV?$function@$$A6A_NJ@Z@wistd@@@Z; UnionFs::StackEventTracer::SetIgnoreStatusCallback(wistd::function<bool (long)>)
0x14002d8fa  mov     rax, [rbp+450h+var_460]
0x14002d8fe  lea     rcx, [rbp+450h+var_328]
0x14002d905  mov     rsi, [rsp+550h+var_500]
0x14002d90a  mov     r8, rbx
0x14002d90d  mov     [rsp+550h+var_520], rcx
0x14002d912  mov     r9, rsi
0x14002d915  lea     rcx, [rsp+550h+Entry]
0x14002d91a  mov     [rsp+550h+Entry], r13
0x14002d91f  mov     [rsp+550h+var_528], rcx; char *
0x14002d924  mov     rdx, r15
0x14002d927  mov     rcx, rdi
0x14002d92a  mov     [rsp+550h+var_530], rax
0x14002d92f  call    ?PrepareForDeleteOnCleanupIfNeeded@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsStreamHandleCtx@2@AEAVUfsFileCtx@2@AEAVUfsUnionCtx@2@AEAV?$unique_ptr@UCleanupContext@UnionFs@@U?$default_delete@UCleanupContext@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsFileCtx &,UnionFs::UfsUnionCtx &,utl::unique_ptr<UnionFs::CleanupContext,utl::default_delete<UnionFs::CleanupContext>> &,UnionFs::StackEventTracer &)
0x14002d934  movzx   ecx, [rbp+450h+var_13E]
0x14002d93b  mov     edi, eax
0x14002d93d  test    cx, cx
0x14002d940  jz      short loc_14002D979
0x14002d942  mov     eax, 0FFFFh
0x14002d947  add     cx, ax
0x14002d94a  mov     [rbp+450h+var_13E], cx
0x14002d951  movzx   ecx, cx
0x14002d954  imul    rdx, rcx, 78h ; 'x'
0x14002d958  mov     rcx, [rbp+rdx+450h+var_2B0]
0x14002d960  mov     [rbp+rdx+450h+var_2B0], r13
0x14002d968  test    rcx, rcx
0x14002d96b  jz      short loc_14002D979
0x14002d96d  mov     rax, [rcx]
0x14002d970  mov     rax, [rax+18h]
0x14002d974  call    _guard_dispatch_icall
0x14002d979  test    edi, edi
0x14002d97b  jns     short loc_14002D9E1
0x14002d97d  cmp     edi, 0C0000101h
0x14002d983  jz      short loc_14002D9B0
0x14002d985  lea     rax, aPushPreparingF_1; "PUSH: Preparing for delete"
0x14002d98c  mov     r8, 4F6000B096Bh; struct UnionFs::StackEventTracer *
0x14002d996  lea     r9, aUnionfsUnionfs_10; "UnionFs::UnionFsFilter::PreCleanup"
0x14002d99d  mov     [rsp+550h+var_530], rax; char *
0x14002d9a2  lea     rdx, [rbp+450h+var_328]; int
0x14002d9a9  mov     ecx, edi; this
0x14002d9ab  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002d9b0  mov     rdi, [rsp+550h+Entry]
0x14002d9b5  test    rdi, rdi
0x14002d9b8  jz      short loc_14002D9F5
0x14002d9ba  mov     rcx, rdi; this
0x14002d9bd  call    ??1CleanupContext@UnionFs@@QEAA@XZ; UnionFs::CleanupContext::~CleanupContext(void)
0x14002d9c2  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002d9c9  mov     rdx, rdi; Entry
0x14002d9cc  add     rcx, 320h; Lookaside
0x14002d9d3  call    cs:__imp_ExFreeToLookasideListEx
0x14002d9da  nop     dword ptr [rax+rax+00h]
0x14002d9df  jmp     short loc_14002D9F5
0x14002d9e1  mov     rdi, [rsp+550h+Entry]
0x14002d9e6  test    rdi, rdi
0x14002d9e9  jnz     loc_14002DAB5
0x14002d9ef  mov     eax, [rbx]
0x14002d9f1  test    al, 40h
0x14002d9f3  jnz     short loc_14002DA4C
0x14002d9f5  test    rsi, rsi
0x14002d9f8  jz      short loc_14002DA09
0x14002d9fa  mov     rcx, rsi; Context
0x14002d9fd  call    cs:__imp_FltReleaseContext
0x14002da04  nop     dword ptr [rax+rax+00h]
0x14002da09  lea     rcx, [rbp+450h+var_450]; this
0x14002da0d  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002da12  mov     rcx, [rbp+450h+var_3D0]
0x14002da19  test    rcx, rcx
0x14002da1c  jz      short loc_14002DA2A
0x14002da1e  mov     rax, [rcx]
0x14002da21  mov     rax, [rax+18h]
0x14002da25  call    _guard_dispatch_icall
0x14002da2a  mov     rcx, [rbp+450h+var_458]; this
0x14002da2e  test    rcx, rcx
0x14002da31  jz      short loc_14002DA38
0x14002da33  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002da38  mov     rcx, rbx; Context
0x14002da3b  call    cs:__imp_FltReleaseContext
0x14002da42  nop     dword ptr [rax+rax+00h]
0x14002da47  jmp     loc_14002DB86
0x14002da4c  xorps   xmm0, xmm0
0x14002da4f  mov     [rsp+550h+var_4E8], r13
0x14002da54  lea     rdx, [rsp+550h+var_4F8]
0x14002da59  mov     [rsp+550h+var_4E0], rbx
0x14002da5e  lea     rcx, [rsp+550h+Entry]
0x14002da63  movdqu  [rsp+550h+var_4F8], xmm0
0x14002da69  call    ??$make_unique@UCleanupContext@UnionFs@@U12@$0A@@utl@@YA?AV?$unique_ptr@UCleanupContext@UnionFs@@U?$default_delete@UCleanupContext@UnionFs@@@utl@@@0@$$QEAUCleanupContext@UnionFs@@@Z; utl::make_unique<UnionFs::CleanupContext,UnionFs::CleanupContext,0>(UnionFs::CleanupContext &&)
0x14002da6e  mov     rdi, [rax]
0x14002da71  mov     [rax], r13
0x14002da74  mov     rbx, [rsp+550h+Entry]
0x14002da79  test    rbx, rbx
0x14002da7c  jz      short loc_14002DAA3
0x14002da7e  mov     rcx, rbx; this
0x14002da81  call    ??1CleanupContext@UnionFs@@QEAA@XZ; UnionFs::CleanupContext::~CleanupContext(void)
0x14002da86  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002da8d  mov     rdx, rbx; Entry
0x14002da90  add     rcx, 320h; Lookaside
0x14002da97  call    cs:__imp_ExFreeToLookasideListEx
0x14002da9e  nop     dword ptr [rax+rax+00h]
0x14002daa3  lea     rcx, [rsp+550h+var_4F8]; this
0x14002daa8  call    ??1CleanupContext@UnionFs@@QEAA@XZ; UnionFs::CleanupContext::~CleanupContext(void)
0x14002daad  test    rdi, rdi
0x14002dab0  jz      short loc_14002DB15
0x14002dab2  mov     rbx, r13
0x14002dab5  mov     [r12], rdi
0x14002dab9  test    rsi, rsi
0x14002dabc  jz      short loc_14002DACD
0x14002dabe  mov     rcx, rsi; Context
0x14002dac1  call    cs:__imp_FltReleaseContext
0x14002dac8  nop     dword ptr [rax+rax+00h]
0x14002dacd  lea     rcx, [rbp+450h+var_450]; this
0x14002dad1  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002dad6  mov     rcx, [rbp+450h+var_3D0]
0x14002dadd  test    rcx, rcx
0x14002dae0  jz      short loc_14002DAEE
0x14002dae2  mov     rax, [rcx]
0x14002dae5  mov     rax, [rax+18h]
0x14002dae9  call    _guard_dispatch_icall
0x14002daee  mov     rcx, [rbp+450h+var_458]; this
0x14002daf2  test    rcx, rcx
0x14002daf5  jz      short loc_14002DAFC
0x14002daf7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002dafc  test    rbx, rbx
0x14002daff  jz      short loc_14002DB10
0x14002db01  mov     rcx, rbx; Context
0x14002db04  call    cs:__imp_FltReleaseContext
0x14002db0b  nop     dword ptr [rax+rax+00h]
0x14002db10  mov     r14d, r13d
0x14002db13  jmp     short loc_14002DB86
0x14002db15  lea     rax, aPushAllocating_20; "PUSH: Allocating cleanup context"
0x14002db1c  mov     r8, 28A000B097Bh; struct UnionFs::StackEventTracer *
0x14002db26  lea     r9, aUnionfsUnionfs_10; "UnionFs::UnionFsFilter::PreCleanup"
0x14002db2d  mov     [rsp+550h+var_530], rax; char *
0x14002db32  lea     rdx, [rbp+450h+var_328]; int
0x14002db39  mov     ecx, 0C000009Ah; this
0x14002db3e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002db43  test    rsi, rsi
0x14002db46  jz      short loc_14002DB57
0x14002db48  mov     rcx, rsi; Context
0x14002db4b  call    cs:__imp_FltReleaseContext
0x14002db52  nop     dword ptr [rax+rax+00h]
0x14002db57  lea     rcx, [rbp+450h+var_450]; this
0x14002db5b  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002db60  mov     rcx, [rbp+450h+var_3D0]
0x14002db67  test    rcx, rcx
0x14002db6a  jz      short loc_14002DB78
0x14002db6c  mov     rax, [rcx]
0x14002db6f  mov     rax, [rax+18h]
0x14002db73  call    _guard_dispatch_icall
0x14002db78  mov     rcx, [rbp+450h+var_458]; this
0x14002db7c  test    rcx, rcx
0x14002db7f  jz      short loc_14002DB86
0x14002db81  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002db86  lea     rcx, [rbp+450h+Context]; this
  ... truncated ...
```
