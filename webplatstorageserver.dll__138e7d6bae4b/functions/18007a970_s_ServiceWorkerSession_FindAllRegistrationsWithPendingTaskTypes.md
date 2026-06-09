# s_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes

- ea: `0x18007a970`
- end: `0x18007ab25`
- name: `s_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes`
- size: `437`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `service_task`

## callees

- `0x180006e9c`
- `0x18000f2b0`
- `0x18001d480`
- `0x18001f470`
- `0x18001f7d0`
- `0x1800273f0`
- `0x180028c50`
- `0x18002d290`
- `0x1800340f8`
- `0x180052704`
- `0x18005a954`
- `0x18007a970`
- `0x18007ab2c`
- `0x18007adb4`
- `0x18007e240`
- `0x180080fb0`
- `0x1800965ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18007aac5`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18007aac5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007aaf0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007aaf0`

## string_xrefs

- `0x18007a9ca`: `SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall s_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        unsigned int *a4,
        __int64 *a5)
{
  struct HangDetectionWatchDog *v8; // rdx
  unsigned int v9; // edi
  _QWORD *v10; // rax
  unsigned int v11; // eax
  __int64 v12; // rbx
  __int64 v13; // rcx
  volatile signed __int64 *v14; // rcx
  _BYTE v16[16]; // [rsp+20h] [rbp-1E8h] BYREF
  __int128 v17; // [rsp+30h] [rbp-1D8h] BYREF
  volatile signed __int64 *v18; // [rsp+40h] [rbp-1C8h] BYREF
  _BYTE v19[32]; // [rsp+48h] [rbp-1C0h] BYREF
  unsigned __int64 v20; // [rsp+68h] [rbp-1A0h]
  _BYTE v21[16]; // [rsp+70h] [rbp-198h] BYREF
  _QWORD v22[43]; // [rsp+80h] [rbp-188h] BYREF

  SetThreadName((WCHAR *)L"RPC SWSess_FindAllRegWithPTT");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v18, v8);
  *a5 = 0;
  *a4 = 0;
  v9 = 0;
  wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v22,
    "SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes");
  v22[0] = &ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes::`vftable';
  ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes::StartActivity(
    (ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes *)v22,
    a2,
    a3);
  v16[0] = a3;
  SequentialExecutionEnforcer::Start(a2[10], &v17);
  v10 = (_QWORD *)DelayInitObject<std::shared_ptr<EseHelper::IDatabaseEngine>>::Get(a2 + 6);
  ServiceWorkerDatabaseTable::FindAllRegistrationsWithPendingTaskTypes(*v10, v19, v16);
  SequentialExecutionEnforcer::InProgressExecution::~InProgressExecution((SequentialExecutionEnforcer::InProgressExecution *)&v17);
  *a5 = AllocateRPCRegistrationList(v19);
  v11 = wil::safe_cast_failfast<unsigned int,unsigned __int64,0>(v20);
  *a4 = v11;
  v12 = *a5;
  gsl::details::extent_type<-1>::extent_type<-1>(&v17, v11);
  *((_QWORD *)&v17 + 1) = v12;
  if ( (_QWORD)v17 == -1 || !v12 && (_QWORD)v17 )
  {
    _o_terminate(v13);
    v9 = v17;
  }
  else
  {
    v17 = *(_OWORD *)gsl::span<unsigned char const,-1>::span<unsigned char const,-1>(v21, &v17);
    ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes::Stop(v22, &v17);
    std::deque<std::unique_ptr<StoredServiceWorkerRegistration>>::~deque<std::unique_ptr<StoredServiceWorkerRegistration>>(v19);
    ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes::~SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes((ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes *)v22);
  }
  v14 = v18;
  if ( _InterlockedExchangeAdd64(v18, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v14 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return v9;
}

```

## disassembly

