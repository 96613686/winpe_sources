# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14000cde8`
- end: `0x14000ceba`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `210`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000cb7c`

## callees

- `0x140001a8c`
- `0x14000c498`
- `0x14000c4c0`
- `0x14000cde8`
- `0x14001106c`
- `0x14001152c`
- `0x14001ca90`
- `0x14001da94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ce1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ce1b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000ce78`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000ce78`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  unsigned __int64 v6; // r8
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  RTL_SRWLOCK *v9; // [rsp+30h] [rbp-18h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v9 = pv + 1;
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v5) )
      {
        v8[0] = 38322610;
        v8[1] = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v8, v6);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)v8);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v8);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3]);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x14000cde8  mov     [rsp+arg_8], rbx
0x14000cded  mov     [rsp+arg_10], rsi
0x14000cdf2  push    rdi
0x14000cdf3  sub     rsp, 40h
0x14000cdf7  mov     rsi, r8
0x14000cdfa  mov     rdi, rcx
0x14000cdfd  mov     eax, [rcx]
0x14000cdff  test    eax, eax
0x14000ce01  jz      loc_14000CEAA
0x14000ce07  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000ce0c  test    al, al
0x14000ce0e  jnz     loc_14000CEAA
0x14000ce14  lea     rbx, [rdi+8]
0x14000ce18  mov     rcx, rbx; SRWLock
0x14000ce1b  call    cs:__imp_AcquireSRWLockExclusive
0x14000ce21  mov     [rsp+48h+var_18], rbx
0x14000ce26  mov     eax, [rdi]
0x14000ce28  test    eax, eax
0x14000ce2a  jz      short loc_14000CE9F
0x14000ce2c  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000ce31  test    al, al
0x14000ce33  jnz     short loc_14000CE9F
0x14000ce35  mov     [rsp+48h+var_28], 248C1B2h
0x14000ce3e  mov     [rsp+48h+var_20], rsi
0x14000ce43  lea     rcx, [rdi+20h]; this
0x14000ce47  lea     rdx, [rsp+48h+var_28]; void *
0x14000ce4c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000ce51  cmp     byte ptr [rdi+18h], 0
0x14000ce55  jnz     short loc_14000CE9F
0x14000ce57  lea     rbx, [rdi+10h]
0x14000ce5b  cmp     qword ptr [rbx], 0
0x14000ce5f  jnz     short loc_14000CE93
0x14000ce61  lea     rcx, [rsp+48h+var_28]; this
0x14000ce66  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000ce6b  xor     r8d, r8d; pcbe
0x14000ce6e  mov     rdx, rdi; pv
0x14000ce71  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000ce78  call    cs:__imp_CreateThreadpoolTimer
0x14000ce7e  mov     rdx, rax
0x14000ce81  mov     rcx, rbx
0x14000ce84  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000ce89  lea     rcx, [rsp+48h+var_28]; this
0x14000ce8e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000ce93  lea     rdx, [rdi+18h]
0x14000ce97  mov     rcx, rbx
0x14000ce9a  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14000ce9f  lea     rcx, [rsp+48h+var_18]
0x14000cea4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000cea9  nop
0x14000ceaa  mov     rbx, [rsp+48h+arg_8]
0x14000ceaf  mov     rsi, [rsp+48h+arg_10]
0x14000ceb4  add     rsp, 40h
0x14000ceb8  pop     rdi
0x14000ceb9  retn
```
