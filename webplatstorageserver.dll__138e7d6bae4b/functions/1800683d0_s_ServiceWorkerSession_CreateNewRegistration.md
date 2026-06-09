# s_ServiceWorkerSession_CreateNewRegistration

- ea: `0x1800683d0`
- end: `0x1800686aa`
- name: `s_ServiceWorkerSession_CreateNewRegistration`
- size: `730`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, __int64, unsigned __int16 *, unsigned __int8, const struct RPCServiceWorkerRegistration **, void **)`
- caller_count: `0`
- callee_count: `20`
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
- `0x1800683d0`
- `0x1800686b0`
- `0x1800687e8`
- `0x180068934`
- `0x180068dec`
- `0x1800690d0`
- `0x180069178`
- `0x1800697a4`
- `0x18006980c`
- `0x1800766b8`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800686a2`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800686a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180068669`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180068669`

## string_xrefs

- `0x18006850d`: `onecoreuap\inetcore\lib\common\serviceworkerutilities.cpp`
- `0x18006844f`: `SW_ServiceWorkerSession_CreateNewRegistration`
- `0x18006842c`: `RPC SWSess_CreateNewReg`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall s_ServiceWorkerSession_CreateNewRegistration(
        __int64 a1,
        void *a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int8 a6,
        const struct RPCServiceWorkerRegistration **a7,
        void **a8)
{
  struct HangDetectionWatchDog *v11; // rdx
  unsigned int v12; // ebx
  __int64 v13; // rsi
  __int64 v14; // rcx
  const char *v15; // r9
  __int64 v16; // r8
  __int64 NewRegistration; // rax
  void **v18; // rdi
  const char *v19; // r9
  volatile signed __int64 *v20; // rcx
  wil *v22; // rcx
  __int128 v24; // [rsp+50h] [rbp-218h] BYREF
  __int64 v25; // [rsp+60h] [rbp-208h] BYREF
  __int64 v26; // [rsp+68h] [rbp-200h] BYREF
  volatile signed __int64 *v27; // [rsp+70h] [rbp-1F8h] BYREF
  __int128 v28; // [rsp+80h] [rbp-1E8h] BYREF
  void **v29; // [rsp+90h] [rbp-1D8h]
  char v30[8]; // [rsp+98h] [rbp-1D0h] BYREF
  std::_Ref_count_base *v31; // [rsp+A0h] [rbp-1C8h]
  _BYTE v32[16]; // [rsp+A8h] [rbp-1C0h] BYREF
  char v33[24]; // [rsp+B8h] [rbp-1B0h] BYREF
  _QWORD v34[43]; // [rsp+D0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v29 = a8;
  SetThreadName(L"RPC SWSess_CreateNewReg");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v27, v11);
  *a7 = 0;
  *a8 = 0;
  v12 = 0;
  wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v34,
    "SW_ServiceWorkerSession_CreateNewRegistration");
  try
  {
    v34[0] = &ServiceWorkerTraceLogging::SW_ServiceWorkerSession_CreateNewRegistration::`vftable';
    ServiceWorkerTraceLogging::SW_ServiceWorkerSession_CreateNewRegistration::StartActivity(
      (ServiceWorkerTraceLogging::SW_ServiceWorkerSession_CreateNewRegistration *)v34,
      a2,
      a3,
      (const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 *)a4,
      a5,
      a6);
    v13 = *(_QWORD *)(a4 + 8);
    gsl::details::extent_type<-1>::extent_type<-1>(&v24, *(unsigned int *)(a4 + 4));
    *((_QWORD *)&v24 + 1) = v13;
    if ( (_QWORD)v24 == -1 || !v13 && (_QWORD)v24 )
    {
      _o_terminate(v14);
      __debugbreak();
      JUMPOUT(0x1800686AALL);
    }
    v28 = *(_OWORD *)gsl::span<unsigned char const,-1>::span<unsigned char const,-1>(v32, &v24);
    ServiceWorkerStorageSession::CreateQuotaSessionForOrigin(a2, v30, &v28);
    if ( a6 >= 3u )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecoreuap\\inetcore\\lib\\common\\serviceworkerutilities.cpp",
        v15);
    v26 = 0;
    v25 = 0;
    v16 = -1;
    do
      ++v16;
    while ( a5[v16] );
    gsl::span<unsigned short const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(
      &v28,
      a5,
      v16);
    v24 = *(_OWORD *)gsl::span<unsigned char const,-1>::span<unsigned char const,-1>(v33, &v24);
    NewRegistration = ServiceWorkerStorageSession::CreateNewRegistration(
                        (_DWORD)a2,
                        (unsigned int)v32,
                        (unsigned int)v30,
                        a3,
                        (__int64)&v24,
                        (__int64)&v28,
                        a6);
    *(_QWORD *)&v24 = &v25;
    *((_QWORD *)&v24 + 1) = &v26;
    std::tuple<std::unique_ptr<StoredServiceWorkerRegistration> &,std::unique_ptr<ServiceWorkerRegistrationSession> &>::operator=<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>,0>(
      &v24,
      NewRegistration);
    std::tuple<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>>::~tuple<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>>(v32);
    v18 = v29;
    InitializeServiceWorkerRegistrationSession(&v26, &v25, a7, v29);
    ServiceWorkerTraceLogging::SW_ServiceWorkerSession_CreateNewRegistration::Stop(
      (ServiceWorkerTraceLogging::SW_ServiceWorkerSession_CreateNewRegistration *)v34,
      *a7,
      *v18);
    std::unique_ptr<ServiceWorkerRegistrationSession>::~unique_ptr<ServiceWorkerRegistrationSession>(&v25);
    std::unique_ptr<StoredServiceWorkerRegistration>::~unique_ptr<StoredServiceWorkerRegistration>(&v26);
    if ( v31 )
      std::_Ref_count_base::_Decref(v31);
    ServiceWorkerTraceLogging::SW_ServiceWorkerSession_CreateNewRegistration::~SW_ServiceWorkerSession_CreateNewRegistration((ServiceWorkerTraceLogging::SW_ServiceWorkerSession_CreateNewRegistration *)v34);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\serviceworkerstorage\\serviceworkerrpcapi.cxx",
      v19);
    v12 = wil::ResultFromCaughtException(v22);
  }
  v20 = v27;
  if ( _InterlockedExchangeAdd64(v27, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v20 + 1), 0, 0, 0);
  SetThreadName(&word_1800D6108);
  return v12;
}

```

## disassembly

```asm
0x1800683d0  push    rbx
0x1800683d2  push    rsi
0x1800683d3  push    rdi
0x1800683d4  push    r12
0x1800683d6  push    r13
0x1800683d8  push    r14
0x1800683da  push    r15
0x1800683dc  sub     rsp, 230h
0x1800683e3  mov     rax, cs:__security_cookie
0x1800683ea  xor     rax, rsp
0x1800683ed  mov     [rsp+268h+var_40], rax
0x1800683f5  mov     rdi, r9
0x1800683f8  mov     esi, r8d
0x1800683fb  mov     [rsp+268h+var_228], r8d
0x180068400  mov     r12, rdx
0x180068403  movzx   r14d, [rsp+268h+arg_28]
0x18006840c  mov     r15, [rsp+268h+arg_20]
0x180068414  mov     r13, [rsp+268h+arg_30]
0x18006841c  mov     rbx, [rsp+268h+arg_38]
0x180068424  mov     [rsp+268h+var_1D8], rbx
0x18006842c  lea     rcx, aRpcSwsessCreat; "RPC SWSess_CreateNewReg"
0x180068433  call    SetThreadName
0x180068438  nop
0x180068439  lea     rcx, [rsp+268h+var_1F8]; this
0x18006843e  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x180068443  nop
0x180068444  xor     eax, eax
0x180068446  mov     [r13+0], rax
0x18006844a  mov     [rbx], rax
0x18006844d  mov     ebx, eax
0x18006844f  lea     rdx, aSwServiceworke_3; "SW_ServiceWorkerSession_CreateNewRegist"...
0x180068456  lea     rcx, [rsp+268h+var_198]
0x18006845e  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180068463  lea     rax, ??_7SW_ServiceWorkerSession_CreateNewRegistration@ServiceWorkerTraceLogging@@6B@; const ServiceWorkerTraceLogging::SW_ServiceWorkerSession_CreateNewRegistration::`vftable'
0x18006846a  mov     [rsp+268h+var_198], rax
0x180068472  mov     [rsp+268h+var_240], r14b; char
0x180068477  mov     [rsp+268h+var_248], r15; unsigned __int16 *
0x18006847c  mov     r9, rdi; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 *
0x18006847f  mov     r8d, esi; unsigned int
0x180068482  mov     rdx, r12; void *
0x180068485  lea     rcx, [rsp+268h+var_198]; this
0x18006848d  call    ?StartActivity@SW_ServiceWorkerSession_CreateNewRegistration@ServiceWorkerTraceLogging@@QEAAXPEAXIAEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002@@PEBGE@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_CreateNewRegistration::StartActivity(void *,uint,__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 const &,ushort const *,uchar)
0x180068492  nop
0x180068493  mov     rsi, [rdi+8]
0x180068497  mov     edx, [rdi+4]
0x18006849a  lea     rcx, [rsp+268h+var_218]
0x18006849f  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x1800684a4  mov     qword ptr [rsp+268h+var_218+8], rsi
0x1800684a9  mov     rax, qword ptr [rsp+268h+var_218]
0x1800684ae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800684b2  jz      loc_1800686A2
0x1800684b8  xor     edi, edi
0x1800684ba  test    rsi, rsi
0x1800684bd  jnz     short loc_1800684C8
0x1800684bf  test    rax, rax
0x1800684c2  jnz     loc_1800686A2
0x1800684c8  lea     rdx, [rsp+268h+var_218]
0x1800684cd  lea     rcx, [rsp+268h+var_1C0]
0x1800684d5  call    ??$?0E$0?0$0?0$0A@@?$span@$$CBE$0?0@gsl@@QEAA@AEBV?$span@E$0?0@1@@Z; gsl::span<uchar const,-1>::span<uchar const,-1>(gsl::span<uchar,-1> const &)
0x1800684da  movups  xmm0, xmmword ptr [rax]
0x1800684dd  movdqu  [rsp+268h+var_1E8], xmm0
0x1800684e6  lea     r8, [rsp+268h+var_1E8]
0x1800684ee  lea     rdx, [rsp+268h+var_1D0]
0x1800684f6  mov     rcx, r12
0x1800684f9  call    ?CreateQuotaSessionForOrigin@ServiceWorkerStorageSession@@QEAA?AV?$shared_ptr@UIQuotaSession@@@std@@V?$span@$$CBE$0?0@gsl@@@Z; ServiceWorkerStorageSession::CreateQuotaSessionForOrigin(gsl::span<uchar const,-1>)
0x1800684fe  nop
0x1800684ff  mov     rcx, [rsp+268h]; this
0x180068507  cmp     r14b, 3
0x18006850b  jb      short loc_18006851F
0x18006850d  lea     r8, aOnecoreuapInet_32; "onecoreuap\\inetcore\\lib\\common\\serv"...
0x180068514  mov     edx, 5Dh ; ']'; void *
0x180068519  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18006851f  mov     [rsp+268h+var_200], rdi
0x180068524  mov     [rsp+268h+var_208], rdi
0x180068529  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006852d  inc     r8
0x180068530  cmp     [r15+r8*2], di
0x180068535  jnz     short loc_18006852D
0x180068537  mov     rdx, r15
0x18006853a  lea     rcx, [rsp+268h+var_1E8]
0x180068542  call    ??$?0_K@?$storage_type@V?$extent_type@$0?0@details@gsl@@@?$span@$$CBG$0?0@gsl@@QEAA@PEBG_K@Z; gsl::span<ushort const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(ushort const *,unsigned __int64)
0x180068547  movaps  xmm0, [rsp+268h+var_1E8]
0x18006854f  movdqa  [rsp+268h+var_1E8], xmm0
0x180068558  lea     rdx, [rsp+268h+var_218]
0x18006855d  lea     rcx, [rsp+268h+var_1B0]
0x180068565  call    ??$?0E$0?0$0?0$0A@@?$span@$$CBE$0?0@gsl@@QEAA@AEBV?$span@E$0?0@1@@Z; gsl::span<uchar const,-1>::span<uchar const,-1>(gsl::span<uchar,-1> const &)
0x18006856a  movups  xmm0, xmmword ptr [rax]
0x18006856d  movdqu  [rsp+268h+var_218], xmm0
0x180068573  mov     [rsp+268h+var_238], r14d
0x180068578  lea     rax, [rsp+268h+var_1E8]
0x180068580  mov     qword ptr [rsp+268h+var_240], rax
0x180068585  lea     rax, [rsp+268h+var_218]
0x18006858a  mov     [rsp+268h+var_248], rax
0x18006858f  mov     r9d, [rsp+268h+var_228]
0x180068594  lea     r8, [rsp+268h+var_1D0]
0x18006859c  lea     rdx, [rsp+268h+var_1C0]
0x1800685a4  mov     rcx, r12
0x1800685a7  call    ?CreateNewRegistration@ServiceWorkerStorageSession@@QEAA?AV?$tuple@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@V?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@2@@std@@AEBV?$shared_ptr@UIQuotaSession@@@3@W4_IsoIntegrity@@V?$span@$$CBE$0?0@gsl@@V?$basic_string_span@$$CBG$0?0@7@W4ServiceWorkerUpdateViaCache@@@Z; ServiceWorkerStorageSession::CreateNewRegistration(std::shared_ptr<IQuotaSession> const &,_IsoIntegrity,gsl::span<uchar const,-1>,gsl::basic_string_span<ushort const,-1>,ServiceWorkerUpdateViaCache)
0x1800685ac  lea     rcx, [rsp+268h+var_208]
0x1800685b1  mov     qword ptr [rsp+268h+var_218], rcx
0x1800685b6  lea     rcx, [rsp+268h+var_200]
0x1800685bb  mov     qword ptr [rsp+268h+var_218+8], rcx
0x1800685c0  mov     rdx, rax
0x1800685c3  lea     rcx, [rsp+268h+var_218]
0x1800685c8  call    ??$?4V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@V?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@1@$0A@@?$tuple@AEAV?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@AEAV?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@2@@std@@QEAAAEAV01@$$QEAV?$tuple@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@V?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@2@@1@@Z; std::tuple<std::unique_ptr<StoredServiceWorkerRegistration> &,std::unique_ptr<ServiceWorkerRegistrationSession> &>::operator=<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>,0>(std::tuple<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>> &&)
0x1800685cd  lea     rcx, [rsp+268h+var_1C0]
0x1800685d5  call    ??1?$tuple@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@V?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@2@@std@@QEAA@XZ; std::tuple<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>>::~tuple<std::unique_ptr<StoredServiceWorkerRegistration>,std::unique_ptr<ServiceWorkerRegistrationSession>>(void)
0x1800685da  mov     rdi, [rsp+268h+var_1D8]
0x1800685e2  mov     r9, rdi
0x1800685e5  mov     r8, r13
0x1800685e8  lea     rdx, [rsp+268h+var_208]
0x1800685ed  lea     rcx, [rsp+268h+var_200]
0x1800685f2  call    InitializeServiceWorkerRegistrationSession
0x1800685f7  mov     r8, [rdi]; void *
0x1800685fa  mov     rdx, [r13+0]; struct RPCServiceWorkerRegistration *
0x1800685fe  lea     rcx, [rsp+268h+var_198]; this
0x180068606  call    ?Stop@SW_ServiceWorkerSession_CreateNewRegistration@ServiceWorkerTraceLogging@@QEAAXPEBURPCServiceWorkerRegistration@@PEAX@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_CreateNewRegistration::Stop(RPCServiceWorkerRegistration const *,void *)
0x18006860b  nop
0x18006860c  lea     rcx, [rsp+268h+var_208]
0x180068611  call    ??1?$unique_ptr@VServiceWorkerRegistrationSession@@U?$default_delete@VServiceWorkerRegistrationSession@@@std@@@std@@QEAA@XZ; std::unique_ptr<ServiceWorkerRegistrationSession>::~unique_ptr<ServiceWorkerRegistrationSession>(void)
0x180068616  nop
0x180068617  lea     rcx, [rsp+268h+var_200]
0x18006861c  call    ??1?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@QEAA@XZ; std::unique_ptr<StoredServiceWorkerRegistration>::~unique_ptr<StoredServiceWorkerRegistration>(void)
0x180068621  nop
0x180068622  mov     rcx, [rsp+268h+var_1C8]; this
0x18006862a  test    rcx, rcx
0x18006862d  jz      short loc_180068635
0x18006862f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180068634  nop
0x180068635  lea     rcx, [rsp+268h+var_198]; this
0x18006863d  call    ??1SW_ServiceWorkerSession_CreateNewRegistration@ServiceWorkerTraceLogging@@QEAA@XZ; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_CreateNewRegistration::~SW_ServiceWorkerSession_CreateNewRegistration(void)
0x180068642  nop
0x180068643  jmp     short loc_180068649
0x180068645  mov     ebx, [rsp+268h+var_228]
0x180068649  mov     rcx, [rsp+268h+var_1F8]
0x18006864e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180068652  lock xadd [rcx], rax
0x180068657  cmp     rax, 1
0x18006865b  jnz     short loc_180068670
0x18006865d  xor     r9d, r9d; msWindowLength
0x180068660  xor     r8d, r8d; msPeriod
0x180068663  xor     edx, edx; pftDueTime
0x180068665  mov     rcx, [rcx+8]; pti
0x180068669  call    cs:__imp_SetThreadpoolTimer
0x18006866f  nop
0x180068670  lea     rcx, word_1800D6108; lpWideCharStr
0x180068677  call    SetThreadName
0x18006867c  nop
0x18006867d  mov     eax, ebx
0x18006867f  mov     rcx, [rsp+268h+var_40]
0x180068687  xor     rcx, rsp; StackCookie
0x18006868a  call    __security_check_cookie
0x18006868f  add     rsp, 230h
0x180068696  pop     r15
0x180068698  pop     r14
0x18006869a  pop     r13
0x18006869c  pop     r12
0x18006869e  pop     rdi
0x18006869f  pop     rsi
0x1800686a0  pop     rbx
0x1800686a1  retn
0x1800686a2  call    cs:__imp__o_terminate
0x1800686a8  nop
0x1800686a9  int     3; Trap to Debugger
```
