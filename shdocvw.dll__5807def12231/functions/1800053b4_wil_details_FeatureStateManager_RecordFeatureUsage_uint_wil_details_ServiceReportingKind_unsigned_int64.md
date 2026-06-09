# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800053b4`
- end: `0x180005475`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1800108b0`

## callees

- `0x180003c60`
- `0x1800042f0`
- `0x1800053b4`
- `0x18000547c`
- `0x180005540`
- `0x180005560`
- `0x180005590`
- `0x18000f5fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005403`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005403`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005465`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005465`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005430`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005430`

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
0x1800053b4  push    rbx
0x1800053b6  push    rbp
0x1800053b7  push    rsi
0x1800053b8  push    rdi
0x1800053b9  sub     rsp, 28h
0x1800053bd  mov     rdi, r9
0x1800053c0  mov     esi, r8d
0x1800053c3  mov     ebp, edx
0x1800053c5  mov     rbx, rcx
0x1800053c8  cmp     byte ptr [rcx], 0
0x1800053cb  jz      loc_18000546C
0x1800053d1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800053d6  test    al, al
0x1800053d8  jz      loc_18000546C
0x1800053de  mov     r9, rdi
0x1800053e1  mov     r8d, esi
0x1800053e4  mov     edx, ebp
0x1800053e6  mov     rcx, [rbx+18h]
0x1800053ea  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800053ef  test    al, al
0x1800053f1  jz      short loc_18000546C
0x1800053f3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800053f8  test    al, al
0x1800053fa  jnz     short loc_18000546C
0x1800053fc  lea     rdi, [rbx+20h]
0x180005400  mov     rcx, rdi; SRWLock
0x180005403  call    cs:__imp_AcquireSRWLockExclusive
0x180005409  cmp     byte ptr [rbx+41h], 0
0x18000540d  jnz     short loc_18000545D
0x18000540f  lea     rsi, [rbx+30h]
0x180005413  cmp     qword ptr [rsi], 0
0x180005417  jnz     short loc_18000544B
0x180005419  lea     rcx, [rsp+48h+arg_0]; this
0x18000541e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180005423  xor     r8d, r8d; pcbe
0x180005426  mov     rdx, rbx; pv
0x180005429  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005430  call    cs:__imp_CreateThreadpoolTimer
0x180005436  mov     rdx, rax
0x180005439  mov     rcx, rsi
0x18000543c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180005441  lea     rcx, [rsp+48h+arg_0]; this
0x180005446  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000544b  mov     r8d, 493E0h
0x180005451  lea     rdx, [rbx+41h]
0x180005455  mov     rcx, rsi
0x180005458  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000545d  test    rdi, rdi
0x180005460  jz      short loc_18000546C
0x180005462  mov     rcx, rdi; SRWLock
0x180005465  call    cs:__imp_ReleaseSRWLockExclusive
0x18000546b  nop
0x18000546c  add     rsp, 28h
0x180005470  pop     rdi
0x180005471  pop     rsi
0x180005472  pop     rbp
0x180005473  pop     rbx
0x180005474  retn
```
