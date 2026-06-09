# UnionFs::UfsPathCacheManager::RemovalListWorkerImpl(UnionFs::StackEventTracer &)

- ea: `0x14003e44c`
- end: `0x14003e955`
- name: `?RemovalListWorkerImpl@UfsPathCacheManager@UnionFs@@AEAAJAEAVStackEventTracer@2@@Z`
- size: `1289`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14003e3e0`

## callees

- `0x14000f7fc`
- `0x14000ffb4`
- `0x14002b1d8`
- `0x14003b728`
- `0x14003c5ec`
- `0x14003dd20`
- `0x14003e08c`
- `0x14003e44c`
- `0x1400567f4`
- `0x140056ac4`
- `0x140056afc`
- `0x140079970`
- `0x1400799a4`
- `0x140079a24`
- `0x140079da0`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003e886`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003e886`
- `ntoskrnl!KeClearEvent` at `0x14003e8b3`
- `ntoskrnl!KeClearEvent` at `0x14003e8b3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003e8c3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003e925`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003e8c3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003e925`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003e65c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003e65c`
- `ntoskrnl!KeSetEvent` at `0x14003e90b`
- `ntoskrnl!KeSetEvent` at `0x14003e90b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003e4f1`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003e82e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003e4f1`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003e82e`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14003e8f3`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14003e8f3`

## string_xrefs

- `0x14003e5ae`: `Could not DeleteEntry for item removal`
- `0x14003e5cb`: `UnionFs::UfsPathCacheManager::RemovalListWorkerImpl`
- `0x14003e7da`: `UnionFs::UfsPathCacheManager::RemovalListWorkerImpl`
- `0x14003e7c9`: `ORIGIN: Inserting into CachesOverThreshold`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCacheManager::RemovalListWorkerImpl(
        PKSPIN_LOCK SpinLock,
        struct UnionFs::StackEventTracer *a2)
{
  bool v3; // zf
  _QWORD *v5; // rdx
  void *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // r8
  signed __int32 v9; // edx
  signed __int32 v10; // eax
  utl::_RefCountBase *v11; // rdi
  int v12; // eax
  unsigned int v13; // r14d
  _QWORD *v14; // rbx
  char v15; // r13
  const struct std::nothrow_t *v16; // rdx
  char *v17; // rax
  __int64 v18; // rdi
  __int64 v19; // rax
  unsigned __int64 v20; // r12
  PKSPIN_LOCK v21; // r14
  unsigned __int64 *v22; // rax
  unsigned __int64 *v23; // rbx
  struct _KSPIN_LOCK_QUEUE *v24; // rcx
  struct _KSPIN_LOCK_QUEUE *v25; // r8
  char v26; // r14
  unsigned __int64 *v27; // rax
  struct _FAST_MUTEX *v28; // rcx
  char *v30; // [rsp+28h] [rbp-48h]
  char *v31; // [rsp+30h] [rbp-40h]
  PVOID Entry; // [rsp+38h] [rbp-38h] BYREF
  PVOID *p_Entry; // [rsp+40h] [rbp-30h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-28h] BYREF
  PKSPIN_LOCK v35; // [rsp+60h] [rbp-10h] BYREF
  char v36; // [rsp+68h] [rbp-8h]
  PFAST_MUTEX FastMutex; // [rsp+B0h] [rbp+40h] BYREF
  PFAST_MUTEX v38; // [rsp+C0h] [rbp+50h] BYREF
  FsFltWil::Details *v39; // [rsp+C8h] [rbp+58h] BYREF

  v35 = SpinLock;
  ++*((_DWORD *)SpinLock + 66);
  v3 = *((_DWORD *)SpinLock + 54) == 0;
  v36 = 1;
  if ( !v3 )
  {
    p_Entry = &Entry;
    Entry = &Entry;
    FsFltWil::AcquireFastMutex(&FastMutex, SpinLock + 20);
    v5 = (_QWORD *)SpinLock[18];
    p_Entry = (PVOID *)SpinLock[19];
    SpinLock[19] = (KSPIN_LOCK)(SpinLock + 18);
    SpinLock[18] = (KSPIN_LOCK)(SpinLock + 18);
    Entry = v5;
    *((_DWORD *)SpinLock + 54) = 0;
    v5[1] = &Entry;
    *p_Entry = &Entry;
    if ( FastMutex )
      ExReleaseFastMutex(FastMutex);
    while ( 1 )
    {
      while ( 1 )
      {
        v6 = Entry;
        if ( Entry == &Entry )
          goto LABEL_25;
        if ( *((PVOID **)Entry + 1) != &Entry || (v7 = *(_QWORD *)Entry, *(PVOID *)(*(_QWORD *)Entry + 8LL) != Entry) )
          __fastfail(3u);
        Entry = *(PVOID *)Entry;
        *(_QWORD *)(v7 + 8) = &Entry;
        v8 = *((_QWORD *)v6 + 6);
        FastMutex = (PFAST_MUTEX)v6;
        if ( v8 )
        {
          v9 = *(_DWORD *)(v8 + 8);
          if ( v9 )
            break;
        }
LABEL_23:
        UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem((UnionFs::UfsPathCacheListItem *)v6);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 992), v6);
      }
      while ( 1 )
      {
        v10 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 8), v9 + 1, v9);
        if ( v9 == v10 )
          break;
        v9 = v10;
        if ( !v10 )
          goto LABEL_23;
      }
      v11 = (utl::_RefCountBase *)*((_QWORD *)v6 + 6);
      if ( !*((_QWORD *)v6 + 5) )
      {
        if ( v11 )
          utl::_RefCountBase::_DecStrong(*((utl::_RefCountBase **)v6 + 6));
        goto LABEL_23;
      }
      v30 = 0;
      v12 = UnionFs::UfsPathCache::DeleteEntry(*((_QWORD *)v6 + 2), *((_QWORD *)v6 + 3), *((_QWORD *)v6 + 4), a2, 0);
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( v12 == -1073741275 )
        {
          *(_DWORD *)a2 = 0;
          *((_WORD *)a2 + 274) = 0;
        }
        else
        {
          MicrosoftTelemetryAssertTriggeredMsgKM("Could not DeleteEntry for item removal");
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)v13,
            (int)a2,
            (struct UnionFs::StackEventTracer *)0x436001101C4LL,
            (unsigned __int64)"UnionFs::UfsPathCacheManager::RemovalListWorkerImpl",
            "PUSH: Deleting entry",
            0);
          UnionFs::StackEventTracer::LogError(a2);
          *(_DWORD *)a2 = 0;
          *((_WORD *)a2 + 274) = 0;
          UnionFs::UfsPathCacheManager::AddToRemovalList(SpinLock, &FastMutex);
          v6 = FastMutex;
        }
      }
      if ( v11 )
        utl::_RefCountBase::_DecStrong(v11);
      if ( v6 )
        goto LABEL_23;
    }
  }
LABEL_25:
  v14 = UnionFs::g_FilterState;
  v15 = 0;
  FsFltWil::AcquirePushLockShared(&v39, (char *)UnionFs::g_FilterState + 64);
  v17 = (char *)(v14 + 4);
  v18 = v14[6];
  v31 = (char *)(v14 + 4);
  while ( (char *)v18 != v17 )
  {
    v19 = *(_QWORD *)(v18 + 40);
    if ( *(_DWORD *)(v19 + 28) == 2 )
      v20 = *(_QWORD *)(*(_QWORD *)(v19 + 32) + 16LL);
    else
      v20 = *((_QWORD *)UnionFs::g_FilterState + 10);
    if ( *(_DWORD *)(v20 + 224) <= *((_DWORD *)SpinLock + 101) )
      goto LABEL_55;
    FsFltWil::AcquireFastMutex(&v38, SpinLock + 39);
    v21 = SpinLock + 35;
    if ( (PKSPIN_LOCK)SpinLock[37] == SpinLock + 35 )
    {
      v22 = (unsigned __int64 *)operator new(0x20u, v16);
      v23 = v22;
      if ( !v22 )
        goto LABEL_49;
      v22[3] = v20;
      *v22 = (unsigned __int64)v21 | 1;
      v22[1] = (unsigned __int64)&utl::_TreeSentinel;
      v22[2] = (unsigned __int64)&utl::_TreeSentinel;
      *v21 = (KSPIN_LOCK)v22;
      SpinLock[36] = (KSPIN_LOCK)v22;
      SpinLock[37] = (KSPIN_LOCK)v22;
      ++SpinLock[38];
    }
    else
    {
      v24 = (struct _KSPIN_LOCK_QUEUE *)*v21;
      v23 = 0;
      do
      {
        if ( (volatile PKSPIN_LOCK)v20 >= v24[1].Lock )
        {
          v23 = (unsigned __int64 *)v24;
          LOBYTE(v16) = 1;
        }
        else
        {
          LOBYTE(v16) = 0;
        }
        v25 = v24;
        v24 = (struct _KSPIN_LOCK_QUEUE *)*((_QWORD *)&v24->Lock + (unsigned __int8)v16);
      }
      while ( v24 != (struct _KSPIN_LOCK_QUEUE *)&utl::_TreeSentinel );
      if ( v23 && v23[3] < v20 )
        v23 = 0;
      LockHandle.LockQueue.Next = v25;
      LOBYTE(LockHandle.LockQueue.Lock) = (_BYTE)v16;
      if ( v23 )
      {
        v26 = 0;
        goto LABEL_47;
      }
      v27 = (unsigned __int64 *)operator new(0x20u, v16);
      v23 = v27;
      if ( !v27 )
      {
LABEL_49:
        v26 = 0;
LABEL_50:
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a2,
          (struct UnionFs::StackEventTracer *)0x431001101F0LL,
          (unsigned __int64)"UnionFs::UfsPathCacheManager::RemovalListWorkerImpl",
          "ORIGIN: Inserting into CachesOverThreshold",
          v30);
        UnionFs::StackEventTracer::LogError(a2);
        *(_DWORD *)a2 = 0;
        *((_WORD *)a2 + 274) = 0;
        goto LABEL_51;
      }
      v27[3] = v20;
      utl::_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>,UnionFs::Utils::GuidComparator,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>>,0>::_InsertAt(
        SpinLock + 35,
        &LockHandle,
        v27);
    }
    v26 = 1;
LABEL_47:
    if ( !v23 )
      goto LABEL_50;
LABEL_51:
    v28 = v38;
    if ( v26 )
      v15 = 1;
    v38 = 0;
    if ( v28 )
      ExReleaseFastMutex(v28);
LABEL_55:
    LOBYTE(v16) = 1;
    v18 = utl::_TreeNodeHeader<utl::pair<_GUID const,utl::shared_ptr<UnionFs::UfsUnionCtx>>>::_Traverse(v18, v16);
    v17 = v31;
  }
  if ( v39 )
    FsFltWil::Details::ReleasePushLockShared(v39, (unsigned __int64 *)v16);
  if ( v15 )
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
    if ( !*((_BYTE *)SpinLock + 8) || _InterlockedCompareExchange((volatile signed __int32 *)SpinLock + 92, 1, 0) )
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    else
    {
      KeClearEvent((PRKEVENT)(SpinLock + 47));
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( FltQueueGenericWorkItem(
             (PFLT_GENERIC_WORKITEM)SpinLock[34],
             *(PVOID *)UnionFs::g_FilterState,
             UnionFs::UfsPathCacheManager::TrimmerWorker,
             DelayedWorkQueue,
             0) < 0 )
      {
        KeSetEvent((PRKEVENT)(SpinLock + 47), 0, 0);
        _InterlockedExchange((volatile __int32 *)SpinLock + 92, 0);
      }
    }
  }
  wil::details::lambda_call__lambda_90c8f2e607214e2792b7aa8cdd49375f___::_lambda_call__lambda_90c8f2e607214e2792b7aa8cdd49375f___(&v35);
  return 0;
}

```

