# s_ServiceWorkerSession_FindActiveMatchingRegistration

- ea: `0x18001f8c0`
- end: `0x18001fc25`
- name: `s_ServiceWorkerSession_FindActiveMatchingRegistration`
- size: `869`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, service_task`

## callees

- `0x18000e1c0`
- `0x18001d344`
- `0x18001d424`
- `0x18001d480`
- `0x18001d540`
- `0x18001d65c`
- `0x18001f024`
- `0x18001f650`
- `0x18001f680`
- `0x18001f8c0`
- `0x1800206fc`
- `0x1800273f0`
- `0x18002d290`
- `0x18003af70`
- `0x18005c46c`
- `0x18005eb24`
- `0x180068dec`
- `0x18006910c`
- `0x180069144`
- `0x1800697a4`
- `0x180069d8c`
- `0x180080fb0`
- `0x1800810a4`
- `0x180095760`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001f98f`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001fbbf`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001f98f`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001fbbf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fbeb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fbeb`

## string_xrefs

- `0x18001f93d`: `SW_ServiceWorkerSession_FindActiveMatchingRegistration`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall s_ServiceWorkerSession_FindActiveMatchingRegistration(
        __int64 a1,
        void *a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int16 *a5,
        const struct RPCServiceWorkerRegistration **a6,
        const struct RPCNavigationPreloadState **a7,
        void **a8)
{
  struct HangDetectionWatchDog *v10; // rdx
  unsigned int v11; // r14d
  __int64 v12; // rcx
  void **v13; // rdi
  __int64 *v14; // rbx
  __int64 v15; // rax
  __int64 *ActiveMatchingRegistration; // rbx
  void *v17; // rax
  void *v18; // rdx
  void **v19; // rdi
  _QWORD *v20; // rbx
  const struct RPCNavigationPreloadState *v21; // rax
  void *v22; // rbx
  RpcHelper::AllocationTracker *v23; // rbx
  volatile signed __int64 *v24; // rcx
  void *Block; // [rsp+38h] [rbp-220h] BYREF
  RpcHelper::AllocationTracker *v28; // [rsp+40h] [rbp-218h] BYREF
  __int64 v29; // [rsp+48h] [rbp-210h] BYREF
  void **v30; // [rsp+50h] [rbp-208h]
  volatile signed __int64 *v31; // [rsp+58h] [rbp-200h] BYREF
  __int64 *v32; // [rsp+60h] [rbp-1F8h] BYREF
  unsigned __int16 *v33; // [rsp+68h] [rbp-1F0h]
  __int64 *v34; // [rsp+70h] [rbp-1E8h] BYREF
  void **p_Block; // [rsp+78h] [rbp-1E0h]
  RpcHelper::AllocationTracker **v36; // [rsp+80h] [rbp-1D8h]
  char v37[8]; // [rsp+90h] [rbp-1C8h] BYREF
  std::_Ref_count_base *v38; // [rsp+98h] [rbp-1C0h]
  char v39[8]; // [rsp+A0h] [rbp-1B8h] BYREF
  char v40[8]; // [rsp+A8h] [rbp-1B0h] BYREF
  char v41[16]; // [rsp+B0h] [rbp-1A8h] BYREF
  void **v42; // [rsp+C0h] [rbp-198h] BYREF
  char v43[272]; // [rsp+C8h] [rbp-190h] BYREF
  char v44[8]; // [rsp+1D8h] [rbp-80h] BYREF
  char v45[56]; // [rsp+1E0h] [rbp-78h] BYREF

  v30 = a8;
  SetThreadName((WCHAR *)L"RPC SWSess_FindAtvMatchingReg");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v31, v10);
  *a6 = 0;
  *a8 = 0;
  *a7 = 0;
  v11 = 0;
  wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(
    &v42,
    "SW_ServiceWorkerSession_FindActiveMatchingRegistration");
  v42 = &ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindActiveMatchingRegistration::`vftable';
  ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindActiveMatchingRegistration::StartActivity(
    (ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindActiveMatchingRegistration *)&v42,
    a2,
    a3,
    (const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 *)a4,
    a5);
  v13 = *(void ***)(a4 + 8);
  v14 = (__int64 *)*(unsigned int *)(a4 + 4);
  if ( !v13 && v14 )
  {
    _o_terminate(v12);
    __debugbreak();
  }
  v32 = v14;
  v33 = (unsigned __int16 *)v13;
  ServiceWorkerStorageSession::CreateQuotaSessionForOrigin(a2, v37, &v32);
  v28 = 0;
  Block = 0;
  v29 = 0;
  v15 = -1;
  do
    ++v15;
  while ( a5[v15] );
  if ( v15 == -1 || !a5 && v15 || !v13 && v14 )
  {
    _o_terminate(0);
    v11 = a3;
  }
  else
  {
    v32 = (__int64 *)v15;
    v33 = a5;
    v34 = v14;
    p_Block = v13;
    ActiveMatchingRegistration = (__int64 *)ServiceWorkerStorageSession::FindActiveMatchingRegistration(
                                              (_DWORD)a2,
                                              (unsigned int)v39,
                                              (unsigned int)v37,
                                              a3,
                                              (__int64)&v34,
                                              (__int64)&v32);
    v34 = &v29;
    p_Block = &Block;
    v36 = &v28;
    std::unique_ptr<StoredServiceWorkerRegistration>::operator=<std::default_delete<StoredServiceWorkerRegistration>,0>(
      (__int64 *)&v28,
      ActiveMatchingRegistration + 2);
    v17 = (void *)ActiveMatchingRegistration[1];
    ActiveMatchingRegistration[1] = 0;
    v18 = Block;
    Block = v17;
    if ( v18 )
      std::default_delete<StoredNavigationPreloadState>::operator()();
    std::tuple<std::unique_ptr<ServiceWorkerRegistrationSession> &>::operator=<std::unique_ptr<ServiceWorkerRegistrationSession>,0>(
      &v34,
      ActiveMatchingRegistration);
    std::unique_ptr<StoredServiceWorkerRegistration>::~unique_ptr<StoredServiceWorkerRegistration>(v41);
    std::unique_ptr<StoredServiceWorkerRegistration>::~unique_ptr<StoredServiceWorkerRegistration>(v40);
    std::unique_ptr<ServiceWorkerRegistrationSession>::~unique_ptr<ServiceWorkerRegistrationSession>(v39);
    v19 = v30;
    if ( v28 )
    {
      InitializeServiceWorkerRegistrationSession(&v28, &v29, a6, v30);
      v20 = Block;
      std::deque<void *>::_Tidy(Block);
      v21 = (const struct RPCNavigationPreloadState *)v20[5];
      v20[5] = 0;
      *a7 = v21;
    }
    ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindActiveMatchingRegistration::Stop(
      (ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindActiveMatchingRegistration *)&v42,
      *a6,
      *a7,
      *v19);
    if ( v29 )
      std::default_delete<ServiceWorkerRegistrationSession>::operator()();
    v22 = Block;
    if ( Block )
    {
      RpcHelper::AllocationTracker::~AllocationTracker((RpcHelper::AllocationTracker *)Block);
      operator delete(v22);
    }
    v23 = v28;
    if ( v28 )
    {
      RpcHelper::AllocationTracker::~AllocationTracker(v28);
      operator delete(v23);
    }
    if ( v38 )
      std::_Ref_count_base::_Decref(v38);
    v42 = &ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindActiveMatchingRegistration::`vftable';
    wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v42);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v45);
    wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v44);
    wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>(v43);
  }
  v24 = v31;
  if ( _InterlockedExchangeAdd64(v31, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v24 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return v11;
}

```

## disassembly

```asm
0x18001f8c0  push    rbx
0x18001f8c2  push    rsi
0x18001f8c3  push    rdi
0x18001f8c4  push    r12
0x18001f8c6  push    r13
0x18001f8c8  push    r14
0x18001f8ca  push    r15
0x18001f8cc  sub     rsp, 220h
0x18001f8d3  mov     rax, cs:__security_cookie
0x18001f8da  xor     rax, rsp
0x18001f8dd  mov     [rsp+258h+var_40], rax
0x18001f8e5  mov     rbx, r9
0x18001f8e8  mov     [rsp+258h+var_228], r8d
0x18001f8ed  mov     r15, rdx
0x18001f8f0  mov     rsi, [rsp+258h+arg_20]
0x18001f8f8  mov     r12, [rsp+258h+arg_28]
0x18001f900  mov     r13, [rsp+258h+arg_30]
0x18001f908  mov     rdi, [rsp+258h+arg_38]
0x18001f910  mov     [rsp+258h+var_208], rdi
0x18001f915  lea     rcx, aRpcSwsessFinda_0; "RPC SWSess_FindAtvMatchingReg"
0x18001f91c  call    SetThreadName
0x18001f921  nop
0x18001f922  lea     rcx, [rsp+258h+var_200]; this
0x18001f927  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x18001f92c  nop
0x18001f92d  xor     eax, eax
0x18001f92f  mov     [r12], rax
0x18001f933  mov     [rdi], rax
0x18001f936  mov     [r13+0], rax
0x18001f93a  mov     r14d, eax
0x18001f93d  lea     rdx, aSwServiceworke_26; "SW_ServiceWorkerSession_FindActiveMatch"...
0x18001f944  lea     rcx, [rsp+258h+var_198]
0x18001f94c  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001f951  lea     rax, ??_7SW_ServiceWorkerSession_FindActiveMatchingRegistration@ServiceWorkerTraceLogging@@6B@; const ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindActiveMatchingRegistration::`vftable'
0x18001f958  mov     [rsp+258h+var_198], rax
0x18001f960  mov     [rsp+258h+var_238], rsi; unsigned __int16 *
0x18001f965  mov     r9, rbx; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 *
0x18001f968  mov     r8d, [rsp+258h+var_228]; unsigned int
0x18001f96d  mov     rdx, r15; void *
0x18001f970  lea     rcx, [rsp+258h+var_198]; this
0x18001f978  call    ?StartActivity@SW_ServiceWorkerSession_FindActiveMatchingRegistration@ServiceWorkerTraceLogging@@QEAAXPEAXIAEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002@@PEBG@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindActiveMatchingRegistration::StartActivity(void *,uint,__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 const &,ushort const *)
0x18001f97d  nop
0x18001f97e  mov     rdi, [rbx+8]
0x18001f982  mov     ebx, [rbx+4]
0x18001f985  test    rdi, rdi
0x18001f988  jnz     short loc_18001F996
0x18001f98a  test    rbx, rbx
0x18001f98d  jz      short loc_18001F996
0x18001f98f  call    cs:__imp__o_terminate
0x18001f995  int     3; Trap to Debugger
0x18001f996  mov     [rsp+258h+var_1F8], rbx
0x18001f99b  mov     [rsp+258h+var_1F0], rdi
0x18001f9a0  lea     r8, [rsp+258h+var_1F8]
0x18001f9a5  lea     rdx, [rsp+258h+var_1C8]
0x18001f9ad  mov     rcx, r15
0x18001f9b0  call    ?CreateQuotaSessionForOrigin@ServiceWorkerStorageSession@@QEAA?AV?$shared_ptr@UIQuotaSession@@@std@@V?$span@$$CBE$0?0@gsl@@@Z; ServiceWorkerStorageSession::CreateQuotaSessionForOrigin(gsl::span<uchar const,-1>)
0x18001f9b5  nop
0x18001f9b6  xor     ecx, ecx
0x18001f9b8  mov     [rsp+258h+var_218], rcx
0x18001f9bd  mov     [rsp+258h+Block], rcx
0x18001f9c2  mov     [rsp+258h+var_210], rcx
0x18001f9c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f9cb  inc     rax
0x18001f9ce  cmp     [rsi+rax*2], cx
0x18001f9d2  jnz     short loc_18001F9CB
0x18001f9d4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f9d8  jz      loc_18001FBBF
0x18001f9de  test    rsi, rsi
0x18001f9e1  jnz     short loc_18001F9EC
0x18001f9e3  test    rax, rax
0x18001f9e6  jnz     loc_18001FBBF
0x18001f9ec  test    rdi, rdi
0x18001f9ef  jnz     short loc_18001F9FA
0x18001f9f1  test    rbx, rbx
0x18001f9f4  jnz     loc_18001FBBF
0x18001f9fa  mov     [rsp+258h+var_1F8], rax
0x18001f9ff  mov     [rsp+258h+var_1F0], rsi
0x18001fa04  mov     [rsp+258h+var_1E8], rbx
0x18001fa09  mov     [rsp+258h+var_1E0], rdi
0x18001fa0e  lea     rax, [rsp+258h+var_1F8]
0x18001fa13  mov     [rsp+258h+var_230], rax
0x18001fa18  lea     rax, [rsp+258h+var_1E8]
0x18001fa1d  mov     [rsp+258h+var_238], rax
0x18001fa22  mov     r9d, [rsp+258h+var_228]
0x18001fa27  lea     r8, [rsp+258h+var_1C8]
0x18001fa2f  lea     rdx, [rsp+258h+var_1B8]
0x18001fa37  mov     rcx, r15
0x18001fa3a  call    ?FindActiveMatchingRegistration@ServiceWorkerStorageSession@@QEAA?AV?$tuple@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@V?$unique_ptr@VStoredNavigationPreloadState@@U?$default_delete@VStoredNavigationPreloadState@@@std@@@2@V?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@2@@std@@AEBV?$shared_ptr@UIQuotaSession@@@3@W4_IsoIntegrity@@V?$span@$$CBE$0?0@gsl@@V?$basic_string_span@$$CBG$0?0@7@@Z; ServiceWorkerStorageSession::FindActiveMatchingRegistration(std::shared_ptr<IQuotaSession> const &,_IsoIntegrity,gsl::span<uchar const,-1>,gsl::basic_string_span<ushort const,-1>)
0x18001fa3f  mov     rbx, rax
0x18001fa42  lea     rax, [rsp+258h+var_210]
0x18001fa47  mov     [rsp+258h+var_1E8], rax
0x18001fa4c  lea     rax, [rsp+258h+Block]
0x18001fa51  mov     [rsp+258h+var_1E0], rax
0x18001fa56  lea     rax, [rsp+258h+var_218]
0x18001fa5b  mov     [rsp+258h+var_1D8], rax
0x18001fa63  lea     rdx, [rbx+10h]
0x18001fa67  lea     rcx, [rsp+258h+var_218]
0x18001fa6c  call    ??$?4U?$default_delete@VStoredServiceWorkerRegistration@@@std@@$0A@@?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<StoredServiceWorkerRegistration>::operator=<std::default_delete<StoredServiceWorkerRegistration>,0>(std::unique_ptr<StoredServiceWorkerRegistration> &&)
0x18001fa71  mov     rax, [rbx+8]
0x18001fa75  xor     esi, esi
0x18001fa77  mov     [rbx+8], rsi
0x18001fa7b  mov     rdx, [rsp+258h+Block]
0x18001fa80  mov     [rsp+258h+Block], rax
0x18001fa85  test    rdx, rdx
0x18001fa88  jz      short loc_18001FA8F
0x18001fa8a  call    ??R?$default_delete@VStoredNavigationPreloadState@@@std@@QEBAXPEAVStoredNavigationPreloadState@@@Z; std::default_delete<StoredNavigationPreloadState>::operator()(StoredNavigationPreloadState *)
0x18001fa8f  mov     rdx, rbx
0x18001fa92  lea     rcx, [rsp+258h+var_1E8]
0x18001fa97  call    ??$?4V?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@std@@$0A@@?$tuple@AEAV?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@std@@@std@@QEAAAEAV01@$$QEAV?$tuple@V?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@std@@@1@@Z; std::tuple<std::unique_ptr<ServiceWorkerRegistrationSession> &>::operator=<std::unique_ptr<ServiceWorkerRegistrationSession>,0>(std::tuple<std::unique_ptr<ServiceWorkerRegistrationSession>> &&)
0x18001fa9c  lea     rcx, [rsp+258h+var_1A8]
0x18001faa4  call    ??1?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@QEAA@XZ; std::unique_ptr<StoredServiceWorkerRegistration>::~unique_ptr<StoredServiceWorkerRegistration>(void)
0x18001faa9  lea     rcx, [rsp+258h+var_1B0]
0x18001fab1  call    ??1?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@QEAA@XZ; std::unique_ptr<StoredServiceWorkerRegistration>::~unique_ptr<StoredServiceWorkerRegistration>(void)
0x18001fab6  lea     rcx, [rsp+258h+var_1B8]
0x18001fabe  call    ??1?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@std@@QEAA@XZ; std::unique_ptr<ServiceWorkerRegistrationSession>::~unique_ptr<ServiceWorkerRegistrationSession>(void)
0x18001fac3  mov     rdi, [rsp+258h+var_208]
0x18001fac8  cmp     [rsp+258h+var_218], rsi
0x18001facd  jz      short loc_18001FAFD
0x18001facf  mov     r9, rdi
0x18001fad2  mov     r8, r12
0x18001fad5  lea     rdx, [rsp+258h+var_210]
0x18001fada  lea     rcx, [rsp+258h+var_218]
0x18001fadf  call    InitializeServiceWorkerRegistrationSession
0x18001fae4  mov     rbx, [rsp+258h+Block]
0x18001fae9  mov     rcx, rbx
0x18001faec  call    ?_Tidy@?$deque@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::deque<void *>::_Tidy(void)
0x18001faf1  mov     rax, [rbx+28h]
0x18001faf5  mov     [rbx+28h], rsi
0x18001faf9  mov     [r13+0], rax
0x18001fafd  mov     r9, [rdi]; void *
0x18001fb00  mov     r8, [r13+0]; struct RPCNavigationPreloadState *
0x18001fb04  mov     rdx, [r12]; struct RPCServiceWorkerRegistration *
0x18001fb08  lea     rcx, [rsp+258h+var_198]; this
0x18001fb10  call    ?Stop@SW_ServiceWorkerSession_FindActiveMatchingRegistration@ServiceWorkerTraceLogging@@QEAAXPEBURPCServiceWorkerRegistration@@PEBURPCNavigationPreloadState@@PEAX@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindActiveMatchingRegistration::Stop(RPCServiceWorkerRegistration const *,RPCNavigationPreloadState const *,void *)
0x18001fb15  nop
0x18001fb16  mov     rdx, [rsp+258h+var_210]
0x18001fb1b  test    rdx, rdx
0x18001fb1e  jz      short loc_18001FB26
0x18001fb20  call    ??R?$default_delete@VServiceWorkerRegistrationSession@@@std@@QEBAXPEAVServiceWorkerRegistrationSession@@@Z; std::default_delete<ServiceWorkerRegistrationSession>::operator()(ServiceWorkerRegistrationSession *)
0x18001fb25  nop
0x18001fb26  mov     rbx, [rsp+258h+Block]
0x18001fb2b  test    rbx, rbx
0x18001fb2e  jz      short loc_18001FB46
0x18001fb30  mov     rcx, rbx; this
0x18001fb33  call    ??1AllocationTracker@RpcHelper@@QEAA@XZ; RpcHelper::AllocationTracker::~AllocationTracker(void)
0x18001fb38  mov     edx, 30h ; '0'
0x18001fb3d  mov     rcx, rbx; Block
0x18001fb40  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fb45  nop
0x18001fb46  mov     rbx, [rsp+258h+var_218]
0x18001fb4b  test    rbx, rbx
0x18001fb4e  jz      short loc_18001FB66
0x18001fb50  mov     rcx, rbx; this
0x18001fb53  call    ??1AllocationTracker@RpcHelper@@QEAA@XZ; RpcHelper::AllocationTracker::~AllocationTracker(void)
0x18001fb58  mov     edx, 30h ; '0'
0x18001fb5d  mov     rcx, rbx; Block
0x18001fb60  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fb65  nop
0x18001fb66  mov     rcx, [rsp+258h+var_1C0]; this
0x18001fb6e  test    rcx, rcx
0x18001fb71  jz      short loc_18001FB79
0x18001fb73  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001fb78  nop
0x18001fb79  lea     rax, ??_7SW_ServiceWorkerSession_FindActiveMatchingRegistration@ServiceWorkerTraceLogging@@6B@; const ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindActiveMatchingRegistration::`vftable'
0x18001fb80  mov     [rsp+258h+var_198], rax
0x18001fb88  lea     rcx, [rsp+258h+var_198]
0x18001fb90  call    ?Destroy@?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001fb95  lea     rcx, [rsp+258h+var_78]; this
0x18001fb9d  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18001fba2  lea     rcx, [rsp+258h+var_80]
0x18001fbaa  call    ?reset@?$shared_object@V?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001fbaf  lea     rcx, [rsp+258h+var_190]
0x18001fbb7  call    ??1?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001fbbc  nop
0x18001fbbd  jmp     short loc_18001FBCB
0x18001fbbf  call    cs:__imp__o_terminate
0x18001fbc5  nop
0x18001fbc6  mov     r14d, [rsp+258h+var_228]
0x18001fbcb  mov     rcx, [rsp+258h+var_200]
0x18001fbd0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fbd4  lock xadd [rcx], rax
0x18001fbd9  cmp     rax, 1
0x18001fbdd  jnz     short loc_18001FBF2
0x18001fbdf  xor     r9d, r9d; msWindowLength
0x18001fbe2  xor     r8d, r8d; msPeriod
0x18001fbe5  xor     edx, edx; pftDueTime
0x18001fbe7  mov     rcx, [rcx+8]; pti
0x18001fbeb  call    cs:__imp_SetThreadpoolTimer
0x18001fbf1  nop
0x18001fbf2  lea     rcx, word_1800D6108; lpWideCharStr
0x18001fbf9  call    SetThreadName
0x18001fbfe  nop
0x18001fbff  mov     eax, r14d
0x18001fc02  mov     rcx, [rsp+258h+var_40]
0x18001fc0a  xor     rcx, rsp; StackCookie
0x18001fc0d  call    __security_check_cookie
0x18001fc12  add     rsp, 220h
0x18001fc19  pop     r15
0x18001fc1b  pop     r14
0x18001fc1d  pop     r13
0x18001fc1f  pop     r12
0x18001fc21  pop     rdi
0x18001fc22  pop     rsi
0x18001fc23  pop     rbx
0x18001fc24  retn
```
