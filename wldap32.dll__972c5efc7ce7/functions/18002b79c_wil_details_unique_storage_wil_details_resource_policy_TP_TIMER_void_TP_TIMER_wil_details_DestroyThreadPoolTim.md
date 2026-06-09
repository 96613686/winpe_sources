# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18002b79c`
- end: `0x18002b7eb`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180033134`
- `0x18003322c`

## callees

- `0x18002b79c`
- `0x180033304`
- `0x180033370`
- `0x180036654`

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
0x18002b79c  mov     [rsp+arg_8], rbx
0x18002b7a1  mov     [rsp+arg_10], rsi
0x18002b7a6  push    rdi
0x18002b7a7  sub     rsp, 20h
0x18002b7ab  mov     rdi, [rcx]
0x18002b7ae  mov     rsi, rdx
0x18002b7b1  mov     rbx, rcx
0x18002b7b4  test    rdi, rdi
0x18002b7b7  jnz     short loc_18002B7CD
0x18002b7b9  mov     [rbx], rsi
0x18002b7bc  mov     rbx, [rsp+28h+arg_8]
0x18002b7c1  mov     rsi, [rsp+28h+arg_10]
0x18002b7c6  add     rsp, 20h
0x18002b7ca  pop     rdi
0x18002b7cb  retn
0x18002b7cd  lea     rcx, [rsp+28h+arg_0]; this
0x18002b7d2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002b7d7  mov     rcx, rdi; pti
0x18002b7da  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18002b7df  lea     rcx, [rsp+28h+arg_0]; this
0x18002b7e4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002b7e9  jmp     short loc_18002B7B9
```
