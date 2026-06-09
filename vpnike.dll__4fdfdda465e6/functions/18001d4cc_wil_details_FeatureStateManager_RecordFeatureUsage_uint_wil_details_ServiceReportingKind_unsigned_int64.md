# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001d4cc`
- end: `0x18001d58e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `194`
- prototype: `void __fastcall(_BYTE *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18001fe80`

## callees

- `0x180015f64`
- `0x1800161e0`
- `0x180016660`
- `0x180017c54`
- `0x180017c98`
- `0x18001bcd8`
- `0x18001d424`
- `0x18001d4cc`
- `0x180020608`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d54d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d54d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d51b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d51b`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v10; // [rsp+20h] [rbp-38h] BYREF
  char v11; // [rsp+60h] [rbp+8h] BYREF

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && wil::details_abi::FeatureStateData::RecordFeatureUsage(
         *((wil::details_abi::FeatureStateData **)a1 + 3),
         a2,
         a3,
         a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
    v10 = (RTL_SRWLOCK *)(a1 + 32);
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
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18001d4cc  push    rbx
0x18001d4ce  push    rbp
0x18001d4cf  push    rsi
0x18001d4d0  push    rdi
0x18001d4d1  sub     rsp, 38h
0x18001d4d5  mov     rbx, r9
0x18001d4d8  mov     esi, r8d
0x18001d4db  mov     ebp, edx
0x18001d4dd  mov     rdi, rcx
0x18001d4e0  cmp     byte ptr [rcx], 0
0x18001d4e3  jz      loc_18001D585
0x18001d4e9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001d4ee  test    al, al
0x18001d4f0  jz      loc_18001D585
0x18001d4f6  mov     r9, rbx
0x18001d4f9  mov     r8d, esi
0x18001d4fc  mov     edx, ebp
0x18001d4fe  mov     rcx, [rdi+18h]
0x18001d502  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001d507  test    al, al
0x18001d509  jz      short loc_18001D585
0x18001d50b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001d510  test    al, al
0x18001d512  jnz     short loc_18001D585
0x18001d514  lea     rbx, [rdi+20h]
0x18001d518  mov     rcx, rbx; SRWLock
0x18001d51b  call    cs:__imp_AcquireSRWLockExclusive
0x18001d521  mov     [rsp+58h+var_38], rbx
0x18001d526  cmp     byte ptr [rdi+41h], 0
0x18001d52a  jnz     short loc_18001D57A
0x18001d52c  lea     rbx, [rdi+30h]
0x18001d530  cmp     qword ptr [rbx], 0
0x18001d534  jnz     short loc_18001D568
0x18001d536  lea     rcx, [rsp+58h+arg_0]; this
0x18001d53b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001d540  xor     r8d, r8d; pcbe
0x18001d543  mov     rdx, rdi; pv
0x18001d546  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001d54d  call    cs:__imp_CreateThreadpoolTimer
0x18001d553  mov     rdx, rax
0x18001d556  mov     rcx, rbx
0x18001d559  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001d55e  lea     rcx, [rsp+58h+arg_0]; this
0x18001d563  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001d568  mov     r8d, 493E0h
0x18001d56e  lea     rdx, [rdi+41h]
0x18001d572  mov     rcx, rbx
0x18001d575  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001d57a  lea     rcx, [rsp+58h+var_38]
0x18001d57f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d584  nop
0x18001d585  add     rsp, 38h
0x18001d589  pop     rdi
0x18001d58a  pop     rsi
0x18001d58b  pop     rbp
0x18001d58c  pop     rbx
0x18001d58d  retn
```
