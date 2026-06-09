# UnionFs::UnionFsFilter::PreWrite(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x140079600`
- end: `0x140079969`
- name: `?PreWrite@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `873`
- prototype: `enum _FLT_PREOP_CALLBACK_STATUS __fastcall(enum _FLT_PREOP_CALLBACK_STATUS, const struct _FLT_RELATED_OBJECTS *, void **)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, installer_update`

## callees

- `0x1400056b4`
- `0x140006168`
- `0x14000f374`
- `0x140010148`
- `0x1400277f0`
- `0x14002793c`
- `0x140029518`
- `0x14002b640`
- `0x14002bd64`
- `0x140056ac4`
- `0x140056afc`
- `0x140074a84`
- `0x140079600`
- `0x140079df4`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x1400796b1`
- `FLTMGR!FltReleaseContext` at `0x140079785`
- `FLTMGR!FltReleaseContext` at `0x140079841`
- `FLTMGR!FltReleaseContext` at `0x14007989f`
- `FLTMGR!FltReleaseContext` at `0x140079915`
- `FLTMGR!FltReleaseContext` at `0x1400796b1`
- `FLTMGR!FltReleaseContext` at `0x140079785`
- `FLTMGR!FltReleaseContext` at `0x140079841`
- `FLTMGR!FltReleaseContext` at `0x14007989f`
- `FLTMGR!FltReleaseContext` at `0x140079915`

## string_xrefs

- `0x1400797ce`: `ORIGIN: Allocating SetFileSizeContext`
- `0x1400796d5`: `UnionFs::UnionFsFilter::PreWrite`
- `0x14007974e`: `UnionFs::UnionFsFilter::PreWrite`
- `0x1400797e1`: `UnionFs::UnionFsFilter::PreWrite`
- `0x1400796c2`: `ORIGIN: Failing write on SFO`

## pseudocode

