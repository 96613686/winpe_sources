# HcsClient::OperationTracker::CompleteOperationSynchronously(std::shared_ptr<ClientOperation> const &,long,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ProcessInformation *)

- ea: `0x18003d4cc`
- end: `0x18003d8be`
- name: `?CompleteOperationSynchronously@OperationTracker@HcsClient@@QEAAXAEBV?$shared_ptr@VClientOperation@@@std@@JV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUProcessInformation@@@Z`
- size: `1010`
- prototype: ``
- caller_count: `15`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180026ad0`
- `0x180027f40`
- `0x180041390`
- `0x18004178c`
- `0x180041944`
- `0x180047368`
- `0x1800475a0`
- `0x180047c2c`
- `0x180048028`
- `0x1800487bc`
- `0x1800489e4`
- `0x180048c0c`
- `0x180048e34`
- `0x18004906c`
- `0x180049260`

## callees

- `0x180002f50`
- `0x1800033cc`
- `0x180003440`
- `0x180003c78`
- `0x1800171ac`
- `0x180017980`
- `0x18001a014`
- `0x1800212c4`
- `0x180038040`
- `0x18003816c`
- `0x180038710`
- `0x18003881c`
- `0x18003af94`
- `0x18003b540`
- `0x18003bbe8`
- `0x18003c43c`
- `0x18003d210`
- `0x18003d29c`
- `0x18003d328`
- `0x18003d4cc`
- `0x18003e9fc`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d810`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d810`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d843`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d843`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003d82d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003d82d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d88e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d88e`

## string_xrefs

