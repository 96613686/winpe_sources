# wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)

- ea: `0x180032c1c`
- end: `0x180032cbc`
- name: `??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180039884`

## callees

- `0x1800015d0`
- `0x180032c1c`
- `0x1800334c4`
- `0x1800338dc`
- `0x18003c188`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x180032c5e`
- `KERNEL32!CreateThreadpoolTimer` at `0x180032c5e`
- `KERNEL32!SetThreadpoolTimer` at `0x180032c9e`
- `KERNEL32!SetThreadpoolTimer` at `0x180032c9e`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(
        struct _TP_TIMER **a1,
        _BYTE *a2,
        void *a3)
{
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

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
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *a2 = 1;
    }
  }
}

```

## disassembly

```asm
0x180032c1c  push    rbx
0x180032c1e  push    rsi
0x180032c1f  push    rdi
0x180032c20  sub     rsp, 30h
0x180032c24  mov     rax, cs:__security_cookie
0x180032c2b  xor     rax, rsp
0x180032c2e  mov     [rsp+48h+var_20], rax
0x180032c33  cmp     byte ptr [rdx], 0
0x180032c36  mov     rsi, r8
0x180032c39  mov     rdi, rdx
0x180032c3c  mov     rbx, rcx
0x180032c3f  jnz     short loc_180032CA7
0x180032c41  cmp     qword ptr [rcx], 0
0x180032c45  jnz     short loc_180032C79
0x180032c47  lea     rcx, [rsp+48h+pftDueTime]; this
0x180032c4c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180032c51  xor     r8d, r8d; pcbe
0x180032c54  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180032c5b  mov     rdx, rsi; pv
0x180032c5e  call    cs:__imp_CreateThreadpoolTimer
0x180032c64  mov     rdx, rax
0x180032c67  mov     rcx, rbx
0x180032c6a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180032c6f  lea     rcx, [rsp+48h+pftDueTime]; this
0x180032c74  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180032c79  mov     rcx, [rbx]; pti
0x180032c7c  test    rcx, rcx
0x180032c7f  jz      short loc_180032CA7
0x180032c81  mov     rax, 0FFFFFFFF4D2FA200h
0x180032c8b  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180032c90  mov     r9d, 124F8h; msWindowLength
0x180032c96  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x180032c9b  xor     r8d, r8d; msPeriod
0x180032c9e  call    cs:__imp_SetThreadpoolTimer
0x180032ca4  mov     byte ptr [rdi], 1
0x180032ca7  mov     rcx, [rsp+48h+var_20]
0x180032cac  xor     rcx, rsp; StackCookie
0x180032caf  call    __security_check_cookie
0x180032cb4  add     rsp, 30h
0x180032cb8  pop     rdi
0x180032cb9  pop     rsi
0x180032cba  pop     rbx
0x180032cbb  retn
```
