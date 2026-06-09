# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000660c`
- end: `0x18000665a`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `78`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004120`
- `0x1800064a4`
- `0x180006518`
- `0x1800066c8`
- `0x18000af78`
- `0x18000aff4`

## callees

- `0x18000660c`
- `0x18000b188`
- `0x18000b1a8`
- `0x180016d40`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000660c  mov     [rsp+arg_8], rbx
0x180006611  mov     [rsp+arg_10], rsi
0x180006616  push    rdi
0x180006617  sub     rsp, 20h
0x18000661b  mov     rdi, [rcx]
0x18000661e  mov     rsi, rdx
0x180006621  mov     rbx, rcx
0x180006624  test    rdi, rdi
0x180006627  jnz     short loc_18000663C
0x180006629  mov     [rbx], rsi
0x18000662c  mov     rbx, [rsp+28h+arg_8]
0x180006631  mov     rsi, [rsp+28h+arg_10]
0x180006636  add     rsp, 20h
0x18000663a  pop     rdi
0x18000663b  retn
0x18000663c  lea     rcx, [rsp+28h+arg_0]; this
0x180006641  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180006646  mov     rcx, rdi; pti
0x180006649  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000664e  lea     rcx, [rsp+28h+arg_0]; this
0x180006653  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180006658  jmp     short loc_180006629
```
