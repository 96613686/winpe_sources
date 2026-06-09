# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001f934`
- end: `0x18001fa02`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `206`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800208b0`

## callees

- `0x1800155f0`
- `0x180015800`
- `0x1800162bc`
- `0x18001ab44`
- `0x18001f890`
- `0x18001f934`
- `0x180027180`
- `0x1800272a8`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18001f9c4`
- `KERNEL32!CreateThreadpoolTimer` at `0x18001f9c4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001f966`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001f966`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int Ptr; // eax
  unsigned __int64 v8; // r8
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD Source[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v11; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v12; // [rsp+30h] [rbp-28h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v12 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        Source[0] = a2;
        Source[1] = 0;
        v11 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], Source, v8);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)Source);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)Source);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3]);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x18001f934  mov     [rsp+arg_18], rbx
0x18001f939  push    rbp
0x18001f93a  push    rsi
0x18001f93b  push    rdi
0x18001f93c  sub     rsp, 40h
0x18001f940  mov     eax, [rcx]
0x18001f942  mov     rbp, r8
0x18001f945  mov     esi, edx
0x18001f947  mov     rdi, rcx
0x18001f94a  test    eax, eax
0x18001f94c  jz      loc_18001F9F5
0x18001f952  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001f957  test    al, al
0x18001f959  jnz     loc_18001F9F5
0x18001f95f  lea     rbx, [rdi+8]
0x18001f963  mov     rcx, rbx; SRWLock
0x18001f966  call    cs:__imp_AcquireSRWLockExclusive
0x18001f96c  mov     eax, [rdi]
0x18001f96e  mov     [rsp+58h+var_28], rbx
0x18001f973  test    eax, eax
0x18001f975  jz      short loc_18001F9EB
0x18001f977  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001f97c  test    al, al
0x18001f97e  jnz     short loc_18001F9EB
0x18001f980  xor     eax, eax
0x18001f982  mov     [rsp+58h+Source], esi
0x18001f986  lea     rcx, [rdi+20h]; this
0x18001f98a  mov     [rsp+58h+var_34], eax
0x18001f98e  lea     rdx, [rsp+58h+Source]; Source
0x18001f993  mov     [rsp+58h+var_30], rbp
0x18001f998  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001f99d  cmp     byte ptr [rdi+18h], 0
0x18001f9a1  jnz     short loc_18001F9EB
0x18001f9a3  lea     rbx, [rdi+10h]
0x18001f9a7  cmp     qword ptr [rbx], 0
0x18001f9ab  jnz     short loc_18001F9DF
0x18001f9ad  lea     rcx, [rsp+58h+Source]; this
0x18001f9b2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001f9b7  xor     r8d, r8d; pcbe
0x18001f9ba  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001f9c1  mov     rdx, rdi; pv
0x18001f9c4  call    cs:__imp_CreateThreadpoolTimer
0x18001f9ca  mov     rdx, rax
0x18001f9cd  mov     rcx, rbx
0x18001f9d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001f9d5  lea     rcx, [rsp+58h+Source]; this
0x18001f9da  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001f9df  lea     rdx, [rdi+18h]
0x18001f9e3  mov     rcx, rbx
0x18001f9e6  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001f9eb  lea     rcx, [rsp+58h+var_28]
0x18001f9f0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001f9f5  mov     rbx, [rsp+58h+arg_18]
0x18001f9fa  add     rsp, 40h
0x18001f9fe  pop     rdi
0x18001f9ff  pop     rsi
0x18001fa00  pop     rbp
0x18001fa01  retn
```
