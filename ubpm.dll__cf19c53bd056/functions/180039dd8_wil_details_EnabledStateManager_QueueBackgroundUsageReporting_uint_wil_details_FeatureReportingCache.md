# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180039dd8`
- end: `0x180039eb0`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800303a4`

## callees

- `0x18002fd38`
- `0x18002fd58`
- `0x18002fd9c`
- `0x18002fdbc`
- `0x18002fde0`
- `0x18002ff08`
- `0x180039dd8`
- `0x18003b94c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180039e6c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180039e6c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039e0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039e0a`

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
  _DWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-20h]
  char v11; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v12 = pv + 1;
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
            wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x180039dd8  mov     [rsp+arg_8], rbx
0x180039ddd  push    rbp
0x180039dde  push    rsi
0x180039ddf  push    rdi
0x180039de0  sub     rsp, 30h
0x180039de4  mov     eax, [rcx]
0x180039de6  mov     rsi, r8
0x180039de9  mov     ebp, edx
0x180039deb  mov     rdi, rcx
0x180039dee  test    eax, eax
0x180039df0  jz      loc_180039EA3
0x180039df6  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180039dfb  test    al, al
0x180039dfd  jnz     loc_180039EA3
0x180039e03  lea     rbx, [rdi+8]
0x180039e07  mov     rcx, rbx; SRWLock
0x180039e0a  call    cs:__imp_AcquireSRWLockExclusive
0x180039e10  mov     eax, [rdi]
0x180039e12  mov     [rsp+48h+arg_18], rbx
0x180039e17  test    eax, eax
0x180039e19  jz      short loc_180039E99
0x180039e1b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180039e20  test    al, al
0x180039e22  jnz     short loc_180039E99
0x180039e24  xor     eax, eax
0x180039e26  mov     [rsp+48h+var_28], ebp
0x180039e2a  lea     rcx, [rdi+20h]; this
0x180039e2e  mov     [rsp+48h+var_24], eax
0x180039e32  lea     rdx, [rsp+48h+var_28]; void *
0x180039e37  mov     [rsp+48h+var_20], rsi
0x180039e3c  lea     r8d, [rax+10h]; unsigned __int64
0x180039e40  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180039e45  cmp     byte ptr [rdi+18h], 0
0x180039e49  jnz     short loc_180039E99
0x180039e4b  lea     rbx, [rdi+10h]
0x180039e4f  cmp     qword ptr [rbx], 0
0x180039e53  jnz     short loc_180039E87
0x180039e55  lea     rcx, [rsp+48h+arg_0]; this
0x180039e5a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180039e5f  xor     r8d, r8d; pcbe
0x180039e62  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180039e69  mov     rdx, rdi; pv
0x180039e6c  call    cs:__imp_CreateThreadpoolTimer
0x180039e72  mov     rdx, rax
0x180039e75  mov     rcx, rbx
0x180039e78  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180039e7d  lea     rcx, [rsp+48h+arg_0]; this
0x180039e82  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180039e87  mov     r8d, 493E0h
0x180039e8d  lea     rdx, [rdi+18h]
0x180039e91  mov     rcx, rbx
0x180039e94  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180039e99  lea     rcx, [rsp+48h+arg_18]
0x180039e9e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180039ea3  mov     rbx, [rsp+48h+arg_8]
0x180039ea8  add     rsp, 30h
0x180039eac  pop     rdi
0x180039ead  pop     rsi
0x180039eae  pop     rbp
0x180039eaf  retn
```
