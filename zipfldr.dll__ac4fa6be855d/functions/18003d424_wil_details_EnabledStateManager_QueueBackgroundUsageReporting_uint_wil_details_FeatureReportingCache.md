# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18003d424`
- end: `0x18003d4fc`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180029610`

## callees

- `0x18000ac9c`
- `0x180025674`
- `0x180025790`
- `0x1800398bc`
- `0x180039a18`
- `0x18003b558`
- `0x18003d424`
- `0x18003f0c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d456`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d456`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003d4b8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003d4b8`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int Ptr; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v11; // [rsp+30h] [rbp-28h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v11 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v9[0] = a2;
        v9[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v9, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)v9);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18003d424  mov     [rsp+arg_18], rbx
0x18003d429  push    rbp
0x18003d42a  push    rsi
0x18003d42b  push    rdi
0x18003d42c  sub     rsp, 40h
0x18003d430  mov     eax, [rcx]
0x18003d432  mov     rbp, r8
0x18003d435  mov     esi, edx
0x18003d437  mov     rdi, rcx
0x18003d43a  test    eax, eax
0x18003d43c  jz      loc_18003D4EF
0x18003d442  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003d447  test    al, al
0x18003d449  jnz     loc_18003D4EF
0x18003d44f  lea     rbx, [rdi+8]
0x18003d453  mov     rcx, rbx; SRWLock
0x18003d456  call    cs:__imp_AcquireSRWLockExclusive
0x18003d45c  mov     eax, [rdi]
0x18003d45e  mov     [rsp+58h+var_28], rbx
0x18003d463  test    eax, eax
0x18003d465  jz      short loc_18003D4E5
0x18003d467  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003d46c  test    al, al
0x18003d46e  jnz     short loc_18003D4E5
0x18003d470  xor     eax, eax
0x18003d472  mov     [rsp+58h+var_38], esi
0x18003d476  lea     rcx, [rdi+20h]; this
0x18003d47a  mov     [rsp+58h+var_34], eax
0x18003d47e  lea     rdx, [rsp+58h+var_38]; void *
0x18003d483  mov     [rsp+58h+var_30], rbp
0x18003d488  lea     r8d, [rax+10h]; unsigned __int64
0x18003d48c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003d491  cmp     byte ptr [rdi+18h], 0
0x18003d495  jnz     short loc_18003D4E5
0x18003d497  lea     rbx, [rdi+10h]
0x18003d49b  cmp     qword ptr [rbx], 0
0x18003d49f  jnz     short loc_18003D4D3
0x18003d4a1  lea     rcx, [rsp+58h+var_38]; this
0x18003d4a6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003d4ab  xor     r8d, r8d; pcbe
0x18003d4ae  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003d4b5  mov     rdx, rdi; pv
0x18003d4b8  call    cs:__imp_CreateThreadpoolTimer
0x18003d4be  mov     rdx, rax
0x18003d4c1  mov     rcx, rbx
0x18003d4c4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003d4c9  lea     rcx, [rsp+58h+var_38]; this
0x18003d4ce  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003d4d3  mov     r8d, 493E0h
0x18003d4d9  lea     rdx, [rdi+18h]
0x18003d4dd  mov     rcx, rbx
0x18003d4e0  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003d4e5  lea     rcx, [rsp+58h+var_28]
0x18003d4ea  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003d4ef  mov     rbx, [rsp+58h+arg_18]
0x18003d4f4  add     rsp, 40h
0x18003d4f8  pop     rdi
0x18003d4f9  pop     rsi
0x18003d4fa  pop     rbp
0x18003d4fb  retn
```
