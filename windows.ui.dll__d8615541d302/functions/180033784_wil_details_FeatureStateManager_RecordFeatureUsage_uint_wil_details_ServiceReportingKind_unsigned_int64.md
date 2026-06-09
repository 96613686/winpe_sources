# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180033784`
- end: `0x180033845`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18004ca90`

## callees

- `0x180033610`
- `0x180033634`
- `0x180033784`
- `0x180033c24`
- `0x180034790`
- `0x1800348cc`
- `0x1800349c4`
- `0x180034b28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033835`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033835`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800337d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800337d3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180033800`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180033800`

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
0x180033784  push    rbx
0x180033786  push    rbp
0x180033787  push    rsi
0x180033788  push    rdi
0x180033789  sub     rsp, 28h
0x18003378d  mov     rdi, r9
0x180033790  mov     esi, r8d
0x180033793  mov     ebp, edx
0x180033795  mov     rbx, rcx
0x180033798  cmp     byte ptr [rcx], 0
0x18003379b  jz      loc_18003383C
0x1800337a1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800337a6  test    al, al
0x1800337a8  jz      loc_18003383C
0x1800337ae  mov     r9, rdi
0x1800337b1  mov     r8d, esi
0x1800337b4  mov     edx, ebp
0x1800337b6  mov     rcx, [rbx+18h]
0x1800337ba  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800337bf  test    al, al
0x1800337c1  jz      short loc_18003383C
0x1800337c3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800337c8  test    al, al
0x1800337ca  jnz     short loc_18003383C
0x1800337cc  lea     rdi, [rbx+20h]
0x1800337d0  mov     rcx, rdi; SRWLock
0x1800337d3  call    cs:__imp_AcquireSRWLockExclusive
0x1800337d9  cmp     byte ptr [rbx+41h], 0
0x1800337dd  jnz     short loc_18003382D
0x1800337df  lea     rsi, [rbx+30h]
0x1800337e3  cmp     qword ptr [rsi], 0
0x1800337e7  jnz     short loc_18003381B
0x1800337e9  lea     rcx, [rsp+48h+arg_0]; this
0x1800337ee  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800337f3  xor     r8d, r8d; pcbe
0x1800337f6  mov     rdx, rbx; pv
0x1800337f9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180033800  call    cs:__imp_CreateThreadpoolTimer
0x180033806  mov     rdx, rax
0x180033809  mov     rcx, rsi
0x18003380c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180033811  lea     rcx, [rsp+48h+arg_0]; this
0x180033816  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003381b  mov     r8d, 493E0h
0x180033821  lea     rdx, [rbx+41h]
0x180033825  mov     rcx, rsi
0x180033828  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003382d  test    rdi, rdi
0x180033830  jz      short loc_18003383C
0x180033832  mov     rcx, rdi; SRWLock
0x180033835  call    cs:__imp_ReleaseSRWLockExclusive
0x18003383b  nop
0x18003383c  add     rsp, 28h
0x180033840  pop     rdi
0x180033841  pop     rsi
0x180033842  pop     rbp
0x180033843  pop     rbx
0x180033844  retn
```
