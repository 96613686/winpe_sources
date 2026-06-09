# UnionFs::UfsShadowFileObject::Cleanup(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsUnionCtx &,UnionFs::StackEventTracer &)

- ea: `0x140057e88`
- end: `0x14005836e`
- name: `?Cleanup@UfsShadowFileObject@UnionFs@@QEAAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsStreamHandleCtx@2@AEAVUfsUnionCtx@2@AEAVStackEventTracer@2@@Z`
- size: `1254`
- prototype: `__int64 __usercall@<rax>(UnionFs::UfsShadowFileObject *__hidden this@<rcx>, const struct _FLT_CALLBACK_DATA *@<rdx>, const struct _FLT_RELATED_OBJECTS *@<r8>, struct UnionFs::UfsStreamHandleCtx *@<r9>, struct UnionFs::UfsUnionCtx *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002d630`

## callees

- `0x14000f7fc`
- `0x140010148`
- `0x14002742c`
- `0x14002bde4`
- `0x1400567f4`
- `0x140056a50`
- `0x140056afc`
- `0x140057e88`
- `0x140059f6c`
- `0x14005a0a8`
- `0x14005a228`
- `0x1400699dc`
- `0x1400700c8`
- `0x140074b3c`
- `0x140075c30`
- `0x1400799dc`
- `0x140079a24`
- `0x140079a6c`
- `0x140079d74`
- `0x140079da0`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140058189`
- `ntoskrnl!ZwClose` at `0x140058311`
- `ntoskrnl!ZwClose` at `0x140058189`
- `ntoskrnl!ZwClose` at `0x140058311`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005833f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005833f`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14005813f`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14005813f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400581cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400581cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400581d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400581d7`
- `FLTMGR!FltReferenceContext` at `0x140057f27`
- `FLTMGR!FltReferenceContext` at `0x140057f27`
- `FLTMGR!FltReleaseContext` at `0x1400580ca`
- `FLTMGR!FltReleaseContext` at `0x1400580e7`
- `FLTMGR!FltReleaseContext` at `0x1400580ca`
- `FLTMGR!FltReleaseContext` at `0x1400580e7`

## string_xrefs

