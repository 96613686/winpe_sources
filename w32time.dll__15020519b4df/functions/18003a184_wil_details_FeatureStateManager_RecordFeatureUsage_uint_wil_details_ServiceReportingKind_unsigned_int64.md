# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18003a184`
- end: `0x18003a251`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180048450`

## callees

- `0x1800345fc`
- `0x18003a184`
- `0x18003a258`
- `0x18003a280`
- `0x18003a2c8`
- `0x18003a2f0`
- `0x18003a320`
- `0x18003cbf8`
- `0x180042448`
- `0x180044e74`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003a207`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003a207`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v10[7]; // [rsp+20h] [rbp-38h] BYREF
  char v11; // [rsp+60h] [rbp+8h] BYREF

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(*((_QWORD *)a1 + 3), a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    wil::srwlock::lock_exclusive((RTL_SRWLOCK *)a1 + 4, v10);
    if ( !a1[65] )
    {
      if ( !*((_QWORD *)a1 + 6) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          a1 + 48,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)a1 + 6, a1 + 65, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v10);
  }
}

```

## disassembly

```asm
0x18003a184  push    rbx
0x18003a186  push    rbp
0x18003a187  push    rsi
0x18003a188  push    rdi
0x18003a189  sub     rsp, 38h
0x18003a18d  mov     rdi, r9
0x18003a190  mov     esi, r8d
0x18003a193  mov     ebp, edx
0x18003a195  mov     rbx, rcx
0x18003a198  cmp     byte ptr [rcx], 0
0x18003a19b  jz      loc_18003A247
0x18003a1a1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18003a1a6  test    al, al
0x18003a1a8  jz      loc_18003A247
0x18003a1ae  mov     r9, rdi
0x18003a1b1  mov     r8d, esi
0x18003a1b4  mov     edx, ebp
0x18003a1b6  mov     rcx, [rbx+18h]
0x18003a1ba  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18003a1bf  test    al, al
0x18003a1c1  jz      loc_18003A247
0x18003a1c7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003a1cc  test    al, al
0x18003a1ce  jnz     short loc_18003A247
0x18003a1d0  lea     rcx, [rbx+20h]
0x18003a1d4  lea     rdx, [rsp+58h+var_38]
0x18003a1d9  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x18003a1de  nop
0x18003a1df  cmp     byte ptr [rbx+41h], 0
0x18003a1e3  jnz     short loc_18003A23C
0x18003a1e5  lea     rdi, [rbx+30h]
0x18003a1e9  cmp     qword ptr [rdi], 0
0x18003a1ed  jnz     short loc_18003A229
0x18003a1ef  lea     rcx, [rsp+58h+arg_0]; this
0x18003a1f4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003a1f9  nop
0x18003a1fa  xor     r8d, r8d; pcbe
0x18003a1fd  mov     rdx, rbx; pv
0x18003a200  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003a207  call    cs:__imp_CreateThreadpoolTimer
0x18003a20e  nop     dword ptr [rax+rax+00h]
0x18003a213  mov     rdx, rax
0x18003a216  mov     rcx, rdi
0x18003a219  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003a21e  nop
0x18003a21f  lea     rcx, [rsp+58h+arg_0]; this
0x18003a224  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003a229  mov     r8d, 493E0h
0x18003a22f  lea     rdx, [rbx+41h]
0x18003a233  mov     rcx, rdi
0x18003a236  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003a23b  nop
0x18003a23c  lea     rcx, [rsp+58h+var_38]
0x18003a241  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003a246  nop
0x18003a247  add     rsp, 38h
0x18003a24b  pop     rdi
0x18003a24c  pop     rsi
0x18003a24d  pop     rbp
0x18003a24e  pop     rbx
0x18003a24f  retn
```
