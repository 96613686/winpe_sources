# s_ServiceWorkerSession_FindAllRegistrationsForOrigin

- ea: `0x18001edc0`
- end: `0x18001f01d`
- name: `s_ServiceWorkerSession_FindAllRegistrationsForOrigin`
- size: `605`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `service_task`

## callees

- `0x18000e1c0`
- `0x18000f2b0`
- `0x18001d344`
- `0x18001d424`
- `0x18001d480`
- `0x18001d540`
- `0x18001d65c`
- `0x18001e190`
- `0x18001edc0`
- `0x18001f024`
- `0x18001f104`
- `0x18001f470`
- `0x18001f7d0`
- `0x1800273f0`
- `0x18002d290`
- `0x1800343f0`
- `0x180064cc4`
- `0x180064ec8`
- `0x180075c08`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001ee6d`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001ee9b`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001efb7`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001ee6d`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001ee9b`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001efb7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001efe3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001efe3`

## string_xrefs

- `0x18001ee22`: `SW_ServiceWorkerSession_FindAllRegistrationsForOrigin`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall s_ServiceWorkerSession_FindAllRegistrationsForOrigin(
        __int64 a1,
        void *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int *a5,
        __int64 *a6)
{
  struct HangDetectionWatchDog *v9; // rdx
  unsigned int v10; // r15d
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // rbx
  __int64 v17; // rcx
  void *v18; // rcx
  volatile signed __int64 *v19; // rcx
  unsigned int v21; // [rsp+20h] [rbp-1F8h]
  __int64 v22; // [rsp+30h] [rbp-1E8h] BYREF
  __int64 v23; // [rsp+38h] [rbp-1E0h]
  volatile signed __int64 *v24; // [rsp+40h] [rbp-1D8h] BYREF
  _QWORD v25[4]; // [rsp+48h] [rbp-1D0h] BYREF
  unsigned __int64 v26; // [rsp+68h] [rbp-1B0h]
  _BYTE v27[8]; // [rsp+70h] [rbp-1A8h] BYREF
  std::_Ref_count_base *v28; // [rsp+78h] [rbp-1A0h]
  void **v29; // [rsp+80h] [rbp-198h] BYREF
  _BYTE v30[272]; // [rsp+88h] [rbp-190h] BYREF
  _BYTE v31[8]; // [rsp+198h] [rbp-80h] BYREF
  _BYTE v32[56]; // [rsp+1A0h] [rbp-78h] BYREF

  SetThreadName((WCHAR *)L"RPC SWSess_FindAllRegForOrigin");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v24, v9);
  *a6 = 0;
  *a5 = 0;
  v10 = 0;
  wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(
    &v29,
    "SW_ServiceWorkerSession_FindAllRegistrationsForOrigin");
  v29 = &ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsForOrigin::`vftable';
  ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsForOrigin::StartActivity(
    (ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsForOrigin *)&v29,
    a2,
    a3,
    (const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 *)a4);
  v12 = *(unsigned int *)(a4 + 4);
  v13 = *(_QWORD *)(a4 + 8);
  if ( !v13 && v12 )
  {
    _o_terminate(v11);
    __debugbreak();
  }
  v22 = v12;
  v23 = v13;
  ServiceWorkerStorageSession::CreateQuotaSessionForOrigin(a2, v27, &v22);
  if ( !v13 && v12 )
  {
    _o_terminate(v14);
    __debugbreak();
  }
  v22 = v12;
  v23 = v13;
  ServiceWorkerStorageSession::FindAllRegistrationsForOrigin(a2, v25, a3, &v22);
  *a6 = AllocateRPCRegistrationList(v25);
  v15 = wil::safe_cast_failfast<unsigned int,unsigned __int64,0>(v26);
  *a5 = v15;
  v16 = *a6;
  gsl::details::extent_type<-1>::extent_type<-1>(&v22, v15);
  if ( v22 == -1 || !v16 && v22 )
  {
    _o_terminate(v17);
    v10 = v21;
  }
  else
  {
    v23 = v16;
    ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsForOrigin::Stop(&v29, &v22);
    while ( v26 )
      std::deque<std::unique_ptr<StoredServiceWorkerRegistration>>::pop_back(v25);
    if ( v25[1] )
      std::deque<EventChannel::Event>::_Reset_map(v25);
    v18 = (void *)v25[0];
    v25[0] = 0;
    std::_Deallocate<16>(v18, 0x10u);
    if ( v28 )
      std::_Ref_count_base::_Decref(v28);
    v29 = &ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsForOrigin::`vftable';
    wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v29);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v32);
    wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v31);
    wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>(v30);
  }
  v19 = v24;
  if ( _InterlockedExchangeAdd64(v24, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v19 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return v10;
}

```

## disassembly

```asm
0x18001edc0  push    rbx
0x18001edc2  push    rsi
0x18001edc3  push    rdi
0x18001edc4  push    r12
0x18001edc6  push    r13
0x18001edc8  push    r14
0x18001edca  push    r15
0x18001edcc  sub     rsp, 1E0h
0x18001edd3  mov     rax, cs:__security_cookie
0x18001edda  xor     rax, rsp
0x18001eddd  mov     [rsp+218h+var_40], rax
0x18001ede5  mov     rdi, r9
0x18001ede8  mov     r12d, r8d
0x18001edeb  mov     rsi, rdx
0x18001edee  mov     r13, [rsp+218h+arg_20]
0x18001edf6  mov     r14, [rsp+218h+arg_28]
0x18001edfe  xor     ebx, ebx
0x18001ee00  lea     rcx, aRpcSwsessFinda; "RPC SWSess_FindAllRegForOrigin"
0x18001ee07  call    SetThreadName
0x18001ee0c  nop
0x18001ee0d  lea     rcx, [rsp+218h+var_1D8]; this
0x18001ee12  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x18001ee17  nop
0x18001ee18  mov     [r14], rbx
0x18001ee1b  mov     [r13+0], ebx
0x18001ee1f  mov     r15d, ebx
0x18001ee22  lea     rdx, aSwServiceworke_19; "SW_ServiceWorkerSession_FindAllRegistra"...
0x18001ee29  lea     rcx, [rsp+218h+var_198]
0x18001ee31  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001ee36  lea     rax, ??_7SW_ServiceWorkerSession_FindAllRegistrationsForOrigin@ServiceWorkerTraceLogging@@6B@; const ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsForOrigin::`vftable'
0x18001ee3d  mov     [rsp+218h+var_198], rax
0x18001ee45  mov     r9, rdi; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 *
0x18001ee48  mov     r8d, r12d; unsigned int
0x18001ee4b  mov     rdx, rsi; void *
0x18001ee4e  lea     rcx, [rsp+218h+var_198]; this
0x18001ee56  call    ?StartActivity@SW_ServiceWorkerSession_FindAllRegistrationsForOrigin@ServiceWorkerTraceLogging@@QEAAXPEAXIAEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002@@@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsForOrigin::StartActivity(void *,uint,__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 const &)
0x18001ee5b  nop
0x18001ee5c  mov     ebx, [rdi+4]
0x18001ee5f  mov     rdi, [rdi+8]
0x18001ee63  test    rdi, rdi
0x18001ee66  jnz     short loc_18001EE74
0x18001ee68  test    rbx, rbx
0x18001ee6b  jz      short loc_18001EE74
0x18001ee6d  call    cs:__imp__o_terminate
0x18001ee73  int     3; Trap to Debugger
0x18001ee74  mov     [rsp+218h+var_1E8], rbx
0x18001ee79  mov     [rsp+218h+var_1E0], rdi
0x18001ee7e  lea     r8, [rsp+218h+var_1E8]
0x18001ee83  lea     rdx, [rsp+218h+var_1A8]
0x18001ee88  mov     rcx, rsi
0x18001ee8b  call    ?CreateQuotaSessionForOrigin@ServiceWorkerStorageSession@@QEAA?AV?$shared_ptr@UIQuotaSession@@@std@@V?$span@$$CBE$0?0@gsl@@@Z; ServiceWorkerStorageSession::CreateQuotaSessionForOrigin(gsl::span<uchar const,-1>)
0x18001ee90  nop
0x18001ee91  test    rdi, rdi
0x18001ee94  jnz     short loc_18001EEA2
0x18001ee96  test    rbx, rbx
0x18001ee99  jz      short loc_18001EEA2
0x18001ee9b  call    cs:__imp__o_terminate
0x18001eea1  int     3; Trap to Debugger
0x18001eea2  mov     [rsp+218h+var_1E8], rbx
0x18001eea7  mov     [rsp+218h+var_1E0], rdi
0x18001eeac  lea     r9, [rsp+218h+var_1E8]
0x18001eeb1  mov     r8d, r12d
0x18001eeb4  lea     rdx, [rsp+218h+var_1D0]
0x18001eeb9  mov     rcx, rsi
0x18001eebc  call    ?FindAllRegistrationsForOrigin@ServiceWorkerStorageSession@@QEAA?AV?$deque@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@V?$allocator@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@@2@@std@@W4_IsoIntegrity@@V?$span@$$CBE$0?0@gsl@@@Z; ServiceWorkerStorageSession::FindAllRegistrationsForOrigin(_IsoIntegrity,gsl::span<uchar const,-1>)
0x18001eec1  nop
0x18001eec2  lea     rcx, [rsp+218h+var_1D0]
0x18001eec7  call    AllocateRPCRegistrationList
0x18001eecc  mov     [r14], rax
0x18001eecf  mov     rcx, [rsp+218h+var_1B0]
0x18001eed4  call    ??$safe_cast_failfast@I_K$0A@@wil@@YAI_K@Z; wil::safe_cast_failfast<uint,unsigned __int64,0>(unsigned __int64)
0x18001eed9  mov     [r13+0], eax
0x18001eedd  mov     rbx, [r14]
0x18001eee0  mov     edx, eax
0x18001eee2  lea     rcx, [rsp+218h+var_1E8]
0x18001eee7  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x18001eeec  mov     rax, [rsp+218h+var_1E8]
0x18001eef1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001eef5  jz      loc_18001EFB7
0x18001eefb  xor     edi, edi
0x18001eefd  test    rbx, rbx
0x18001ef00  jnz     short loc_18001EF0B
0x18001ef02  test    rax, rax
0x18001ef05  jnz     loc_18001EFB7
0x18001ef0b  mov     [rsp+218h+var_1E8], rax
0x18001ef10  mov     [rsp+218h+var_1E0], rbx
0x18001ef15  lea     rdx, [rsp+218h+var_1E8]
0x18001ef1a  lea     rcx, [rsp+218h+var_198]
0x18001ef22  call    ?Stop@SW_ServiceWorkerSession_FindAllRegistrationsForOrigin@ServiceWorkerTraceLogging@@QEAAXV?$span@QEAURPCServiceWorkerRegistration@@$0?0@gsl@@@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsForOrigin::Stop(gsl::span<RPCServiceWorkerRegistration * const,-1>)
0x18001ef27  nop
0x18001ef28  cmp     [rsp+218h+var_1B0], rdi
0x18001ef2d  jz      short loc_18001EF3B
0x18001ef2f  lea     rcx, [rsp+218h+var_1D0]
0x18001ef34  call    ?pop_back@?$deque@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@V?$allocator@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@@2@@std@@QEAAXXZ; std::deque<std::unique_ptr<StoredServiceWorkerRegistration>>::pop_back(void)
0x18001ef39  jmp     short loc_18001EF28
0x18001ef3b  cmp     [rsp+218h+var_1C8], rdi
0x18001ef40  jz      short loc_18001EF4C
0x18001ef42  lea     rcx, [rsp+218h+var_1D0]
0x18001ef47  call    ?_Reset_map@?$deque@UEvent@EventChannel@@V?$allocator@UEvent@EventChannel@@@std@@@std@@AEAAXXZ; std::deque<EventChannel::Event>::_Reset_map(void)
0x18001ef4c  mov     rcx, [rsp+218h+var_1D0]
0x18001ef51  mov     [rsp+218h+var_1D0], rdi
0x18001ef56  mov     edx, 10h
0x18001ef5b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ef60  nop
0x18001ef61  mov     rcx, [rsp+218h+var_1A0]; this
0x18001ef66  test    rcx, rcx
0x18001ef69  jz      short loc_18001EF71
0x18001ef6b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ef70  nop
0x18001ef71  lea     rax, ??_7SW_ServiceWorkerSession_FindAllRegistrationsForOrigin@ServiceWorkerTraceLogging@@6B@; const ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsForOrigin::`vftable'
0x18001ef78  mov     [rsp+218h+var_198], rax
0x18001ef80  lea     rcx, [rsp+218h+var_198]
0x18001ef88  call    ?Destroy@?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001ef8d  lea     rcx, [rsp+218h+var_78]; this
0x18001ef95  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18001ef9a  lea     rcx, [rsp+218h+var_80]
0x18001efa2  call    ?reset@?$shared_object@V?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001efa7  lea     rcx, [rsp+218h+var_190]
0x18001efaf  call    ??1?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001efb4  nop
0x18001efb5  jmp     short loc_18001EFC3
0x18001efb7  call    cs:__imp__o_terminate
0x18001efbd  nop
0x18001efbe  mov     r15d, [rsp+218h+var_1F8]
0x18001efc3  mov     rcx, [rsp+218h+var_1D8]
0x18001efc8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001efcc  lock xadd [rcx], rax
0x18001efd1  cmp     rax, 1
0x18001efd5  jnz     short loc_18001EFEA
0x18001efd7  xor     r9d, r9d; msWindowLength
0x18001efda  xor     r8d, r8d; msPeriod
0x18001efdd  xor     edx, edx; pftDueTime
0x18001efdf  mov     rcx, [rcx+8]; pti
0x18001efe3  call    cs:__imp_SetThreadpoolTimer
0x18001efe9  nop
0x18001efea  lea     rcx, word_1800D6108; lpWideCharStr
0x18001eff1  call    SetThreadName
0x18001eff6  nop
0x18001eff7  mov     eax, r15d
0x18001effa  mov     rcx, [rsp+218h+var_40]
0x18001f002  xor     rcx, rsp; StackCookie
0x18001f005  call    __security_check_cookie
0x18001f00a  add     rsp, 1E0h
0x18001f011  pop     r15
0x18001f013  pop     r14
0x18001f015  pop     r13
0x18001f017  pop     r12
0x18001f019  pop     rdi
0x18001f01a  pop     rsi
0x18001f01b  pop     rbx
0x18001f01c  retn
```