```c
enum _FLT_PREOP_CALLBACK_STATUS __fastcall UnionFs::UnionFsFilter::PreWrite(
        const struct _FLT_CALLBACK_DATA *a1,
        const struct _FLT_RELATED_OBJECTS *a2,
        void ***a3,
        int a4)
{
  _WORD *FsContext; // rax
  const PFLT_INSTANCE *p_Instance; // rbx
  char v9; // r14
  struct _FILE_OBJECT *FileObject; // rdx
  struct _FLT_INSTANCE *v12; // rcx
  int v13; // ebx
  int v14; // r9d
  enum _FLT_PREOP_CALLBACK_STATUS v15; // ebx
  PFLT_CONTEXT v16; // rbx
  void **v17; // rsi
  int v18; // r9d
  __int64 v19; // r8
  __int64 v20; // rcx
  enum _FLT_PREOP_CALLBACK_STATUS v21; // edi
  struct FsFltWil::Details::RundownRefCacheAware *v22; // rdx
  void *v23; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v24; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v25; // rdx
  char *v26; // [rsp+20h] [rbp-E0h]
  char *v27; // [rsp+20h] [rbp-E0h]
  char *v28; // [rsp+20h] [rbp-E0h]
  const char *v29; // [rsp+28h] [rbp-D8h]
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v31[128]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v32; // [rsp+B8h] [rbp-48h]
  int v33[188]; // [rsp+C0h] [rbp-40h] BYREF

  if ( a1->Iopb->TargetFileObject && (a2->FileObject->Flags & 0x400000) == 0 )
  {
    UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v33, 0x29900220026uLL, a1);
    FsContext = a2->FileObject->FsContext;
    if ( FsContext && *FsContext == 17217 )
    {
      p_Instance = &a2->Instance;
      UnionFs::UfsStreamHandleCtx::FltGet(&Context, a2->Instance);
      if ( Context )
      {
        v9 = *(_BYTE *)Context & 1;
        FltReleaseContext(Context);
        if ( v9 )
        {
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC00000BBLL,
            (int)v33,
            (struct UnionFs::StackEventTracer *)0x29A0022006ALL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreWrite",
            "ORIGIN: Failing write on SFO",
            v29);
          a1->IoStatus.Status = -1073741637;
          a1->IoStatus.Information = 0;
          UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v33);
          return 4;
        }
      }
    }
    else
    {
      p_Instance = &a2->Instance;
    }
    FileObject = a2->FileObject;
    v12 = *p_Instance;
    Context = 0;
    v13 = UnionFs::UfsStreamCtx::FltGet(v12, FileObject, (int)v33);
    if ( v13 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v13,
        (int)v33,
        (struct UnionFs::StackEventTracer *)0x4D400220037LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreWrite",
        "PUSH: Getting stream context",
        v29);
      v15 = UnionFs::Utils::PreOpFinishProcessing(
              (UnionFs::Utils *)4,
              (enum _FLT_PREOP_CALLBACK_STATUS)a1,
              (struct _FLT_CALLBACK_DATA *)(unsigned int)v13,
              v14,
              (unsigned __int64)v28);
      if ( Context )
        FltReleaseContext(Context);
      goto LABEL_36;
    }
    v16 = Context;
    if ( Context )
    {
      UnionFs::UfsStreamCtx::SyncWithCOW((UnionFs::UfsStreamCtx *)Context);
      utl::make_unique<UnionFs::SetFileSizeContext,wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>,0>(
        &Context,
        v31);
      v17 = (void **)Context;
      if ( !Context )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)v33,
          (struct UnionFs::StackEventTracer *)0x4D200220047LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreWrite",
          "ORIGIN: Allocating SetFileSizeContext",
          v29);
        v19 = 3221225626LL;
        v20 = 4;
LABEL_15:
        v21 = UnionFs::Utils::PreOpFinishProcessing(
                (UnionFs::Utils *)v20,
                (enum _FLT_PREOP_CALLBACK_STATUS)a1,
                (struct _FLT_CALLBACK_DATA *)v19,
                v18,
                (unsigned __int64)v27);
        utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(&Context);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v31, v22);
        if ( v32 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 24LL))(v32);
        if ( v16 )
          FltReleaseContext(v16);
        v15 = v21;
        goto LABEL_36;
      }
      if ( *((_BYTE *)v16 + 160) && UnionFs::UfsStreamCtx::HasSFOs((UnionFs::UfsStreamCtx *)v16) )
      {
        if ( !(unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline()
          || (a1->Flags & 2) == 0
          || *(_BYTE *)(*((_QWORD *)v16 + 4) + 5LL) == 1 )
        {
          v23 = *v17;
          *v17 = v16;
          if ( v23 )
            FltReleaseContext(v23);
          Context = 0;
          *a3 = v17;
          utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(&Context);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v31, v24);
          if ( v32 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 24LL))(v32);
          v15 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
          goto LABEL_36;
        }
        v19 = 0;
        v20 = 3;
        goto LABEL_15;
      }
      utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(&Context);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v31, v25);
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 24LL))(v32);
      if ( v16 )
        FltReleaseContext(v16);
    }
    v15 = FLT_PREOP_SUCCESS_NO_CALLBACK;
LABEL_36:
    UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v33);
    return v15;
  }
  return UnionFs::Utils::PreOpFinishProcessing(
           (UnionFs::Utils *)1,
           (enum _FLT_PREOP_CALLBACK_STATUS)a1,
           0,
           a4,
           (unsigned __int64)v26);
}

```

## disassembly

