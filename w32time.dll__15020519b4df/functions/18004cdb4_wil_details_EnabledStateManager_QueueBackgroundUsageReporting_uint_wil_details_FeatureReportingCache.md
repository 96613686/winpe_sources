# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18004cdb4`
- end: `0x18004cea4`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `240`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18004d024`

## callees

- `0x1800345fc`
- `0x18003a258`
- `0x18003a280`
- `0x18003a2c8`
- `0x18003a2f0`
- `0x18003a320`
- `0x18003cbf8`
- `0x180048ba4`
- `0x18004cdb4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004ce51`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004ce51`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-18h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-10h]
  RTL_SRWLOCK *v10; // [rsp+40h] [rbp+8h] BYREF
  char v11; // [rsp+58h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    wil::srwlock::lock_exclusive((RTL_SRWLOCK *)pv + 1, &v10);
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), v8, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18004cdb4  mov     [rsp+arg_8], rbx
0x18004cdb9  mov     [rsp+arg_10], rsi
0x18004cdbe  push    rdi
0x18004cdbf  sub     rsp, 30h
0x18004cdc3  mov     rdi, r8
0x18004cdc6  mov     esi, edx
0x18004cdc8  mov     rbx, rcx
0x18004cdcb  mov     eax, [rcx]
0x18004cdcd  test    eax, eax
0x18004cdcf  jz      loc_18004CE93
0x18004cdd5  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004cdda  test    al, al
0x18004cddc  jnz     loc_18004CE93
0x18004cde2  lea     rcx, [rbx+8]
0x18004cde6  lea     rdx, [rsp+38h+arg_0]
0x18004cdeb  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x18004cdf0  nop
0x18004cdf1  mov     eax, [rbx]
0x18004cdf3  test    eax, eax
0x18004cdf5  jz      loc_18004CE88
0x18004cdfb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004ce00  test    al, al
0x18004ce02  jnz     loc_18004CE88
0x18004ce08  mov     [rsp+38h+var_18], esi
0x18004ce0c  xor     eax, eax
0x18004ce0e  mov     [rsp+38h+var_14], eax
0x18004ce12  mov     [rsp+38h+var_10], rdi
0x18004ce17  lea     rcx, [rbx+20h]; this
0x18004ce1b  lea     r8d, [rax+10h]; unsigned __int64
0x18004ce1f  lea     rdx, [rsp+38h+var_18]; void *
0x18004ce24  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18004ce29  cmp     byte ptr [rbx+18h], 0
0x18004ce2d  jnz     short loc_18004CE86
0x18004ce2f  lea     rdi, [rbx+10h]
0x18004ce33  cmp     qword ptr [rdi], 0
0x18004ce37  jnz     short loc_18004CE73
0x18004ce39  lea     rcx, [rsp+38h+arg_18]; this
0x18004ce3e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004ce43  nop
0x18004ce44  xor     r8d, r8d; pcbe
0x18004ce47  mov     rdx, rbx; pv
0x18004ce4a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004ce51  call    cs:__imp_CreateThreadpoolTimer
0x18004ce58  nop     dword ptr [rax+rax+00h]
0x18004ce5d  mov     rdx, rax
0x18004ce60  mov     rcx, rdi
0x18004ce63  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18004ce68  nop
0x18004ce69  lea     rcx, [rsp+38h+arg_18]; this
0x18004ce6e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004ce73  mov     r8d, 493E0h
0x18004ce79  lea     rdx, [rbx+18h]
0x18004ce7d  mov     rcx, rdi
0x18004ce80  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18004ce85  nop
0x18004ce86  jmp     short $+2
0x18004ce88  lea     rcx, [rsp+38h+arg_0]
0x18004ce8d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004ce92  nop
0x18004ce93  mov     rbx, [rsp+38h+arg_8]
0x18004ce98  mov     rsi, [rsp+38h+arg_10]
0x18004ce9d  add     rsp, 30h
0x18004cea1  pop     rdi
0x18004cea2  retn
```
