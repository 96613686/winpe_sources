# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001cfac`
- end: `0x18001d09b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `239`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001fe80`

## callees

- `0x180015f64`
- `0x1800161e0`
- `0x180016660`
- `0x180017c54`
- `0x18001bcd8`
- `0x18001cfac`
- `0x1800204fc`
- `0x180020608`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d04b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d04b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cfef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cfef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001cfac  push    rbx
0x18001cfae  push    rbp
0x18001cfaf  push    rsi
0x18001cfb0  push    rdi
0x18001cfb1  push    r14
0x18001cfb3  sub     rsp, 50h
0x18001cfb7  mov     rax, cs:__security_cookie
0x18001cfbe  xor     rax, rsp
0x18001cfc1  mov     [rsp+78h+var_38], rax
0x18001cfc6  mov     r14d, r9d
0x18001cfc9  movzx   ebp, r8w
0x18001cfcd  mov     esi, edx
0x18001cfcf  mov     rdi, rcx
0x18001cfd2  cmp     byte ptr [rcx], 0
0x18001cfd5  jz      loc_18001D083
0x18001cfdb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001cfe0  test    al, al
0x18001cfe2  jnz     loc_18001D083
0x18001cfe8  lea     rbx, [rdi+28h]
0x18001cfec  mov     rcx, rbx; SRWLock
0x18001cfef  call    cs:__imp_AcquireSRWLockExclusive
0x18001cff5  mov     [rsp+78h+var_50], rbx
0x18001cffa  xor     eax, eax
0x18001cffc  mov     [rsp+78h+var_42], ax
0x18001d001  mov     [rsp+78h+var_48], esi
0x18001d005  mov     [rsp+78h+var_44], bp
0x18001d00a  mov     [rsp+78h+var_40], r14d
0x18001d00f  lea     rcx, [rdi+0E8h]; this
0x18001d016  lea     r8d, [rax+0Ch]; unsigned __int64
0x18001d01a  lea     rdx, [rsp+78h+var_48]; void *
0x18001d01f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001d024  cmp     byte ptr [rdi+40h], 0
0x18001d028  jnz     short loc_18001D078
0x18001d02a  lea     rbx, [rdi+38h]
0x18001d02e  cmp     qword ptr [rbx], 0
0x18001d032  jnz     short loc_18001D066
0x18001d034  lea     rcx, [rsp+78h+var_58]; this
0x18001d039  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001d03e  xor     r8d, r8d; pcbe
0x18001d041  mov     rdx, rdi; pv
0x18001d044  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001d04b  call    cs:__imp_CreateThreadpoolTimer
0x18001d051  mov     rdx, rax
0x18001d054  mov     rcx, rbx
0x18001d057  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001d05c  lea     rcx, [rsp+78h+var_58]; this
0x18001d061  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001d066  mov     r8d, 1388h
0x18001d06c  lea     rdx, [rdi+40h]
0x18001d070  mov     rcx, rbx
0x18001d073  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001d078  lea     rcx, [rsp+78h+var_50]
0x18001d07d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d082  nop
0x18001d083  mov     rcx, [rsp+78h+var_38]
0x18001d088  xor     rcx, rsp; StackCookie
0x18001d08b  call    __security_check_cookie
0x18001d090  add     rsp, 50h
0x18001d094  pop     r14
0x18001d096  pop     rdi
0x18001d097  pop     rsi
0x18001d098  pop     rbp
0x18001d099  pop     rbx
0x18001d09a  retn
```
