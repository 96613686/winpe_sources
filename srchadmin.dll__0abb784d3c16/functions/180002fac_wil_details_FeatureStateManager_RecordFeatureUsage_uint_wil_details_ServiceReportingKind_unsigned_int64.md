# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180002fac`
- end: `0x18000306d`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18000c320`

## callees

- `0x180002fac`
- `0x180003074`
- `0x180003138`
- `0x180003158`
- `0x18000317c`
- `0x1800031c0`
- `0x180003770`
- `0x18000b0f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002ffb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002ffb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000305d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000305d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003028`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003028`

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
0x180002fac  push    rbx
0x180002fae  push    rbp
0x180002faf  push    rsi
0x180002fb0  push    rdi
0x180002fb1  sub     rsp, 28h
0x180002fb5  mov     rdi, r9
0x180002fb8  mov     esi, r8d
0x180002fbb  mov     ebp, edx
0x180002fbd  mov     rbx, rcx
0x180002fc0  cmp     byte ptr [rcx], 0
0x180002fc3  jz      loc_180003064
0x180002fc9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180002fce  test    al, al
0x180002fd0  jz      loc_180003064
0x180002fd6  mov     r9, rdi
0x180002fd9  mov     r8d, esi
0x180002fdc  mov     edx, ebp
0x180002fde  mov     rcx, [rbx+18h]
0x180002fe2  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180002fe7  test    al, al
0x180002fe9  jz      short loc_180003064
0x180002feb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180002ff0  test    al, al
0x180002ff2  jnz     short loc_180003064
0x180002ff4  lea     rdi, [rbx+20h]
0x180002ff8  mov     rcx, rdi; SRWLock
0x180002ffb  call    cs:__imp_AcquireSRWLockExclusive
0x180003001  cmp     byte ptr [rbx+41h], 0
0x180003005  jnz     short loc_180003055
0x180003007  lea     rsi, [rbx+30h]
0x18000300b  cmp     qword ptr [rsi], 0
0x18000300f  jnz     short loc_180003043
0x180003011  lea     rcx, [rsp+48h+arg_0]; this
0x180003016  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000301b  xor     r8d, r8d; pcbe
0x18000301e  mov     rdx, rbx; pv
0x180003021  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180003028  call    cs:__imp_CreateThreadpoolTimer
0x18000302e  mov     rdx, rax
0x180003031  mov     rcx, rsi
0x180003034  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180003039  lea     rcx, [rsp+48h+arg_0]; this
0x18000303e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180003043  mov     r8d, 493E0h
0x180003049  lea     rdx, [rbx+41h]
0x18000304d  mov     rcx, rsi
0x180003050  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180003055  test    rdi, rdi
0x180003058  jz      short loc_180003064
0x18000305a  mov     rcx, rdi; SRWLock
0x18000305d  call    cs:__imp_ReleaseSRWLockExclusive
0x180003063  nop
0x180003064  add     rsp, 28h
0x180003068  pop     rdi
0x180003069  pop     rsi
0x18000306a  pop     rbp
0x18000306b  pop     rbx
0x18000306c  retn
```