- `0x18003d54b`: `ClientLib_SyncOperationCompletion`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
HLOCAL __fastcall HcsClient::OperationTracker::CompleteOperationSynchronously(
        __int64 a1,
        RTL_SRWLOCK **a2,
        int a3,
        HLOCAL *a4,
        int *a5)
{
  _QWORD *v9; // rax
  RTL_SRWLOCK *v10; // r8
  __int64 v11; // rsi
  volatile signed __int32 *v12; // rbx
  RTL_SRWLOCK *v13; // rcx
  RTL_SRWLOCK *v14; // rcx
  void (*v15)(void *); // r8
  void (*v16)(void *, void *); // r9
  int v17; // ebx
  int v18; // ecx
  _BYTE *v19; // rdx
  char v20; // al
  __int64 v21; // rbx
  HLOCAL result; // rax
  PVOID Ptr; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL *v25; // [rsp+40h] [rbp-C0h] BYREF
  volatile signed __int32 *v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+5Ch] [rbp-A4h]
  HLOCAL v30; // [rsp+60h] [rbp-A0h]
  __int128 v31; // [rsp+68h] [rbp-98h]
  PVOID v32; // [rsp+78h] [rbp-88h]
  int v33; // [rsp+80h] [rbp-80h]
  _BYTE v34[24]; // [rsp+88h] [rbp-78h] BYREF
  char v35; // [rsp+A0h] [rbp-60h]
  int v36; // [rsp+A8h] [rbp-58h]
  _BYTE v37[24]; // [rsp+B0h] [rbp-50h] BYREF
  char v38; // [rsp+C8h] [rbp-38h]
  int v39; // [rsp+D0h] [rbp-30h]
  _BYTE v40[24]; // [rsp+D8h] [rbp-28h] BYREF
  char v41; // [rsp+F0h] [rbp-10h]
  HLOCAL v42; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v43[8]; // [rsp+100h] [rbp+0h] BYREF
  char v44; // [rsp+108h] [rbp+8h]
  _QWORD v45[42]; // [rsp+110h] [rbp+10h] BYREF

  LODWORD(v42) = a3;
  v25 = a4;
  LODWORD(Ptr) = 0;
  memset_0(v45, 0, sizeof(v45));
  Ptr = (*a2)[10].Ptr;
  v9 = (_QWORD *)(a1 + 112);
  if ( *(_QWORD *)(a1 + 136) > 7u )
    v9 = (_QWORD *)*v9;
  v24 = v9;
  wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v45,
    "ClientLib_SyncOperationCompletion");
  v45[0] = &ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::`vftable';
  ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::StartActivity<unsigned short const *,unsigned __int64,long &>(
    (__int64)v45,
    (__int64 *)&v24,
    (__int64 *)&Ptr,
    &v42);
  CallbackManager::Enter(*(PSRWLOCK *)(a1 + 104));
  if ( v44 )
  {
    if ( !ClientOperation::HasCompletionCallback(*a2) && (!*(_QWORD *)(a1 + 16) || (*(_BYTE *)(a1 + 32) & 1) == 0) )
    {
      v10 = *a2;
      if ( !*a2 || HIDWORD(v10[12].Ptr) != 1 && HIDWORD(v10[12].Ptr) != 10 )
      {
        v11 = *(_QWORD *)HcsClient::OperationTracker::RemoveOperationById(a1, &v25, v10[10].Ptr);
        v12 = v26;
        if ( v26 )
        {
          if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
            if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
          }
        }
        if ( v11 )
        {
          ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::ClientLib_SyncOperationCompletion_Complete((ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion *)v45);
          v13 = *a2;
          v42 = *a4;
          *a4 = 0;
          ClientOperation::Complete(v13);
        }
        else
        {
          ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::ClientLib_SyncOperationCompletion_Drop((ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion *)v45);
        }
        wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v45);
        if ( v44 )
          CallbackReference::~CallbackReference((CallbackReference *)v43);
        v45[0] = &ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::`vftable';
        goto LABEL_43;
      }
    }
    ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::ClientLib_SyncOperationCompletion_Queue((ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion *)v45);
    v27 = 0;
    v28 = a3;
    v29 = 0;
    v30 = *a4;
    *a4 = 0;
    v31 = 0;
    v14 = a2[1];
    if ( v14 )
    {
      *(_QWORD *)&v31 = *a2;
      *((_QWORD *)&v31 + 1) = v14;
      _InterlockedIncrement((volatile signed __int32 *)&v14[1].Ptr + 1);
    }
    v32 = (*a2)[10].Ptr;
    v15 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>;
    v16 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>;
    if ( a5 )
    {
      v36 = *a5;
      `eh vector copy constructor iterator'(
        v37,
        a5 + 2,
        8u,
        3u,
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
      v38 = 1;
      v17 = 1;
      v18 = v36;
      v19 = v37;
      v20 = 1;
      v15 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>;
      v16 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>;
    }
    else
    {
      v41 = 0;
      v17 = 2;
      v18 = v39;
      v19 = v40;
      v20 = 0;
    }
    LODWORD(Ptr) = v17;
    v35 = 0;
    if ( v20 )
    {
      v33 = v18;
      `eh vector copy constructor iterator'(
        v34,
        v19,
        8u,
        3u,
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
      v35 = 1;
    }
    if ( *(_QWORD *)(a1 + 80) == *(_QWORD *)(a1 + 88) )
    {
      std::vector<HcsClient::OperationTracker::WorkItem>::_Emplace_reallocate<HcsClient::OperationTracker::WorkItem>(
        a1 + 72,
        *(_QWORD *)(a1 + 80),
        &v27,
        v16);
    }
    else
    {
      HcsClient::OperationTracker::WorkItem::WorkItem(*(_QWORD *)(a1 + 80), &v27, v15, v16);
      *(_QWORD *)(a1 + 80) += 88LL;
    }
    HcsClient::OperationTracker::WorkItem::~WorkItem((HcsClient::OperationTracker::WorkItem *)&v27);
    if ( (v17 & 2) != 0 )
    {
      v17 &= ~2u;
      LODWORD(Ptr) = v17;
      if ( v41 )
        `eh vector destructor iterator'(
          v40,
          8u,
          3u,
          wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
    }
    if ( (v17 & 1) != 0 && v38 )
      `eh vector destructor iterator'(
        v37,
        8u,
        3u,
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
    v21 = *(_QWORD *)(a1 + 104);
    AcquireSRWLockExclusive((PSRWLOCK)(v21 + 40));
    if ( !*(_DWORD *)(v21 + 56) )
    {
      *(_DWORD *)(v21 + 56) = 1;
      SubmitThreadpoolWork(*(PTP_WORK *)(v21 + 32));
    }
    if ( v21 != -40 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v21 + 40));
  }
  wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v45);
  if ( v44 )
    CallbackReference::~CallbackReference((CallbackReference *)v43);
  v45[0] = &ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::`vftable';
LABEL_43:
  wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v45);
  result = (HLOCAL)wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>(v45);
  if ( *a4 )
    return LocalFree(*a4);
  return result;
}

```

## disassembly

