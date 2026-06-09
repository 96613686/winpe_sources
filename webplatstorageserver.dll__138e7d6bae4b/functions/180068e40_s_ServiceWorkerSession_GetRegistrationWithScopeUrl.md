# s_ServiceWorkerSession_GetRegistrationWithScopeUrl

- ea: `0x180068e40`
- end: `0x1800690c9`
- name: `s_ServiceWorkerSession_GetRegistrationWithScopeUrl`
- size: `649`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006e9c`
- `0x18000e1c0`
- `0x18001d480`
- `0x18001f024`
- `0x18001f470`
- `0x18001f680`
- `0x1800273f0`
- `0x18002d290`
- `0x18003cd20`
- `0x180068dec`
- `0x180068e40`
- `0x1800690d0`
- `0x180069178`
- `0x1800691a0`
- `0x1800692b4`
- `0x1800694e8`
- `0x180069514`
- `0x1800697a4`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800690c1`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800690c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180069088`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180069088`

## string_xrefs

- `0x180068eb3`: `SW_ServiceWorkerSession_GetRegistrationWithScopeUrl`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall s_ServiceWorkerSession_GetRegistrationWithScopeUrl(
        __int64 a1,
        void *a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int16 *a5,
        const struct RPCServiceWorkerRegistration **a6,
        void **a7)
{
  struct HangDetectionWatchDog *v10; // rdx
  unsigned int v11; // esi
  __int64 v12; // r15
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 *RegistrationWithScopeUrl; // rax
  const char *v16; // r9
  volatile signed __int64 *v17; // rcx
  wil *v19; // rcx
  __int64 v21; // [rsp+38h] [rbp-200h] BYREF
  __int128 v22; // [rsp+40h] [rbp-1F8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-1E8h] BYREF
  volatile signed __int64 *v24; // [rsp+58h] [rbp-1E0h] BYREF
  __int128 v25; // [rsp+60h] [rbp-1D8h] BYREF
  _BYTE v26[8]; // [rsp+70h] [rbp-1C8h] BYREF
  std::_Ref_count_base *v27; // [rsp+78h] [rbp-1C0h]
  _BYTE v28[16]; // [rsp+80h] [rbp-1B8h] BYREF
  _BYTE v29[16]; // [rsp+90h] [rbp-1A8h] BYREF
  _QWORD v30[43]; // [rsp+A0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  SetThreadName((WCHAR *)L"RPC SWSess_GetRegWithScopeUrl");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v24, v10);
  *a6 = 0;
  *a7 = 0;
  v11 = 0;
  wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v30,
    "SW_ServiceWorkerSession_GetRegistrationWithScopeUrl");
  try
  {
    v30[0] = &ServiceWorkerTraceLogging::SW_ServiceWorkerSession_GetRegistrationWithScopeUrl::`vftable';
    ServiceWorkerTraceLogging::SW_ServiceWorkerSession_GetRegistrationWithScopeUrl::StartActivity(
      (ServiceWorkerTraceLogging::SW_ServiceWorkerSession_GetRegistrationWithScopeUrl *)v30,
      a2,
      a3,
      (const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 *)a4,
      a5);
    v12 = *(_QWORD *)(a4 + 8);
    gsl::details::extent_type<-1>::extent_type<-1>(&v22, *(unsigned int *)(a4 + 4));
    *((_QWORD *)&v22 + 1) = v12;
    if ( (_QWORD)v22 == -1 || !v12 && (_QWORD)v22 )
    {
      _o_terminate(v13);
      __debugbreak();
      JUMPOUT(0x1800690C9LL);
    }
    v25 = *(_OWORD *)gsl::span<unsigned char const,-1>::span<unsigned char const,-1>(v28, &v22);
    ServiceWorkerStorageSession::CreateQuotaSessionForOrigin(a2, v26, &v25);
    v21 = 0;
    v23 = 0;
    v14 = -1;
    do
      ++v14;
    while ( a5[v14] );
    gsl::span<unsigned short const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(
      &v25,
      a5,
      v14);
    v22 = *(_OWORD *)gsl::span<unsigned char const,-1>::span<unsigned char const,-1>(v29, &v22);
    RegistrationWithScopeUrl = (__int64 *)ServiceWorkerStorageSession::GetRegistrationWithScopeUrl(
                                            (_DWORD)a2,
                                            (unsigned int)v28,
                                            (unsigned int)v26,
                                            a3,
                                            (__int64)&v22,
                                            (__int64)&v25);
    *(_QWORD *)&v22 = &v23;
    *((_QWORD *)&v22 + 1) = &v21;
    std::tuple<std::unique_ptr<StoredServiceWorkerRegistration> &,std::unique_ptr<ServiceWorkerRegistrationSession> &>::operator=<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>,0>(
      (__int64 **)&v22,
      RegistrationWithScopeUrl);
    std::tuple<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>>::~tuple<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>>(v28);
    if ( v21 )
      InitializeServiceWorkerRegistrationSession(&v21, &v23, a6, a7);
    ServiceWorkerTraceLogging::SW_ServiceWorkerSession_GetRegistrationWithScopeUrl::Stop(
      (ServiceWorkerTraceLogging::SW_ServiceWorkerSession_GetRegistrationWithScopeUrl *)v30,
      *a6,
      *a7);
    std::unique_ptr<ServiceWorkerRegistrationSession>::~unique_ptr<ServiceWorkerRegistrationSession>(&v23);
    std::unique_ptr<StoredServiceWorkerRegistration>::~unique_ptr<StoredServiceWorkerRegistration>(&v21);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    ServiceWorkerTraceLogging::SW_ServiceWorkerSession_GetRegistrationWithScopeUrl::~SW_ServiceWorkerSession_GetRegistrationWithScopeUrl((ServiceWorkerTraceLogging::SW_ServiceWorkerSession_GetRegistrationWithScopeUrl *)v30);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\serviceworkerstorage\\serviceworkerrpcapi.cxx",
      v16);
    v11 = wil::ResultFromCaughtException(v19);
  }
  v17 = v24;
  if ( _InterlockedExchangeAdd64(v24, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v17 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return v11;
}

```

## disassembly

```asm
0x180068e40  push    rbx
0x180068e42  push    rsi
0x180068e43  push    rdi
0x180068e44  push    r12
0x180068e46  push    r13
0x180068e48  push    r14
0x180068e4a  push    r15
0x180068e4c  sub     rsp, 200h
0x180068e53  mov     rax, cs:__security_cookie
0x180068e5a  xor     rax, rsp
0x180068e5d  mov     [rsp+238h+var_40], rax
0x180068e65  mov     r14, r9
0x180068e68  mov     r15d, r8d
0x180068e6b  mov     [rsp+238h+var_208], r8d
0x180068e70  mov     r13, rdx
0x180068e73  mov     r12, [rsp+238h+arg_20]
0x180068e7b  mov     rbx, [rsp+238h+arg_28]
0x180068e83  mov     rdi, [rsp+238h+arg_30]
0x180068e8b  lea     rcx, aRpcSwsessGetre_0; "RPC SWSess_GetRegWithScopeUrl"
0x180068e92  call    SetThreadName
0x180068e97  nop
0x180068e98  lea     rcx, [rsp+238h+var_1E0]; this
0x180068e9d  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x180068ea2  nop
0x180068ea3  mov     qword ptr [rbx], 0
0x180068eaa  mov     qword ptr [rdi], 0
0x180068eb1  xor     esi, esi
0x180068eb3  lea     rdx, aSwServiceworke_7; "SW_ServiceWorkerSession_GetRegistration"...
0x180068eba  lea     rcx, [rsp+238h+var_198]
0x180068ec2  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180068ec7  lea     rax, ??_7SW_ServiceWorkerSession_GetRegistrationWithScopeUrl@ServiceWorkerTraceLogging@@6B@; const ServiceWorkerTraceLogging::SW_ServiceWorkerSession_GetRegistrationWithScopeUrl::`vftable'
0x180068ece  mov     [rsp+238h+var_198], rax
0x180068ed6  mov     [rsp+238h+var_218], r12; unsigned __int16 *
0x180068edb  mov     r9, r14; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 *
0x180068ede  mov     r8d, r15d; unsigned int
0x180068ee1  mov     rdx, r13; void *
0x180068ee4  lea     rcx, [rsp+238h+var_198]; this
0x180068eec  call    ?StartActivity@SW_ServiceWorkerSession_GetRegistrationWithScopeUrl@ServiceWorkerTraceLogging@@QEAAXPEAXIAEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002@@PEBG@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_GetRegistrationWithScopeUrl::StartActivity(void *,uint,__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 const &,ushort const *)
0x180068ef1  nop
0x180068ef2  mov     r15, [r14+8]
0x180068ef6  mov     edx, [r14+4]
0x180068efa  lea     rcx, [rsp+238h+var_1F8]
0x180068eff  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x180068f04  mov     qword ptr [rsp+238h+var_1F8+8], r15
0x180068f09  mov     rax, qword ptr [rsp+238h+var_1F8]
0x180068f0e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180068f12  jz      loc_1800690C1
0x180068f18  xor     r14d, r14d
0x180068f1b  test    r15, r15
0x180068f1e  jnz     short loc_180068F29
0x180068f20  test    rax, rax
0x180068f23  jnz     loc_1800690C1
0x180068f29  lea     rdx, [rsp+238h+var_1F8]
0x180068f2e  lea     rcx, [rsp+238h+var_1B8]
0x180068f36  call    ??$?0E$0?0$0?0$0A@@?$span@$$CBE$0?0@gsl@@QEAA@AEBV?$span@E$0?0@1@@Z; gsl::span<uchar const,-1>::span<uchar const,-1>(gsl::span<uchar,-1> const &)
0x180068f3b  movups  xmm0, xmmword ptr [rax]
0x180068f3e  movdqu  [rsp+238h+var_1D8], xmm0
0x180068f44  lea     r8, [rsp+238h+var_1D8]
0x180068f49  lea     rdx, [rsp+238h+var_1C8]
0x180068f4e  mov     rcx, r13
0x180068f51  call    ?CreateQuotaSessionForOrigin@ServiceWorkerStorageSession@@QEAA?AV?$shared_ptr@UIQuotaSession@@@std@@V?$span@$$CBE$0?0@gsl@@@Z; ServiceWorkerStorageSession::CreateQuotaSessionForOrigin(gsl::span<uchar const,-1>)
0x180068f56  nop
0x180068f57  mov     [rsp+238h+var_200], r14
0x180068f5c  mov     [rsp+238h+var_1E8], r14
0x180068f61  or      r8, 0FFFFFFFFFFFFFFFFh
0x180068f65  inc     r8
0x180068f68  cmp     [r12+r8*2], r14w
0x180068f6d  jnz     short loc_180068F65
0x180068f6f  mov     rdx, r12
0x180068f72  lea     rcx, [rsp+238h+var_1D8]
0x180068f77  call    ??$?0_K@?$storage_type@V?$extent_type@$0?0@details@gsl@@@?$span@$$CBG$0?0@gsl@@QEAA@PEBG_K@Z; gsl::span<ushort const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(ushort const *,unsigned __int64)
0x180068f7c  movaps  xmm0, [rsp+238h+var_1D8]
0x180068f81  movdqa  [rsp+238h+var_1D8], xmm0
0x180068f87  lea     rdx, [rsp+238h+var_1F8]
0x180068f8c  lea     rcx, [rsp+238h+var_1A8]
0x180068f94  call    ??$?0E$0?0$0?0$0A@@?$span@$$CBE$0?0@gsl@@QEAA@AEBV?$span@E$0?0@1@@Z; gsl::span<uchar const,-1>::span<uchar const,-1>(gsl::span<uchar,-1> const &)
0x180068f99  movups  xmm0, xmmword ptr [rax]
0x180068f9c  movdqu  [rsp+238h+var_1F8], xmm0
0x180068fa2  lea     rax, [rsp+238h+var_1D8]
0x180068fa7  mov     [rsp+238h+var_210], rax
0x180068fac  lea     rax, [rsp+238h+var_1F8]
0x180068fb1  mov     [rsp+238h+var_218], rax
0x180068fb6  mov     r9d, [rsp+238h+var_208]
0x180068fbb  lea     r8, [rsp+238h+var_1C8]
0x180068fc0  lea     rdx, [rsp+238h+var_1B8]
0x180068fc8  mov     rcx, r13
0x180068fcb  call    ?GetRegistrationWithScopeUrl@ServiceWorkerStorageSession@@QEAA?AV?$tuple@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@V?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@2@@std@@AEBV?$shared_ptr@UIQuotaSession@@@3@W4_IsoIntegrity@@V?$span@$$CBE$0?0@gsl@@V?$basic_string_span@$$CBG$0?0@7@@Z; ServiceWorkerStorageSession::GetRegistrationWithScopeUrl(std::shared_ptr<IQuotaSession> const &,_IsoIntegrity,gsl::span<uchar const,-1>,gsl::basic_string_span<ushort const,-1>)
0x180068fd0  lea     rcx, [rsp+238h+var_1E8]
0x180068fd5  mov     qword ptr [rsp+238h+var_1F8], rcx
0x180068fda  lea     rcx, [rsp+238h+var_200]
0x180068fdf  mov     qword ptr [rsp+238h+var_1F8+8], rcx
0x180068fe4  mov     rdx, rax
0x180068fe7  lea     rcx, [rsp+238h+var_1F8]
0x180068fec  call    ??$?4V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@V?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@1@$0A@@?$tuple@AEAV?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@AEAV?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@2@@std@@QEAAAEAV01@$$QEAV?$tuple@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@V?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@2@@1@@Z; std::tuple<std::unique_ptr<StoredServiceWorkerRegistration> &,std::unique_ptr<ServiceWorkerRegistrationSession> &>::operator=<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>,0>(std::tuple<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>> &&)
0x180068ff1  lea     rcx, [rsp+238h+var_1B8]
0x180068ff9  call    ??1?$tuple@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@V?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@2@@std@@QEAA@XZ; std::tuple<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>>::~tuple<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>>(void)
0x180068ffe  cmp     [rsp+238h+var_200], r14
0x180069003  jz      short loc_18006901A
0x180069005  mov     r9, rdi
0x180069008  mov     r8, rbx
0x18006900b  lea     rdx, [rsp+238h+var_1E8]
0x180069010  lea     rcx, [rsp+238h+var_200]
0x180069015  call    InitializeServiceWorkerRegistrationSession
0x18006901a  mov     r8, [rdi]; void *
0x18006901d  mov     rdx, [rbx]; struct RPCServiceWorkerRegistration *
0x180069020  lea     rcx, [rsp+238h+var_198]; this
0x180069028  call    ?Stop@SW_ServiceWorkerSession_GetRegistrationWithScopeUrl@ServiceWorkerTraceLogging@@QEAAXPEBURPCServiceWorkerRegistration@@PEAX@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_GetRegistrationWithScopeUrl::Stop(RPCServiceWorkerRegistration const *,void *)
0x18006902d  nop
0x18006902e  lea     rcx, [rsp+238h+var_1E8]
0x180069033  call    ??1?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@std@@QEAA@XZ; std::unique_ptr<ServiceWorkerRegistrationSession>::~unique_ptr<ServiceWorkerRegistrationSession>(void)
0x180069038  nop
0x180069039  lea     rcx, [rsp+238h+var_200]
0x18006903e  call    ??1?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@QEAA@XZ; std::unique_ptr<StoredServiceWorkerRegistration>::~unique_ptr<StoredServiceWorkerRegistration>(void)
0x180069043  nop
0x180069044  mov     rcx, [rsp+238h+var_1C0]; this
0x180069049  test    rcx, rcx
0x18006904c  jz      short loc_180069054
0x18006904e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180069053  nop
0x180069054  lea     rcx, [rsp+238h+var_198]; this
0x18006905c  call    ??1SW_ServiceWorkerSession_GetRegistrationWithScopeUrl@ServiceWorkerTraceLogging@@QEAA@XZ; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_GetRegistrationWithScopeUrl::~SW_ServiceWorkerSession_GetRegistrationWithScopeUrl(void)
0x180069061  nop
0x180069062  jmp     short loc_180069068
0x180069064  mov     esi, [rsp+238h+var_208]
0x180069068  mov     rcx, [rsp+238h+var_1E0]
0x18006906d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180069071  lock xadd [rcx], rax
0x180069076  cmp     rax, 1
0x18006907a  jnz     short loc_18006908F
0x18006907c  xor     r9d, r9d; msWindowLength
0x18006907f  xor     r8d, r8d; msPeriod
0x180069082  xor     edx, edx; pftDueTime
0x180069084  mov     rcx, [rcx+8]; pti
0x180069088  call    cs:__imp_SetThreadpoolTimer
0x18006908e  nop
0x18006908f  lea     rcx, word_1800D6108; lpWideCharStr
0x180069096  call    SetThreadName
0x18006909b  nop
0x18006909c  mov     eax, esi
0x18006909e  mov     rcx, [rsp+238h+var_40]
0x1800690a6  xor     rcx, rsp; StackCookie
0x1800690a9  call    __security_check_cookie
0x1800690ae  add     rsp, 200h
0x1800690b5  pop     r15
0x1800690b7  pop     r14
0x1800690b9  pop     r13
0x1800690bb  pop     r12
0x1800690bd  pop     rdi
0x1800690be  pop     rsi
0x1800690bf  pop     rbx
0x1800690c0  retn
0x1800690c1  call    cs:__imp__o_terminate
0x1800690c7  nop
0x1800690c8  int     3; Trap to Debugger
```
