# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000a4dc`
- end: `0x18000a59d`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: `void __fastcall(_BYTE *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18000b8c0`

## callees

- `0x1800078cc`
- `0x180007b44`
- `0x180007e30`
- `0x1800083f4`
- `0x180008438`
- `0x18000a070`
- `0x18000a434`
- `0x18000a4dc`
- `0x18000bfa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a52b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a52b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a55d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a55d`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  wil *v8; // rcx
  bool v9; // zf
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v11; // [rsp+20h] [rbp-38h] BYREF
  char v12; // [rsp+60h] [rbp+8h] BYREF

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)a1)
    && wil::details_abi::FeatureStateData::RecordFeatureUsage(
         *((wil::details_abi::FeatureStateData **)a1 + 3),
         a2,
         a3,
         a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
    v9 = a1[65] == 0;
    v11 = (RTL_SRWLOCK *)(a1 + 32);
    if ( v9 )
    {
      if ( !*((_QWORD *)a1 + 6) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          a1 + 48,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)a1 + 6, a1 + 65, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18000a4dc  push    rbx
0x18000a4de  push    rbp
0x18000a4df  push    rsi
0x18000a4e0  push    rdi
0x18000a4e1  sub     rsp, 38h
0x18000a4e5  cmp     byte ptr [rcx], 0
0x18000a4e8  mov     rbx, r9
0x18000a4eb  mov     esi, r8d
0x18000a4ee  mov     ebp, edx
0x18000a4f0  mov     rdi, rcx
0x18000a4f3  jz      loc_18000A594
0x18000a4f9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000a4fe  test    al, al
0x18000a500  jz      loc_18000A594
0x18000a506  mov     rcx, [rdi+18h]
0x18000a50a  mov     r9, rbx
0x18000a50d  mov     r8d, esi
0x18000a510  mov     edx, ebp
0x18000a512  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000a517  test    al, al
0x18000a519  jz      short loc_18000A594
0x18000a51b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000a520  test    al, al
0x18000a522  jnz     short loc_18000A594
0x18000a524  lea     rbx, [rdi+20h]
0x18000a528  mov     rcx, rbx; SRWLock
0x18000a52b  call    cs:__imp_AcquireSRWLockExclusive
0x18000a531  cmp     byte ptr [rdi+41h], 0
0x18000a535  mov     [rsp+58h+var_38], rbx
0x18000a53a  jnz     short loc_18000A58A
0x18000a53c  lea     rbx, [rdi+30h]
0x18000a540  cmp     qword ptr [rbx], 0
0x18000a544  jnz     short loc_18000A578
0x18000a546  lea     rcx, [rsp+58h+arg_0]; this
0x18000a54b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000a550  xor     r8d, r8d; pcbe
0x18000a553  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a55a  mov     rdx, rdi; pv
0x18000a55d  call    cs:__imp_CreateThreadpoolTimer
0x18000a563  mov     rdx, rax
0x18000a566  mov     rcx, rbx
0x18000a569  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000a56e  lea     rcx, [rsp+58h+arg_0]; this
0x18000a573  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000a578  mov     r8d, 493E0h
0x18000a57e  lea     rdx, [rdi+41h]
0x18000a582  mov     rcx, rbx
0x18000a585  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000a58a  lea     rcx, [rsp+58h+var_38]
0x18000a58f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a594  add     rsp, 38h
0x18000a598  pop     rdi
0x18000a599  pop     rsi
0x18000a59a  pop     rbp
0x18000a59b  pop     rbx
0x18000a59c  retn
```