```asm
0x18007a970  push    rbx
0x18007a972  push    rsi
0x18007a973  push    rdi
0x18007a974  push    r14
0x18007a976  push    r15
0x18007a978  sub     rsp, 1E0h
0x18007a97f  mov     rax, cs:__security_cookie
0x18007a986  xor     rax, rsp
0x18007a989  mov     [rsp+208h+var_30], rax
0x18007a991  mov     r15, r9
0x18007a994  mov     r14d, r8d
0x18007a997  mov     rsi, rdx
0x18007a99a  mov     rbx, [rsp+208h+arg_20]
0x18007a9a2  lea     rcx, aRpcSwsessFinda_1; "RPC SWSess_FindAllRegWithPTT"
0x18007a9a9  call    SetThreadName
0x18007a9ae  nop
0x18007a9af  lea     rcx, [rsp+208h+var_1C8]; this
0x18007a9b4  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x18007a9b9  nop
0x18007a9ba  mov     qword ptr [rbx], 0
0x18007a9c1  mov     dword ptr [r15], 0
0x18007a9c8  xor     edi, edi
0x18007a9ca  lea     rdx, aSwServiceworke_9; "SW_ServiceWorkerSession_FindAllRegistra"...
0x18007a9d1  lea     rcx, [rsp+208h+var_188]
0x18007a9d9  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$03$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,4,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18007a9de  lea     rax, ??_7SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes@ServiceWorkerTraceLogging@@6B@; const ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes::`vftable'
0x18007a9e5  mov     [rsp+208h+var_188], rax
0x18007a9ed  mov     r8d, r14d; unsigned int
0x18007a9f0  mov     rdx, rsi; void *
0x18007a9f3  lea     rcx, [rsp+208h+var_188]; this
0x18007a9fb  call    ?StartActivity@SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes@ServiceWorkerTraceLogging@@QEAAXPEAXI@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes::StartActivity(void *,uint)
0x18007aa00  nop
0x18007aa01  mov     [rsp+208h+var_1E8], r14b
0x18007aa06  lea     rdx, [rsp+208h+var_1D8]
0x18007aa0b  mov     rcx, [rsi+50h]
0x18007aa0f  call    ?Start@SequentialExecutionEnforcer@@QEAA?AVInProgressExecution@1@XZ; SequentialExecutionEnforcer::Start(void)
0x18007aa14  nop
0x18007aa15  lea     rcx, [rsi+30h]
0x18007aa19  call    ?Get@?$DelayInitObject@V?$shared_ptr@UIDatabaseEngine@EseHelper@@@std@@@@QEBAAEBV?$shared_ptr@UIDatabaseEngine@EseHelper@@@std@@XZ; DelayInitObject<std::shared_ptr<EseHelper::IDatabaseEngine>>::Get(void)
0x18007aa1e  lea     r8, [rsp+208h+var_1E8]
0x18007aa23  lea     rdx, [rsp+208h+var_1C0]
0x18007aa28  mov     rcx, [rax]
0x18007aa2b  call    ?FindAllRegistrationsWithPendingTaskTypes@ServiceWorkerDatabaseTable@@QEAA?AV?$deque@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@V?$allocator@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@@2@@std@@AEBUServiceWorkerPendingRegistrationTasks@@@Z; ServiceWorkerDatabaseTable::FindAllRegistrationsWithPendingTaskTypes(ServiceWorkerPendingRegistrationTasks const &)
0x18007aa30  nop
0x18007aa31  lea     rcx, [rsp+208h+var_1D8]; this
0x18007aa36  call    ??1InProgressExecution@SequentialExecutionEnforcer@@QEAA@XZ; SequentialExecutionEnforcer::InProgressExecution::~InProgressExecution(void)
0x18007aa3b  nop
0x18007aa3c  lea     rcx, [rsp+208h+var_1C0]
0x18007aa41  call    AllocateRPCRegistrationList
0x18007aa46  mov     [rbx], rax
0x18007aa49  mov     rcx, [rsp+208h+var_1A0]
0x18007aa4e  call    ??$safe_cast_failfast@I_K$0A@@wil@@YAI_K@Z; wil::safe_cast_failfast<uint,unsigned __int64,0>(unsigned __int64)
0x18007aa53  mov     [r15], eax
0x18007aa56  mov     rbx, [rbx]
0x18007aa59  mov     edx, eax
0x18007aa5b  lea     rcx, [rsp+208h+var_1D8]
0x18007aa60  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x18007aa65  mov     qword ptr [rsp+208h+var_1D8+8], rbx
0x18007aa6a  mov     rax, qword ptr [rsp+208h+var_1D8]
0x18007aa6f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007aa73  jz      short loc_18007AAC5
0x18007aa75  test    rbx, rbx
0x18007aa78  jnz     short loc_18007AA7F
0x18007aa7a  test    rax, rax
0x18007aa7d  jnz     short loc_18007AAC5
0x18007aa7f  lea     rdx, [rsp+208h+var_1D8]
0x18007aa84  lea     rcx, [rsp+208h+var_198]
0x18007aa89  call    ??$?0E$0?0$0?0$0A@@?$span@$$CBE$0?0@gsl@@QEAA@AEBV?$span@E$0?0@1@@Z; gsl::span<uchar const,-1>::span<uchar const,-1>(gsl::span<uchar,-1> const &)
0x18007aa8e  movups  xmm0, xmmword ptr [rax]
0x18007aa91  movdqu  [rsp+208h+var_1D8], xmm0
0x18007aa97  lea     rdx, [rsp+208h+var_1D8]
0x18007aa9c  lea     rcx, [rsp+208h+var_188]
0x18007aaa4  call    ?Stop@SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes@ServiceWorkerTraceLogging@@QEAAXV?$span@QEAURPCServiceWorkerRegistration@@$0?0@gsl@@@Z; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes::Stop(gsl::span<RPCServiceWorkerRegistration * const,-1>)
0x18007aaa9  nop
0x18007aaaa  lea     rcx, [rsp+208h+var_1C0]
0x18007aaaf  call    ??1?$deque@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@V?$allocator@V?$unique_ptr@VStoredServiceWorkerRegistration@@U?$default_delete@VStoredServiceWorkerRegistration@@@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::unique_ptr<StoredServiceWorkerRegistration>>::~deque<std::unique_ptr<StoredServiceWorkerRegistration>>(void)
0x18007aab4  nop
0x18007aab5  lea     rcx, [rsp+208h+var_188]; this
0x18007aabd  call    ??1SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes@ServiceWorkerTraceLogging@@QEAA@XZ; ServiceWorkerTraceLogging::SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes::~SW_ServiceWorkerSession_FindAllRegistrationsWithPendingTaskTypes(void)
0x18007aac2  nop
0x18007aac3  jmp     short loc_18007AAD0
0x18007aac5  call    cs:__imp__o_terminate
0x18007aacb  nop
0x18007aacc  mov     edi, dword ptr [rsp+208h+var_1D8]
0x18007aad0  mov     rcx, [rsp+208h+var_1C8]
0x18007aad5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007aad9  lock xadd [rcx], rax
0x18007aade  cmp     rax, 1
0x18007aae2  jnz     short loc_18007AAF7
0x18007aae4  xor     r9d, r9d; msWindowLength
0x18007aae7  xor     r8d, r8d; msPeriod
0x18007aaea  xor     edx, edx; pftDueTime
0x18007aaec  mov     rcx, [rcx+8]; pti
0x18007aaf0  call    cs:__imp_SetThreadpoolTimer
0x18007aaf6  nop
0x18007aaf7  lea     rcx, word_1800D6108; lpWideCharStr
0x18007aafe  call    SetThreadName
0x18007ab03  nop
0x18007ab04  mov     eax, edi
0x18007ab06  mov     rcx, [rsp+208h+var_30]
0x18007ab0e  xor     rcx, rsp; StackCookie
0x18007ab11  call    __security_check_cookie
0x18007ab16  add     rsp, 1E0h
0x18007ab1d  pop     r15
0x18007ab1f  pop     r14
0x18007ab21  pop     rdi
0x18007ab22  pop     rsi
0x18007ab23  pop     rbx
0x18007ab24  retn
```