- `0x140058084`: `PUSH: Prepare for delete on SFO cleanup`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsShadowFileObject::Cleanup(
        UnionFs::UfsShadowFileObject *this,
        const struct _FLT_CALLBACK_DATA *a2,
        const struct _FLT_CALLBACK_DATA *a3,
        struct UnionFs::UfsStreamHandleCtx *a4,
        struct _ERESOURCE *a5,
        struct UnionFs::StackEventTracer *a6)
{
  __int64 v6; // r12
  __int64 v8; // r14
  unsigned __int64 *v9; // rdx
  char *v10; // rsi
  __int64 v11; // rbx
  _BYTE *v12; // r15
  int BackingLayer; // eax
  unsigned __int64 *v14; // rdx
  struct _FILE_OBJECT *v15; // rbx
  int v16; // ebx
  PFLT_CONTEXT v17; // rcx
  PFLT_CONTEXT v18; // rbx
  int v19; // eax
  char v20; // bl
  unsigned __int64 *v21; // rdx
  HANDLE v22; // rbx
  struct _ERESOURCE *v23; // rcx
  char v24; // r15
  int v25; // esi
  int v26; // eax
  PVOID v27; // rbx
  char *v29; // [rsp+28h] [rbp-81h]
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-69h] BYREF
  PVOID Entry; // [rsp+48h] [rbp-61h] BYREF
  const struct _FLT_CALLBACK_DATA *v32; // [rsp+50h] [rbp-59h]
  PERESOURCE Resource; // [rsp+58h] [rbp-51h] BYREF
  utl::_RefCountBase *v34[2]; // [rsp+60h] [rbp-49h] BYREF
  struct _FLT_CALLBACK_DATA *v35; // [rsp+70h] [rbp-39h]
  FsFltWil::Details *v36; // [rsp+78h] [rbp-31h] BYREF
  char v37; // [rsp+80h] [rbp-29h] BYREF
  char v38; // [rsp+88h] [rbp-21h] BYREF
  _BYTE v39[12]; // [rsp+90h] [rbp-19h] BYREF

  v6 = *((_QWORD *)this + 4);
  v8 = *((_QWORD *)this + 3);
  v35 = (struct _FLT_CALLBACK_DATA *)a2;
  *(_QWORD *)v39 = a4;
  v32 = a3;
  Resource = a5;
  FsFltWil::AcquirePushLockShared(&Context, v6 + 32);
  v10 = (char *)(v6 + 16);
  v11 = *(_QWORD *)(v6 + 16);
  if ( Context )
    FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Context, v9);
  if ( !v11 )
    MicrosoftTelemetryAssertTriggeredMsgKM("fsContext2->GetBackingFileHandle()");
  Entry = 0;
  if ( UnionFs::CloseHandleWithResult )
  {
    v12 = *(_BYTE **)(v8 + 136);
    FltReferenceContext(v12);
    if ( !v12[160] )
    {
LABEL_22:
      FltReleaseContext(v12);
      goto LABEL_23;
    }
    *(_OWORD *)v34 = 0;
    BackingLayer = UnionFs::UfsFsContext2::TryGetBackingLayer(v6, v34, a6);
    if ( BackingLayer < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)BackingLayer,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x4F2001D03E2LL,
        (unsigned __int64)"UnionFs::UfsShadowFileObject::Cleanup",
        "PUSH: No backing layer",
        v29);
      UnionFs::StackEventTracer::LogError(a6);
      *(_DWORD *)a6 = 0;
      *((_WORD *)a6 + 274) = 0;
      goto LABEL_20;
    }
    Context = 0;
    FsFltWil::AcquirePushLockShared(&v36, v6 + 32);
    v15 = *(struct _FILE_OBJECT **)(v6 + 24);
    if ( v36 )
      FsFltWil::Details::ReleasePushLockShared(v36, v14);
    v16 = UnionFs::UfsFileCtx::FltGet(**((PFLT_INSTANCE **)v34[0] + 1), v15, (int)a6);
    if ( v16 >= 0 )
    {
      v18 = Context;
      if ( *((_BYTE *)Context + 56) )
      {
        v19 = UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded(
                v35,
                v32,
                *(struct _FLT_RELATED_OBJECTS **)v39,
                (const struct UnionFs::UfsStreamHandleCtx *)Context,
                (__int64)Resource,
                (UnionFs::CleanupContext **)&Entry,
                a6);
        if ( v19 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v19,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x4F8001D0416LL,
            (unsigned __int64)"UnionFs::UfsShadowFileObject::Cleanup",
            "PUSH: Prepare for delete on SFO cleanup",
            v29);
          UnionFs::StackEventTracer::LogError(a6);
          *(_DWORD *)a6 = 0;
          *((_WORD *)a6 + 274) = 0;
        }
      }
      if ( !v18 )
        goto LABEL_20;
      v17 = v18;
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("UfsShadowFileObject::Cleanup failed to get backing file context!");
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v16,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x4F4001D03F9LL,
        (unsigned __int64)"UnionFs::UfsShadowFileObject::Cleanup",
        "PUSH: Getting backing file context",
        v29);
      UnionFs::StackEventTracer::LogError(a6);
      v17 = Context;
      *(_DWORD *)a6 = 0;
      *((_WORD *)a6 + 274) = 0;
      if ( !v17 )
        goto LABEL_20;
    }
    FltReleaseContext(v17);
LABEL_20:
    if ( v34[1] )
      utl::_RefCountBase::_DecStrong(v34[1]);
    goto LABEL_22;
  }
