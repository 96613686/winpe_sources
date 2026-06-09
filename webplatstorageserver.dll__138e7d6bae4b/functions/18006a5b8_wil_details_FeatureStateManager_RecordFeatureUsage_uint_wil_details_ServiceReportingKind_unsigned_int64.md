# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18006a5b8`
- end: `0x18006a690`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18008be90`

## callees

- `0x1800568c0`
- `0x1800572fc`
- `0x180057fc0`
- `0x18006a5b8`
- `0x18006a698`
- `0x18006a6f8`
- `0x18006a94c`
- `0x18008ab78`
- `0x18008b588`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006a67c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006a67c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006a645`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006a645`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  PSRWLOCK SRWLock; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v11[32]; // [rsp+28h] [rbp-20h] BYREF

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(*((_QWORD *)a1 + 3), a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    SRWLock = 0;
    wil::AcquireSRWLockExclusive(&SRWLock, a1 + 32);
    if ( !a1[65] )
    {
      if ( !*((_QWORD *)a1 + 6) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          a1 + 48,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v11);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(a1 + 48, a1 + 65, 300000);
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
  }
}

```

## disassembly

```asm
0x18006a5b8  mov     [rsp+arg_18], rbx
0x18006a5bd  push    rbp
0x18006a5be  push    rsi
0x18006a5bf  push    rdi
0x18006a5c0  sub     rsp, 30h
0x18006a5c4  mov     rdi, r9
0x18006a5c7  mov     ebp, r8d
0x18006a5ca  mov     esi, edx
0x18006a5cc  mov     rbx, rcx
0x18006a5cf  cmp     byte ptr [rcx], 0
0x18006a5d2  jz      loc_18006A683
0x18006a5d8  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18006a5dd  test    al, al
0x18006a5df  jz      loc_18006A683
0x18006a5e5  mov     r9, rdi
0x18006a5e8  mov     r8d, ebp
0x18006a5eb  mov     edx, esi
0x18006a5ed  mov     rcx, [rbx+18h]
0x18006a5f1  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18006a5f6  test    al, al
0x18006a5f8  jz      loc_18006A683
0x18006a5fe  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18006a603  test    al, al
0x18006a605  jnz     short loc_18006A683
0x18006a607  mov     [rsp+48h+SRWLock], 0
0x18006a610  lea     rdx, [rbx+20h]
0x18006a614  lea     rcx, [rsp+48h+SRWLock]
0x18006a619  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18006a61e  cmp     byte ptr [rbx+41h], 0
0x18006a622  jnz     short loc_18006A672
0x18006a624  lea     rdi, [rbx+30h]
0x18006a628  cmp     qword ptr [rdi], 0
0x18006a62c  jnz     short loc_18006A660
0x18006a62e  lea     rcx, [rsp+48h+var_20]; this
0x18006a633  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18006a638  xor     r8d, r8d; pcbe
0x18006a63b  mov     rdx, rbx; pv
0x18006a63e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18006a645  call    cs:__imp_CreateThreadpoolTimer
0x18006a64b  mov     rdx, rax
0x18006a64e  mov     rcx, rdi
0x18006a651  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18006a656  lea     rcx, [rsp+48h+var_20]; this
0x18006a65b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006a660  mov     r8d, 493E0h
0x18006a666  lea     rdx, [rbx+41h]
0x18006a66a  mov     rcx, rdi
0x18006a66d  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18006a672  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x18006a677  test    rcx, rcx
0x18006a67a  jz      short loc_18006A683
0x18006a67c  call    cs:__imp_ReleaseSRWLockExclusive
0x18006a682  nop
0x18006a683  mov     rbx, [rsp+48h+arg_18]
0x18006a688  add     rsp, 30h
0x18006a68c  pop     rdi
0x18006a68d  pop     rsi
0x18006a68e  pop     rbp
0x18006a68f  retn
```
