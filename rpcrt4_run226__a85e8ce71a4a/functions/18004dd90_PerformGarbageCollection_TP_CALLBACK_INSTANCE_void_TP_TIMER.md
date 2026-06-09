# PerformGarbageCollection(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18004dd90`
- end: `0x18004e093`
- name: `?PerformGarbageCollection@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `771`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001a2f0`
- `0x18001bf80`
- `0x180022870`
- `0x18002b7c0`
- `0x18004d254`
- `0x18004d76c`
- `0x18004db20`
- `0x18004dc88`
- `0x18004dd90`
- `0x18004e09c`
- `0x18004f480`
- `0x180050898`
- `0x18007362c`
- `0x180092ba0`
- `0x180094418`
- `0x1800bc6e8`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18004df70`
- `ntdll!RtlLeaveCriticalSection` at `0x18004e077`
- `ntdll!RtlLeaveCriticalSection` at `0x18004df70`
- `ntdll!RtlLeaveCriticalSection` at `0x18004e077`
- `ntdll!RtlEnterCriticalSection` at `0x18004df17`
- `ntdll!RtlEnterCriticalSection` at `0x18004df17`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004debc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004debc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004de7b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004de7b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004e01e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004e01e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004de98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004de98`

## pseudocode

```c
void __fastcall PerformGarbageCollection(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)
{
  BCACHE *v3; // rcx
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
  BCache2Stats *v15; // rbx
  DWORD TickCount; // edi
  void *lpMem[2]; // [rsp+20h] [rbp-68h] BYREF
  _OWORD v18[5]; // [rsp+30h] [rbp-58h] BYREF

  if ( _InterlockedIncrement(&GarbageCollectingInProgress) <= 1 )
  {
    RpcpSetThreadpoolCallbackInstance(Instance);
    v3 = (BCACHE *)EnableIdleLrpcSContextsCleanupCount;
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
        lpMem[0] = v18;
        memset(v18, 0, 32);
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
        v3 = (BCACHE *)lpMem[0];
        if ( lpMem[0] != v18 )
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
      {
        v15 = gBufferCache2;
        TickCount = GetTickCount();
        v3 = (BCACHE *)(TickCount - *((_DWORD *)v15 + 12));
        if ( (unsigned int)v3 >= 0xEA60 )
        {
          BCache2Stats::UpdateStatsIfNecessary(v15);
          *((_DWORD *)v15 + 12) = TickCount;
        }
      }
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
0x18004dd90  push    rbx
0x18004dd92  push    rbp
0x18004dd93  push    rsi
0x18004dd94  push    rdi
0x18004dd95  push    r12
0x18004dd97  push    r14
0x18004dd99  push    r15
0x18004dd9b  sub     rsp, 50h
0x18004dd9f  mov     ebx, 1
0x18004dda4  mov     eax, ebx
0x18004dda6  lock xadd cs:?GarbageCollectingInProgress@@3JA, eax; long GarbageCollectingInProgress
0x18004ddae  add     eax, ebx
0x18004ddb0  cmp     eax, ebx
0x18004ddb2  jg      loc_18004DE55
0x18004ddb8  call    ?RpcpSetThreadpoolCallbackInstance@@YAXPEAU_TP_CALLBACK_INSTANCE@@@Z; RpcpSetThreadpoolCallbackInstance(_TP_CALLBACK_INSTANCE *)
0x18004ddbd  mov     ecx, cs:?EnableIdleLrpcSContextsCleanupCount@@3KA; ulong EnableIdleLrpcSContextsCleanupCount
0x18004ddc3  xor     r12d, r12d
0x18004ddc6  cmp     cs:?fEnableIdleConnectionCleanup@@3IA, r12d; uint fEnableIdleConnectionCleanup
0x18004ddcd  mov     eax, cs:?EnableLrpcCompletionListCheckupCount@@3KA; ulong EnableLrpcCompletionListCheckupCount
0x18004ddd3  jnz     loc_18004DEC4
0x18004ddd9  test    ecx, ecx
0x18004dddb  jnz     loc_18004DEC4
0x18004dde1  test    eax, eax
0x18004dde3  jnz     loc_18004DEC4
0x18004dde9  cmp     cs:?fEnableBCache2Cleanup@@3IA, r12d; uint fEnableBCache2Cleanup
0x18004ddf0  jnz     loc_18004DEC4
0x18004ddf6  cmp     cs:?EnableCachedLrpcViewsCleanupCount@@3KA, r12d; ulong EnableCachedLrpcViewsCleanupCount
0x18004ddfd  ja      loc_18004DEC4
0x18004de03  cmp     cs:?fEnableLrpcSecurityCacheCleanup@@3KA, r12d; ulong fEnableLrpcSecurityCacheCleanup
0x18004de0a  jnz     loc_18004DEC4
0x18004de10  cmp     cs:?EnableSparseLrpcSPipesCleanupCount@@3KA, r12d; ulong EnableSparseLrpcSPipesCleanupCount
0x18004de17  ja      loc_18004DEC4
0x18004de1d  cmp     cs:?GarbageCollectionRequested@@3JA, r12d; long GarbageCollectionRequested
0x18004de24  jz      short loc_18004DE40
0x18004de26  call    ?RpcpConvertToLongRunning@@YAJXZ; RpcpConvertToLongRunning(void)
0x18004de2b  test    eax, eax
0x18004de2d  jnz     short loc_18004DE40
0x18004de2f  mov     cs:?GarbageCollectionRequested@@3JA, r12d; long GarbageCollectionRequested
0x18004de36  call    ?OsfDeleteLingeringAssociations@OSF_CASSOCIATION@@SAXXZ; OSF_CASSOCIATION::OsfDeleteLingeringAssociations(void)
0x18004de3b  call    ?LrpcDeleteLingeringAssociations@LRPC_CASSOCIATION@@SAXXZ; LRPC_CASSOCIATION::LrpcDeleteLingeringAssociations(void)
0x18004de40  cmp     cs:?GarbageCollectionRequested@@3JA, r12d; long GarbageCollectionRequested
0x18004de47  jz      short loc_18004DE6B
0x18004de49  call    ?Flush@BCACHE@@QEAAXXZ; BCACHE::Flush(void)
0x18004de4e  xor     ecx, ecx; struct _TP_CALLBACK_INSTANCE *
0x18004de50  call    ?RpcpSetThreadpoolCallbackInstance@@YAXPEAU_TP_CALLBACK_INSTANCE@@@Z; RpcpSetThreadpoolCallbackInstance(_TP_CALLBACK_INSTANCE *)
0x18004de55  lock dec cs:?GarbageCollectingInProgress@@3JA; long GarbageCollectingInProgress
0x18004de5c  add     rsp, 50h
0x18004de60  pop     r15
0x18004de62  pop     r14
0x18004de64  pop     r12
0x18004de66  pop     rdi
0x18004de67  pop     rsi
0x18004de68  pop     rbp
0x18004de69  pop     rbx
0x18004de6a  retn
0x18004de6b  cmp     cs:?PeriodicGarbageCollectItems@@3JA, r12d; long PeriodicGarbageCollectItems
0x18004de72  jnz     short loc_18004DE49
0x18004de74  lea     rcx, ?gGarbageCollectionTimerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gGarbageCollectionTimerLock
0x18004de7b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18004de81  mov     rcx, cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA; RPC_THREAD_POOL_TIMER * gGarbageCollectionTimer
0x18004de88  test    rcx, rcx
0x18004de8b  jz      short loc_18004DEB5
0x18004de8d  mov     rcx, [rcx]; pti
0x18004de90  xor     r9d, r9d; msWindowLength
0x18004de93  xor     r8d, r8d; msPeriod
0x18004de96  xor     edx, edx; pftDueTime
0x18004de98  call    cs:__imp_SetThreadpoolTimer
0x18004de9e  mov     rcx, cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA; this
0x18004dea5  test    rcx, rcx
0x18004dea8  jnz     loc_18004E047
0x18004deae  mov     cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA, r12; RPC_THREAD_POOL_TIMER * gGarbageCollectionTimer
0x18004deb5  lea     rcx, ?gGarbageCollectionTimerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gGarbageCollectionTimerLock
0x18004debc  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18004dec2  jmp     short loc_18004DE49
0x18004dec4  cmp     cs:?PeriodicGarbageCollectItems@@3JA, r12d; long PeriodicGarbageCollectItems
0x18004decb  jz      loc_18004DE1D
0x18004ded1  test    ecx, ecx
0x18004ded3  jz      short loc_18004DEE5
0x18004ded5  xor     r8d, r8d
0x18004ded8  mov     edx, ebx
0x18004deda  call    ?EnumerateAndCallEachAddress@RPC_SERVER@@QEAAJW4AddressCallbackType@1@PEAX@Z; RPC_SERVER::EnumerateAndCallEachAddress(RPC_SERVER::AddressCallbackType,void *)
0x18004dedf  mov     eax, cs:?EnableLrpcCompletionListCheckupCount@@3KA; ulong EnableLrpcCompletionListCheckupCount
0x18004dee5  test    eax, eax
0x18004dee7  jz      loc_18004DFD9
0x18004deed  mov     rdi, cs:?GlobalRpcServer@@3PEAVRPC_SERVER@@EA; RPC_SERVER * GlobalRpcServer
0x18004def4  lea     rax, [rsp+88h+var_58]
0x18004def9  xorps   xmm0, xmm0
0x18004defc  mov     [rsp+88h+var_60], 4
0x18004df05  mov     rcx, rdi; CriticalSection
0x18004df08  mov     [rsp+88h+lpMem], rax
0x18004df0d  movups  [rsp+88h+var_58], xmm0
0x18004df12  movups  [rsp+88h+var_48], xmm0
0x18004df17  call    cs:__imp_RtlEnterCriticalSection
0x18004df1d  mov     edx, [rdi+54h]; unsigned int
0x18004df20  lea     rcx, [rsp+88h+lpMem]; this
0x18004df25  call    ?ExpandToSize@SIMPLE_DICT@@QEAAII@Z; SIMPLE_DICT::ExpandToSize(uint)
0x18004df2a  mov     r15d, eax
0x18004df2d  test    eax, eax
0x18004df2f  jz      loc_18004E051
0x18004df35  lea     r14, [rsp+88h+lpMem]
0x18004df3a  mov     ecx, r12d
0x18004df3d  cmp     ecx, [rdi+50h]
0x18004df40  jnb     short loc_18004DF6D
0x18004df42  mov     rax, [rdi+48h]
0x18004df46  lea     ebp, [rcx+1]
0x18004df49  mov     rsi, [rax+rcx*8]
0x18004df4d  test    rsi, rsi
0x18004df50  jnz     short loc_18004DF56
0x18004df52  mov     ecx, ebp
0x18004df54  jmp     short loc_18004DF3D
0x18004df56  mov     rdx, rsi; void *
0x18004df59  lea     rcx, [rsp+88h+lpMem]; this
0x18004df5e  call    ?Insert@SIMPLE_DICT@@QEAAIPEAX@Z; SIMPLE_DICT::Insert(void *)
0x18004df63  mov     rcx, rsi; this
0x18004df66  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x18004df6b  jmp     short loc_18004DF52
0x18004df6d  mov     rcx, rdi; CriticalSection
0x18004df70  call    cs:__imp_RtlLeaveCriticalSection
0x18004df76  mov     eax, r12d
0x18004df79  cmp     eax, [r14+8]
0x18004df7d  jnb     short loc_18004DFBC
0x18004df7f  mov     ecx, eax
0x18004df81  lea     esi, [rax+1]
0x18004df84  mov     rax, [r14]
0x18004df87  mov     rbx, [rax+rcx*8]
0x18004df8b  test    rbx, rbx
0x18004df8e  jnz     short loc_18004DF94
0x18004df90  mov     eax, esi
0x18004df92  jmp     short loc_18004DF79
0x18004df94  mov     rax, [rbx]
0x18004df97  mov     rcx, rbx
0x18004df9a  mov     rax, [rax+98h]
0x18004dfa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfa6  test    r15d, r15d
0x18004dfa9  jz      short loc_18004DF90
0x18004dfab  mov     rax, [rbx]
0x18004dfae  mov     rcx, rbx
0x18004dfb1  mov     rax, [rax+20h]
0x18004dfb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfba  jmp     short loc_18004DF90
0x18004dfbc  test    r15d, r15d
0x18004dfbf  jz      loc_18004E074
0x18004dfc5  mov     rcx, [rsp+88h+lpMem]; lpMem
0x18004dfca  lea     rax, [rsp+88h+var_58]
0x18004dfcf  cmp     rcx, rax
0x18004dfd2  jz      short loc_18004DFD9
0x18004dfd4  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18004dfd9  cmp     cs:?fEnableLrpcSecurityCacheCleanup@@3KA, r12d; ulong fEnableLrpcSecurityCacheCleanup
0x18004dfe0  jnz     loc_18004E06A
0x18004dfe6  cmp     cs:?EnableSparseLrpcSPipesCleanupCount@@3KA, r12d; ulong EnableSparseLrpcSPipesCleanupCount
0x18004dfed  ja      loc_18004E082
0x18004dff3  cmp     cs:?EnableCachedLrpcViewsCleanupCount@@3KA, r12d; ulong EnableCachedLrpcViewsCleanupCount
0x18004dffa  jbe     short loc_18004E001
0x18004dffc  call    ?LrpcTrimCachedViews@LRPC_CASSOCIATION@@SAXXZ; LRPC_CASSOCIATION::LrpcTrimCachedViews(void)
0x18004e001  cmp     cs:?fEnableIdleConnectionCleanup@@3IA, r12d; uint fEnableIdleConnectionCleanup
0x18004e008  jnz     short loc_18004E05A
0x18004e00a  cmp     cs:?fEnableBCache2Cleanup@@3IA, r12d; uint fEnableBCache2Cleanup
0x18004e011  jz      loc_18004DE1D
0x18004e017  mov     rbx, cs:?gBufferCache2@@3PEAVBCache2@@EA; BCache2 * gBufferCache2
0x18004e01e  call    cs:__imp_GetTickCount
0x18004e024  mov     ecx, eax
0x18004e026  mov     edi, eax
0x18004e028  sub     ecx, [rbx+30h]
0x18004e02b  cmp     ecx, 0EA60h
0x18004e031  jb      loc_18004DE1D
0x18004e037  mov     rcx, rbx; this
0x18004e03a  call    ?UpdateStatsIfNecessary@BCache2Stats@@QEAAXXZ; BCache2Stats::UpdateStatsIfNecessary(void)
0x18004e03f  mov     [rbx+30h], edi
0x18004e042  jmp     loc_18004DE1D
0x18004e047  call    ??_GRPC_THREAD_POOL_TIMER@@QEAAPEAXI@Z; RPC_THREAD_POOL_TIMER::`scalar deleting destructor'(uint)
0x18004e04c  jmp     loc_18004DEAE
0x18004e051  lea     r14, [rdi+48h]
0x18004e055  jmp     loc_18004DF76
0x18004e05a  call    ?RpcpConvertToLongRunning@@YAJXZ; RpcpConvertToLongRunning(void)
0x18004e05f  test    eax, eax
0x18004e061  jnz     short loc_18004E00A
0x18004e063  call    ?OsfDeleteIdleConnections@OSF_CCONNECTION@@SAXXZ; OSF_CCONNECTION::OsfDeleteIdleConnections(void)
0x18004e068  jmp     short loc_18004E00A
0x18004e06a  call    ?EnumerateAndCallEachInterface@RPC_SERVER@@QEAAJW4InterfaceCallbackType@1@@Z; RPC_SERVER::EnumerateAndCallEachInterface(RPC_SERVER::InterfaceCallbackType)
0x18004e06f  jmp     loc_18004DFE6
0x18004e074  mov     rcx, rdi; CriticalSection
0x18004e077  call    cs:__imp_RtlLeaveCriticalSection
0x18004e07d  jmp     loc_18004DFC5
0x18004e082  xor     r8d, r8d
0x18004e085  lea     edx, [r8+2]
0x18004e089  call    ?EnumerateAndCallEachAddress@RPC_SERVER@@QEAAJW4AddressCallbackType@1@PEAX@Z; RPC_SERVER::EnumerateAndCallEachAddress(RPC_SERVER::AddressCallbackType,void *)
0x18004e08e  jmp     loc_18004DFF3
```
