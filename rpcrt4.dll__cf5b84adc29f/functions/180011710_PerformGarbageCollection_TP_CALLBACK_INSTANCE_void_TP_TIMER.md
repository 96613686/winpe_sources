# PerformGarbageCollection(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180011710`
- end: `0x180011a03`
- name: `?PerformGarbageCollection@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `755`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d64c`
- `0x18000fd70`
- `0x1800112a8`
- `0x180011710`
- `0x180011a0c`
- `0x180011a80`
- `0x180011b94`
- `0x180012f84`
- `0x180016f98`
- `0x18001b2c0`
- `0x18001cfb0`
- `0x180023a40`
- `0x18002cab0`
- `0x1800692f0`
- `0x180096d3c`
- `0x1800a870c`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001190c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800119e4`
- `ntdll!RtlLeaveCriticalSection` at `0x18001190c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800119e4`
- `ntdll!RtlEnterCriticalSection` at `0x1800118ad`
- `ntdll!RtlEnterCriticalSection` at `0x1800118ad`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011849`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011849`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800117fc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800117fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001181f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001181f`

## pseudocode

```c
void __fastcall PerformGarbageCollection(struct _TP_CALLBACK_INSTANCE *a1, void *a2, struct _TP_TIMER *a3)
{
  BCache2 *v3; // rcx
  unsigned int v4; // eax
  PRTL_CRITICAL_SECTION v5; // rdi
  unsigned int v6; // r15d
  void **p_SpinCount; // r14
  __int64 i; // rcx
  ULONG_PTR SpinCount; // rax
  unsigned int v10; // ebp
  REFERENCED_OBJECT *v11; // rsi
  unsigned int j; // eax
  unsigned int v13; // esi
  __int64 v14; // rbx
  void *lpMem[2]; // [rsp+20h] [rbp-68h] BYREF
  _OWORD v16[5]; // [rsp+30h] [rbp-58h] BYREF

  if ( _InterlockedIncrement(&GarbageCollectingInProgress) <= 1 )
  {
    RpcpSetThreadpoolCallbackInstance(a1);
    v3 = (BCache2 *)EnableIdleLrpcSContextsCleanupCount;
    v4 = EnableLrpcCompletionListCheckupCount;
    if ( (fEnableIdleConnectionCleanup
       || EnableIdleLrpcSContextsCleanupCount
       || EnableLrpcCompletionListCheckupCount
       || fEnableBCache2Cleanup
       || EnableCachedLrpcViewsCleanupCount
       || fEnableLrpcSecurityCacheCleanup
       || EnableSparseLrpcSPipesCleanupCount)
      && PeriodicGarbageCollectItems )
    {
      if ( EnableIdleLrpcSContextsCleanupCount )
      {
        RPC_SERVER::EnumerateAndCallEachAddress(EnableIdleLrpcSContextsCleanupCount, 1, 0);
        v4 = EnableLrpcCompletionListCheckupCount;
      }
      if ( v4 )
      {
        v5 = GlobalRpcServer;
        lpMem[1] = (void *)4;
        lpMem[0] = v16;
        memset(v16, 0, 32);
        RtlEnterCriticalSection(GlobalRpcServer);
        v6 = SIMPLE_DICT::ExpandToSize((SIMPLE_DICT *)lpMem, HIDWORD(v5[2].DebugInfo));
        if ( v6 )
        {
          p_SpinCount = lpMem;
          for ( i = 0; (unsigned int)i < LODWORD(v5[2].DebugInfo); i = v10 )
          {
            SpinCount = v5[1].SpinCount;
            v10 = i + 1;
            v11 = *(REFERENCED_OBJECT **)(SpinCount + 8 * i);
            if ( v11 )
            {
              SIMPLE_DICT::Insert((SIMPLE_DICT *)lpMem, *(void **)(SpinCount + 8 * i));
              REFERENCED_OBJECT::AddReference(v11);
            }
          }
          RtlLeaveCriticalSection(v5);
        }
        else
        {
          p_SpinCount = (void **)&v5[1].SpinCount;
        }
        for ( j = 0; j < *((_DWORD *)p_SpinCount + 2); j = v13 )
        {
          v13 = j + 1;
          v14 = *((_QWORD *)*p_SpinCount + j);
          if ( v14 )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14 + 152LL))(*((_QWORD *)*p_SpinCount + j));
            if ( v6 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14);
          }
        }
        if ( !v6 )
          RtlLeaveCriticalSection(v5);
        v3 = (BCache2 *)lpMem[0];
        if ( lpMem[0] != v16 )
          FreeWrapper(lpMem[0]);
      }
      if ( fEnableLrpcSecurityCacheCleanup )
        RPC_SERVER::EnumerateAndCallEachInterface();
      if ( EnableSparseLrpcSPipesCleanupCount )
        RPC_SERVER::EnumerateAndCallEachAddress(v3, 2, 0);
      if ( EnableCachedLrpcViewsCleanupCount )
        LRPC_CASSOCIATION::LrpcTrimCachedViews();
      if ( fEnableIdleConnectionCleanup && !(unsigned int)RpcpConvertToLongRunning() )
        OSF_CCONNECTION::OsfDeleteIdleConnections();
      if ( fEnableBCache2Cleanup )
        BCache2::DoWork(v3);
    }
    if ( GarbageCollectionRequested && !(unsigned int)RpcpConvertToLongRunning() )
    {
      GarbageCollectionRequested = 0;
      OSF_CASSOCIATION::OsfDeleteLingeringAssociations();
      LRPC_CASSOCIATION::LrpcDeleteLingeringAssociations();
    }
    if ( !GarbageCollectionRequested && !PeriodicGarbageCollectItems )
    {
      RtlAcquireSRWLockExclusive(&gGarbageCollectionTimerLock);
      if ( gGarbageCollectionTimer )
      {
        SetThreadpoolTimer(*(PTP_TIMER *)gGarbageCollectionTimer, 0, 0, 0);
        if ( gGarbageCollectionTimer )
          RPC_THREAD_POOL_TIMER::`scalar deleting destructor'((PTP_TIMER *)gGarbageCollectionTimer);
        gGarbageCollectionTimer = 0;
      }
      RtlReleaseSRWLockExclusive(&gGarbageCollectionTimerLock);
    }
    BCACHE::Flush(v3);
    RpcpSetThreadpoolCallbackInstance(0);
  }
  _InterlockedDecrement(&GarbageCollectingInProgress);
}

