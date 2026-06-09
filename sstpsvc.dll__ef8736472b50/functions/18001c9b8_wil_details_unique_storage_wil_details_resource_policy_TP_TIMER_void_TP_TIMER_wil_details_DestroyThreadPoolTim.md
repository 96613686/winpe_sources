# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18001c9b8`
- end: `0x18001ca05`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018898`
- `0x18001ab7c`
- `0x18001af74`

## callees

- `0x180018570`
- `0x180018a00`
- `0x180019024`
- `0x18001c9b8`

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
0x18001c9b8  mov     [rsp+arg_8], rbx
0x18001c9bd  mov     [rsp+arg_10], rsi
0x18001c9c2  push    rdi
0x18001c9c3  sub     rsp, 20h
0x18001c9c7  mov     rdi, [rcx]
0x18001c9ca  mov     rsi, rdx
0x18001c9cd  mov     rbx, rcx
0x18001c9d0  test    rdi, rdi
0x18001c9d3  jz      short loc_18001C9F1
0x18001c9d5  lea     rcx, [rsp+28h+arg_0]; this
0x18001c9da  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001c9df  mov     rcx, rdi; pti
0x18001c9e2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18001c9e7  lea     rcx, [rsp+28h+arg_0]; this
0x18001c9ec  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001c9f1  mov     [rbx], rsi
0x18001c9f4  mov     rbx, [rsp+28h+arg_8]
0x18001c9f9  mov     rsi, [rsp+28h+arg_10]
0x18001c9fe  add     rsp, 20h
0x18001ca02  pop     rdi
0x18001ca03  retn
```
