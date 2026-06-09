# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001b944`
- end: `0x18001ba32`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001c9a0`

## callees

- `0x180002610`
- `0x18000594c`
- `0x180005cb8`
- `0x180005e50`
- `0x180008bc0`
- `0x18001b178`
- `0x18001b944`
- `0x18001cc80`
- `0x18001cd88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b987`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b987`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b9e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b9e3`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-58h] BYREF
  RTL_SRWLOCK *v10; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v10 = (RTL_SRWLOCK *)(pv + 40);
    v13 = 0;
    v11 = a2;
    v12 = a3;
    v14 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v11, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18001b944  push    rbx
0x18001b946  push    rbp
0x18001b947  push    rsi
0x18001b948  push    rdi
0x18001b949  push    r14
0x18001b94b  sub     rsp, 50h
0x18001b94f  mov     rax, cs:__security_cookie
0x18001b956  xor     rax, rsp
0x18001b959  mov     [rsp+78h+var_38], rax
0x18001b95e  cmp     byte ptr [rcx], 0
0x18001b961  mov     r14d, r9d
0x18001b964  movzx   ebp, r8w
0x18001b968  mov     esi, edx
0x18001b96a  mov     rdi, rcx
0x18001b96d  jz      loc_18001BA1A
0x18001b973  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001b978  test    al, al
0x18001b97a  jnz     loc_18001BA1A
0x18001b980  lea     rbx, [rdi+28h]
0x18001b984  mov     rcx, rbx; SRWLock
0x18001b987  call    cs:__imp_AcquireSRWLockExclusive
0x18001b98d  xor     eax, eax
0x18001b98f  mov     [rsp+78h+var_50], rbx
0x18001b994  lea     rcx, [rdi+0E8h]; this
0x18001b99b  mov     [rsp+78h+var_42], ax
0x18001b9a0  lea     rdx, [rsp+78h+var_48]; void *
0x18001b9a5  mov     [rsp+78h+var_48], esi
0x18001b9a9  mov     [rsp+78h+var_44], bp
0x18001b9ae  lea     r8d, [rax+0Ch]; unsigned __int64
0x18001b9b2  mov     [rsp+78h+var_40], r14d
0x18001b9b7  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001b9bc  cmp     byte ptr [rdi+40h], 0
0x18001b9c0  jnz     short loc_18001BA10
0x18001b9c2  lea     rbx, [rdi+38h]
0x18001b9c6  cmp     qword ptr [rbx], 0
0x18001b9ca  jnz     short loc_18001B9FE
0x18001b9cc  lea     rcx, [rsp+78h+var_58]; this
0x18001b9d1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001b9d6  xor     r8d, r8d; pcbe
0x18001b9d9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001b9e0  mov     rdx, rdi; pv
0x18001b9e3  call    cs:__imp_CreateThreadpoolTimer
0x18001b9e9  mov     rdx, rax
0x18001b9ec  mov     rcx, rbx
0x18001b9ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001b9f4  lea     rcx, [rsp+78h+var_58]; this
0x18001b9f9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001b9fe  mov     r8d, 1388h
0x18001ba04  lea     rdx, [rdi+40h]
0x18001ba08  mov     rcx, rbx
0x18001ba0b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001ba10  lea     rcx, [rsp+78h+var_50]
0x18001ba15  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001ba1a  mov     rcx, [rsp+78h+var_38]
0x18001ba1f  xor     rcx, rsp; StackCookie
0x18001ba22  call    __security_check_cookie
0x18001ba27  add     rsp, 50h
0x18001ba2b  pop     r14
0x18001ba2d  pop     rdi
0x18001ba2e  pop     rsi
0x18001ba2f  pop     rbp
0x18001ba30  pop     rbx
0x18001ba31  retn
```
