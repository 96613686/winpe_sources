# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18006f4bc`
- end: `0x18006f595`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180089560`

## callees

- `0x18006f4bc`
- `0x18006f59c`
- `0x18006f5c0`
- `0x18006f624`
- `0x18006f648`
- `0x18006f730`
- `0x18006f864`
- `0x180086938`
- `0x1800885e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f512`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f512`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006f54a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006f54a`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  bool v9; // zf
  PTP_TIMER ThreadpoolTimer; // rax
  char v11[8]; // [rsp+20h] [rbp-28h] BYREF
  RTL_SRWLOCK *v12; // [rsp+28h] [rbp-20h] BYREF

  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    v9 = BYTE1(a1[8].Ptr) == 0;
    v12 = a1 + 4;
    if ( v9 )
    {
      if ( !a1[6].Ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v11);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x18006f4bc  mov     [rsp+arg_18], rbx
0x18006f4c1  push    rbp
0x18006f4c2  push    rsi
0x18006f4c3  push    rdi
0x18006f4c4  sub     rsp, 30h
0x18006f4c8  cmp     byte ptr [rcx], 0
0x18006f4cb  mov     rbx, r9
0x18006f4ce  mov     ebp, r8d
0x18006f4d1  mov     esi, edx
0x18006f4d3  mov     rdi, rcx
0x18006f4d6  jz      loc_18006F587
0x18006f4dc  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18006f4e1  test    al, al
0x18006f4e3  jz      loc_18006F587
0x18006f4e9  mov     rcx, [rdi+18h]
0x18006f4ed  mov     r9, rbx
0x18006f4f0  mov     r8d, ebp
0x18006f4f3  mov     edx, esi
0x18006f4f5  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18006f4fa  test    al, al
0x18006f4fc  jz      loc_18006F587
0x18006f502  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18006f507  test    al, al
0x18006f509  jnz     short loc_18006F587
0x18006f50b  lea     rbx, [rdi+20h]
0x18006f50f  mov     rcx, rbx; SRWLock
0x18006f512  call    cs:__imp_AcquireSRWLockExclusive
0x18006f519  nop     dword ptr [rax+rax+00h]
0x18006f51e  cmp     byte ptr [rdi+41h], 0
0x18006f522  mov     [rsp+48h+var_20], rbx
0x18006f527  jnz     short loc_18006F57D
0x18006f529  lea     rbx, [rdi+30h]
0x18006f52d  cmp     qword ptr [rbx], 0
0x18006f531  jnz     short loc_18006F56B
0x18006f533  lea     rcx, [rsp+48h+var_28]; this
0x18006f538  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18006f53d  xor     r8d, r8d; pcbe
0x18006f540  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18006f547  mov     rdx, rdi; pv
0x18006f54a  call    cs:__imp_CreateThreadpoolTimer
0x18006f551  nop     dword ptr [rax+rax+00h]
0x18006f556  mov     rdx, rax
0x18006f559  mov     rcx, rbx
0x18006f55c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18006f561  lea     rcx, [rsp+48h+var_28]; this
0x18006f566  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006f56b  mov     r8d, 493E0h
0x18006f571  lea     rdx, [rdi+41h]
0x18006f575  mov     rcx, rbx
0x18006f578  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18006f57d  lea     rcx, [rsp+48h+var_20]
0x18006f582  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006f587  mov     rbx, [rsp+48h+arg_18]
0x18006f58c  add     rsp, 30h
0x18006f590  pop     rdi
0x18006f591  pop     rsi
0x18006f592  pop     rbp
0x18006f593  retn
```