```asm
0x140079600  mov     [rsp-8+arg_18], rbx
0x140079605  push    rbp
0x140079606  push    rsi
0x140079607  push    rdi
0x140079608  push    r14
0x14007960a  push    r15
0x14007960c  lea     rbp, [rsp-2C0h]
0x140079614  sub     rsp, 3C0h
0x14007961b  mov     rax, cs:__security_cookie
0x140079622  xor     rax, rsp
0x140079625  mov     [rbp+2E0h+var_30], rax
0x14007962c  mov     rax, [rcx+10h]
0x140079630  mov     r15, r8
0x140079633  mov     rsi, rdx
0x140079636  mov     rdi, rcx
0x140079639  cmp     qword ptr [rax+8], 0
0x14007963e  jz      loc_140079933
0x140079644  mov     rax, [rdx+20h]
0x140079648  test    dword ptr [rax+50h], 400000h
0x14007964f  jnz     loc_140079933
0x140079655  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x140079658  mov     rdx, 29900220026h; unsigned __int64
0x140079662  lea     rcx, [rbp+2E0h+var_320]; this
0x140079666  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x14007966b  mov     r8, [rsi+20h]
0x14007966f  mov     rax, [r8+18h]
0x140079673  test    rax, rax
0x140079676  jz      loc_14007970D
0x14007967c  mov     ecx, 4341h
0x140079681  cmp     [rax], cx
0x140079684  jnz     loc_14007970D
0x14007968a  lea     rbx, [rsi+18h]
0x14007968e  mov     rdx, [rbx]
0x140079691  lea     rcx, [rsp+3E0h+Context]
0x140079696  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SA?AV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &)
0x14007969b  mov     rcx, [rsp+3E0h+Context]; Context
0x1400796a0  test    rcx, rcx
0x1400796a3  jz      short loc_140079711
0x1400796a5  mov     r14b, [rcx]
0x1400796a8  and     r14b, 1
0x1400796ac  test    rcx, rcx
0x1400796af  jz      short loc_1400796BD
0x1400796b1  call    cs:__imp_FltReleaseContext
0x1400796b8  nop     dword ptr [rax+rax+00h]
0x1400796bd  test    r14b, r14b
0x1400796c0  jz      short loc_140079711
0x1400796c2  lea     rax, aOriginFailingW; "ORIGIN: Failing write on SFO"
0x1400796c9  mov     ebx, 0C00000BBh
0x1400796ce  mov     ecx, ebx; this
0x1400796d0  mov     [rsp+3E0h+var_3C0], rax; char *
0x1400796d5  lea     r9, aUnionfsUnionfs_3; "UnionFs::UnionFsFilter::PreWrite"
0x1400796dc  mov     r8, 29A0022006Ah; struct UnionFs::StackEventTracer *
0x1400796e6  lea     rdx, [rbp+2E0h+var_320]; int
0x1400796ea  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400796ef  lea     rcx, [rbp+2E0h+var_320]; this
0x1400796f3  mov     [rdi+18h], ebx
0x1400796f6  mov     qword ptr [rdi+20h], 0
0x1400796fe  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140079703  mov     eax, 4
0x140079708  jmp     loc_140079942
0x14007970d  lea     rbx, [rsi+18h]
0x140079711  mov     rdx, [rsi+20h]; FileObject
0x140079715  lea     rax, [rbp+2E0h+var_320]
0x140079719  mov     rcx, [rbx]; Instance
0x14007971c  lea     r9, [rsp+3E0h+Context]
0x140079721  mov     r8b, 1
0x140079724  mov     [rsp+3E0h+var_3C0], rax; int
0x140079729  mov     [rsp+3E0h+Context], 0
0x140079732  call    ?FltGet@UfsStreamCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsStreamCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsStreamCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140079737  mov     ebx, eax
0x140079739  test    eax, eax
0x14007973b  jns     short loc_140079796
0x14007973d  lea     rax, aPushGettingStr; "PUSH: Getting stream context"
0x140079744  mov     r8, 4D400220037h; struct UnionFs::StackEventTracer *
0x14007974e  lea     r9, aUnionfsUnionfs_3; "UnionFs::UnionFsFilter::PreWrite"
0x140079755  mov     [rsp+3E0h+var_3C0], rax; unsigned __int64
0x14007975a  lea     rdx, [rbp+2E0h+var_320]; int
0x14007975e  mov     ecx, ebx; this
0x140079760  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140079765  mov     r8d, ebx; struct _FLT_CALLBACK_DATA *
0x140079768  mov     rdx, rdi; enum _FLT_PREOP_CALLBACK_STATUS
0x14007976b  mov     ecx, 4; this
0x140079770  call    ?PreOpFinishProcessing@Utils@UnionFs@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@W43@AEAU_FLT_CALLBACK_DATA@@J_K@Z; UnionFs::Utils::PreOpFinishProcessing(_FLT_PREOP_CALLBACK_STATUS,_FLT_CALLBACK_DATA &,long,unsigned __int64)
0x140079775  mov     rcx, [rsp+3E0h+Context]; Context
0x14007977a  mov     ebx, eax
0x14007977c  test    rcx, rcx
0x14007977f  jz      loc_140079926
0x140079785  call    cs:__imp_FltReleaseContext
0x14007978c  nop     dword ptr [rax+rax+00h]
0x140079791  jmp     loc_140079926
0x140079796  mov     rbx, [rsp+3E0h+Context]
0x14007979b  test    rbx, rbx
0x14007979e  jz      loc_140079921
0x1400797a4  lea     rdx, [rsp+3E0h+var_3A8]
0x1400797a9  mov     rcx, rbx; this
0x1400797ac  call    ?SyncWithCOW@UfsStreamCtx@UnionFs@@QEAA@XZ; UnionFs::UfsStreamCtx::SyncWithCOW(void)
0x1400797b1  lea     rdx, [rsp+3E0h+var_3A8]
0x1400797b6  lea     rcx, [rsp+3E0h+Context]
0x1400797bb  call    ??$make_unique@USetFileSizeContext@UnionFs@@V?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@$0A@@utl@@YA?AV?$unique_ptr@USetFileSizeContext@UnionFs@@U?$default_delete@USetFileSizeContext@UnionFs@@@utl@@@0@$$QEAV?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@@Z; utl::make_unique<UnionFs::SetFileSizeContext,wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>,0>(wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0> &&)
0x1400797c0  mov     rsi, [rsp+3E0h+Context]
0x1400797c5  test    rsi, rsi
0x1400797c8  jnz     loc_140079854
0x1400797ce  lea     rax, aOriginAllocati_88; "ORIGIN: Allocating SetFileSizeContext"
0x1400797d5  mov     esi, 0C000009Ah
0x1400797da  mov     ecx, esi; this
0x1400797dc  mov     [rsp+3E0h+var_3C0], rax; unsigned __int64
0x1400797e1  lea     r9, aUnionfsUnionfs_3; "UnionFs::UnionFsFilter::PreWrite"
0x1400797e8  mov     r8, 4D200220047h; struct UnionFs::StackEventTracer *
0x1400797f2  lea     rdx, [rbp+2E0h+var_320]; int
0x1400797f6  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400797fb  mov     r8d, esi; struct _FLT_CALLBACK_DATA *
0x1400797fe  mov     ecx, 4; this
0x140079803  mov     rdx, rdi; enum _FLT_PREOP_CALLBACK_STATUS
0x140079806  call    ?PreOpFinishProcessing@Utils@UnionFs@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@W43@AEAU_FLT_CALLBACK_DATA@@J_K@Z; UnionFs::Utils::PreOpFinishProcessing(_FLT_PREOP_CALLBACK_STATUS,_FLT_CALLBACK_DATA &,long,unsigned __int64)
0x14007980b  lea     rcx, [rsp+3E0h+Context]
0x140079810  mov     edi, eax
0x140079812  call    ??1?$unique_ptr@USetFileSizeContext@UnionFs@@U?$default_delete@USetFileSizeContext@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(void)
0x140079817  lea     rcx, [rsp+3E0h+var_3A8]; this
0x14007981c  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140079821  mov     rdx, [rbp+2E0h+var_328]
0x140079825  test    rdx, rdx
0x140079828  jz      short loc_140079839
0x14007982a  mov     rcx, [rdx]
0x14007982d  mov     rax, [rcx+18h]
0x140079831  mov     rcx, rdx
0x140079834  call    _guard_dispatch_icall
0x140079839  test    rbx, rbx
0x14007983c  jz      short loc_14007984D
0x14007983e  mov     rcx, rbx; Context
0x140079841  call    cs:__imp_FltReleaseContext
0x140079848  nop     dword ptr [rax+rax+00h]
0x14007984d  mov     ebx, edi
0x14007984f  jmp     loc_140079926
0x140079854  cmp     byte ptr [rbx+0A0h], 0
0x14007985b  jz      loc_1400798E4
0x140079861  mov     rcx, rbx; this
0x140079864  call    ?HasSFOs@UfsStreamCtx@UnionFs@@QEBA_NXZ; UnionFs::UfsStreamCtx::HasSFOs(void)
0x140079869  test    al, al
0x14007986b  jz      short loc_1400798E4
0x14007986d  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140079872  test    eax, eax
0x140079874  jz      short loc_140079894
0x140079876  mov     eax, [rdi]
0x140079878  test    al, 2
0x14007987a  jz      short loc_140079894
0x14007987c  mov     rax, [rbx+20h]
0x140079880  mov     cl, [rax+5]
0x140079883  cmp     cl, 1
0x140079886  jz      short loc_140079894
0x140079888  xor     r8d, r8d
0x14007988b  lea     ecx, [r8+3]
0x14007988f  jmp     loc_140079803
0x140079894  mov     rcx, [rsi]; Context
0x140079897  mov     [rsi], rbx
0x14007989a  test    rcx, rcx
0x14007989d  jz      short loc_1400798AB
0x14007989f  call    cs:__imp_FltReleaseContext
0x1400798a6  nop     dword ptr [rax+rax+00h]
0x1400798ab  lea     rcx, [rsp+3E0h+Context]
0x1400798b0  mov     [rsp+3E0h+Context], 0
0x1400798b9  mov     [r15], rsi
0x1400798bc  call    ??1?$unique_ptr@USetFileSizeContext@UnionFs@@U?$default_delete@USetFileSizeContext@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(void)
0x1400798c1  lea     rcx, [rsp+3E0h+var_3A8]; this
0x1400798c6  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x1400798cb  mov     rcx, [rbp+2E0h+var_328]
0x1400798cf  test    rcx, rcx
0x1400798d2  jz      short loc_1400798E0
0x1400798d4  mov     rax, [rcx]
0x1400798d7  mov     rax, [rax+18h]
0x1400798db  call    _guard_dispatch_icall
0x1400798e0  xor     ebx, ebx
0x1400798e2  jmp     short loc_140079926
0x1400798e4  lea     rcx, [rsp+3E0h+Context]
0x1400798e9  call    ??1?$unique_ptr@USetFileSizeContext@UnionFs@@U?$default_delete@USetFileSizeContext@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(void)
0x1400798ee  lea     rcx, [rsp+3E0h+var_3A8]; this
0x1400798f3  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x1400798f8  mov     rcx, [rbp+2E0h+var_328]
0x1400798fc  test    rcx, rcx
0x1400798ff  jz      short loc_14007990D
0x140079901  mov     rax, [rcx]
0x140079904  mov     rax, [rax+18h]
0x140079908  call    _guard_dispatch_icall
0x14007990d  test    rbx, rbx
0x140079910  jz      short loc_140079921
0x140079912  mov     rcx, rbx; Context
0x140079915  call    cs:__imp_FltReleaseContext
0x14007991c  nop     dword ptr [rax+rax+00h]
0x140079921  mov     ebx, 1
0x140079926  lea     rcx, [rbp+2E0h+var_320]; this
0x14007992a  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x14007992f  mov     eax, ebx
0x140079931  jmp     short loc_140079942
0x140079933  xor     r8d, r8d; struct _FLT_CALLBACK_DATA *
0x140079936  mov     rdx, rdi; enum _FLT_PREOP_CALLBACK_STATUS
0x140079939  lea     ecx, [r8+1]; this
0x14007993d  call    ?PreOpFinishProcessing@Utils@UnionFs@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@W43@AEAU_FLT_CALLBACK_DATA@@J_K@Z; UnionFs::Utils::PreOpFinishProcessing(_FLT_PREOP_CALLBACK_STATUS,_FLT_CALLBACK_DATA &,long,unsigned __int64)
0x140079942  mov     rcx, [rbp+2E0h+var_30]
0x140079949  xor     rcx, rsp; StackCookie
0x14007994c  call    __security_check_cookie
0x140079951  mov     rbx, [rsp+3E0h+arg_18]
0x140079959  add     rsp, 3C0h
0x140079960  pop     r15
0x140079962  pop     r14
0x140079964  pop     rdi
0x140079965  pop     rsi
0x140079966  pop     rbp
0x140079967  retn
```
