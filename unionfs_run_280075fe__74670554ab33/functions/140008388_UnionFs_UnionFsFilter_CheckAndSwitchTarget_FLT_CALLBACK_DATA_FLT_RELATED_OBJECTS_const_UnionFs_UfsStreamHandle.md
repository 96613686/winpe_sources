# UnionFs::UnionFsFilter::CheckAndSwitchTarget(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::StackEventTracer &,UnionFs::CheckAndSwitchResults *)

- ea: `0x140008388`
- end: `0x1400086a8`
- name: `?CheckAndSwitchTarget@UnionFsFilter@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsStreamHandleCtx@2@AEAVStackEventTracer@2@PEAUCheckAndSwitchResults@2@@Z`
- size: `800`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, const struct UnionFs::UfsStreamHandleCtx *, struct UnionFs::StackEventTracer *, struct UnionFs::CheckAndSwitchResults *)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140008140`
- `0x14000cce0`
- `0x14001b820`

## callees

- `0x1400053c0`
- `0x140005574`
- `0x140008388`
- `0x14000c008`
- `0x14000ef30`
- `0x14000f374`
- `0x140056ac4`
- `0x140056afc`
- `0x140079df4`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140008492`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400084d9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140008492`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400084d9`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140008672`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140008672`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::CheckAndSwitchTarget(
        UnionFs::UnionFsFilter *this,
        struct _FLT_CALLBACK_DATA *a2,
        const struct _FLT_RELATED_OBJECTS *a3,
        const struct UnionFs::UfsStreamHandleCtx *a4,
        struct UnionFs::StackEventTracer *a5,
        FsFltWil::Details **a6)
{
  int v6; // edi
  FsFltWil::Details **v10; // rax
  struct FsFltWil::Details::RundownRefCacheAware *v11; // rdx
  FsFltWil::Details *v12; // rcx
  FsFltWil::Details *v13; // rdi
  __int64 v14; // rcx
  _QWORD *v15; // rdi
  __int64 v16; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v17; // rdx
  unsigned int v18; // ebx
  struct FsFltWil::Details::RundownRefCacheAware *v19; // rdx
  struct _FILE_OBJECT *FileObject; // r8
  const struct _FLT_INSTANCE *Instance; // rdx
  int v23; // edi
  struct UnionFs::UfsStreamHandleCtx *v24; // [rsp+28h] [rbp-D8h]
  struct UnionFs::UfsStreamHandleCtx *v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  char v27; // [rsp+34h] [rbp-CCh]
  __int16 v28; // [rsp+35h] [rbp-CBh]
  char v29; // [rsp+37h] [rbp-C9h]
  __int128 v30; // [rsp+38h] [rbp-C8h]
  __int64 v31; // [rsp+48h] [rbp-B8h]
  PVOID Entry; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v33[17]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+E0h] [rbp-20h] BYREF
  char v35; // [rsp+E8h] [rbp-18h]
  char v36[112]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v37; // [rsp+160h] [rbp+60h]

  LOBYTE(v6) = 0;
  if ( a6 )
  {
    v6 = *(_DWORD *)a6;
    UnionFs::CheckAndSwitchResults::Reset((UnionFs::CheckAndSwitchResults *)a6);
  }
  if ( (*(_DWORD *)a4 & 1) != 0 )
  {
    if ( (v6 & 2) != 0 && (*(_DWORD *)a4 & 0x20) == 0 )
    {
      UnionFs::UfsStreamCtx::SyncWithCOW(*((UnionFs::UfsStreamCtx **)a3->FileObject->FsContext + 17));
      v34 = v33[0];
      v35 = v33[1];
      wistd::function<void (bool)>::function<void (bool)>(v36, &v33[2]);
      memset(v33, 0, sizeof(v33));
      v10 = (FsFltWil::Details **)utl::make_unique<UnionFs::IoSyncContext,UnionFs::IoSyncContext,0>(&Entry, &v34);
      v12 = *v10;
      *v10 = 0;
      v13 = a6[2];
      a6[2] = v12;
      if ( v13 )
      {
        FsFltWil::Details::ReleaseRundownProtectionCacheAware(v13, v11);
        v14 = *((_QWORD *)v13 + 16);
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), v13);
      }
      v15 = Entry;
      if ( Entry )
      {
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)Entry, v11);
        v16 = v15[16];
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), v15);
      }
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v34, v11);
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 24LL))(v37);
      if ( !a6[2] )
      {
        v18 = -1073741670;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a5,
          (struct UnionFs::StackEventTracer *)0x4B100010D76LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::CheckAndSwitchTarget",
          "ORIGIN: Allocating IoSyncContext",
          (const char *)v24);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v33, v19);
        if ( v33[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v33[16] + 24LL))(v33[16]);
        return v18;
      }
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v33, v17);
      this = (UnionFs::UnionFsFilter *)v33[16];
      if ( v33[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v33[16] + 24LL))(v33[16]);
    }
    FileObject = a3->FileObject;
    Instance = a3->Instance;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v26 = 3;
    v27 = 0;
    v23 = UnionFs::UnionFsFilter::MapShadowFileObjectToBacking(
            this,
            Instance,
            FileObject,
            (struct UnionFs::MapShadowFileObjectResults *)&v26,
            a5,
            a4);
    if ( v23 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v23,
        (int)a5,
        (struct UnionFs::StackEventTracer *)0x23400010D82LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::CheckAndSwitchTarget",
        "PUSH: MapShadowFileObjectToBacking failure when for an SFO",
        (const char *)v25);
      return (unsigned int)v23;
    }
    if ( !v27 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("MapShadowFileObjectToBacking failed with a valid handle ctx");
      v18 = -1073741595;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC00000E5LL,
        (int)a5,
        (struct UnionFs::StackEventTracer *)0x38F00010D8CLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::CheckAndSwitchTarget",
        "ORIGIN: MapShadowFileObjectToBacking failed with a valid handle ctx",
        (const char *)v25);
      return v18;
    }
    if ( a6 )
    {
      a6[3] = a2->Iopb->TargetInstance;
      a6[4] = (FsFltWil::Details *)a2->Iopb->TargetFileObject;
    }
    a2->Iopb->TargetInstance = (PFLT_INSTANCE)v30;
    a2->Iopb->TargetFileObject = (PFILE_OBJECT)*((_QWORD *)&v30 + 1);
    FltSetCallbackDataDirty(a2);
    if ( a6 )
      *((_BYTE *)a6 + 4) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x140008388  push    rbp
