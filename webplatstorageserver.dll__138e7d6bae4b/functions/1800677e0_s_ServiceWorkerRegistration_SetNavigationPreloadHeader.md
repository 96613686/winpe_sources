# s_ServiceWorkerRegistration_SetNavigationPreloadHeader

- ea: `0x1800677e0`
- end: `0x180067926`
- name: `s_ServiceWorkerRegistration_SetNavigationPreloadHeader`
- size: `326`
- prototype: `__int64 __fastcall(__int64, void *, const struct RPCByteBuffer *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task`

## callees

- `0x180006e9c`
- `0x18001d480`
- `0x18001ecd0`
- `0x18001f470`
- `0x1800273f0`
- `0x18002d290`
- `0x1800677e0`
- `0x18006792c`
- `0x180067a28`
- `0x180067a54`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18006791e`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18006791e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800678e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800678e4`

## string_xrefs

- `0x180067822`: `SW_ServiceWorkerRegistration_SetNavigationPreloadHeader`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall s_ServiceWorkerRegistration_SetNavigationPreloadHeader(
        __int64 a1,
        void *a2,
        const struct RPCByteBuffer *a3)
{
  struct HangDetectionWatchDog *v5; // rdx
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 v8; // rcx
  const char *v9; // r9
  volatile signed __int64 *v10; // rcx
  wil *v12; // rcx
  volatile signed __int64 *v13; // [rsp+28h] [rbp-1A0h] BYREF
  __int128 v14; // [rsp+30h] [rbp-198h] BYREF
  _BYTE v15[16]; // [rsp+40h] [rbp-188h] BYREF
  _QWORD v16[43]; // [rsp+50h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  SetThreadName(L"RPC SWReg_SetNavPreloadHeader");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v13, v5);
  v6 = 0;
  wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v16,
    "SW_ServiceWorkerRegistration_SetNavigationPreloadHeader");
  try
  {
    v16[0] = &ServiceWorkerTraceLogging::SW_ServiceWorkerRegistration_SetNavigationPreloadHeader::`vftable';
    ServiceWorkerTraceLogging::SW_ServiceWorkerRegistration_SetNavigationPreloadHeader::StartActivity(
      (ServiceWorkerTraceLogging::SW_ServiceWorkerRegistration_SetNavigationPreloadHeader *)v16,
      a2,
      a3);
    v7 = *((_QWORD *)a3 + 1);
    gsl::details::extent_type<-1>::extent_type<-1>(&v14, *(unsigned int *)a3);
    *((_QWORD *)&v14 + 1) = v7;
    if ( (_QWORD)v14 == -1 || !v7 && (_QWORD)v14 )
    {
      _o_terminate(v8);
      __debugbreak();
      JUMPOUT(0x180067926LL);
    }
    v14 = *(_OWORD *)gsl::span<unsigned char const,-1>::span<unsigned char const,-1>(v15, &v14);
    ServiceWorkerRegistrationSession::SetNavigationPreloadHeader(a2, &v14);
    wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v16);
    ServiceWorkerTraceLogging::SW_ServiceWorkerRegistration_SetNavigationPreloadHeader::~SW_ServiceWorkerRegistration_SetNavigationPreloadHeader((ServiceWorkerTraceLogging::SW_ServiceWorkerRegistration_SetNavigationPreloadHeader *)v16);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x33E,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\serviceworkerstorage\\serviceworkerrpcapi.cxx",
      v9);
    v6 = wil::ResultFromCaughtException(v12);
  }
  v10 = v13;
  if ( _InterlockedExchangeAdd64(v13, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v10 + 1), 0, 0, 0);
  SetThreadName(&word_1800D6108);
  return v6;
}

```

## disassembly

```asm
0x1800677e0  mov     [rsp+arg_0], rbx
0x1800677e5  push    rsi
0x1800677e6  push    rdi
0x1800677e7  push    r14
0x1800677e9  sub     rsp, 1B0h
0x1800677f0  mov     rax, cs:__security_cookie
0x1800677f7  xor     rax, rsp
0x1800677fa  mov     [rsp+1C8h+var_20], rax
0x180067802  mov     r14, r8
0x180067805  mov     rsi, rdx
0x180067808  lea     rcx, aRpcSwregSetnav; "RPC SWReg_SetNavPreloadHeader"
0x18006780f  call    SetThreadName
0x180067814  nop
0x180067815  lea     rcx, [rsp+1C8h+var_1A0]; this
0x18006781a  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x18006781f  nop
0x180067820  xor     ebx, ebx
0x180067822  lea     rdx, aSwServiceworke_15; "SW_ServiceWorkerRegistration_SetNavigat"...
0x180067829  lea     rcx, [rsp+1C8h+var_178]
0x18006782e  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180067833  lea     rax, ??_7SW_ServiceWorkerRegistration_SetNavigationPreloadHeader@ServiceWorkerTraceLogging@@6B@; const ServiceWorkerTraceLogging::SW_ServiceWorkerRegistration_SetNavigationPreloadHeader::`vftable'
0x18006783a  mov     [rsp+1C8h+var_178], rax
0x18006783f  mov     r8, r14; struct RPCByteBuffer *
0x180067842  mov     rdx, rsi; void *
0x180067845  lea     rcx, [rsp+1C8h+var_178]; this
0x18006784a  call    ?StartActivity@SW_ServiceWorkerRegistration_SetNavigationPreloadHeader@ServiceWorkerTraceLogging@@QEAAXPEAXAEBURPCByteBuffer@@@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerRegistration_SetNavigationPreloadHeader::StartActivity(void *,RPCByteBuffer const &)
0x18006784f  nop
0x180067850  mov     rdi, [r14+8]
0x180067854  mov     edx, [r14]
0x180067857  lea     rcx, [rsp+1C8h+var_198]
0x18006785c  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x180067861  mov     qword ptr [rsp+1C8h+var_198+8], rdi
0x180067866  mov     rax, qword ptr [rsp+1C8h+var_198]
0x18006786b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006786f  jz      loc_18006791E
0x180067875  test    rdi, rdi
0x180067878  jnz     short loc_180067883
0x18006787a  test    rax, rax
0x18006787d  jnz     loc_18006791E
0x180067883  lea     rdx, [rsp+1C8h+var_198]
0x180067888  lea     rcx, [rsp+1C8h+var_188]
0x18006788d  call    ??$?0E$0?0$0?0$0A@@?$span@$$CBE$0?0@gsl@@QEAA@AEBV?$span@E$0?0@1@@Z; gsl::span<uchar const,-1>::span<uchar const,-1>(gsl::span<uchar,-1> const &)
0x180067892  movups  xmm0, xmmword ptr [rax]
0x180067895  movdqu  [rsp+1C8h+var_198], xmm0
0x18006789b  lea     rdx, [rsp+1C8h+var_198]
0x1800678a0  mov     rcx, rsi
0x1800678a3  call    ?SetNavigationPreloadHeader@ServiceWorkerRegistrationSession@@QEAAXV?$span@$$CBE$0?0@gsl@@@Z; ServiceWorkerRegistrationSession::SetNavigationPreloadHeader(gsl::span<uchar const,-1>)
0x1800678a8  lea     rcx, [rsp+1C8h+var_178]
0x1800678ad  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800678b2  nop
0x1800678b3  lea     rcx, [rsp+1C8h+var_178]; this
0x1800678b8  call    ??1SW_ServiceWorkerRegistration_SetNavigationPreloadHeader@ServiceWorkerTraceLogging@@QEAA@XZ; ServiceWorkerTraceLogging::SW_ServiceWorkerRegistration_SetNavigationPreloadHeader::~SW_ServiceWorkerRegistration_SetNavigationPreloadHeader(void)
0x1800678bd  nop
0x1800678be  jmp     short loc_1800678C4
0x1800678c0  mov     ebx, [rsp+1C8h+var_1A8]
0x1800678c4  mov     rcx, [rsp+1C8h+var_1A0]
0x1800678c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800678cd  lock xadd [rcx], rax
0x1800678d2  cmp     rax, 1
0x1800678d6  jnz     short loc_1800678EB
0x1800678d8  xor     r9d, r9d; msWindowLength
0x1800678db  xor     r8d, r8d; msPeriod
0x1800678de  xor     edx, edx; pftDueTime
0x1800678e0  mov     rcx, [rcx+8]; pti
0x1800678e4  call    cs:__imp_SetThreadpoolTimer
0x1800678ea  nop
0x1800678eb  lea     rcx, word_1800D6108; lpWideCharStr
0x1800678f2  call    SetThreadName
0x1800678f7  nop
0x1800678f8  mov     eax, ebx
0x1800678fa  mov     rcx, [rsp+1C8h+var_20]
0x180067902  xor     rcx, rsp; StackCookie
0x180067905  call    __security_check_cookie
0x18006790a  mov     rbx, [rsp+1C8h+arg_0]
0x180067912  add     rsp, 1B0h
0x180067919  pop     r14
0x18006791b  pop     rdi
0x18006791c  pop     rsi
0x18006791d  retn
0x18006791e  call    cs:__imp__o_terminate
0x180067924  nop
0x180067925  int     3; Trap to Debugger
```