```

## disassembly

```asm
0x180011710  push    rbx
0x180011712  push    rbp
0x180011713  push    rsi
0x180011714  push    rdi
0x180011715  push    r12
0x180011717  push    r14
0x180011719  push    r15
0x18001171b  sub     rsp, 50h
0x18001171f  mov     ebx, 1
0x180011724  mov     eax, ebx
0x180011726  lock xadd cs:?GarbageCollectingInProgress@@3JA, eax; long GarbageCollectingInProgress
0x18001172e  add     eax, ebx
0x180011730  cmp     eax, ebx
0x180011732  jg      loc_1800117D5
0x180011738  call    ?RpcpSetThreadpoolCallbackInstance@@YAXPEAU_TP_CALLBACK_INSTANCE@@@Z; RpcpSetThreadpoolCallbackInstance(_TP_CALLBACK_INSTANCE *)
0x18001173d  mov     ecx, cs:?EnableIdleLrpcSContextsCleanupCount@@3KA; ulong EnableIdleLrpcSContextsCleanupCount
0x180011743  xor     r12d, r12d
0x180011746  cmp     cs:?fEnableIdleConnectionCleanup@@3IA, r12d; uint fEnableIdleConnectionCleanup
0x18001174d  mov     eax, cs:?EnableLrpcCompletionListCheckupCount@@3KA; ulong EnableLrpcCompletionListCheckupCount
0x180011753  jnz     loc_18001185A
0x180011759  test    ecx, ecx
0x18001175b  jnz     loc_18001185A
0x180011761  test    eax, eax
0x180011763  jnz     loc_18001185A
0x180011769  cmp     cs:?fEnableBCache2Cleanup@@3IA, r12d; uint fEnableBCache2Cleanup
0x180011770  jnz     loc_18001185A
0x180011776  cmp     cs:?EnableCachedLrpcViewsCleanupCount@@3KA, r12d; ulong EnableCachedLrpcViewsCleanupCount
0x18001177d  ja      loc_18001185A
0x180011783  cmp     cs:?fEnableLrpcSecurityCacheCleanup@@3KA, r12d; ulong fEnableLrpcSecurityCacheCleanup
0x18001178a  jnz     loc_18001185A
0x180011790  cmp     cs:?EnableSparseLrpcSPipesCleanupCount@@3KA, r12d; ulong EnableSparseLrpcSPipesCleanupCount
0x180011797  ja      loc_18001185A
0x18001179d  cmp     cs:?GarbageCollectionRequested@@3JA, r12d; long GarbageCollectionRequested
0x1800117a4  jz      short loc_1800117C0
0x1800117a6  call    ?RpcpConvertToLongRunning@@YAJXZ; RpcpConvertToLongRunning(void)
0x1800117ab  test    eax, eax
0x1800117ad  jnz     short loc_1800117C0
0x1800117af  mov     cs:?GarbageCollectionRequested@@3JA, r12d; long GarbageCollectionRequested
0x1800117b6  call    ?OsfDeleteLingeringAssociations@OSF_CASSOCIATION@@SAXXZ; OSF_CASSOCIATION::OsfDeleteLingeringAssociations(void)
0x1800117bb  call    ?LrpcDeleteLingeringAssociations@LRPC_CASSOCIATION@@SAXXZ; LRPC_CASSOCIATION::LrpcDeleteLingeringAssociations(void)
0x1800117c0  cmp     cs:?GarbageCollectionRequested@@3JA, r12d; long GarbageCollectionRequested
0x1800117c7  jz      short loc_1800117EC
0x1800117c9  call    ?Flush@BCACHE@@QEAAXXZ; BCACHE::Flush(void)
0x1800117ce  xor     ecx, ecx; struct _TP_CALLBACK_INSTANCE *
0x1800117d0  call    ?RpcpSetThreadpoolCallbackInstance@@YAXPEAU_TP_CALLBACK_INSTANCE@@@Z; RpcpSetThreadpoolCallbackInstance(_TP_CALLBACK_INSTANCE *)
0x1800117d5  lock dec cs:?GarbageCollectingInProgress@@3JA; long GarbageCollectingInProgress
0x1800117dc  add     rsp, 50h
0x1800117e0  pop     r15
0x1800117e2  pop     r14
0x1800117e4  pop     r12
0x1800117e6  pop     rdi
0x1800117e7  pop     rsi
0x1800117e8  pop     rbp
0x1800117e9  pop     rbx
0x1800117ea  retn
0x1800117ec  cmp     cs:?PeriodicGarbageCollectItems@@3JA, r12d; long PeriodicGarbageCollectItems
0x1800117f3  jnz     short loc_1800117C9
0x1800117f5  lea     rcx, ?gGarbageCollectionTimerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gGarbageCollectionTimerLock
0x1800117fc  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180011803  nop     dword ptr [rax+rax+00h]
0x180011808  mov     rcx, cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA; RPC_THREAD_POOL_TIMER * gGarbageCollectionTimer
0x18001180f  test    rcx, rcx
0x180011812  jz      short loc_180011842
0x180011814  mov     rcx, [rcx]; pti
0x180011817  xor     r9d, r9d; msWindowLength
0x18001181a  xor     r8d, r8d; msPeriod
0x18001181d  xor     edx, edx; pftDueTime
0x18001181f  call    cs:__imp_SetThreadpoolTimer
0x180011826  nop     dword ptr [rax+rax+00h]
0x18001182b  mov     rcx, cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA; this
0x180011832  test    rcx, rcx
0x180011835  jnz     loc_1800119B7
0x18001183b  mov     cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA, r12; RPC_THREAD_POOL_TIMER * gGarbageCollectionTimer
0x180011842  lea     rcx, ?gGarbageCollectionTimerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gGarbageCollectionTimerLock
0x180011849  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180011850  nop     dword ptr [rax+rax+00h]
0x180011855  jmp     loc_1800117C9
0x18001185a  cmp     cs:?PeriodicGarbageCollectItems@@3JA, r12d; long PeriodicGarbageCollectItems
0x180011861  jz      loc_18001179D
0x180011867  test    ecx, ecx
0x180011869  jz      short loc_18001187B
0x18001186b  xor     r8d, r8d
0x18001186e  mov     edx, ebx
0x180011870  call    ?EnumerateAndCallEachAddress@RPC_SERVER@@QEAAJW4AddressCallbackType@1@PEAX@Z; RPC_SERVER::EnumerateAndCallEachAddress(RPC_SERVER::AddressCallbackType,void *)
0x180011875  mov     eax, cs:?EnableLrpcCompletionListCheckupCount@@3KA; ulong EnableLrpcCompletionListCheckupCount
0x18001187b  test    eax, eax
0x18001187d  jz      loc_180011977
0x180011883  mov     rdi, cs:?GlobalRpcServer@@3PEAVRPC_SERVER@@EA; RPC_SERVER * GlobalRpcServer
0x18001188a  lea     rax, [rsp+88h+var_58]
0x18001188f  xorps   xmm0, xmm0
0x180011892  mov     [rsp+88h+var_60], 4
0x18001189b  mov     rcx, rdi; CriticalSection
0x18001189e  mov     [rsp+88h+lpMem], rax
0x1800118a3  movups  [rsp+88h+var_58], xmm0
0x1800118a8  movups  [rsp+88h+var_48], xmm0
0x1800118ad  call    cs:__imp_RtlEnterCriticalSection
0x1800118b4  nop     dword ptr [rax+rax+00h]
0x1800118b9  mov     edx, [rdi+54h]; unsigned int
0x1800118bc  lea     rcx, [rsp+88h+lpMem]; this
0x1800118c1  call    ?ExpandToSize@SIMPLE_DICT@@QEAAII@Z; SIMPLE_DICT::ExpandToSize(uint)
0x1800118c6  mov     r15d, eax
0x1800118c9  test    eax, eax
0x1800118cb  jz      loc_1800119C1
0x1800118d1  lea     r14, [rsp+88h+lpMem]
0x1800118d6  mov     ecx, r12d
0x1800118d9  cmp     ecx, [rdi+50h]
0x1800118dc  jnb     short loc_180011909
0x1800118de  mov     rax, [rdi+48h]
0x1800118e2  lea     ebp, [rcx+1]
0x1800118e5  mov     rsi, [rax+rcx*8]
0x1800118e9  test    rsi, rsi
0x1800118ec  jnz     short loc_1800118F2
0x1800118ee  mov     ecx, ebp
0x1800118f0  jmp     short loc_1800118D9
0x1800118f2  mov     rdx, rsi; void *
0x1800118f5  lea     rcx, [rsp+88h+lpMem]; this
0x1800118fa  call    ?Insert@SIMPLE_DICT@@QEAAIPEAX@Z; SIMPLE_DICT::Insert(void *)
0x1800118ff  mov     rcx, rsi; this
0x180011902  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x180011907  jmp     short loc_1800118EE
0x180011909  mov     rcx, rdi; CriticalSection
0x18001190c  call    cs:__imp_RtlLeaveCriticalSection
0x180011913  nop     dword ptr [rax+rax+00h]
0x180011918  mov     eax, r12d
0x18001191b  cmp     eax, [r14+8]
0x18001191f  jnb     short loc_18001195E
0x180011921  mov     ecx, eax
0x180011923  lea     esi, [rax+1]
0x180011926  mov     rax, [r14]
0x180011929  mov     rbx, [rax+rcx*8]
0x18001192d  test    rbx, rbx
0x180011930  jnz     short loc_180011936
0x180011932  mov     eax, esi
0x180011934  jmp     short loc_18001191B
0x180011936  mov     rax, [rbx]
0x180011939  mov     rcx, rbx
0x18001193c  mov     rax, [rax+98h]
0x180011943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011948  test    r15d, r15d
0x18001194b  jz      short loc_180011932
0x18001194d  mov     rax, [rbx]
0x180011950  mov     rcx, rbx
0x180011953  mov     rax, [rax+20h]
0x180011957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001195c  jmp     short loc_180011932
0x18001195e  test    r15d, r15d
0x180011961  jz      short loc_1800119E1
0x180011963  mov     rcx, [rsp+88h+lpMem]; lpMem
0x180011968  lea     rax, [rsp+88h+var_58]
0x18001196d  cmp     rcx, rax
0x180011970  jz      short loc_180011977
0x180011972  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180011977  cmp     cs:?fEnableLrpcSecurityCacheCleanup@@3KA, r12d; ulong fEnableLrpcSecurityCacheCleanup
0x18001197e  jnz     short loc_1800119DA
0x180011980  cmp     cs:?EnableSparseLrpcSPipesCleanupCount@@3KA, r12d; ulong EnableSparseLrpcSPipesCleanupCount
0x180011987  ja      short loc_1800119F5
0x180011989  cmp     cs:?EnableCachedLrpcViewsCleanupCount@@3KA, r12d; ulong EnableCachedLrpcViewsCleanupCount
0x180011990  jbe     short loc_180011997
0x180011992  call    ?LrpcTrimCachedViews@LRPC_CASSOCIATION@@SAXXZ; LRPC_CASSOCIATION::LrpcTrimCachedViews(void)
0x180011997  cmp     cs:?fEnableIdleConnectionCleanup@@3IA, r12d; uint fEnableIdleConnectionCleanup
0x18001199e  jnz     short loc_1800119CA
0x1800119a0  cmp     cs:?fEnableBCache2Cleanup@@3IA, r12d; uint fEnableBCache2Cleanup
0x1800119a7  jz      loc_18001179D
0x1800119ad  call    ?DoWork@BCache2@@QEAAXXZ; BCache2::DoWork(void)
0x1800119b2  jmp     loc_18001179D
0x1800119b7  call    ??_GRPC_THREAD_POOL_TIMER@@QEAAPEAXI@Z; RPC_THREAD_POOL_TIMER::`scalar deleting destructor'(uint)
0x1800119bc  jmp     loc_18001183B
0x1800119c1  lea     r14, [rdi+48h]
0x1800119c5  jmp     loc_180011918
0x1800119ca  call    ?RpcpConvertToLongRunning@@YAJXZ; RpcpConvertToLongRunning(void)
0x1800119cf  test    eax, eax
0x1800119d1  jnz     short loc_1800119A0
0x1800119d3  call    ?OsfDeleteIdleConnections@OSF_CCONNECTION@@SAXXZ; OSF_CCONNECTION::OsfDeleteIdleConnections(void)
0x1800119d8  jmp     short loc_1800119A0
0x1800119da  call    ?EnumerateAndCallEachInterface@RPC_SERVER@@QEAAJW4InterfaceCallbackType@1@@Z; RPC_SERVER::EnumerateAndCallEachInterface(RPC_SERVER::InterfaceCallbackType)
0x1800119df  jmp     short loc_180011980
0x1800119e1  mov     rcx, rdi; CriticalSection
0x1800119e4  call    cs:__imp_RtlLeaveCriticalSection
0x1800119eb  nop     dword ptr [rax+rax+00h]
0x1800119f0  jmp     loc_180011963
0x1800119f5  xor     r8d, r8d
0x1800119f8  lea     edx, [r8+2]
0x1800119fc  call    ?EnumerateAndCallEachAddress@RPC_SERVER@@QEAAJW4AddressCallbackType@1@PEAX@Z; RPC_SERVER::EnumerateAndCallEachAddress(RPC_SERVER::AddressCallbackType,void *)
0x180011a01  jmp     short loc_180011989
```