## disassembly

```asm
0x14003e44c  mov     [rsp-38h+arg_8], rbx
0x14003e451  push    rbp
0x14003e452  push    rsi
0x14003e453  push    rdi
0x14003e454  push    r12
0x14003e456  push    r13
0x14003e458  push    r14
0x14003e45a  push    r15
0x14003e45c  mov     rbp, rsp
0x14003e45f  sub     rsp, 70h
0x14003e463  mov     r12d, 1
0x14003e469  mov     [rbp+var_10], rcx
0x14003e46d  add     [rcx+108h], r12d
0x14003e474  mov     r15, rdx
0x14003e477  cmp     dword ptr [rcx+0D8h], 0
0x14003e47e  mov     rsi, rcx
0x14003e481  mov     [rbp+var_8], r12b
0x14003e485  jbe     loc_14003E674
0x14003e48b  lea     rax, [rbp+Entry]
0x14003e48f  mov     [rbp+var_30], rax
0x14003e493  lea     rdx, [rcx+0A0h]
0x14003e49a  lea     rax, [rbp+Entry]
0x14003e49e  lea     rcx, [rbp+FastMutex]
0x14003e4a2  mov     [rbp+Entry], rax
0x14003e4a6  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x14003e4ab  mov     rax, [rsi+98h]
0x14003e4b2  lea     rcx, [rsi+90h]
0x14003e4b9  mov     rdx, [rcx]
0x14003e4bc  mov     [rbp+var_30], rax
0x14003e4c0  lea     rax, [rbp+Entry]
0x14003e4c4  mov     [rcx+8], rcx
0x14003e4c8  mov     [rcx], rcx
0x14003e4cb  lea     rcx, [rbp+Entry]
0x14003e4cf  mov     [rbp+Entry], rdx
0x14003e4d3  mov     dword ptr [rsi+0D8h], 0
0x14003e4dd  mov     [rdx+8], rax
0x14003e4e1  mov     rax, [rbp+var_30]
0x14003e4e5  mov     [rax], rcx
0x14003e4e8  mov     rcx, [rbp+FastMutex]; FastMutex
0x14003e4ec  test    rcx, rcx
0x14003e4ef  jz      short loc_14003E4FD
0x14003e4f1  call    cs:__imp_ExReleaseFastMutex
0x14003e4f8  nop     dword ptr [rax+rax+00h]
0x14003e4fd  mov     rbx, [rbp+Entry]
0x14003e501  lea     rax, [rbp+Entry]
0x14003e505  cmp     rbx, rax
0x14003e508  jz      loc_14003E674
0x14003e50e  lea     rax, [rbp+Entry]
0x14003e512  cmp     [rbx+8], rax
0x14003e516  jnz     loc_14003E66D
0x14003e51c  mov     rax, [rbx]
0x14003e51f  cmp     [rax+8], rbx
0x14003e523  jnz     loc_14003E66D
0x14003e529  mov     [rbp+Entry], rax
0x14003e52d  lea     rcx, [rbp+Entry]
0x14003e531  mov     [rax+8], rcx
0x14003e535  mov     r8, [rbx+30h]
0x14003e539  mov     [rbp+FastMutex], rbx
0x14003e53d  test    r8, r8
0x14003e540  jz      loc_14003E643
0x14003e546  mov     edx, [r8+8]
0x14003e54a  test    edx, edx
0x14003e54c  jz      loc_14003E643
0x14003e552  lea     ecx, [rdx+1]
0x14003e555  mov     eax, edx
0x14003e557  lock cmpxchg [r8+8], ecx
0x14003e55d  cmp     edx, eax
0x14003e55f  jz      short loc_14003E56C
0x14003e561  mov     edx, eax
0x14003e563  test    eax, eax
0x14003e565  jnz     short loc_14003E552
0x14003e567  jmp     loc_14003E643
0x14003e56c  cmp     qword ptr [rbx+28h], 0
0x14003e571  mov     rdi, [rbx+30h]
0x14003e575  jz      loc_14003E636
0x14003e57b  mov     r8, [rbx+20h]
0x14003e57f  mov     r9, r15
0x14003e582  mov     rdx, [rbx+18h]
0x14003e586  mov     rcx, [rbx+10h]
0x14003e58a  mov     [rsp+70h+var_48], 0; char *
0x14003e593  mov     dword ptr [rsp+70h+Context], 0
0x14003e59b  call    ?DeleteEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEBVUfsUnionCtx@2@@Z; UnionFs::UfsPathCache::DeleteEntry(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,UnionFs::UfsUnionCtx const *)
0x14003e5a0  mov     r14d, eax
0x14003e5a3  test    eax, eax
0x14003e5a5  jns     short loc_14003E61E
0x14003e5a7  cmp     eax, 0C0000225h
0x14003e5ac  jz      short loc_14003E60D
0x14003e5ae  lea     rcx, aCouldNotDelete; "Could not DeleteEntry for item removal"
0x14003e5b5  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003e5ba  lea     rax, aPushDeletingEn; "PUSH: Deleting entry"
0x14003e5c1  mov     r8, 436001101C4h; struct UnionFs::StackEventTracer *
0x14003e5cb  lea     r9, aUnionfsUfspath_74; "UnionFs::UfsPathCacheManager::RemovalLi"...
0x14003e5d2  mov     [rsp+70h+Context], rax; char *
0x14003e5d7  mov     rdx, r15; int
0x14003e5da  mov     ecx, r14d; this
0x14003e5dd  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003e5e2  mov     rcx, r15; this
0x14003e5e5  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14003e5ea  xor     eax, eax
0x14003e5ec  mov     dword ptr [r15], 0
0x14003e5f3  lea     rdx, [rbp+FastMutex]
0x14003e5f7  mov     [r15+224h], ax
0x14003e5ff  mov     rcx, rsi
0x14003e602  call    ?AddToRemovalList@UfsPathCacheManager@UnionFs@@QEAAX$$QEAV?$unique_ptr@VUfsPathCacheListItem@UnionFs@@U?$default_delete@VUfsPathCacheListItem@UnionFs@@@utl@@@utl@@@Z; UnionFs::UfsPathCacheManager::AddToRemovalList(utl::unique_ptr<UnionFs::UfsPathCacheListItem,utl::default_delete<UnionFs::UfsPathCacheListItem>> &&)
0x14003e607  mov     rbx, [rbp+FastMutex]
0x14003e60b  jmp     short loc_14003E61E
0x14003e60d  xor     eax, eax
0x14003e60f  mov     dword ptr [r15], 0
0x14003e616  mov     [r15+224h], ax
0x14003e61e  test    rdi, rdi
0x14003e621  jz      short loc_14003E62B
0x14003e623  mov     rcx, rdi; this
0x14003e626  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003e62b  test    rbx, rbx
0x14003e62e  jz      loc_14003E4FD
0x14003e634  jmp     short loc_14003E643
0x14003e636  test    rdi, rdi
0x14003e639  jz      short loc_14003E643
0x14003e63b  mov     rcx, rdi; this
0x14003e63e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003e643  mov     rcx, rbx; this
0x14003e646  call    ??1UfsPathCacheListItem@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(void)
0x14003e64b  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003e652  mov     rdx, rbx; Entry
0x14003e655  add     rcx, 3E0h; Lookaside
0x14003e65c  call    cs:__imp_ExFreeToLookasideListEx
0x14003e663  nop     dword ptr [rax+rax+00h]
0x14003e668  jmp     loc_14003E4FD
0x14003e66d  mov     ecx, 3
0x14003e672  int     29h; Win8: RtlFailFast(ecx)
0x14003e674  mov     rbx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003e67b  lea     rcx, [rbp+arg_18]
0x14003e67f  xor     r13b, r13b
0x14003e682  lea     rdx, [rbx+40h]
0x14003e686  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14003e68b  lea     rax, [rbx+20h]
0x14003e68f  mov     rdi, [rax+10h]
0x14003e693  mov     [rbp+var_40], rax
0x14003e697  cmp     rdi, rax
0x14003e69a  jz      loc_14003E859
0x14003e6a0  mov     rax, [rdi+28h]
0x14003e6a4  cmp     dword ptr [rax+1Ch], 2
0x14003e6a8  jnz     short loc_14003E6B4
0x14003e6aa  mov     rax, [rax+20h]
0x14003e6ae  mov     r12, [rax+10h]
0x14003e6b2  jmp     short loc_14003E6BF
0x14003e6b4  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003e6bb  mov     r12, [rax+50h]
0x14003e6bf  mov     eax, [rsi+194h]
0x14003e6c5  nop
0x14003e6c6  cmp     [r12+0E0h], eax
0x14003e6ce  jbe     loc_14003E83C
0x14003e6d4  lea     rdx, [rsi+138h]
0x14003e6db  lea     rcx, [rbp+arg_10]
0x14003e6df  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x14003e6e4  lea     r14, [rsi+118h]
0x14003e6eb  cmp     [r14+10h], r14
0x14003e6ef  jnz     short loc_14003E738
0x14003e6f1  mov     ecx, 20h ; ' '; unsigned __int64
0x14003e6f6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003e6fb  mov     rbx, rax
0x14003e6fe  test    rax, rax
0x14003e701  jz      loc_14003E7C6
0x14003e707  mov     [rax+18h], r12
0x14003e70b  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x14003e712  mov     rax, r14
0x14003e715  or      rax, 1
0x14003e719  mov     [rbx], rax
0x14003e71c  mov     [rbx+8], rcx
0x14003e720  mov     [rbx+10h], rcx
0x14003e724  mov     [r14], rbx
0x14003e727  mov     [r14+8], rbx
0x14003e72b  mov     [r14+10h], rbx
0x14003e72f  inc     qword ptr [r14+18h]
0x14003e733  jmp     loc_14003E7BC
0x14003e738  mov     rcx, [r14]
0x14003e73b  xor     ebx, ebx
0x14003e73d  cmp     r12, [rcx+18h]
0x14003e741  jnb     short loc_14003E747
0x14003e743  xor     dl, dl
0x14003e745  jmp     short loc_14003E74C
0x14003e747  mov     rbx, rcx
0x14003e74a  mov     dl, 1; struct std::nothrow_t *
0x14003e74c  movzx   eax, dl
0x14003e74f  mov     r8, rcx
0x14003e752  mov     rcx, [rcx+rax*8+8]
0x14003e757  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x14003e75e  cmp     rcx, rax
0x14003e761  jnz     short loc_14003E73D
0x14003e763  test    rbx, rbx
0x14003e766  jz      short loc_14003E772
0x14003e768  xor     eax, eax
0x14003e76a  cmp     [rbx+18h], r12
0x14003e76e  cmovb   rbx, rax
0x14003e772  mov     eax, dword ptr [rbp+LockHandle.LockQueue.Lock+1]
0x14003e775  mov     dword ptr [rbp+LockHandle.LockQueue.Lock+1], eax
0x14003e778  movzx   eax, word ptr [rbp+LockHandle.LockQueue.Lock+5]
0x14003e77c  mov     word ptr [rbp+LockHandle.LockQueue.Lock+5], ax
0x14003e780  mov     al, byte ptr [rbp+LockHandle.LockQueue.Lock+7]
0x14003e783  mov     byte ptr [rbp+LockHandle.LockQueue.Lock+7], al
0x14003e786  mov     [rbp+LockHandle.LockQueue.Next], r8
0x14003e78a  mov     byte ptr [rbp+LockHandle.LockQueue.Lock], dl
0x14003e78d  test    rbx, rbx
0x14003e790  jz      short loc_14003E797
0x14003e792  xor     r14b, r14b
0x14003e795  jmp     short loc_14003E7BF
0x14003e797  mov     ecx, 20h ; ' '; unsigned __int64
0x14003e79c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003e7a1  mov     rbx, rax
0x14003e7a4  test    rax, rax
0x14003e7a7  jz      short loc_14003E7C6
0x14003e7a9  mov     r8, rax
0x14003e7ac  mov     [rax+18h], r12
0x14003e7b0  lea     rdx, [rbp+LockHandle]
0x14003e7b4  mov     rcx, r14
0x14003e7b7  call    ?_InsertAt@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@UGuidComparator@Utils@UnionFs@@V?$allocator@U?$pair@$$CBU_GUID@@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@3@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBU_GUID@@V?$weak_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@2@@Z; utl::_Tree<_GUID,utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>,UnionFs::Utils::GuidComparator,utl::allocator<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>> *,bool> const &,utl::_TreeNode<utl::pair<_GUID const,utl::weak_ptr<UnionFs::UfsUnionCtx>>> *)
0x14003e7bc  mov     r14b, 1
0x14003e7bf  test    rbx, rbx
0x14003e7c2  jnz     short loc_14003E80C
0x14003e7c4  jmp     short loc_14003E7C9
0x14003e7c6  xor     r14b, r14b
0x14003e7c9  lea     rax, aOriginInsertin_0; "ORIGIN: Inserting into CachesOverThresh"...
0x14003e7d0  mov     r8, 431001101F0h; struct UnionFs::StackEventTracer *
0x14003e7da  lea     r9, aUnionfsUfspath_74; "UnionFs::UfsPathCacheManager::RemovalLi"...
0x14003e7e1  mov     [rsp+70h+Context], rax; char *
0x14003e7e6  mov     rdx, r15; int
0x14003e7e9  mov     ecx, 0C000009Ah; this
0x14003e7ee  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003e7f3  mov     rcx, r15; this
0x14003e7f6  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14003e7fb  xor     eax, eax
0x14003e7fd  mov     dword ptr [r15], 0
0x14003e804  mov     [r15+224h], ax
0x14003e80c  mov     rcx, [rbp+arg_10]; FastMutex
0x14003e810  test    r14b, r14b
0x14003e813  movzx   r13d, r13b
0x14003e817  mov     r12d, 1
0x14003e81d  cmovnz  r13d, r12d
0x14003e821  mov     [rbp+arg_10], 0
0x14003e829  test    rcx, rcx
0x14003e82c  jz      short loc_14003E842
0x14003e82e  call    cs:__imp_ExReleaseFastMutex
0x14003e835  nop     dword ptr [rax+rax+00h]
0x14003e83a  jmp     short loc_14003E842
0x14003e83c  mov     r12d, 1
0x14003e842  mov     dl, r12b
0x14003e845  mov     rcx, rdi
0x14003e848  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBU_GUID@@V?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBU_GUID@@V?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<_GUID const,utl::shared_ptr<UnionFs::UfsUnionCtx>>>::_Traverse(bool)
0x14003e84d  mov     rdi, rax
0x14003e850  mov     rax, [rbp+var_40]
0x14003e854  jmp     loc_14003E697
0x14003e859  cmp     [rbp+arg_18], 0
0x14003e85e  jz      short loc_14003E869
0x14003e860  mov     rcx, [rbp+arg_18]; this
0x14003e864  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14003e869  test    r13b, r13b
0x14003e86c  jz      loc_14003E931
0x14003e872  xorps   xmm0, xmm0
0x14003e875  lea     rdx, [rbp+LockHandle]; LockHandle
0x14003e879  xor     eax, eax
0x14003e87b  mov     rcx, rsi; SpinLock
0x14003e87e  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14003e882  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14003e886  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003e88d  nop     dword ptr [rax+rax+00h]
0x14003e892  cmp     byte ptr [rsi+8], 0
0x14003e896  jz      loc_14003E921
0x14003e89c  xor     eax, eax
0x14003e89e  lock cmpxchg [rsi+170h], r12d
0x14003e8a7  jnz     short loc_14003E921
0x14003e8a9  lea     rbx, [rsi+178h]
0x14003e8b0  mov     rcx, rbx; Event
0x14003e8b3  call    cs:__imp_KeClearEvent
0x14003e8ba  nop     dword ptr [rax+rax+00h]
0x14003e8bf  lea     rcx, [rbp+LockHandle]; LockHandle
0x14003e8c3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003e8ca  nop     dword ptr [rax+rax+00h]
0x14003e8cf  mov     rdx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003e8d6  lea     r8, ?TrimmerWorker@UfsPathCacheManager@UnionFs@@CAXPEAU_FLT_GENERIC_WORKITEM@@PEAX1@Z; WorkerRoutine
0x14003e8dd  mov     rcx, [rsi+110h]; FltWorkItem
0x14003e8e4  mov     r9d, r12d; QueueType
0x14003e8e7  mov     [rsp+70h+Context], 0; Context
0x14003e8f0  mov     rdx, [rdx]; FltObject
0x14003e8f3  call    cs:__imp_FltQueueGenericWorkItem
0x14003e8fa  nop     dword ptr [rax+rax+00h]
0x14003e8ff  test    eax, eax
0x14003e901  jns     short loc_14003E931
0x14003e903  xor     r8d, r8d; Wait
0x14003e906  xor     edx, edx; Increment
0x14003e908  mov     rcx, rbx; Event
0x14003e90b  call    cs:__imp_KeSetEvent
0x14003e912  nop     dword ptr [rax+rax+00h]
0x14003e917  xor     eax, eax
0x14003e919  xchg    eax, [rsi+170h]
0x14003e91f  jmp     short loc_14003E931
0x14003e921  lea     rcx, [rbp+LockHandle]; LockHandle
0x14003e925  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003e92c  nop     dword ptr [rax+rax+00h]
0x14003e931  lea     rcx, [rbp+var_10]
0x14003e935  call    wil__details__lambda_call__lambda_90c8f2e607214e2792b7aa8cdd49375f______lambda_call__lambda_90c8f2e607214e2792b7aa8cdd49375f___
  ... truncated ...
```
