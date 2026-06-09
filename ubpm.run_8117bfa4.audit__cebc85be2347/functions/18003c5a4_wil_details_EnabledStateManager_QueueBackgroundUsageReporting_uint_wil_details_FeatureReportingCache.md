# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18003c5a4`
- end: `0x18003c68d`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `233`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180032674`

## callees

- `0x180031fd4`
- `0x180031ff8`
- `0x180032040`
- `0x180032064`
- `0x180032090`
- `0x1800321c4`
- `0x18003c5a4`
- `0x18003e1fc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003c642`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003c642`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003c5d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003c5d6`

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
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[6], v9, 0x10u);
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
0x18003c5a4  mov     [rsp+arg_8], rbx
0x18003c5a9  push    rbp
0x18003c5aa  push    rsi
0x18003c5ab  push    rdi
0x18003c5ac  sub     rsp, 30h
0x18003c5b0  mov     eax, [rcx]
0x18003c5b2  mov     rsi, r8
0x18003c5b5  mov     ebp, edx
0x18003c5b7  mov     rdi, rcx
0x18003c5ba  test    eax, eax
0x18003c5bc  jz      loc_18003C67F
0x18003c5c2  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003c5c7  test    al, al
0x18003c5c9  jnz     loc_18003C67F
0x18003c5cf  lea     rbx, [rdi+8]
0x18003c5d3  mov     rcx, rbx; SRWLock
0x18003c5d6  call    cs:__imp_AcquireSRWLockExclusive
0x18003c5dd  nop     dword ptr [rax+rax+00h]
0x18003c5e2  mov     eax, [rdi]
0x18003c5e4  mov     [rsp+48h+arg_18], rbx
0x18003c5e9  test    eax, eax
0x18003c5eb  jz      loc_18003C675
0x18003c5f1  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003c5f6  test    al, al
0x18003c5f8  jnz     short loc_18003C675
0x18003c5fa  xor     eax, eax
0x18003c5fc  mov     [rsp+48h+var_28], ebp
0x18003c600  lea     rcx, [rdi+30h]; this
0x18003c604  mov     [rsp+48h+var_24], eax
0x18003c608  lea     rdx, [rsp+48h+var_28]; void *
0x18003c60d  mov     [rsp+48h+var_20], rsi
0x18003c612  lea     r8d, [rax+10h]; unsigned __int64
0x18003c616  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003c61b  cmp     byte ptr [rdi+18h], 0
0x18003c61f  jnz     short loc_18003C675
0x18003c621  lea     rbx, [rdi+10h]
0x18003c625  cmp     qword ptr [rbx], 0
0x18003c629  jnz     short loc_18003C663
0x18003c62b  lea     rcx, [rsp+48h+arg_0]; this
0x18003c630  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003c635  xor     r8d, r8d; pcbe
0x18003c638  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003c63f  mov     rdx, rdi; pv
0x18003c642  call    cs:__imp_CreateThreadpoolTimer
0x18003c649  nop     dword ptr [rax+rax+00h]
0x18003c64e  mov     rdx, rax
0x18003c651  mov     rcx, rbx
0x18003c654  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003c659  lea     rcx, [rsp+48h+arg_0]; this
0x18003c65e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003c663  mov     r8d, 493E0h
0x18003c669  lea     rdx, [rdi+18h]
0x18003c66d  mov     rcx, rbx
0x18003c670  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003c675  lea     rcx, [rsp+48h+arg_18]
0x18003c67a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003c67f  mov     rbx, [rsp+48h+arg_8]
0x18003c684  add     rsp, 30h
0x18003c688  pop     rdi
0x18003c689  pop     rsi
0x18003c68a  pop     rbp
0x18003c68b  retn
```
