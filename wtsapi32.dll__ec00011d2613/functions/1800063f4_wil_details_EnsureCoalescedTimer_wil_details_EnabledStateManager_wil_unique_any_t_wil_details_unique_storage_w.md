# wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)

- ea: `0x1800063f4`
- end: `0x180006487`
- name: `??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010e28`

## callees

- `0x1800063f4`
- `0x180006490`
- `0x1800064b0`
- `0x1800064d4`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18000642e`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000642e`
- `KERNEL32!SetThreadpoolTimer` at `0x18000646e`
- `KERNEL32!SetThreadpoolTimer` at `0x18000646e`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(
        struct _TP_TIMER **a1,
        _BYTE *a2,
        void *a3)
{
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v7; // rcx
  _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a2 )
  {
    if ( !*a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&pftDueTime);
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_, a3, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        a1,
        ThreadpoolTimer);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&pftDueTime);
    }
    v7 = *a1;
    if ( *a1 )
    {
      pftDueTime = (_FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *a2 = 1;
    }
  }
}

```

## disassembly

```asm
0x1800063f4  mov     [rsp+arg_0], rbx
0x1800063f9  mov     [rsp+arg_10], rsi
0x1800063fe  push    rdi
0x1800063ff  sub     rsp, 20h
0x180006403  cmp     byte ptr [rdx], 0
0x180006406  mov     rsi, r8
0x180006409  mov     rdi, rdx
0x18000640c  mov     rbx, rcx
0x18000640f  jnz     short loc_180006477
0x180006411  cmp     qword ptr [rcx], 0
0x180006415  jnz     short loc_180006449
0x180006417  lea     rcx, [rsp+28h+pftDueTime]; this
0x18000641c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180006421  xor     r8d, r8d; pcbe
0x180006424  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000642b  mov     rdx, rsi; pv
0x18000642e  call    cs:__imp_CreateThreadpoolTimer
0x180006434  mov     rdx, rax
0x180006437  mov     rcx, rbx
0x18000643a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000643f  lea     rcx, [rsp+28h+pftDueTime]; this
0x180006444  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180006449  mov     rcx, [rbx]; pti
0x18000644c  test    rcx, rcx
0x18000644f  jz      short loc_180006477
0x180006451  mov     rax, 0FFFFFFFF4D2FA200h
0x18000645b  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180006460  mov     r9d, 124F8h; msWindowLength
0x180006466  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000646b  xor     r8d, r8d; msPeriod
0x18000646e  call    cs:__imp_SetThreadpoolTimer
0x180006474  mov     byte ptr [rdi], 1
0x180006477  mov     rbx, [rsp+28h+arg_0]
0x18000647c  mov     rsi, [rsp+28h+arg_10]
0x180006481  add     rsp, 20h
0x180006485  pop     rdi
0x180006486  retn
```
