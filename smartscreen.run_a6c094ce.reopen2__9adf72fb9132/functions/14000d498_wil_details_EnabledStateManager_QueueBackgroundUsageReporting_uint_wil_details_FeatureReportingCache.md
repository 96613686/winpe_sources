# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14000d498`
- end: `0x14000d577`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `223`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000d22c`

## callees

- `0x140001b14`
- `0x14000cb90`
- `0x14000cbc0`
- `0x14000d498`
- `0x140011968`
- `0x140011d38`
- `0x14001d9f4`
- `0x14001e9fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d4cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d4cb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000d52e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000d52e`

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
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[6], v8, v6);
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
0x14000d498  mov     [rsp+arg_8], rbx
0x14000d49d  mov     [rsp+arg_10], rsi
0x14000d4a2  push    rdi
0x14000d4a3  sub     rsp, 40h
0x14000d4a7  mov     rsi, r8
0x14000d4aa  mov     rdi, rcx
0x14000d4ad  mov     eax, [rcx]
0x14000d4af  test    eax, eax
0x14000d4b1  jz      loc_14000D566
0x14000d4b7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000d4bc  test    al, al
0x14000d4be  jnz     loc_14000D566
0x14000d4c4  lea     rbx, [rdi+8]
0x14000d4c8  mov     rcx, rbx; SRWLock
0x14000d4cb  call    cs:__imp_AcquireSRWLockExclusive
0x14000d4d2  nop     dword ptr [rax+rax+00h]
0x14000d4d7  mov     [rsp+48h+var_18], rbx
0x14000d4dc  mov     eax, [rdi]
0x14000d4de  test    eax, eax
0x14000d4e0  jz      short loc_14000D55B
0x14000d4e2  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000d4e7  test    al, al
0x14000d4e9  jnz     short loc_14000D55B
0x14000d4eb  mov     [rsp+48h+var_28], 248C1B2h
0x14000d4f4  mov     [rsp+48h+var_20], rsi
0x14000d4f9  lea     rcx, [rdi+30h]; this
0x14000d4fd  lea     rdx, [rsp+48h+var_28]; void *
0x14000d502  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000d507  cmp     byte ptr [rdi+18h], 0
0x14000d50b  jnz     short loc_14000D55B
0x14000d50d  lea     rbx, [rdi+10h]
0x14000d511  cmp     qword ptr [rbx], 0
0x14000d515  jnz     short loc_14000D54F
0x14000d517  lea     rcx, [rsp+48h+var_28]; this
0x14000d51c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000d521  xor     r8d, r8d; pcbe
0x14000d524  mov     rdx, rdi; pv
0x14000d527  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000d52e  call    cs:__imp_CreateThreadpoolTimer
0x14000d535  nop     dword ptr [rax+rax+00h]
0x14000d53a  mov     rdx, rax
0x14000d53d  mov     rcx, rbx
0x14000d540  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000d545  lea     rcx, [rsp+48h+var_28]; this
0x14000d54a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000d54f  lea     rdx, [rdi+18h]
0x14000d553  mov     rcx, rbx
0x14000d556  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14000d55b  lea     rcx, [rsp+48h+var_18]
0x14000d560  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000d565  nop
0x14000d566  mov     rbx, [rsp+48h+arg_8]
0x14000d56b  mov     rsi, [rsp+48h+arg_10]
0x14000d570  add     rsp, 40h
0x14000d574  pop     rdi
0x14000d575  retn
```
