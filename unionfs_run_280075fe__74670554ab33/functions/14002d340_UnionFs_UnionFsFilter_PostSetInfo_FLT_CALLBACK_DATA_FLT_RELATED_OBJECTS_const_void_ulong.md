# UnionFs::UnionFsFilter::PostSetInfo(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)

- ea: `0x14002d340`
- end: `0x14002d629`
- name: `?PostSetInfo@UnionFsFilter@UnionFs@@SA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z`
- size: `745`
- prototype: `enum _FLT_POSTOP_CALLBACK_STATUS __fastcall(struct _FLT_CALLBACK_DATA *this, const struct _FLT_RELATED_OBJECTS *, struct _FLT_RELATED_OBJECTS *, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update`

## callees

- `0x1400056b4`
- `0x140006168`
- `0x14000f7fc`
- `0x14002aecc`
- `0x14002bd64`
- `0x14002c9f0`
- `0x14002d340`
- `0x1400424ec`
- `0x1400430fc`
- `0x140043474`
- `0x140056afc`
- `0x140079df4`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d508`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d508`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d4eb`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d4eb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d4aa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d57a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d4aa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d57a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002d4b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002d586`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002d4b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002d586`

## string_xrefs

- `0x14002d5c1`: `PUSH: Post rename`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PostSetInfo(
        struct _FLT_CALLBACK_DATA *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _ERESOURCE *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  PFILE_OBJECT v7; // rcx
  struct _LOOKASIDE_LIST_EX *v8; // rcx
  bool v9; // sf
  PFLT_FILTER Blink; // r14
  const PFLT_VOLUME *p_OwnerTable; // rsi
  volatile signed __int32 *v12; // rdi
  struct _ERESOURCE *v13; // rcx
  utl::_RefCountBase *OwnerTable; // rcx
  struct _LIST_ENTRY *Flink; // rcx
  NTSTATUS v16; // r14d
  struct _ERESOURCE *v17; // rcx
  NTSTATUS v18; // ebx
  const char *v20; // [rsp+28h] [rbp-D8h]
  PERESOURCE Resource; // [rsp+30h] [rbp-D0h] BYREF
  int v22[188]; // [rsp+38h] [rbp-C8h] BYREF

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v22, 0x339000B0A84uLL, this);
  Iopb = this->Iopb;
  switch ( Iopb->Parameters.Create.Options )
  {
    case 0xAu:
      goto LABEL_39;
    case 0xBu:
      goto LABEL_16;
    case 0x13u:
    case 0x14u:
    case 0x27u:
      v9 = this->IoStatus.Status < 0;
      Resource = a3;
      if ( !v9 && a3->SystemResourcesList.Flink )
        UnionFs::UfsStreamCtx::UpdateSFOFileSizesForScratchBFO((UnionFs::UfsStreamCtx *)a3->SystemResourcesList.Flink);
      utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(&Resource);
      goto LABEL_41;
    case 0x41u:
LABEL_39:
      v18 = UnionFs::PostRename(
              (UnionFs *)this,
              a2,
              (struct _FLT_RELATED_OBJECTS *)a3,
              (struct UnionFs::StackEventTracer *)v22);
      if ( v18 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v18,
          (int)v22,
          (struct UnionFs::StackEventTracer *)0x344000B0A8FLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PostSetInfo",
          "PUSH: Post rename",
          v20);
        this->IoStatus.Status = v18;
        this->IoStatus.Information = 0;
      }
      goto LABEL_41;
    case 0x48u:
LABEL_16:
      Blink = (PFLT_FILTER)a3->SystemResourcesList.Blink;
      p_OwnerTable = (const PFLT_VOLUME *)&a3->OwnerTable;
      if ( Blink )
      {
        v12 = (volatile signed __int32 *)*p_OwnerTable;
        if ( *p_OwnerTable )
          _InterlockedIncrement(v12 + 2);
        (*(void (__fastcall **)(PFLT_FILTER, PERESOURCE *))(*(_QWORD *)Blink + 16LL))(Blink, &Resource);
        if ( *((_WORD *)Blink + 81) != 2 || this->IoStatus.Status )
        {
          v16 = UnionFs::UfsPathCachePayload::RevertSoftTombstone(Blink, (struct UnionFs::StackEventTracer *)v22);
          if ( v16 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v16,
              (int)v22,
              (struct UnionFs::StackEventTracer *)0x45D000B0AB1LL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PostSetInfo",
              "PUSH: Reverting soft tombstone",
              v20);
            v17 = Resource;
            this->IoStatus.Status = v16;
            this->IoStatus.Information = 0;
            Resource = 0;
            if ( v17 )
            {
              ExReleaseResourceLite(v17);
              KeLeaveCriticalRegion();
            }
            if ( v12 )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v12);
            OwnerTable = (utl::_RefCountBase *)a3->OwnerTable;
            goto LABEL_27;
          }
        }
        else
        {
          UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(Blink, 0x44F000B0AAALL);
          UnionFs::UfsPathCachePayload::RevertSoftTombstone(Blink);
        }
        v13 = Resource;
        Resource = 0;
        if ( v13 )
        {
          ExReleaseResourceLite(v13);
          KeLeaveCriticalRegion();
        }
        if ( v12 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v12);
      }
      OwnerTable = *p_OwnerTable;
LABEL_27:
      if ( OwnerTable )
        utl::_RefCountBase::_DecStrong(OwnerTable);
      Flink = a3->SystemResourcesList.Flink;
      a3->SystemResourcesList.Flink = 0;
      if ( Flink )
        ObfDereferenceObject(Flink);
      v8 = (struct _LOOKASIDE_LIST_EX *)((char *)UnionFs::g_FilterState + 416);
      goto LABEL_32;
  }
  if ( a3 )
  {
    FsFltWil::Details::ReleaseRundownProtectionCacheAware(
      (FsFltWil::Details *)a3,
      (struct FsFltWil::Details::RundownRefCacheAware *)Iopb);
    v7 = *(PFILE_OBJECT *)&a3[1].ActiveCount;
    if ( v7 )
      (*(void (__fastcall **)(PFILE_OBJECT))(*(_QWORD *)&v7->Type + 24LL))(v7);
    v8 = (struct _LOOKASIDE_LIST_EX *)((char *)UnionFs::g_FilterState + 896);
LABEL_32:
    ExFreeToLookasideListEx(v8, a3);
  }
LABEL_41:
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v22);
  return 0;
}

```

