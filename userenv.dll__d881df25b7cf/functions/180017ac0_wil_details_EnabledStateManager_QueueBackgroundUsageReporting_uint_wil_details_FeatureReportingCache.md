# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180017ac0`
- end: `0x180017baa`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180018854`

## callees

- `0x18000ddcc`
- `0x18001136c`
- `0x1800114c4`
- `0x18001205c`
- `0x180016280`
- `0x180017ac0`
- `0x1800194ac`
- `0x1800195b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017af2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017af2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017b5e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017b5e`

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
0x180017ac0  mov     [rsp+arg_8], rbx
0x180017ac5  push    rbp
0x180017ac6  push    rsi
0x180017ac7  push    rdi
0x180017ac8  sub     rsp, 30h
0x180017acc  mov     rsi, r8
0x180017acf  mov     ebp, edx
0x180017ad1  mov     rdi, rcx
0x180017ad4  mov     eax, [rcx]
0x180017ad6  test    eax, eax
0x180017ad8  jz      loc_180017B9C
0x180017ade  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180017ae3  test    al, al
0x180017ae5  jnz     loc_180017B9C
0x180017aeb  lea     rbx, [rdi+8]
0x180017aef  mov     rcx, rbx; SRWLock
0x180017af2  call    cs:__imp_AcquireSRWLockExclusive
0x180017af9  nop     dword ptr [rax+rax+00h]
0x180017afe  mov     [rsp+48h+arg_18], rbx
0x180017b03  mov     eax, [rdi]
0x180017b05  test    eax, eax
0x180017b07  jz      loc_180017B91
0x180017b0d  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180017b12  test    al, al
0x180017b14  jnz     short loc_180017B91
0x180017b16  mov     [rsp+48h+var_28], ebp
0x180017b1a  xor     eax, eax
0x180017b1c  mov     [rsp+48h+var_24], eax
0x180017b20  mov     [rsp+48h+var_20], rsi
0x180017b25  lea     rcx, [rdi+30h]; this
0x180017b29  lea     r8d, [rax+10h]; unsigned __int64
0x180017b2d  lea     rdx, [rsp+48h+var_28]; void *
0x180017b32  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180017b37  cmp     byte ptr [rdi+18h], 0
0x180017b3b  jnz     short loc_180017B91
0x180017b3d  lea     rbx, [rdi+10h]
0x180017b41  cmp     qword ptr [rbx], 0
0x180017b45  jnz     short loc_180017B7F
0x180017b47  lea     rcx, [rsp+48h+arg_0]; this
0x180017b4c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180017b51  xor     r8d, r8d; pcbe
0x180017b54  mov     rdx, rdi; pv
0x180017b57  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180017b5e  call    cs:__imp_CreateThreadpoolTimer
0x180017b65  nop     dword ptr [rax+rax+00h]
0x180017b6a  mov     rdx, rax
0x180017b6d  mov     rcx, rbx
0x180017b70  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180017b75  lea     rcx, [rsp+48h+arg_0]; this
0x180017b7a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180017b7f  mov     r8d, 493E0h
0x180017b85  lea     rdx, [rdi+18h]
0x180017b89  mov     rcx, rbx
0x180017b8c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180017b91  lea     rcx, [rsp+48h+arg_18]
0x180017b96  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017b9b  nop
0x180017b9c  mov     rbx, [rsp+48h+arg_8]
0x180017ba1  add     rsp, 30h
0x180017ba5  pop     rdi
0x180017ba6  pop     rsi
0x180017ba7  pop     rbp
0x180017ba8  retn
```