LABEL_23:
  FsFltWil::AcquireResourceExclusive(&Resource, *(_QWORD *)(v8 + 120) + 56LL);
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    UnionFs::Utils::CheckOplock(v35, (__int64)v32, (PVOID *)(v8 + 88), (int)a6, 0x80000000);
    if ( *(_BYTE *)(*(_QWORD *)(v8 + 144) + 96LL) || (v20 = 1, !FsRtlOplockIsFastIoPossible((POPLOCK)(v8 + 88))) )
      v20 = 0;
    *(_BYTE *)(v8 + 5) = v20;
  }
  FsFltWil::AcquirePushLockExclusive(v39, v6 + 32);
  v22 = 0;
  if ( &v37 != v10 )
  {
    v22 = *(HANDLE *)v10;
    *(_QWORD *)v10 = 0;
  }
  if ( v10 != &v38 )
  {
    if ( *(_QWORD *)v10 )
      ZwClose(*(HANDLE *)v10);
    *(_QWORD *)v10 = 0;
  }
  if ( *(_QWORD *)v39 )
    FsFltWil::Details::ReleasePushLockExclusive(*(FsFltWil::Details **)v39, v21);
  *(_DWORD *)(v6 + 40) |= 2u;
  *((_DWORD *)this + 20) |= 0x4000u;
  v23 = Resource;
  v24 = *((_BYTE *)this + 72);
  *((_QWORD *)this + 6) = 0;
  if ( v23 )
  {
    ExReleaseResourceLite(v23);
    KeLeaveCriticalRegion();
  }
  v25 = 0;
  if ( v24 )
  {
    v25 = UnionFs::UfsFsContext2::UnlockAll((UnionFs::UfsFsContext2 *)v6, a6);
    if ( v25 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v25,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0xC0001D0452LL,
        (unsigned __int64)"UnionFs::UfsShadowFileObject::Cleanup",
        "PUSH: Unlocking byte-range locks",
        v29);
      UnionFs::StackEventTracer::LogError(a6);
      *(_DWORD *)a6 = 0;
      *((_WORD *)a6 + 274) = 0;
    }
  }
  UnionFs::UfsShadowFileObject::UpdateFileSizesFromBFO(this);
  UnionFs::Utils::RemoveShareAccess(this, 14);
  v26 = *((_DWORD *)this + 20);
  _InterlockedDecrement((volatile signed __int32 *)(v8 + 208));
  if ( (v26 & 8) != 0 )
    _InterlockedDecrement((volatile signed __int32 *)(v8 + 212));
  if ( Entry )
  {
    *(_QWORD *)&v39[4] = 0;
    *(_DWORD *)v39 = 1;
    v25 = ((__int64 (__fastcall *)(HANDLE, _QWORD, __int64, _BYTE *))UnionFs::CloseHandleWithResult)(v22, 0, 12, v39);
    if ( v25 >= 0 )
    {
      UnionFs::Utils::HandlePostCleanupWork(v32, &Entry, *(unsigned int *)&v39[8], a6);
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Closing backing file handle");
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v25,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x4F9001D0474LL,
        (unsigned __int64)"UnionFs::UfsShadowFileObject::Cleanup",
        "API: Closing backing file handle",
        v29);
      UnionFs::StackEventTracer::LogError(a6);
      *(_DWORD *)a6 = 0;
      *((_WORD *)a6 + 274) = 0;
    }
  }
  else if ( v22 )
  {
    ZwClose(v22);
  }
  v27 = Entry;
  if ( Entry )
  {
    UnionFs::CleanupContext::~CleanupContext((UnionFs::CleanupContext *)Entry);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 800), v27);
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x140057e88  push    rbp
0x140057e8a  push    rbx
0x140057e8b  push    rsi
0x140057e8c  push    rdi
0x140057e8d  push    r12
0x140057e8f  push    r13
0x140057e91  push    r14
0x140057e93  push    r15
0x140057e95  lea     rbp, [rsp-0Fh]
0x140057e9a  sub     rsp, 0B8h
0x140057ea1  mov     rax, cs:__security_cookie
0x140057ea8  xor     rax, rsp
0x140057eab  mov     [rbp+47h+var_50], rax
0x140057eaf  mov     r12, [rcx+20h]
0x140057eb3  mov     r13, rcx
0x140057eb6  mov     rax, [rbp+47h+arg_20]
0x140057eba  mov     r14, [rcx+18h]
0x140057ebe  lea     rcx, [rbp+47h+Context]
0x140057ec2  mov     rdi, [rbp+47h+arg_28]
0x140057ec6  mov     [rbp+47h+var_80], rdx
0x140057eca  lea     rdx, [r12+20h]
0x140057ecf  mov     [rbp+47h+var_60], r9
0x140057ed3  mov     [rbp+47h+var_A0], r8
0x140057ed7  mov     [rbp+47h+Resource], rax
0x140057edb  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140057ee0  mov     rcx, [rbp+47h+Context]; this
0x140057ee4  lea     rsi, [r12+10h]
0x140057ee9  mov     rbx, [rsi]
0x140057eec  test    rcx, rcx
0x140057eef  jz      short loc_140057EF6
0x140057ef1  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140057ef6  test    rbx, rbx
0x140057ef9  jnz     short loc_140057F07
0x140057efb  lea     rcx, aFscontext2Getb; "fsContext2->GetBackingFileHandle()"
0x140057f02  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140057f07  cmp     cs:?CloseHandleWithResult@UnionFs@@3P6AJPEAXDKPEAU_OBJECT_CLOSE_RESULT@1@@ZEA, 0; long (*UnionFs::CloseHandleWithResult)(void *,char,ulong,UnionFs::_OBJECT_CLOSE_RESULT *)
0x140057f0f  mov     [rbp+47h+Entry], 0
0x140057f17  jz      loc_1400580F3
0x140057f1d  mov     r15, [r14+88h]
0x140057f24  mov     rcx, r15; Context
0x140057f27  call    cs:__imp_FltReferenceContext
0x140057f2e  nop     dword ptr [rax+rax+00h]
0x140057f33  cmp     byte ptr [r15+0A0h], 0
0x140057f3b  jz      loc_1400580E4
0x140057f41  xorps   xmm0, xmm0
0x140057f44  lea     rdx, [rbp+47h+var_90]
0x140057f48  mov     r8, rdi
0x140057f4b  mov     rcx, r12
0x140057f4e  movdqu  xmmword ptr [rbp+47h+var_90], xmm0
0x140057f53  call    ?TryGetBackingLayer@UfsFsContext2@UnionFs@@QEBAJAEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsFsContext2::TryGetBackingLayer(utl::shared_ptr<UnionFs::UfsLayerCtx> &,UnionFs::StackEventTracer &)
0x140057f58  test    eax, eax
0x140057f5a  jns     short loc_140057F9F
0x140057f5c  lea     rcx, aPushNoBackingL; "PUSH: No backing layer"
0x140057f63  mov     r8, 4F2001D03E2h; struct UnionFs::StackEventTracer *
0x140057f6d  mov     [rsp+0F0h+var_D0], rcx; char *
0x140057f72  lea     r9, aUnionfsUfsshad_2; "UnionFs::UfsShadowFileObject::Cleanup"
0x140057f79  mov     ecx, eax; this
0x140057f7b  mov     rdx, rdi; int
0x140057f7e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140057f83  mov     rcx, rdi; this
0x140057f86  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x140057f8b  xor     eax, eax
0x140057f8d  mov     dword ptr [rdi], 0
0x140057f93  mov     [rdi+224h], ax
0x140057f9a  jmp     loc_1400580D6
0x140057f9f  lea     rdx, [r12+20h]
0x140057fa4  mov     [rbp+47h+Context], 0
0x140057fac  lea     rcx, [rbp+47h+var_78]
0x140057fb0  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140057fb5  mov     rcx, [rbp+47h+var_78]; this
0x140057fb9  mov     rbx, [r12+18h]
0x140057fbe  test    rcx, rcx
0x140057fc1  jz      short loc_140057FC8
0x140057fc3  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140057fc8  mov     rax, [rbp+47h+var_90]
0x140057fcc  lea     r9, [rbp+47h+Context]
0x140057fd0  xor     r8d, r8d
0x140057fd3  mov     [rsp+0F0h+var_D0], rdi; int
0x140057fd8  mov     rdx, rbx; FileObject
0x140057fdb  mov     rcx, [rax+8]
0x140057fdf  mov     rcx, [rcx]; Instance
0x140057fe2  call    ?FltGet@UfsFileCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsFileCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsFileCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsFileCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140057fe7  mov     ebx, eax
0x140057fe9  test    eax, eax
0x140057feb  jns     short loc_140058049
0x140057fed  lea     rcx, aUfsshadowfileo; "UfsShadowFileObject::Cleanup failed to "...
0x140057ff4  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140057ff9  lea     rax, aPushGettingBac; "PUSH: Getting backing file context"
0x140058000  mov     r8, 4F4001D03F9h; struct UnionFs::StackEventTracer *
0x14005800a  lea     r9, aUnionfsUfsshad_2; "UnionFs::UfsShadowFileObject::Cleanup"
0x140058011  mov     [rsp+0F0h+var_D0], rax; char *
0x140058016  mov     rdx, rdi; int
0x140058019  mov     ecx, ebx; this
0x14005801b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140058020  mov     rcx, rdi; this
0x140058023  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x140058028  mov     rcx, [rbp+47h+Context]
0x14005802c  xor     eax, eax
0x14005802e  mov     dword ptr [rdi], 0
0x140058034  mov     [rdi+224h], ax
0x14005803b  test    rcx, rcx
0x14005803e  jz      loc_1400580D6
0x140058044  jmp     loc_1400580CA
0x140058049  mov     rbx, [rbp+47h+Context]
0x14005804d  mov     al, [rbx+38h]
0x140058050  nop
0x140058051  test    al, al
0x140058053  jz      short loc_1400580C2
0x140058055  mov     r8, [rbp+47h+var_60]
0x140058059  lea     rax, [rbp+47h+Entry]
0x14005805d  mov     rdx, [rbp+47h+var_A0]
0x140058061  mov     r9, rbx
0x140058064  mov     rcx, [rbp+47h+var_80]
0x140058068  mov     [rsp+0F0h+var_C0], rdi
0x14005806d  mov     [rsp+0F0h+var_C8], rax; char *
0x140058072  mov     rax, [rbp+47h+Resource]
0x140058076  mov     [rsp+0F0h+var_D0], rax
0x14005807b  call    ?PrepareForDeleteOnCleanupIfNeeded@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsStreamHandleCtx@2@AEAVUfsFileCtx@2@AEAVUfsUnionCtx@2@AEAV?$unique_ptr@UCleanupContext@UnionFs@@U?$default_delete@UCleanupContext@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsFileCtx &,UnionFs::UfsUnionCtx &,utl::unique_ptr<UnionFs::CleanupContext,utl::default_delete<UnionFs::CleanupContext>> &,UnionFs::StackEventTracer &)
0x140058080  test    eax, eax
0x140058082  jns     short loc_1400580C2
0x140058084  lea     rcx, aPushPrepareFor; "PUSH: Prepare for delete on SFO cleanup"
0x14005808b  mov     r8, 4F8001D0416h; struct UnionFs::StackEventTracer *
0x140058095  mov     [rsp+0F0h+var_D0], rcx; char *
0x14005809a  lea     r9, aUnionfsUfsshad_2; "UnionFs::UfsShadowFileObject::Cleanup"
0x1400580a1  mov     ecx, eax; this
0x1400580a3  mov     rdx, rdi; int
0x1400580a6  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400580ab  mov     rcx, rdi; this
0x1400580ae  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x1400580b3  xor     eax, eax
0x1400580b5  mov     dword ptr [rdi], 0
0x1400580bb  mov     [rdi+224h], ax
0x1400580c2  test    rbx, rbx
0x1400580c5  jz      short loc_1400580D6
0x1400580c7  mov     rcx, rbx; Context
0x1400580ca  call    cs:__imp_FltReleaseContext
0x1400580d1  nop     dword ptr [rax+rax+00h]
0x1400580d6  mov     rcx, [rbp+47h+var_90+8]; this
0x1400580da  test    rcx, rcx
0x1400580dd  jz      short loc_1400580E4
0x1400580df  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400580e4  mov     rcx, r15; Context
0x1400580e7  call    cs:__imp_FltReleaseContext
0x1400580ee  nop     dword ptr [rax+rax+00h]
0x1400580f3  mov     rdx, [r14+78h]
0x1400580f7  lea     rcx, [rbp+47h+Resource]
0x1400580fb  add     rdx, 38h ; '8'
0x1400580ff  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140058104  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140058109  test    eax, eax
0x14005810b  jz      short loc_140058155
0x14005810d  mov     rdx, [rbp+47h+var_A0]
0x140058111  lea     r8, [r14+58h]
0x140058115  mov     rcx, [rbp+47h+var_80]
0x140058119  mov     r9, rdi
0x14005811c  mov     dword ptr [rsp+0F0h+var_D0], 80000000h
0x140058124  call    ?CheckOplock@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAPEAXAEAVStackEventTracer@2@W4CheckOplockFlags@12@@Z; UnionFs::Utils::CheckOplock(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,void * &,UnionFs::StackEventTracer &,UnionFs::Utils::CheckOplockFlags)
0x140058129  mov     rax, [r14+90h]
0x140058130  cmp     byte ptr [rax+60h], 0
0x140058134  jnz     short loc_14005814F
0x140058136  lea     rcx, [r14+58h]; Oplock
0x14005813a  mov     ebx, 1
0x14005813f  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x140058146  nop     dword ptr [rax+rax+00h]
0x14005814b  test    al, al
0x14005814d  jnz     short loc_140058151
0x14005814f  xor     ebx, ebx
0x140058151  mov     [r14+5], bl
0x140058155  lea     rdx, [r12+20h]
0x14005815a  lea     rcx, [rbp+47h+var_60]
0x14005815e  call    ?AcquirePushLockExclusive@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockExclusive@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockExclusive(unsigned __int64 &)
0x140058163  lea     rax, [rbp+47h+var_70]
0x140058167  xor     ebx, ebx
0x140058169  cmp     rax, rsi
0x14005816c  jz      short loc_140058178
0x14005816e  mov     rbx, [rsi]
0x140058171  mov     qword ptr [rsi], 0
0x140058178  lea     rax, [rbp+47h+var_68]
0x14005817c  cmp     rsi, rax
0x14005817f  jz      short loc_14005819C
0x140058181  mov     rcx, [rsi]; Handle
0x140058184  test    rcx, rcx
0x140058187  jz      short loc_140058195
0x140058189  call    cs:__imp_ZwClose
0x140058190  nop     dword ptr [rax+rax+00h]
0x140058195  mov     qword ptr [rsi], 0
0x14005819c  mov     rcx, [rbp+47h+var_60]; this
0x1400581a0  test    rcx, rcx
0x1400581a3  jz      short loc_1400581AA
0x1400581a5  call    ?ReleasePushLockExclusive@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockExclusive(unsigned __int64 *)
0x1400581aa  or      dword ptr [r12+28h], 2
0x1400581b0  bts     dword ptr [r13+50h], 0Eh
0x1400581b6  mov     rcx, [rbp+47h+Resource]; Resource
0x1400581ba  mov     r15b, [r13+48h]
0x1400581be  mov     qword ptr [r13+30h], 0
0x1400581c6  test    rcx, rcx
0x1400581c9  jz      short loc_1400581E3
0x1400581cb  call    cs:__imp_ExReleaseResourceLite
0x1400581d2  nop     dword ptr [rax+rax+00h]
0x1400581d7  call    cs:__imp_KeLeaveCriticalRegion
0x1400581de  nop     dword ptr [rax+rax+00h]
0x1400581e3  xor     esi, esi
0x1400581e5  test    r15b, r15b
0x1400581e8  jz      short loc_140058239
0x1400581ea  mov     rdx, rdi; struct UnionFs::StackEventTracer *
0x1400581ed  mov     rcx, r12; this
0x1400581f0  call    ?UnlockAll@UfsFsContext2@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsFsContext2::UnlockAll(UnionFs::StackEventTracer &)
0x1400581f5  mov     esi, eax
0x1400581f7  test    eax, eax
0x1400581f9  jns     short loc_140058239
0x1400581fb  lea     rax, aPushUnlockingB; "PUSH: Unlocking byte-range locks"
0x140058202  mov     r8, 0C0001D0452h; struct UnionFs::StackEventTracer *
0x14005820c  lea     r9, aUnionfsUfsshad_2; "UnionFs::UfsShadowFileObject::Cleanup"
0x140058213  mov     [rsp+0F0h+var_D0], rax; char *
0x140058218  mov     rdx, rdi; int
0x14005821b  mov     ecx, esi; this
0x14005821d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140058222  mov     rcx, rdi; this
0x140058225  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14005822a  xor     eax, eax
0x14005822c  mov     dword ptr [rdi], 0
0x140058232  mov     [rdi+224h], ax
0x140058239  mov     rcx, r13; this
0x14005823c  call    ?UpdateFileSizesFromBFO@UfsShadowFileObject@UnionFs@@QEAAXXZ; UnionFs::UfsShadowFileObject::UpdateFileSizesFromBFO(void)
0x140058241  xor     r8d, r8d
0x140058244  mov     rcx, r13
0x140058247  lea     edx, [r8+0Eh]
0x14005824b  call    ?RemoveShareAccess@Utils@UnionFs@@YAXAEAU_FILE_OBJECT@@W4ShareAccessCaller@2@PEAVUfsFsContext@2@@Z; UnionFs::Utils::RemoveShareAccess(_FILE_OBJECT &,UnionFs::ShareAccessCaller,UnionFs::UfsFsContext *)
0x140058250  mov     eax, [r13+50h]
0x140058254  nop
0x140058255  lock dec dword ptr [r14+0D0h]
0x14005825d  nop
0x14005825e  bt      eax, 3
0x140058262  jnb     short loc_14005826E
0x140058264  nop
0x140058265  lock dec dword ptr [r14+0D4h]
0x14005826d  nop
0x14005826e  cmp     [rbp+47h+Entry], 0
0x140058273  jz      loc_140058309
0x140058279  mov     rax, cs:?CloseHandleWithResult@UnionFs@@3P6AJPEAXDKPEAU_OBJECT_CLOSE_RESULT@1@@ZEA; long (*UnionFs::CloseHandleWithResult)(void *,char,ulong,UnionFs::_OBJECT_CLOSE_RESULT *)
0x140058280  lea     r9, [rbp+47h+var_60]
0x140058284  xor     edx, edx
0x140058286  mov     [rbp+47h+var_60+4], 0
0x14005828e  mov     rcx, rbx
0x140058291  mov     dword ptr [rbp+47h+var_60], 1
0x140058298  lea     r8d, [rdx+0Ch]
0x14005829c  call    _guard_dispatch_icall
0x1400582a1  mov     esi, eax
0x1400582a3  test    eax, eax
0x1400582a5  jns     short loc_1400582F3
0x1400582a7  lea     rcx, aClosingBacking; "Closing backing file handle"
0x1400582ae  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400582b3  lea     rax, aApiClosingBack; "API: Closing backing file handle"
0x1400582ba  mov     r8, 4F9001D0474h; struct UnionFs::StackEventTracer *
0x1400582c4  lea     r9, aUnionfsUfsshad_2; "UnionFs::UfsShadowFileObject::Cleanup"
0x1400582cb  mov     [rsp+0F0h+var_D0], rax; char *
0x1400582d0  mov     rdx, rdi; int
0x1400582d3  mov     ecx, esi; this
0x1400582d5  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400582da  mov     rcx, rdi; this
0x1400582dd  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x1400582e2  xor     eax, eax
0x1400582e4  mov     dword ptr [rdi], 0
0x1400582ea  mov     [rdi+224h], ax
0x1400582f1  jmp     short loc_14005831D
0x1400582f3  mov     r8d, [rbp+47h+var_58]
0x1400582f7  lea     rdx, [rbp+47h+Entry]
0x1400582fb  mov     rcx, [rbp+47h+var_A0]
0x1400582ff  mov     r9, rdi
0x140058302  call    ?HandlePostCleanupWork@Utils@UnionFs@@YAXAEBU_FLT_RELATED_OBJECTS@@$$QEAV?$unique_ptr@UCleanupContext@UnionFs@@U?$default_delete@UCleanupContext@UnionFs@@@utl@@@utl@@KAEAVStackEventTracer@2@@Z; UnionFs::Utils::HandlePostCleanupWork(_FLT_RELATED_OBJECTS const &,utl::unique_ptr<UnionFs::CleanupContext,utl::default_delete<UnionFs::CleanupContext>> &&,ulong,UnionFs::StackEventTracer &)
0x140058307  jmp     short loc_14005831D
0x140058309  test    rbx, rbx
0x14005830c  jz      short loc_14005831D
0x14005830e  mov     rcx, rbx; Handle
0x140058311  call    cs:__imp_ZwClose
0x140058318  nop     dword ptr [rax+rax+00h]
0x14005831d  mov     rbx, [rbp+47h+Entry]
0x140058321  test    rbx, rbx
0x140058324  jz      short loc_14005834B
0x140058326  mov     rcx, rbx; this
0x140058329  call    ??1CleanupContext@UnionFs@@QEAA@XZ; UnionFs::CleanupContext::~CleanupContext(void)
0x14005832e  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140058335  mov     rdx, rbx; Entry
0x140058338  add     rcx, 320h; Lookaside
0x14005833f  call    cs:__imp_ExFreeToLookasideListEx
0x140058346  nop     dword ptr [rax+rax+00h]
0x14005834b  mov     eax, esi
0x14005834d  mov     rcx, [rbp+47h+var_50]
0x140058351  xor     rcx, rsp; StackCookie
0x140058354  call    __security_check_cookie
0x140058359  add     rsp, 0B8h
0x140058360  pop     r15
0x140058362  pop     r14
0x140058364  pop     r13
0x140058366  pop     r12
0x140058368  pop     rdi
0x140058369  pop     rsi
0x14005836a  pop     rbx
0x14005836b  pop     rbp
0x14005836c  retn
  ... truncated ...
```