0x14000838a  push    rbx
0x14000838b  push    rsi
0x14000838c  push    rdi
0x14000838d  push    r12
0x14000838f  push    r14
0x140008391  push    r15
0x140008393  lea     rbp, [rsp-70h]
0x140008398  sub     rsp, 170h
0x14000839f  mov     rax, cs:__security_cookie
0x1400083a6  xor     rax, rsp
0x1400083a9  mov     [rbp+0A0h+var_38], rax
0x1400083ad  mov     rbx, [rbp+0A0h+arg_28]
0x1400083b4  xor     edi, edi
0x1400083b6  mov     r14, [rbp+0A0h+arg_20]
0x1400083bd  mov     r12, r9
0x1400083c0  mov     r15, r8
0x1400083c3  mov     rsi, rdx
0x1400083c6  test    rbx, rbx
0x1400083c9  jz      short loc_1400083D5
0x1400083cb  mov     edi, [rbx]
0x1400083cd  mov     rcx, rbx; this
0x1400083d0  call    ?Reset@CheckAndSwitchResults@UnionFs@@QEAAXXZ; UnionFs::CheckAndSwitchResults::Reset(void)
0x1400083d5  mov     eax, [r12]
0x1400083d9  test    al, 1
0x1400083db  jz      loc_140008687
0x1400083e1  test    dil, 2
0x1400083e5  jz      loc_14000857E
0x1400083eb  test    al, 20h
0x1400083ed  jnz     loc_14000857E
0x1400083f3  mov     rax, [r15+20h]
0x1400083f7  lea     rdx, [rsp+1A0h+var_148]
0x1400083fc  mov     rcx, [rax+18h]
0x140008400  mov     rcx, [rcx+88h]; this
0x140008407  call    ?SyncWithCOW@UfsStreamCtx@UnionFs@@QEAA@XZ; UnionFs::UfsStreamCtx::SyncWithCOW(void)
0x14000840c  mov     rax, [rsp+1A0h+var_148]
0x140008411  lea     rdx, [rsp+1A0h+var_138]
0x140008416  mov     [rbp+0A0h+var_C0], rax
0x14000841a  lea     rcx, [rbp+0A0h+var_B0]
0x14000841e  mov     al, [rsp+1A0h+var_140]
0x140008422  mov     [rbp+0A0h+var_B8], al
0x140008425  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14000842a  xor     edx, edx; Val
0x14000842c  lea     rcx, [rsp+1A0h+var_148]; void *
0x140008431  mov     r8d, 88h; Size
0x140008437  call    memset
0x14000843c  lea     rdx, [rbp+0A0h+var_C0]
0x140008440  lea     rcx, [rsp+1A0h+Entry]
0x140008445  call    ??$make_unique@UIoSyncContext@UnionFs@@U12@$0A@@utl@@YA?AV?$unique_ptr@UIoSyncContext@UnionFs@@U?$default_delete@UIoSyncContext@UnionFs@@@utl@@@0@$$QEAUIoSyncContext@UnionFs@@@Z; utl::make_unique<UnionFs::IoSyncContext,UnionFs::IoSyncContext,0>(UnionFs::IoSyncContext &&)
0x14000844a  mov     rcx, [rax]
0x14000844d  mov     qword ptr [rax], 0
0x140008454  mov     rdi, [rbx+10h]
0x140008458  mov     [rbx+10h], rcx
0x14000845c  test    rdi, rdi
0x14000845f  jz      short loc_14000849E
0x140008461  mov     rcx, rdi; this
0x140008464  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140008469  mov     rcx, [rdi+80h]
0x140008470  test    rcx, rcx
0x140008473  jz      short loc_140008481
0x140008475  mov     rax, [rcx]
0x140008478  mov     rax, [rax+18h]
0x14000847c  call    _guard_dispatch_icall
0x140008481  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140008488  mov     rdx, rdi; Entry
0x14000848b  add     rcx, 380h; Lookaside
0x140008492  call    cs:__imp_ExFreeToLookasideListEx
0x140008499  nop     dword ptr [rax+rax+00h]
0x14000849e  mov     rdi, [rsp+1A0h+Entry]
0x1400084a3  test    rdi, rdi
0x1400084a6  jz      short loc_1400084E5
0x1400084a8  mov     rcx, rdi; this
0x1400084ab  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x1400084b0  mov     rcx, [rdi+80h]
0x1400084b7  test    rcx, rcx
0x1400084ba  jz      short loc_1400084C8
0x1400084bc  mov     rax, [rcx]
0x1400084bf  mov     rax, [rax+18h]
0x1400084c3  call    _guard_dispatch_icall
0x1400084c8  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400084cf  mov     rdx, rdi; Entry
0x1400084d2  add     rcx, 380h; Lookaside
0x1400084d9  call    cs:__imp_ExFreeToLookasideListEx
0x1400084e0  nop     dword ptr [rax+rax+00h]
0x1400084e5  lea     rcx, [rbp+0A0h+var_C0]; this
0x1400084e9  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x1400084ee  mov     rcx, [rbp+0A0h+var_40]
0x1400084f2  test    rcx, rcx
0x1400084f5  jz      short loc_140008503
0x1400084f7  mov     rax, [rcx]
0x1400084fa  mov     rax, [rax+18h]
0x1400084fe  call    _guard_dispatch_icall
0x140008503  cmp     qword ptr [rbx+10h], 0
0x140008508  jnz     short loc_14000855F
0x14000850a  lea     rax, aOriginAllocati_19; "ORIGIN: Allocating IoSyncContext"
0x140008511  mov     ebx, 0C000009Ah
0x140008516  mov     ecx, ebx; this
0x140008518  mov     [rsp+1A0h+var_180], rax; char *
0x14000851d  lea     r9, aUnionfsUnionfs_56; "UnionFs::UnionFsFilter::CheckAndSwitchT"...
0x140008524  mov     r8, 4B100010D76h; struct UnionFs::StackEventTracer *
0x14000852e  mov     rdx, r14; int
0x140008531  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140008536  lea     rcx, [rsp+1A0h+var_148]; this
0x14000853b  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140008540  mov     rdx, [rbp+0A0h+var_C8]
0x140008544  test    rdx, rdx
0x140008547  jz      short loc_140008558
0x140008549  mov     rcx, [rdx]
0x14000854c  mov     rax, [rcx+18h]
0x140008550  mov     rcx, rdx
0x140008553  call    _guard_dispatch_icall
0x140008558  mov     eax, ebx
0x14000855a  jmp     loc_140008689
0x14000855f  lea     rcx, [rsp+1A0h+var_148]; this
0x140008564  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140008569  mov     rcx, [rbp+0A0h+var_C8]
0x14000856d  test    rcx, rcx
0x140008570  jz      short loc_14000857E
0x140008572  mov     rax, [rcx]
0x140008575  mov     rax, [rax+18h]
0x140008579  call    _guard_dispatch_icall
0x14000857e  mov     r8, [r15+20h]; struct _FILE_OBJECT *
0x140008582  lea     r9, [rsp+1A0h+var_170]; struct UnionFs::MapShadowFileObjectResults *
0x140008587  mov     rdx, [r15+18h]; struct _FLT_INSTANCE *
0x14000858b  xor     eax, eax
0x14000858d  xorps   xmm0, xmm0
0x140008590  mov     [rsp+1A0h+var_178], r12; char *
0x140008595  mov     [rsp+1A0h+var_16B], ax
0x14000859a  mov     [rsp+1A0h+var_169], al
0x14000859e  movdqu  [rsp+1A0h+var_168], xmm0
0x1400085a4  mov     [rsp+1A0h+var_158], rax
0x1400085a9  mov     [rsp+1A0h+var_170], 3
0x1400085b1  mov     [rsp+1A0h+var_16C], 0
0x1400085b6  mov     [rsp+1A0h+var_180], r14; struct UnionFs::StackEventTracer *
0x1400085bb  call    ?MapShadowFileObjectToBacking@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAUMapShadowFileObjectResults@2@AEAVStackEventTracer@2@PEBVUfsStreamHandleCtx@2@@Z; UnionFs::UnionFsFilter::MapShadowFileObjectToBacking(_FLT_INSTANCE const &,_FILE_OBJECT &,UnionFs::MapShadowFileObjectResults &,UnionFs::StackEventTracer &,UnionFs::UfsStreamHandleCtx const *)
0x1400085c0  mov     edi, eax
0x1400085c2  test    eax, eax
0x1400085c4  jns     short loc_1400085F4
0x1400085c6  lea     rax, aPushMapshadowf_0; "PUSH: MapShadowFileObjectToBacking fail"...
0x1400085cd  mov     r8, 23400010D82h; struct UnionFs::StackEventTracer *
0x1400085d7  lea     r9, aUnionfsUnionfs_56; "UnionFs::UnionFsFilter::CheckAndSwitchT"...
0x1400085de  mov     [rsp+1A0h+var_180], rax; char *
0x1400085e3  mov     rdx, r14; int
0x1400085e6  mov     ecx, edi; this
0x1400085e8  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400085ed  mov     eax, edi
0x1400085ef  jmp     loc_140008689
0x1400085f4  cmp     [rsp+1A0h+var_16C], 0
0x1400085f9  jnz     short loc_140008638
0x1400085fb  lea     rcx, aMapshadowfileo; "MapShadowFileObjectToBacking failed wit"...
0x140008602  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140008607  lea     rax, aOriginMapshado; "ORIGIN: MapShadowFileObjectToBacking fa"...
0x14000860e  mov     ebx, 0C00000E5h
0x140008613  mov     ecx, ebx; this
0x140008615  mov     [rsp+1A0h+var_180], rax; char *
0x14000861a  lea     r9, aUnionfsUnionfs_56; "UnionFs::UnionFsFilter::CheckAndSwitchT"...
0x140008621  mov     r8, 38F00010D8Ch; struct UnionFs::StackEventTracer *
0x14000862b  mov     rdx, r14; int
0x14000862e  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140008633  jmp     loc_140008558
0x140008638  test    rbx, rbx
0x14000863b  jz      short loc_140008655
0x14000863d  mov     rax, [rsi+10h]
0x140008641  mov     rdx, [rax+10h]
0x140008645  mov     [rbx+18h], rdx
0x140008649  mov     rax, [rsi+10h]
0x14000864d  mov     rdx, [rax+8]
0x140008651  mov     [rbx+20h], rdx
0x140008655  mov     rdx, [rsi+10h]
0x140008659  mov     rcx, rsi; Data
0x14000865c  mov     rax, qword ptr [rsp+1A0h+var_168]
0x140008661  mov     [rdx+10h], rax
0x140008665  mov     rdx, [rsi+10h]
0x140008669  mov     rax, qword ptr [rsp+1A0h+var_168+8]
0x14000866e  mov     [rdx+8], rax
0x140008672  call    cs:__imp_FltSetCallbackDataDirty
0x140008679  nop     dword ptr [rax+rax+00h]
0x14000867e  test    rbx, rbx
0x140008681  jz      short loc_140008687
0x140008683  mov     byte ptr [rbx+4], 1
0x140008687  xor     eax, eax
0x140008689  mov     rcx, [rbp+0A0h+var_38]
0x14000868d  xor     rcx, rsp; StackCookie
0x140008690  call    __security_check_cookie
0x140008695  add     rsp, 170h
0x14000869c  pop     r15
0x14000869e  pop     r14
0x1400086a0  pop     r12
0x1400086a2  pop     rdi
0x1400086a3  pop     rsi
0x1400086a4  pop     rbx
0x1400086a5  pop     rbp
0x1400086a6  retn
```
