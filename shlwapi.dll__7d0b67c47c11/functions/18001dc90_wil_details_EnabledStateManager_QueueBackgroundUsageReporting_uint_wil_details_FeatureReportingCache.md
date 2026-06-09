# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001dc90`
- end: `0x18001dd68`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001e094`

## callees

- `0x1800093b0`
- `0x18000ad10`
- `0x180011714`
- `0x180015cb4`
- `0x180015e20`
- `0x18001a144`
- `0x18001c850`
- `0x18001dc90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001dcc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001dcc2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001dd24`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001dd24`

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
0x18001dc90  mov     [rsp+arg_18], rbx
0x18001dc95  push    rbp
0x18001dc96  push    rsi
0x18001dc97  push    rdi
0x18001dc98  sub     rsp, 40h
0x18001dc9c  mov     eax, [rcx]
0x18001dc9e  mov     rbp, r8
0x18001dca1  mov     esi, edx
0x18001dca3  mov     rdi, rcx
0x18001dca6  test    eax, eax
0x18001dca8  jz      loc_18001DD5B
0x18001dcae  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001dcb3  test    al, al
0x18001dcb5  jnz     loc_18001DD5B
0x18001dcbb  lea     rbx, [rdi+8]
0x18001dcbf  mov     rcx, rbx; SRWLock
0x18001dcc2  call    cs:__imp_AcquireSRWLockExclusive
0x18001dcc8  mov     eax, [rdi]
0x18001dcca  mov     [rsp+58h+var_28], rbx
0x18001dccf  test    eax, eax
0x18001dcd1  jz      short loc_18001DD51
0x18001dcd3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001dcd8  test    al, al
0x18001dcda  jnz     short loc_18001DD51
0x18001dcdc  xor     eax, eax
0x18001dcde  mov     [rsp+58h+var_38], esi
0x18001dce2  lea     rcx, [rdi+20h]; this
0x18001dce6  mov     [rsp+58h+var_34], eax
0x18001dcea  lea     rdx, [rsp+58h+var_38]; void *
0x18001dcef  mov     [rsp+58h+var_30], rbp
0x18001dcf4  lea     r8d, [rax+10h]; unsigned __int64
0x18001dcf8  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001dcfd  cmp     byte ptr [rdi+18h], 0
0x18001dd01  jnz     short loc_18001DD51
0x18001dd03  lea     rbx, [rdi+10h]
0x18001dd07  cmp     qword ptr [rbx], 0
0x18001dd0b  jnz     short loc_18001DD3F
0x18001dd0d  lea     rcx, [rsp+58h+var_38]; this
0x18001dd12  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001dd17  xor     r8d, r8d; pcbe
0x18001dd1a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001dd21  mov     rdx, rdi; pv
0x18001dd24  call    cs:__imp_CreateThreadpoolTimer
0x18001dd2a  mov     rdx, rax
0x18001dd2d  mov     rcx, rbx
0x18001dd30  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001dd35  lea     rcx, [rsp+58h+var_38]; this
0x18001dd3a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001dd3f  mov     r8d, 493E0h
0x18001dd45  lea     rdx, [rdi+18h]
0x18001dd49  mov     rcx, rbx
0x18001dd4c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001dd51  lea     rcx, [rsp+58h+var_28]
0x18001dd56  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001dd5b  mov     rbx, [rsp+58h+arg_18]
0x18001dd60  add     rsp, 40h
0x18001dd64  pop     rdi
0x18001dd65  pop     rsi
0x18001dd66  pop     rbp
0x18001dd67  retn
```
