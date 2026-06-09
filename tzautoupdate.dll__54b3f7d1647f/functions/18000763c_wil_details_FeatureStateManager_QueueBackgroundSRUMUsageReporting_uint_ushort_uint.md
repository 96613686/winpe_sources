# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000763c`
- end: `0x18000772b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `239`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180009a70`

## callees

- `0x1800041ec`
- `0x180004614`
- `0x180004a78`
- `0x1800052b4`
- `0x18000753c`
- `0x18000763c`
- `0x18000b5c0`
- `0x18000b6e0`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000767f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000767f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800076db`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800076db`

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
0x18000763c  push    rbx
0x18000763e  push    rbp
0x18000763f  push    rsi
0x180007640  push    rdi
0x180007641  push    r14
0x180007643  sub     rsp, 50h
0x180007647  mov     rax, cs:__security_cookie
0x18000764e  xor     rax, rsp
0x180007651  mov     [rsp+78h+var_38], rax
0x180007656  mov     r14d, r9d
0x180007659  movzx   ebp, r8w
0x18000765d  mov     esi, edx
0x18000765f  mov     rdi, rcx
0x180007662  cmp     byte ptr [rcx], 0
0x180007665  jz      loc_180007713
0x18000766b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180007670  test    al, al
0x180007672  jnz     loc_180007713
0x180007678  lea     rbx, [rdi+28h]
0x18000767c  mov     rcx, rbx; SRWLock
0x18000767f  call    cs:__imp_AcquireSRWLockExclusive
0x180007685  mov     [rsp+78h+var_50], rbx
0x18000768a  xor     eax, eax
0x18000768c  mov     [rsp+78h+var_42], ax
0x180007691  mov     [rsp+78h+var_48], esi
0x180007695  mov     [rsp+78h+var_44], bp
0x18000769a  mov     [rsp+78h+var_40], r14d
0x18000769f  lea     rcx, [rdi+0E8h]; this
0x1800076a6  lea     r8d, [rax+0Ch]; unsigned __int64
0x1800076aa  lea     rdx, [rsp+78h+var_48]; void *
0x1800076af  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800076b4  cmp     byte ptr [rdi+40h], 0
0x1800076b8  jnz     short loc_180007708
0x1800076ba  lea     rbx, [rdi+38h]
0x1800076be  cmp     qword ptr [rbx], 0
0x1800076c2  jnz     short loc_1800076F6
0x1800076c4  lea     rcx, [rsp+78h+var_58]; this
0x1800076c9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800076ce  xor     r8d, r8d; pcbe
0x1800076d1  mov     rdx, rdi; pv
0x1800076d4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800076db  call    cs:__imp_CreateThreadpoolTimer
0x1800076e1  mov     rdx, rax
0x1800076e4  mov     rcx, rbx
0x1800076e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800076ec  lea     rcx, [rsp+78h+var_58]; this
0x1800076f1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800076f6  mov     r8d, 1388h
0x1800076fc  lea     rdx, [rdi+40h]
0x180007700  mov     rcx, rbx
0x180007703  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180007708  lea     rcx, [rsp+78h+var_50]
0x18000770d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007712  nop
0x180007713  mov     rcx, [rsp+78h+var_38]
0x180007718  xor     rcx, rsp; StackCookie
0x18000771b  call    __security_check_cookie
0x180007720  add     rsp, 50h
0x180007724  pop     r14
0x180007726  pop     rdi
0x180007727  pop     rsi
0x180007728  pop     rbp
0x180007729  pop     rbx
0x18000772a  retn
```
