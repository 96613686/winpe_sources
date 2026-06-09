# wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)

- ea: `0x180020e98`
- end: `0x180020f38`
- name: `??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800101c8`

## callees

- `0x1800118f8`
- `0x180015040`
- `0x180020e98`
- `0x180020f40`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020f18`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180020f18`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020ed2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020ed2`

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
0x180020e98  mov     [rsp+arg_0], rbx
0x180020e9d  mov     [rsp+arg_10], rsi
0x180020ea2  push    rdi
0x180020ea3  sub     rsp, 20h
0x180020ea7  cmp     byte ptr [rdx], 0
0x180020eaa  mov     rsi, r8
0x180020ead  mov     rdi, rdx
0x180020eb0  mov     rbx, rcx
0x180020eb3  jnz     short loc_180020F27
0x180020eb5  cmp     qword ptr [rcx], 0
0x180020eb9  jnz     short loc_180020EF3
0x180020ebb  lea     rcx, [rsp+28h+pftDueTime]; this
0x180020ec0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180020ec5  xor     r8d, r8d; pcbe
0x180020ec8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180020ecf  mov     rdx, rsi; pv
0x180020ed2  call    cs:__imp_CreateThreadpoolTimer
0x180020ed9  nop     dword ptr [rax+rax+00h]
0x180020ede  mov     rdx, rax
0x180020ee1  mov     rcx, rbx
0x180020ee4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180020ee9  lea     rcx, [rsp+28h+pftDueTime]; this
0x180020eee  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180020ef3  mov     rcx, [rbx]; pti
0x180020ef6  test    rcx, rcx
0x180020ef9  jz      short loc_180020F27
0x180020efb  mov     rax, 0FFFFFFFF4D2FA200h
0x180020f05  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180020f0a  mov     r9d, 124F8h; msWindowLength
0x180020f10  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180020f15  xor     r8d, r8d; msPeriod
0x180020f18  call    cs:__imp_SetThreadpoolTimer
0x180020f1f  nop     dword ptr [rax+rax+00h]
0x180020f24  mov     byte ptr [rdi], 1
0x180020f27  mov     rbx, [rsp+28h+arg_0]
0x180020f2c  mov     rsi, [rsp+28h+arg_10]
0x180020f31  add     rsp, 20h
0x180020f35  pop     rdi
0x180020f36  retn
```