```asm
0x18003d4cc  push    rbp
0x18003d4ce  push    rbx
0x18003d4cf  push    rsi
0x18003d4d0  push    rdi
0x18003d4d1  push    r12
0x18003d4d3  push    r13
0x18003d4d5  push    r14
0x18003d4d7  push    r15
0x18003d4d9  lea     rbp, [rsp-178h]
0x18003d4e1  sub     rsp, 278h
0x18003d4e8  mov     rax, cs:__security_cookie
0x18003d4ef  xor     rax, rsp
0x18003d4f2  mov     [rbp+1B0h+var_50], rax
0x18003d4f9  mov     r15, r9
0x18003d4fc  mov     r13d, r8d
0x18003d4ff  mov     rdi, rdx
0x18003d502  mov     r14, rcx
0x18003d505  mov     r12, [rbp+1B0h+arg_20]
0x18003d50c  mov     dword ptr [rbp+1B0h+var_1B8], r8d
0x18003d510  mov     [rsp+2B0h+var_270], r9
0x18003d515  xor     ebx, ebx
0x18003d517  mov     dword ptr [rsp+2B0h+var_280], ebx
0x18003d51b  xor     edx, edx; Val
0x18003d51d  mov     r8d, 150h; Size
0x18003d523  lea     rcx, [rbp+1B0h+var_1A0]; void *
0x18003d527  call    memset_0
0x18003d52c  mov     rax, [rdi]
0x18003d52f  mov     rcx, [rax+50h]
0x18003d533  mov     [rsp+2B0h+var_280], rcx
0x18003d538  lea     rax, [r14+70h]
0x18003d53c  cmp     qword ptr [rax+18h], 7
0x18003d541  jbe     short loc_18003D546
0x18003d543  mov     rax, [rax]
0x18003d546  mov     [rsp+2B0h+var_278], rax
0x18003d54b  lea     rdx, aClientlibSynco; "ClientLib_SyncOperationCompletion"
0x18003d552  lea     rcx, [rbp+1B0h+var_1A0]
0x18003d556  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$0A@$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003d55b  lea     rsi, ??_7ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@6B@; const ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::`vftable'
0x18003d562  mov     [rbp+1B0h+var_1A0], rsi
0x18003d566  lea     r9, [rbp+1B0h+var_1B8]
0x18003d56a  lea     r8, [rsp+2B0h+var_280]
0x18003d56f  lea     rdx, [rsp+2B0h+var_278]
0x18003d574  lea     rcx, [rbp+1B0h+var_1A0]
0x18003d578  call    ??$StartActivity@PEBG_KAEAJ@ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@QEAAX$$QEAPEBG$$QEA_KAEAJ@Z; ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::StartActivity<ushort const *,unsigned __int64,long &>(ushort const * &&,unsigned __int64 &&,long &)
0x18003d57d  nop
0x18003d57e  lea     rdx, [rbp+1B0h+var_1B0]
0x18003d582  mov     rcx, [r14+68h]; SRWLock
0x18003d586  call    ?Enter@CallbackManager@@QEAA?AV?$optional@VCallbackReference@@@std@@XZ; CallbackManager::Enter(void)
0x18003d58b  nop
0x18003d58c  cmp     [rbp+1B0h+var_1A8], bl
0x18003d58f  jz      loc_18003D856
0x18003d595  mov     rcx, [rdi]; SRWLock
0x18003d598  call    ?HasCompletionCallback@ClientOperation@@QEAA_NXZ; ClientOperation::HasCompletionCallback(void)
0x18003d59d  test    al, al
0x18003d59f  jnz     loc_18003D68C
0x18003d5a5  cmp     [r14+10h], rbx
0x18003d5a9  jz      short loc_18003D5B6
0x18003d5ab  test    byte ptr [r14+20h], 1
0x18003d5b0  jnz     loc_18003D68C
0x18003d5b6  mov     r8, [rdi]
0x18003d5b9  test    r8, r8
0x18003d5bc  jz      short loc_18003D5D4
0x18003d5be  cmp     dword ptr [r8+64h], 1
0x18003d5c3  jz      loc_18003D68C
0x18003d5c9  cmp     dword ptr [r8+64h], 0Ah
0x18003d5ce  jz      loc_18003D68C
0x18003d5d4  mov     r8, [r8+50h]
0x18003d5d8  lea     rdx, [rsp+2B0h+var_270]
0x18003d5dd  mov     rcx, r14
0x18003d5e0  call    ?RemoveOperationById@OperationTracker@HcsClient@@QEAA?AV?$shared_ptr@VClientOperation@@@std@@_K@Z; HcsClient::OperationTracker::RemoveOperationById(unsigned __int64)
0x18003d5e5  mov     rsi, [rax]
0x18003d5e8  mov     rbx, [rsp+2B0h+var_268]
0x18003d5ed  test    rbx, rbx
0x18003d5f0  jz      short loc_18003D62D
0x18003d5f2  or      r14d, 0FFFFFFFFh
0x18003d5f6  mov     eax, r14d
0x18003d5f9  lock xadd [rbx+8], eax
0x18003d5fe  add     eax, r14d
0x18003d601  jnz     short loc_18003D62D
0x18003d603  mov     rax, [rbx]
0x18003d606  mov     rcx, rbx
0x18003d609  mov     rax, [rax]
0x18003d60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d611  mov     eax, r14d
0x18003d614  lock xadd [rbx+0Ch], eax
0x18003d619  add     eax, r14d
0x18003d61c  jnz     short loc_18003D62D
0x18003d61e  mov     rax, [rbx]
0x18003d621  mov     rcx, rbx
0x18003d624  mov     rax, [rax+8]
0x18003d628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d62d  lea     rcx, [rbp+1B0h+var_1A0]; this
0x18003d631  test    rsi, rsi
0x18003d634  jz      short loc_18003D65D
0x18003d636  call    ?ClientLib_SyncOperationCompletion_Complete@ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@QEAAXXZ; ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::ClientLib_SyncOperationCompletion_Complete(void)
0x18003d63b  mov     rcx, [rdi]; SRWLock
0x18003d63e  mov     rax, [r15]
0x18003d641  mov     [rbp+1B0h+var_1B8], rax
0x18003d645  mov     qword ptr [r15], 0
0x18003d64c  mov     r9, r12
0x18003d64f  lea     r8, [rbp+1B0h+var_1B8]
0x18003d653  mov     edx, r13d
0x18003d656  call    ?Complete@ClientOperation@@QEAA_NJV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUProcessInformation@@@Z; ClientOperation::Complete(long,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ProcessInformation *)
0x18003d65b  jmp     short loc_18003D662
0x18003d65d  call    ?ClientLib_SyncOperationCompletion_Drop@ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@QEAAXXZ; ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::ClientLib_SyncOperationCompletion_Drop(void)
0x18003d662  lea     rcx, [rbp+1B0h+var_1A0]
0x18003d666  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$0A@$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003d66b  nop
0x18003d66c  cmp     [rbp+1B0h+var_1A8], 0
0x18003d670  jz      short loc_18003D67C
0x18003d672  lea     rcx, [rbp+1B0h+var_1B0]; this
0x18003d676  call    ??1CallbackReference@@QEAA@XZ; CallbackReference::~CallbackReference(void)
0x18003d67b  nop
0x18003d67c  lea     rax, ??_7ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@6B@; const ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::`vftable'
0x18003d683  mov     [rbp+1B0h+var_1A0], rax
0x18003d687  jmp     loc_18003D873
0x18003d68c  lea     rcx, [rbp+1B0h+var_1A0]; this
0x18003d690  call    ?ClientLib_SyncOperationCompletion_Queue@ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@QEAAXXZ; ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::ClientLib_SyncOperationCompletion_Queue(void)
0x18003d695  mov     [rsp+2B0h+var_260], rbx
0x18003d69a  mov     [rsp+2B0h+var_258], r13d
0x18003d69f  xor     eax, eax
0x18003d6a1  mov     [rsp+2B0h+var_254], eax
0x18003d6a5  mov     rax, [r15]
0x18003d6a8  mov     [rsp+2B0h+var_250], rax
0x18003d6ad  mov     [r15], rbx
0x18003d6b0  xorps   xmm0, xmm0
0x18003d6b3  movdqu  [rsp+2B0h+var_248], xmm0
0x18003d6b9  mov     rcx, [rdi+8]
0x18003d6bd  test    rcx, rcx
0x18003d6c0  jz      short loc_18003D6D3
0x18003d6c2  mov     rax, [rdi]
0x18003d6c5  mov     qword ptr [rsp+2B0h+var_248], rax
0x18003d6ca  mov     qword ptr [rsp+2B0h+var_248+8], rcx
0x18003d6cf  lock inc dword ptr [rcx+0Ch]
0x18003d6d3  mov     rax, [rdi]
0x18003d6d6  mov     rcx, [rax+50h]
0x18003d6da  mov     [rsp+2B0h+var_238], rcx
0x18003d6df  lea     r8, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x18003d6e6  lea     r9, ??0?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18003d6ed  mov     edi, 3
0x18003d6f2  lea     r13d, [rdi+5]
0x18003d6f6  test    r12, r12
0x18003d6f9  jz      short loc_18003D741
0x18003d6fb  mov     eax, [r12]
0x18003d6ff  mov     [rbp+1B0h+var_208], eax
0x18003d702  lea     rdx, [r12+8]; void *
0x18003d707  mov     [rsp+2B0h+var_288], r8; void (*)(void *)
0x18003d70c  mov     [rsp+2B0h+var_290], r9; void (*)(void *, void *)
0x18003d711  mov     r9d, edi; unsigned __int64
0x18003d714  mov     r8d, r13d; unsigned __int64
0x18003d717  lea     rcx, [rbp+1B0h+var_200]; void *
0x18003d71b  call    ??__C@YAXPEAX0_K1P6AX00@ZP6AX0@Z@Z; `eh vector copy constructor iterator'(void *,void *,unsigned __int64,unsigned __int64,void (*)(void *,void *),void (*)(void *))
0x18003d720  nop
0x18003d721  mov     [rbp+1B0h+var_1E8], 1
0x18003d725  lea     ebx, [rdi-2]
0x18003d728  mov     ecx, [rbp+1B0h+var_208]
0x18003d72b  lea     rdx, [rbp+1B0h+var_200]
0x18003d72f  mov     al, bl
0x18003d731  lea     r8, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x18003d738  lea     r9, ??0?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18003d73f  jmp     short loc_18003D752
0x18003d741  mov     [rbp+1B0h+var_1C0], bl
0x18003d744  mov     ebx, 2
0x18003d749  mov     ecx, [rbp+1B0h+var_1E0]
0x18003d74c  lea     rdx, [rbp+1B0h+var_1D8]; void *
0x18003d750  xor     al, al
0x18003d752  mov     dword ptr [rsp+2B0h+var_280], ebx
0x18003d756  mov     [rbp+1B0h+var_210], 0
0x18003d75a  test    al, al
0x18003d75c  jz      short loc_18003D77F
0x18003d75e  mov     [rbp+1B0h+var_230], ecx
0x18003d761  mov     [rsp+2B0h+var_288], r8; void (*)(void *)
0x18003d766  mov     [rsp+2B0h+var_290], r9; void (*)(void *, void *)
0x18003d76b  mov     r9, rdi; unsigned __int64
0x18003d76e  mov     r8, r13; unsigned __int64
0x18003d771  lea     rcx, [rbp+1B0h+var_228]; void *
0x18003d775  call    ??__C@YAXPEAX0_K1P6AX00@ZP6AX0@Z@Z; `eh vector copy constructor iterator'(void *,void *,unsigned __int64,unsigned __int64,void (*)(void *,void *),void (*)(void *))
0x18003d77a  nop
0x18003d77b  mov     [rbp+1B0h+var_210], 1
0x18003d77f  mov     rax, [r14+50h]
0x18003d783  cmp     rax, [r14+58h]
0x18003d787  jz      short loc_18003D79D
0x18003d789  lea     rdx, [rsp+2B0h+var_260]
0x18003d78e  mov     rcx, rax
0x18003d791  call    ??0WorkItem@OperationTracker@HcsClient@@QEAA@$$QEAU012@@Z; HcsClient::OperationTracker::WorkItem::WorkItem(HcsClient::OperationTracker::WorkItem &&)
0x18003d796  add     qword ptr [r14+50h], 58h ; 'X'
0x18003d79b  jmp     short loc_18003D7AF
0x18003d79d  lea     r8, [rsp+2B0h+var_260]
0x18003d7a2  mov     rdx, rax
0x18003d7a5  lea     rcx, [r14+48h]
0x18003d7a9  call    ??$_Emplace_reallocate@UWorkItem@OperationTracker@HcsClient@@@?$vector@UWorkItem@OperationTracker@HcsClient@@V?$allocator@UWorkItem@OperationTracker@HcsClient@@@std@@@std@@AEAAPEAUWorkItem@OperationTracker@HcsClient@@QEAU234@$$QEAU234@@Z; std::vector<HcsClient::OperationTracker::WorkItem>::_Emplace_reallocate<HcsClient::OperationTracker::WorkItem>(HcsClient::OperationTracker::WorkItem * const,HcsClient::OperationTracker::WorkItem &&)
0x18003d7ae  nop
0x18003d7af  lea     rcx, [rsp+2B0h+var_260]; this
0x18003d7b4  call    ??1WorkItem@OperationTracker@HcsClient@@QEAA@XZ; HcsClient::OperationTracker::WorkItem::~WorkItem(void)
0x18003d7b9  nop
0x18003d7ba  test    bl, 2
0x18003d7bd  jz      short loc_18003D7E3
0x18003d7bf  and     ebx, 0FFFFFFFDh
0x18003d7c2  mov     dword ptr [rsp+2B0h+var_280], ebx
0x18003d7c6  cmp     [rbp+1B0h+var_1C0], 0
0x18003d7ca  jz      short loc_18003D7E3
0x18003d7cc  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x18003d7d3  mov     r8, rdi; unsigned __int64
0x18003d7d6  mov     rdx, r13; unsigned __int64
0x18003d7d9  lea     rcx, [rbp+1B0h+var_1D8]; void *
0x18003d7dd  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003d7e2  nop
0x18003d7e3  test    bl, 1
0x18003d7e6  jz      short loc_18003D805
0x18003d7e8  cmp     [rbp+1B0h+var_1E8], 0
0x18003d7ec  jz      short loc_18003D805
0x18003d7ee  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x18003d7f5  mov     r8, rdi; unsigned __int64
0x18003d7f8  mov     rdx, r13; unsigned __int64
0x18003d7fb  lea     rcx, [rbp+1B0h+var_200]; void *
0x18003d7ff  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003d804  nop
0x18003d805  mov     rbx, [r14+68h]
0x18003d809  lea     rdi, [rbx+28h]
0x18003d80d  mov     rcx, rdi; SRWLock
0x18003d810  call    cs:__imp_AcquireSRWLockExclusive
0x18003d817  nop     dword ptr [rax+rax+00h]
0x18003d81c  cmp     dword ptr [rbx+38h], 0
0x18003d820  jnz     short loc_18003D839
0x18003d822  mov     dword ptr [rbx+38h], 1
0x18003d829  mov     rcx, [rbx+20h]; pwk
0x18003d82d  call    cs:__imp_SubmitThreadpoolWork
0x18003d834  nop     dword ptr [rax+rax+00h]
0x18003d839  xor     ebx, ebx
0x18003d83b  test    rdi, rdi
0x18003d83e  jz      short loc_18003D84F
0x18003d840  mov     rcx, rdi; SRWLock
0x18003d843  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d84a  nop     dword ptr [rax+rax+00h]
0x18003d84f  lea     rsi, ??_7ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@6B@; const ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::`vftable'
0x18003d856  lea     rcx, [rbp+1B0h+var_1A0]
0x18003d85a  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$0A@$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003d85f  nop
0x18003d860  cmp     [rbp+1B0h+var_1A8], bl
0x18003d863  jz      short loc_18003D86F
0x18003d865  lea     rcx, [rbp+1B0h+var_1B0]; this
0x18003d869  call    ??1CallbackReference@@QEAA@XZ; CallbackReference::~CallbackReference(void)
0x18003d86e  nop
0x18003d86f  mov     [rbp+1B0h+var_1A0], rsi
0x18003d873  lea     rcx, [rbp+1B0h+var_1A0]
0x18003d877  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$0A@$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18003d87c  lea     rcx, [rbp+1B0h+var_1A0]
0x18003d880  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$0A@$0BAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,65536,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003d885  nop
0x18003d886  mov     rcx, [r15]; hMem
0x18003d889  test    rcx, rcx
0x18003d88c  jz      short loc_18003D89A
0x18003d88e  call    cs:__imp_LocalFree
0x18003d895  nop     dword ptr [rax+rax+00h]
0x18003d89a  mov     rcx, [rbp+1B0h+var_50]
0x18003d8a1  xor     rcx, rsp; StackCookie
0x18003d8a4  call    __security_check_cookie
0x18003d8a9  add     rsp, 278h
0x18003d8b0  pop     r15
0x18003d8b2  pop     r14
0x18003d8b4  pop     r13
0x18003d8b6  pop     r12
0x18003d8b8  pop     rdi
0x18003d8b9  pop     rsi
0x18003d8ba  pop     rbx
0x18003d8bb  pop     rbp
0x18003d8bc  retn
```
