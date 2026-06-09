# s_ServiceWorkerSession_Open

- ea: `0x180035550`
- end: `0x18003585f`
- name: `s_ServiceWorkerSession_Open`
- size: `783`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `service_task`

## callees

- `0x18000e1c0`
- `0x180014b48`
- `0x18001d344`
- `0x18001d424`
- `0x18001d480`
- `0x18001d540`
- `0x18001d65c`
- `0x1800206fc`
- `0x180024260`
- `0x1800273f0`
- `0x18002d290`
- `0x18002ee6c`
- `0x18002f3cc`
- `0x18002f620`
- `0x18003505c`
- `0x180035550`
- `0x180035868`
- `0x180035b18`
- `0x18005c28c`
- `0x180064ec8`
- `0x180069d8c`
- `0x180080fb0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800357f9`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800357f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035825`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035825`

## string_xrefs

- `0x180035587`: `RPC SWSess_Open`
- `0x1800355aa`: `SW_ServiceWorkerSession_Open`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall s_ServiceWorkerSession_Open(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        void **a4,
        const unsigned __int16 **a5)
{
  struct HangDetectionWatchDog *v8; // rdx
  unsigned int v9; // r15d
  __int64 v10; // rcx
  _QWORD *Instance; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rdi
  __int64 v15; // rcx
  std::_Ref_count_base *v16; // rbx
  _QWORD *v17; // rax
  std::_Ref_count_base *v18; // rax
  __int64 v19; // rcx
  void *v20; // rdx
  volatile signed __int64 *v21; // rcx
  __int64 (__fastcall ***v23)(_QWORD, __int64 *); // [rsp+30h] [rbp-228h] BYREF
  volatile signed __int64 *v24; // [rsp+38h] [rbp-220h] BYREF
  __int64 v25; // [rsp+40h] [rbp-218h] BYREF
  std::_Ref_count_base *v26; // [rsp+48h] [rbp-210h]
  _OWORD v27[2]; // [rsp+50h] [rbp-208h] BYREF
  __int64 v28; // [rsp+70h] [rbp-1E8h]
  void *v29; // [rsp+78h] [rbp-1E0h] BYREF
  std::_Ref_count_base *v30; // [rsp+80h] [rbp-1D8h]
  _QWORD *v31; // [rsp+88h] [rbp-1D0h]
  std::_Ref_count_base *v32; // [rsp+90h] [rbp-1C8h]
  void *v33[2]; // [rsp+98h] [rbp-1C0h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-1B0h]
  void **v35; // [rsp+C0h] [rbp-198h] BYREF
  char v36[272]; // [rsp+C8h] [rbp-190h] BYREF
  char v37[8]; // [rsp+1D8h] [rbp-80h] BYREF
  char v38[56]; // [rsp+1E0h] [rbp-78h] BYREF

  SetThreadName((WCHAR *)L"RPC SWSess_Open");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v24, v8);
  *a4 = 0;
  *a5 = 0;
  v9 = 0;
  wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(
    &v35,
    "SW_ServiceWorkerSession_Open");
  v35 = &ServiceWorkerTraceLogging::SW_ServiceWorkerSession_Open::`vftable';
  ServiceWorkerTraceLogging::SW_ServiceWorkerSession_Open::StartActivity(&v35, a2, a3);
  ClientIdentity::s_GetPackageNameHelper((__int64)v33);
  ClientIdentityTraceLogging::LogPackageName(v33);
  Instance = (_QWORD *)WebPlatStorageClientManager::GetInstance(v10);
  (*(void (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, __int64 *), void **))(*(_QWORD *)*Instance + 8LL))(
    *Instance,
    &v23,
    v33);
  v12 = (_QWORD *)(**v23)(v23, &v25);
  v13 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v12 + 40LL))(*v12, 3);
  v14 = (_QWORD *)*v13;
  v15 = v13[1];
  if ( v15 )
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
  v31 = v14;
  v16 = (std::_Ref_count_base *)v13[1];
  v32 = v16;
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  ServiceWorkerStorageClient::OpenStorageSession((_DWORD)v14, (unsigned int)&v29, (unsigned int)&v23, a2, a3);
  memset(v27, 0, sizeof(v27));
  v28 = 0;
  v17 = std::_Allocate<16,std::_Default_allocate_traits>(0x10u);
  v17[1] = 0;
  *(_QWORD *)&v27[0] = v17;
  *v17 = v27;
  v18 = (std::_Ref_count_base *)(v14 + 11);
  v19 = v14[13];
  if ( v14[14] > 7u )
    v18 = *(std::_Ref_count_base **)v18;
  if ( v19 == -1 || !v18 && v19 )
  {
    _o_terminate(v19);
    v9 = (unsigned int)v23;
  }
  else
  {
    v25 = v14[13];
    v26 = v18;
    *a5 = (const unsigned __int16 *)RpcHelper::AllocationTracker::AllocateString((__int64)v27, (__int64)&v25);
    std::deque<void *>::_Tidy(v27);
    v20 = v29;
    *a4 = v29;
    ServiceWorkerTraceLogging::SW_ServiceWorkerSession_Open::Stop(
      (ServiceWorkerTraceLogging::SW_ServiceWorkerSession_Open *)&v35,
      v20,
      *a5);
    RpcHelper::AllocationTracker::~AllocationTracker((RpcHelper::AllocationTracker *)v27);
    if ( v30 )
      std::_Ref_count_base::_Decref(v30);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    if ( v23 )
      std::default_delete<IWebPlatStorageClientReference>::operator()();
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v33[0], 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v33[0]) = 0;
    v35 = &ServiceWorkerTraceLogging::SW_ServiceWorkerSession_Open::`vftable';
    wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v35);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v38);
    wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v37);
    wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>(v36);
  }
  v21 = v24;
  if ( _InterlockedExchangeAdd64(v24, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v21 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return v9;
}

```

## disassembly

```asm
0x180035550  push    rbx
0x180035552  push    rsi
0x180035553  push    rdi
0x180035554  push    r12
0x180035556  push    r13
0x180035558  push    r14
0x18003555a  push    r15
0x18003555c  sub     rsp, 220h
0x180035563  mov     rax, cs:__security_cookie
0x18003556a  xor     rax, rsp
0x18003556d  mov     [rsp+258h+var_40], rax
0x180035575  mov     r13, r9
0x180035578  mov     r14, r8
0x18003557b  mov     esi, edx
0x18003557d  mov     r12, [rsp+258h+arg_20]
0x180035585  xor     ebx, ebx
0x180035587  lea     rcx, aRpcSwsessOpen; "RPC SWSess_Open"
0x18003558e  call    SetThreadName
0x180035593  nop
0x180035594  lea     rcx, [rsp+258h+var_220]; this
0x180035599  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x18003559e  nop
0x18003559f  mov     [r13+0], rbx
0x1800355a3  mov     [r12], rbx
0x1800355a7  mov     r15d, ebx
0x1800355aa  lea     rdx, aSwServiceworke_2; "SW_ServiceWorkerSession_Open"
0x1800355b1  lea     rcx, [rsp+258h+var_198]
0x1800355b9  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800355be  lea     rax, ??_7SW_ServiceWorkerSession_Open@ServiceWorkerTraceLogging@@6B@; const ServiceWorkerTraceLogging::SW_ServiceWorkerSession_Open::`vftable'
0x1800355c5  mov     [rsp+258h+var_198], rax
0x1800355cd  mov     r8, r14
0x1800355d0  mov     edx, esi
0x1800355d2  lea     rcx, [rsp+258h+var_198]
0x1800355da  call    ?StartActivity@SW_ServiceWorkerSession_Open@ServiceWorkerTraceLogging@@QEAAXW4WEBPLAT_STORAGE_CONTEXT_FLAGS@@AEBURPCServiceWorkerManager@@@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_Open::StartActivity(WEBPLAT_STORAGE_CONTEXT_FLAGS,RPCServiceWorkerManager const &)
0x1800355df  nop
0x1800355e0  lea     rcx, [rsp+258h+var_1C0]
0x1800355e8  call    ?s_GetPackageNameHelper@ClientIdentity@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ClientIdentity::s_GetPackageNameHelper(void)
0x1800355ed  lea     rcx, [rsp+258h+var_1C0]
0x1800355f5  call    ?LogPackageName@ClientIdentityTraceLogging@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ClientIdentityTraceLogging::LogPackageName(std::wstring const &)
0x1800355fa  nop
0x1800355fb  call    ?GetInstance@WebPlatStorageClientManager@@SAAEAV?$unique_ptr@VWebPlatStorageClientManager@@U?$default_delete@VWebPlatStorageClientManager@@@std@@@std@@XZ; WebPlatStorageClientManager::GetInstance(void)
0x180035600  mov     rcx, [rax]
0x180035603  mov     rax, [rcx]
0x180035606  lea     r8, [rsp+258h+var_1C0]
0x18003560e  lea     rdx, [rsp+258h+var_228]
0x180035613  mov     rax, [rax+8]
0x180035617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003561c  nop
0x18003561d  mov     rcx, [rsp+258h+var_228]
0x180035622  mov     rax, [rcx]
0x180035625  lea     rdx, [rsp+258h+var_218]
0x18003562a  mov     rax, [rax]
0x18003562d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035632  nop
0x180035633  mov     rcx, [rax]
0x180035636  mov     rax, [rcx]
0x180035639  lea     edx, [rbx+3]
0x18003563c  mov     rax, [rax+28h]
0x180035640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035645  mov     rdi, [rax]
0x180035648  mov     rcx, [rax+8]
0x18003564c  test    rcx, rcx
0x18003564f  jz      short loc_180035655
0x180035651  lock inc dword ptr [rcx+8]
0x180035655  mov     [rsp+258h+var_1D0], rdi
0x18003565d  mov     rbx, [rax+8]
0x180035661  mov     [rsp+258h+var_1C8], rbx
0x180035669  mov     rcx, [rsp+258h+var_210]; this
0x18003566e  test    rcx, rcx
0x180035671  jz      short loc_180035678
0x180035673  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035678  mov     [rsp+258h+var_238], r14
0x18003567d  mov     r9d, esi
0x180035680  lea     r8, [rsp+258h+var_228]
0x180035685  lea     rdx, [rsp+258h+var_1E0]
0x18003568a  mov     rcx, rdi
0x18003568d  call    ?OpenStorageSession@ServiceWorkerStorageClient@@QEAA?AV?$shared_ptr@VServiceWorkerStorageSession@@@std@@$$QEAV?$unique_ptr@UIWebPlatStorageClientReference@@U?$default_delete@UIWebPlatStorageClientReference@@@std@@@3@W4WEBPLAT_STORAGE_CONTEXT_FLAGS@@AEBURPCServiceWorkerManager@@@Z; ServiceWorkerStorageClient::OpenStorageSession(std::unique_ptr<IWebPlatStorageClientReference> &&,WEBPLAT_STORAGE_CONTEXT_FLAGS,RPCServiceWorkerManager const &)
0x180035692  nop
0x180035693  xorps   xmm0, xmm0
0x180035696  movdqu  [rsp+258h+var_208], xmm0
0x18003569c  xorps   xmm1, xmm1
0x18003569f  movdqu  [rsp+258h+var_1F8], xmm1
0x1800356a5  mov     [rsp+258h+var_1E8], 0
0x1800356ae  mov     ecx, 10h
0x1800356b3  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800356b8  mov     qword ptr [rax+8], 0
0x1800356c0  mov     qword ptr [rsp+258h+var_208], rax
0x1800356c5  lea     rcx, [rsp+258h+var_208]
0x1800356ca  mov     [rax], rcx
0x1800356cd  lea     rax, [rdi+58h]
0x1800356d1  mov     rcx, [rax+10h]
0x1800356d5  cmp     qword ptr [rax+18h], 7
0x1800356da  jbe     short loc_1800356DF
0x1800356dc  mov     rax, [rax]
0x1800356df  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800356e3  jz      loc_1800357F9
0x1800356e9  test    rax, rax
0x1800356ec  jnz     short loc_1800356F7
0x1800356ee  test    rcx, rcx
0x1800356f1  jnz     loc_1800357F9
0x1800356f7  mov     [rsp+258h+var_218], rcx
0x1800356fc  mov     [rsp+258h+var_210], rax
0x180035701  lea     rdx, [rsp+258h+var_218]
0x180035706  lea     rcx, [rsp+258h+var_208]
0x18003570b  call    ?AllocateString@AllocationTracker@RpcHelper@@QEAAPEAGV?$basic_string_span@$$CBG$0?0@gsl@@@Z; RpcHelper::AllocationTracker::AllocateString(gsl::basic_string_span<ushort const,-1>)
0x180035710  mov     [r12], rax
0x180035714  lea     rcx, [rsp+258h+var_208]
0x180035719  call    ?_Tidy@?$deque@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::deque<void *>::_Tidy(void)
0x18003571e  mov     rdx, [rsp+258h+var_1E0]; void *
0x180035723  mov     [r13+0], rdx
0x180035727  mov     r8, [r12]; unsigned __int16 *
0x18003572b  lea     rcx, [rsp+258h+var_198]; this
0x180035733  call    ?Stop@SW_ServiceWorkerSession_Open@ServiceWorkerTraceLogging@@QEAAXPEAXPEBG@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_Open::Stop(void *,ushort const *)
0x180035738  nop
0x180035739  lea     rcx, [rsp+258h+var_208]; this
0x18003573e  call    ??1AllocationTracker@RpcHelper@@QEAA@XZ; RpcHelper::AllocationTracker::~AllocationTracker(void)
0x180035743  nop
0x180035744  mov     rcx, [rsp+258h+var_1D8]; this
0x18003574c  test    rcx, rcx
0x18003574f  jz      short loc_180035757
0x180035751  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035756  nop
0x180035757  test    rbx, rbx
0x18003575a  jz      short loc_180035765
0x18003575c  mov     rcx, rbx; this
0x18003575f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035764  nop
0x180035765  mov     rdx, [rsp+258h+var_228]
0x18003576a  test    rdx, rdx
0x18003576d  jz      short loc_180035775
0x18003576f  call    ??R?$default_delete@UIWebPlatStorageClientReference@@@std@@QEBAXPEAUIWebPlatStorageClientReference@@@Z; std::default_delete<IWebPlatStorageClientReference>::operator()(IWebPlatStorageClientReference *)
0x180035774  nop
0x180035775  mov     rdx, [rsp+258h+var_1A8]
0x18003577d  cmp     rdx, 7
0x180035781  jbe     short loc_180035798
0x180035783  lea     rdx, ds:2[rdx*2]
0x18003578b  mov     rcx, [rsp+258h+var_1C0]
0x180035793  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180035798  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800357a0  movdqu  xmmword ptr [rsp+0A8h], xmm0
0x1800357a9  xor     eax, eax
0x1800357ab  mov     word ptr [rsp+258h+var_1C0], ax
0x1800357b3  lea     rax, ??_7SW_ServiceWorkerSession_Open@ServiceWorkerTraceLogging@@6B@; const ServiceWorkerTraceLogging::SW_ServiceWorkerSession_Open::`vftable'
0x1800357ba  mov     [rsp+258h+var_198], rax
0x1800357c2  lea     rcx, [rsp+258h+var_198]
0x1800357ca  call    ?Destroy@?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800357cf  lea     rcx, [rsp+258h+var_78]; this
0x1800357d7  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800357dc  lea     rcx, [rsp+258h+var_80]
0x1800357e4  call    ?reset@?$shared_object@V?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800357e9  lea     rcx, [rsp+258h+var_190]
0x1800357f1  call    ??1?$ActivityData@VStorageServerProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<StorageServerProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800357f6  nop
0x1800357f7  jmp     short loc_180035805
0x1800357f9  call    cs:__imp__o_terminate
0x1800357ff  nop
0x180035800  mov     r15d, dword ptr [rsp+258h+var_228]
0x180035805  mov     rcx, [rsp+258h+var_220]
0x18003580a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003580e  lock xadd [rcx], rax
0x180035813  cmp     rax, 1
0x180035817  jnz     short loc_18003582C
0x180035819  xor     r9d, r9d; msWindowLength
0x18003581c  xor     r8d, r8d; msPeriod
0x18003581f  xor     edx, edx; pftDueTime
0x180035821  mov     rcx, [rcx+8]; pti
0x180035825  call    cs:__imp_SetThreadpoolTimer
0x18003582b  nop
0x18003582c  lea     rcx, word_1800D6108; lpWideCharStr
0x180035833  call    SetThreadName
0x180035838  nop
0x180035839  mov     eax, r15d
0x18003583c  mov     rcx, [rsp+258h+var_40]
0x180035844  xor     rcx, rsp; StackCookie
0x180035847  call    __security_check_cookie
0x18003584c  add     rsp, 220h
0x180035853  pop     r15
0x180035855  pop     r14
0x180035857  pop     r13
0x180035859  pop     r12
0x18003585b  pop     rdi
0x18003585c  pop     rsi
0x18003585d  pop     rbx
0x18003585e  retn
```
