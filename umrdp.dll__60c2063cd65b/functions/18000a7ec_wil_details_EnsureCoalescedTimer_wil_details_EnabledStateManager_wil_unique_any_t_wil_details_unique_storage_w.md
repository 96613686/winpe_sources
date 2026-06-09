# wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)

- ea: `0x18000a7ec`
- end: `0x18000a87f`
- name: `??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012484`

## callees

- `0x18000a7ec`
- `0x18000a888`
- `0x18000a8a8`
- `0x18000a8cc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a826`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a826`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a866`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a866`

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
0x18000a7ec  mov     [rsp+arg_0], rbx
0x18000a7f1  mov     [rsp+arg_10], rsi
0x18000a7f6  push    rdi
0x18000a7f7  sub     rsp, 20h
0x18000a7fb  cmp     byte ptr [rdx], 0
0x18000a7fe  mov     rsi, r8
0x18000a801  mov     rdi, rdx
0x18000a804  mov     rbx, rcx
0x18000a807  jnz     short loc_18000A86F
0x18000a809  cmp     qword ptr [rcx], 0
0x18000a80d  jnz     short loc_18000A841
0x18000a80f  lea     rcx, [rsp+28h+pftDueTime]; this
0x18000a814  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000a819  xor     r8d, r8d; pcbe
0x18000a81c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a823  mov     rdx, rsi; pv
0x18000a826  call    cs:__imp_CreateThreadpoolTimer
0x18000a82c  mov     rdx, rax
0x18000a82f  mov     rcx, rbx
0x18000a832  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000a837  lea     rcx, [rsp+28h+pftDueTime]; this
0x18000a83c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000a841  mov     rcx, [rbx]; pti
0x18000a844  test    rcx, rcx
0x18000a847  jz      short loc_18000A86F
0x18000a849  mov     rax, 0FFFFFFFF4D2FA200h
0x18000a853  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000a858  mov     r9d, 124F8h; msWindowLength
0x18000a85e  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000a863  xor     r8d, r8d; msPeriod
0x18000a866  call    cs:__imp_SetThreadpoolTimer
0x18000a86c  mov     byte ptr [rdi], 1
0x18000a86f  mov     rbx, [rsp+28h+arg_0]
0x18000a874  mov     rsi, [rsp+28h+arg_10]
0x18000a879  add     rsp, 20h
0x18000a87d  pop     rdi
0x18000a87e  retn
```
