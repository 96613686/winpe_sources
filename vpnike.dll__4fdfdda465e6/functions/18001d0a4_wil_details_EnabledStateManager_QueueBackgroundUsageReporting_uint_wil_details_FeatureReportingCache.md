# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001d0a4`
- end: `0x18001d17d`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(char *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001de80`

## callees

- `0x180015f64`
- `0x1800161e0`
- `0x180016660`
- `0x180017c54`
- `0x18001bcd8`
- `0x18001d0a4`
- `0x1800204fc`
- `0x180020608`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d138`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d138`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d0d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d0d6`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v11 = (RTL_SRWLOCK *)(pv + 8);
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
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18001d0a4  mov     [rsp+arg_8], rbx
0x18001d0a9  push    rbp
0x18001d0aa  push    rsi
0x18001d0ab  push    rdi
0x18001d0ac  sub     rsp, 30h
0x18001d0b0  mov     rsi, r8
0x18001d0b3  mov     ebp, edx
0x18001d0b5  mov     rdi, rcx
0x18001d0b8  mov     eax, [rcx]
0x18001d0ba  test    eax, eax
0x18001d0bc  jz      loc_18001D170
0x18001d0c2  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001d0c7  test    al, al
0x18001d0c9  jnz     loc_18001D170
0x18001d0cf  lea     rbx, [rdi+8]
0x18001d0d3  mov     rcx, rbx; SRWLock
0x18001d0d6  call    cs:__imp_AcquireSRWLockExclusive
0x18001d0dc  mov     [rsp+48h+arg_18], rbx
0x18001d0e1  mov     eax, [rdi]
0x18001d0e3  test    eax, eax
0x18001d0e5  jz      short loc_18001D165
0x18001d0e7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001d0ec  test    al, al
0x18001d0ee  jnz     short loc_18001D165
0x18001d0f0  mov     [rsp+48h+var_28], ebp
0x18001d0f4  xor     eax, eax
0x18001d0f6  mov     [rsp+48h+var_24], eax
0x18001d0fa  mov     [rsp+48h+var_20], rsi
0x18001d0ff  lea     rcx, [rdi+20h]; this
0x18001d103  lea     r8d, [rax+10h]; unsigned __int64
0x18001d107  lea     rdx, [rsp+48h+var_28]; void *
0x18001d10c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001d111  cmp     byte ptr [rdi+18h], 0
0x18001d115  jnz     short loc_18001D165
0x18001d117  lea     rbx, [rdi+10h]
0x18001d11b  cmp     qword ptr [rbx], 0
0x18001d11f  jnz     short loc_18001D153
0x18001d121  lea     rcx, [rsp+48h+arg_0]; this
0x18001d126  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001d12b  xor     r8d, r8d; pcbe
0x18001d12e  mov     rdx, rdi; pv
0x18001d131  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001d138  call    cs:__imp_CreateThreadpoolTimer
0x18001d13e  mov     rdx, rax
0x18001d141  mov     rcx, rbx
0x18001d144  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001d149  lea     rcx, [rsp+48h+arg_0]; this
0x18001d14e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001d153  mov     r8d, 493E0h
0x18001d159  lea     rdx, [rdi+18h]
0x18001d15d  mov     rcx, rbx
0x18001d160  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001d165  lea     rcx, [rsp+48h+arg_18]
0x18001d16a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d16f  nop
0x18001d170  mov     rbx, [rsp+48h+arg_8]
0x18001d175  add     rsp, 30h
0x18001d179  pop     rdi
0x18001d17a  pop     rsi
0x18001d17b  pop     rbp
0x18001d17c  retn
```
