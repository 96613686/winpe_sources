# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140016874`
- end: `0x14001695e`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140016ca8`

## callees

- `0x1400045a0`
- `0x14000483c`
- `0x140004ba4`
- `0x140005358`
- `0x140007274`
- `0x140009b7c`
- `0x140009c88`
- `0x140016874`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1400168a6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400168a6`
- `KERNEL32!CreateThreadpoolTimer` at `0x140016912`
- `KERNEL32!CreateThreadpoolTimer` at `0x140016912`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v11 = pv + 1;
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[6], v8, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
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
0x140016874  mov     [rsp+arg_8], rbx
0x140016879  push    rbp
0x14001687a  push    rsi
0x14001687b  push    rdi
0x14001687c  sub     rsp, 30h
0x140016880  mov     rsi, r8
0x140016883  mov     ebp, edx
0x140016885  mov     rdi, rcx
0x140016888  mov     eax, [rcx]
0x14001688a  test    eax, eax
0x14001688c  jz      loc_140016950
0x140016892  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140016897  test    al, al
0x140016899  jnz     loc_140016950
0x14001689f  lea     rbx, [rdi+8]
0x1400168a3  mov     rcx, rbx; SRWLock
0x1400168a6  call    cs:__imp_AcquireSRWLockExclusive
0x1400168ad  nop     dword ptr [rax+rax+00h]
0x1400168b2  mov     [rsp+48h+arg_18], rbx
0x1400168b7  mov     eax, [rdi]
0x1400168b9  test    eax, eax
0x1400168bb  jz      loc_140016945
0x1400168c1  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1400168c6  test    al, al
0x1400168c8  jnz     short loc_140016945
0x1400168ca  mov     [rsp+48h+var_28], ebp
0x1400168ce  xor     eax, eax
0x1400168d0  mov     [rsp+48h+var_24], eax
0x1400168d4  mov     [rsp+48h+var_20], rsi
0x1400168d9  lea     rcx, [rdi+30h]; this
0x1400168dd  lea     r8d, [rax+10h]; unsigned __int64
0x1400168e1  lea     rdx, [rsp+48h+var_28]; void *
0x1400168e6  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1400168eb  cmp     byte ptr [rdi+18h], 0
0x1400168ef  jnz     short loc_140016945
0x1400168f1  lea     rbx, [rdi+10h]
0x1400168f5  cmp     qword ptr [rbx], 0
0x1400168f9  jnz     short loc_140016933
0x1400168fb  lea     rcx, [rsp+48h+arg_0]; this
0x140016900  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140016905  xor     r8d, r8d; pcbe
0x140016908  mov     rdx, rdi; pv
0x14001690b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140016912  call    cs:__imp_CreateThreadpoolTimer
0x140016919  nop     dword ptr [rax+rax+00h]
0x14001691e  mov     rdx, rax
0x140016921  mov     rcx, rbx
0x140016924  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140016929  lea     rcx, [rsp+48h+arg_0]; this
0x14001692e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140016933  mov     r8d, 493E0h
0x140016939  lea     rdx, [rdi+18h]
0x14001693d  mov     rcx, rbx
0x140016940  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140016945  lea     rcx, [rsp+48h+arg_18]
0x14001694a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14001694f  nop
0x140016950  mov     rbx, [rsp+48h+arg_8]
0x140016955  add     rsp, 30h
0x140016959  pop     rdi
0x14001695a  pop     rsi
0x14001695b  pop     rbp
0x14001695c  retn
```