## disassembly

```asm
0x14002d340  mov     [rsp-8+arg_18], rbx
0x14002d345  push    rbp
0x14002d346  push    rsi
0x14002d347  push    rdi
0x14002d348  push    r14
0x14002d34a  push    r15
0x14002d34c  lea     rbp, [rsp-230h]
0x14002d354  sub     rsp, 330h
0x14002d35b  mov     rax, cs:__security_cookie
0x14002d362  xor     rax, rsp
0x14002d365  mov     [rbp+250h+var_28], rax
0x14002d36c  mov     rbx, r8
0x14002d36f  mov     rdi, rdx
0x14002d372  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x14002d375  mov     r15, rcx
0x14002d378  lea     rcx, [rsp+350h+var_318]; this
0x14002d37d  mov     rdx, 339000B0A84h; unsigned __int64
0x14002d387  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x14002d38c  mov     rdx, [r15+10h]; struct FsFltWil::Details::RundownRefCacheAware *
0x14002d390  mov     r8d, [rdx+20h]
0x14002d394  sub     r8d, 0Ah
0x14002d398  jz      loc_14002D5A8
0x14002d39e  sub     r8d, 1
0x14002d3a2  jz      loc_14002D42E
0x14002d3a8  sub     r8d, 8
0x14002d3ac  jz      short loc_14002D406
0x14002d3ae  sub     r8d, 1
0x14002d3b2  jz      short loc_14002D406
0x14002d3b4  sub     r8d, 13h
0x14002d3b8  jz      short loc_14002D406
0x14002d3ba  sub     r8d, 1Ah
0x14002d3be  jz      loc_14002D5A8
0x14002d3c4  cmp     r8d, 7
0x14002d3c8  jz      short loc_14002D42E
0x14002d3ca  test    rbx, rbx
0x14002d3cd  jz      loc_14002D5F6
0x14002d3d3  mov     rcx, rbx; this
0x14002d3d6  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002d3db  mov     rcx, [rbx+80h]
0x14002d3e2  test    rcx, rcx
0x14002d3e5  jz      short loc_14002D3F3
0x14002d3e7  mov     rax, [rcx]
0x14002d3ea  mov     rax, [rax+18h]
0x14002d3ee  call    _guard_dispatch_icall
0x14002d3f3  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002d3fa  add     rcx, 380h
0x14002d401  jmp     loc_14002D505
0x14002d406  cmp     dword ptr [r15+18h], 0
0x14002d40b  mov     [rsp+350h+Resource], rbx
0x14002d410  jl      short loc_14002D41F
0x14002d412  mov     rcx, [rbx]; this
0x14002d415  test    rcx, rcx
0x14002d418  jz      short loc_14002D41F
0x14002d41a  call    ?UpdateSFOFileSizesForScratchBFO@UfsStreamCtx@UnionFs@@QEAAXXZ; UnionFs::UfsStreamCtx::UpdateSFOFileSizesForScratchBFO(void)
0x14002d41f  lea     rcx, [rsp+350h+Resource]
0x14002d424  call    ??1?$unique_ptr@USetFileSizeContext@UnionFs@@U?$default_delete@USetFileSizeContext@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(void)
0x14002d429  jmp     loc_14002D5F6
0x14002d42e  mov     r14, [rbx+8]
0x14002d432  lea     rsi, [rbx+10h]
0x14002d436  test    r14, r14
0x14002d439  jz      loc_14002D4CF
0x14002d43f  mov     rdi, [rsi]
0x14002d442  test    rdi, rdi
0x14002d445  jz      short loc_14002D44B
0x14002d447  lock inc dword ptr [rdi+8]
0x14002d44b  mov     rax, [r14]
0x14002d44e  lea     rdx, [rsp+350h+Resource]
0x14002d453  mov     rcx, r14
0x14002d456  mov     rax, [rax+10h]
0x14002d45a  call    _guard_dispatch_icall
0x14002d45f  movzx   eax, word ptr [r14+0A2h]
0x14002d467  nop
0x14002d468  cmp     ax, 2
0x14002d46c  jnz     loc_14002D519
0x14002d472  cmp     dword ptr [r15+18h], 0
0x14002d477  jnz     loc_14002D519
0x14002d47d  mov     rdx, 44F000B0AAAh
0x14002d487  mov     rcx, r14
0x14002d48a  call    ?InvalidateNoRevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAAXT_TAGGED_SOURCE@@@Z; UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(_TAGGED_SOURCE)
0x14002d48f  mov     rcx, r14; this
0x14002d492  call    ?RevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAA_NXZ; UnionFs::UfsPathCachePayload::RevertSoftTombstone(void)
0x14002d497  mov     rcx, [rsp+350h+Resource]; Resource
0x14002d49c  mov     [rsp+350h+Resource], 0
0x14002d4a5  test    rcx, rcx
0x14002d4a8  jz      short loc_14002D4C2
0x14002d4aa  call    cs:__imp_ExReleaseResourceLite
0x14002d4b1  nop     dword ptr [rax+rax+00h]
0x14002d4b6  call    cs:__imp_KeLeaveCriticalRegion
0x14002d4bd  nop     dword ptr [rax+rax+00h]
0x14002d4c2  test    rdi, rdi
0x14002d4c5  jz      short loc_14002D4CF
0x14002d4c7  mov     rcx, rdi; this
0x14002d4ca  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002d4cf  mov     rcx, [rsi]; this
0x14002d4d2  test    rcx, rcx
0x14002d4d5  jz      short loc_14002D4DC
0x14002d4d7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002d4dc  mov     rcx, [rbx]; Object
0x14002d4df  mov     qword ptr [rbx], 0
0x14002d4e6  test    rcx, rcx
0x14002d4e9  jz      short loc_14002D4F7
0x14002d4eb  call    cs:__imp_ObfDereferenceObject
0x14002d4f2  nop     dword ptr [rax+rax+00h]
0x14002d4f7  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002d4fe  add     rcx, 1A0h; Lookaside
0x14002d505  mov     rdx, rbx; Entry
0x14002d508  call    cs:__imp_ExFreeToLookasideListEx
0x14002d50f  nop     dword ptr [rax+rax+00h]
0x14002d514  jmp     loc_14002D5F6
0x14002d519  lea     rdx, [rsp+350h+var_318]; struct UnionFs::StackEventTracer *
0x14002d51e  mov     rcx, r14; this
0x14002d521  call    ?RevertSoftTombstone@UfsPathCachePayload@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::RevertSoftTombstone(UnionFs::StackEventTracer &)
0x14002d526  mov     r14d, eax
0x14002d529  test    eax, eax
0x14002d52b  jns     loc_14002D497
0x14002d531  lea     rax, aPushRevertingS; "PUSH: Reverting soft tombstone"
0x14002d538  mov     r8, 45D000B0AB1h; struct UnionFs::StackEventTracer *
0x14002d542  lea     r9, aUnionfsUnionfs_54; "UnionFs::UnionFsFilter::PostSetInfo"
0x14002d549  mov     [rsp+350h+var_330], rax; char *
0x14002d54e  lea     rdx, [rsp+350h+var_318]; int
0x14002d553  mov     ecx, r14d; this
0x14002d556  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002d55b  mov     rcx, [rsp+350h+Resource]; Resource
0x14002d560  mov     [r15+18h], r14d
0x14002d564  mov     qword ptr [r15+20h], 0
0x14002d56c  mov     [rsp+350h+Resource], 0
0x14002d575  test    rcx, rcx
0x14002d578  jz      short loc_14002D592
0x14002d57a  call    cs:__imp_ExReleaseResourceLite
0x14002d581  nop     dword ptr [rax+rax+00h]
0x14002d586  call    cs:__imp_KeLeaveCriticalRegion
0x14002d58d  nop     dword ptr [rax+rax+00h]
0x14002d592  test    rdi, rdi
0x14002d595  jz      short loc_14002D59F
0x14002d597  mov     rcx, rdi; this
0x14002d59a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002d59f  mov     rcx, [rbx+10h]
0x14002d5a3  jmp     loc_14002D4D2
0x14002d5a8  lea     r9, [rsp+350h+var_318]; void *
0x14002d5ad  mov     r8, rbx; struct _FLT_RELATED_OBJECTS *
0x14002d5b0  mov     rdx, rdi; struct _FLT_CALLBACK_DATA *
0x14002d5b3  mov     rcx, r15; this
0x14002d5b6  call    ?PostRename@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@PEAXAEAVStackEventTracer@1@@Z; UnionFs::PostRename(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,void *,UnionFs::StackEventTracer &)
0x14002d5bb  mov     ebx, eax
0x14002d5bd  test    eax, eax
0x14002d5bf  jns     short loc_14002D5F6
0x14002d5c1  lea     rax, aPushPostRename; "PUSH: Post rename"
0x14002d5c8  mov     r8, 344000B0A8Fh; struct UnionFs::StackEventTracer *
0x14002d5d2  lea     r9, aUnionfsUnionfs_54; "UnionFs::UnionFsFilter::PostSetInfo"
0x14002d5d9  mov     [rsp+350h+var_330], rax; char *
0x14002d5de  lea     rdx, [rsp+350h+var_318]; int
0x14002d5e3  mov     ecx, ebx; this
0x14002d5e5  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002d5ea  mov     [r15+18h], ebx
0x14002d5ee  mov     qword ptr [r15+20h], 0
0x14002d5f6  lea     rcx, [rsp+350h+var_318]; this
0x14002d5fb  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x14002d600  xor     eax, eax
0x14002d602  mov     rcx, [rbp+250h+var_28]
0x14002d609  xor     rcx, rsp; StackCookie
0x14002d60c  call    __security_check_cookie
0x14002d611  mov     rbx, [rsp+350h+arg_18]
0x14002d619  add     rsp, 330h
0x14002d620  pop     r15
0x14002d622  pop     r14
0x14002d624  pop     rdi
0x14002d625  pop     rsi
0x14002d626  pop     rbp
0x14002d627  retn
```
