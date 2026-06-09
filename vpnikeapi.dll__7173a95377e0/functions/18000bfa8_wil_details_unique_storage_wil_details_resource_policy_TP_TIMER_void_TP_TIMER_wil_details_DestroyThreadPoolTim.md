# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000bfa8`
- end: `0x18000bff4`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007c20`
- `0x180007cd0`
- `0x180009fb8`
- `0x18000a0a4`
- `0x18000a4dc`

## callees

- `0x1800078cc`
- `0x180007e30`
- `0x180008390`
- `0x18000bfa8`

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
0x18000bfa8  mov     [rsp+arg_8], rbx
0x18000bfad  mov     [rsp+arg_10], rsi
0x18000bfb2  push    rdi
0x18000bfb3  sub     rsp, 20h
0x18000bfb7  mov     rdi, [rcx]
0x18000bfba  mov     rsi, rdx
0x18000bfbd  mov     rbx, rcx
0x18000bfc0  test    rdi, rdi
0x18000bfc3  jz      short loc_18000BFE1
0x18000bfc5  lea     rcx, [rsp+28h+arg_0]; this
0x18000bfca  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000bfcf  mov     rcx, rdi; pti
0x18000bfd2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000bfd7  lea     rcx, [rsp+28h+arg_0]; this
0x18000bfdc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000bfe1  mov     [rbx], rsi
0x18000bfe4  mov     rbx, [rsp+28h+arg_8]
0x18000bfe9  mov     rsi, [rsp+28h+arg_10]
0x18000bfee  add     rsp, 20h
0x18000bff2  pop     rdi
0x18000bff3  retn
```
