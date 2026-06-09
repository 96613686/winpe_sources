# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180040e38`
- end: `0x180040f10`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180042540`

## callees

- `0x180037624`
- `0x180037644`
- `0x180037688`
- `0x1800376a8`
- `0x1800376cc`
- `0x1800377f4`
- `0x180040e38`
- `0x1800444f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040e6a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040e6a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180040ecc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180040ecc`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int v7; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-20h]
  char v11; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v7 = *(_DWORD *)pv;
    v12 = (RTL_SRWLOCK *)(pv + 8);
    if ( v7 )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v9[0] = a2;
        v9[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), v9, 0x10u);
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
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x180040e38  mov     [rsp+arg_8], rbx
0x180040e3d  push    rbp
0x180040e3e  push    rsi
0x180040e3f  push    rdi
0x180040e40  sub     rsp, 30h
0x180040e44  mov     eax, [rcx]
0x180040e46  mov     rsi, r8
0x180040e49  mov     ebp, edx
0x180040e4b  mov     rdi, rcx
0x180040e4e  test    eax, eax
0x180040e50  jz      loc_180040F03
0x180040e56  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180040e5b  test    al, al
0x180040e5d  jnz     loc_180040F03
0x180040e63  lea     rbx, [rdi+8]
0x180040e67  mov     rcx, rbx; SRWLock
0x180040e6a  call    cs:__imp_AcquireSRWLockExclusive
0x180040e70  mov     eax, [rdi]
0x180040e72  mov     [rsp+48h+arg_18], rbx
0x180040e77  test    eax, eax
0x180040e79  jz      short loc_180040EF9
0x180040e7b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180040e80  test    al, al
0x180040e82  jnz     short loc_180040EF9
0x180040e84  xor     eax, eax
0x180040e86  mov     [rsp+48h+var_28], ebp
0x180040e8a  lea     rcx, [rdi+20h]; this
0x180040e8e  mov     [rsp+48h+var_24], eax
0x180040e92  lea     rdx, [rsp+48h+var_28]; void *
0x180040e97  mov     [rsp+48h+var_20], rsi
0x180040e9c  lea     r8d, [rax+10h]; unsigned __int64
0x180040ea0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180040ea5  cmp     byte ptr [rdi+18h], 0
0x180040ea9  jnz     short loc_180040EF9
0x180040eab  lea     rbx, [rdi+10h]
0x180040eaf  cmp     qword ptr [rbx], 0
0x180040eb3  jnz     short loc_180040EE7
0x180040eb5  lea     rcx, [rsp+48h+arg_0]; this
0x180040eba  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180040ebf  xor     r8d, r8d; pcbe
0x180040ec2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180040ec9  mov     rdx, rdi; pv
0x180040ecc  call    cs:__imp_CreateThreadpoolTimer
0x180040ed2  mov     rdx, rax
0x180040ed5  mov     rcx, rbx
0x180040ed8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180040edd  lea     rcx, [rsp+48h+arg_0]; this
0x180040ee2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180040ee7  mov     r8d, 493E0h
0x180040eed  lea     rdx, [rdi+18h]
0x180040ef1  mov     rcx, rbx
0x180040ef4  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180040ef9  lea     rcx, [rsp+48h+arg_18]
0x180040efe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180040f03  mov     rbx, [rsp+48h+arg_8]
0x180040f08  add     rsp, 30h
0x180040f0c  pop     rdi
0x180040f0d  pop     rsi
0x180040f0e  pop     rbp
0x180040f0f  retn
```
