# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000f294`
- end: `0x18000f354`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180016a00`

## callees

- `0x18000f294`
- `0x18000f35c`
- `0x18000f9f8`
- `0x18000fc84`
- `0x180010f28`
- `0x180010f48`
- `0x180011060`
- `0x180015db4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f2e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f2e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f345`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f345`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f310`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f310`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  char v10; // [rsp+50h] [rbp+8h] BYREF

  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    if ( !BYTE1(a1[8].Ptr) )
    {
      if ( !a1[6].Ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    if ( a1 != (RTL_SRWLOCK *)-32LL )
      ReleaseSRWLockExclusive(a1 + 4);
  }
}

```

## disassembly

```asm
0x18000f294  push    rbx
0x18000f296  push    rbp
0x18000f297  push    rsi
0x18000f298  push    rdi
0x18000f299  sub     rsp, 28h
0x18000f29d  cmp     byte ptr [rcx], 0
0x18000f2a0  mov     rdi, r9
0x18000f2a3  mov     esi, r8d
0x18000f2a6  mov     ebp, edx
0x18000f2a8  mov     rbx, rcx
0x18000f2ab  jz      loc_18000F34B
0x18000f2b1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000f2b6  test    al, al
0x18000f2b8  jz      loc_18000F34B
0x18000f2be  mov     rcx, [rbx+18h]
0x18000f2c2  mov     r9, rdi
0x18000f2c5  mov     r8d, esi
0x18000f2c8  mov     edx, ebp
0x18000f2ca  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000f2cf  test    al, al
0x18000f2d1  jz      short loc_18000F34B
0x18000f2d3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000f2d8  test    al, al
0x18000f2da  jnz     short loc_18000F34B
0x18000f2dc  lea     rdi, [rbx+20h]
0x18000f2e0  mov     rcx, rdi; SRWLock
0x18000f2e3  call    cs:__imp_AcquireSRWLockExclusive
0x18000f2e9  cmp     byte ptr [rbx+41h], 0
0x18000f2ed  jnz     short loc_18000F33D
0x18000f2ef  lea     rsi, [rbx+30h]
0x18000f2f3  cmp     qword ptr [rsi], 0
0x18000f2f7  jnz     short loc_18000F32B
0x18000f2f9  lea     rcx, [rsp+48h+arg_0]; this
0x18000f2fe  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000f303  xor     r8d, r8d; pcbe
0x18000f306  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f30d  mov     rdx, rbx; pv
0x18000f310  call    cs:__imp_CreateThreadpoolTimer
0x18000f316  mov     rdx, rax
0x18000f319  mov     rcx, rsi
0x18000f31c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000f321  lea     rcx, [rsp+48h+arg_0]; this
0x18000f326  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000f32b  mov     r8d, 493E0h
0x18000f331  lea     rdx, [rbx+41h]
0x18000f335  mov     rcx, rsi
0x18000f338  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000f33d  test    rdi, rdi
0x18000f340  jz      short loc_18000F34B
0x18000f342  mov     rcx, rdi; SRWLock
0x18000f345  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f34b  add     rsp, 28h
0x18000f34f  pop     rdi
0x18000f350  pop     rsi
0x18000f351  pop     rbp
0x18000f352  pop     rbx
0x18000f353  retn
```
