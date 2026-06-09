# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180041370`
- end: `0x180041449`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800422f0`

## callees

- `0x18000a7b8`
- `0x18000aadc`
- `0x18000c0f4`
- `0x180021174`
- `0x180023328`
- `0x18002ef3c`
- `0x18002f044`
- `0x180041370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800413a2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800413a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180041404`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180041404`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rax
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
              (struct _TP_TIMER **)pv + 2,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(pv + 16, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x180041370  mov     [rsp+arg_8], rbx
0x180041375  push    rbp
0x180041376  push    rsi
0x180041377  push    rdi
0x180041378  sub     rsp, 30h
0x18004137c  mov     rsi, r8
0x18004137f  mov     ebp, edx
0x180041381  mov     rdi, rcx
0x180041384  mov     eax, [rcx]
0x180041386  test    eax, eax
0x180041388  jz      loc_18004143C
0x18004138e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180041393  test    al, al
0x180041395  jnz     loc_18004143C
0x18004139b  lea     rbx, [rdi+8]
0x18004139f  mov     rcx, rbx; SRWLock
0x1800413a2  call    cs:__imp_AcquireSRWLockExclusive
0x1800413a8  mov     [rsp+48h+arg_18], rbx
0x1800413ad  mov     eax, [rdi]
0x1800413af  test    eax, eax
0x1800413b1  jz      short loc_180041431
0x1800413b3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800413b8  test    al, al
0x1800413ba  jnz     short loc_180041431
0x1800413bc  mov     [rsp+48h+var_28], ebp
0x1800413c0  xor     eax, eax
0x1800413c2  mov     [rsp+48h+var_24], eax
0x1800413c6  mov     [rsp+48h+var_20], rsi
0x1800413cb  lea     rcx, [rdi+20h]; this
0x1800413cf  lea     r8d, [rax+10h]; unsigned __int64
0x1800413d3  lea     rdx, [rsp+48h+var_28]; void *
0x1800413d8  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800413dd  cmp     byte ptr [rdi+18h], 0
0x1800413e1  jnz     short loc_180041431
0x1800413e3  lea     rbx, [rdi+10h]
0x1800413e7  cmp     qword ptr [rbx], 0
0x1800413eb  jnz     short loc_18004141F
0x1800413ed  lea     rcx, [rsp+48h+arg_0]; this
0x1800413f2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800413f7  xor     r8d, r8d; pcbe
0x1800413fa  mov     rdx, rdi; pv
0x1800413fd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180041404  call    cs:__imp_CreateThreadpoolTimer
0x18004140a  mov     rdx, rax
0x18004140d  mov     rcx, rbx
0x180041410  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180041415  lea     rcx, [rsp+48h+arg_0]; this
0x18004141a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004141f  mov     r8d, 493E0h
0x180041425  lea     rdx, [rdi+18h]
0x180041429  mov     rcx, rbx
0x18004142c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180041431  lea     rcx, [rsp+48h+arg_18]
0x180041436  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004143b  nop
0x18004143c  mov     rbx, [rsp+48h+arg_8]
0x180041441  add     rsp, 30h
0x180041445  pop     rdi
0x180041446  pop     rsi
0x180041447  pop     rbp
0x180041448  retn
```
