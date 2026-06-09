# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1800272a8`
- end: `0x1800272f4`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016214`
- `0x18001f820`
- `0x18001f934`

## callees

- `0x1800155f0`
- `0x1800162bc`
- `0x18001ab08`
- `0x1800272a8`

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
0x1800272a8  mov     [rsp+arg_8], rbx
0x1800272ad  mov     [rsp+arg_10], rsi
0x1800272b2  push    rdi
0x1800272b3  sub     rsp, 20h
0x1800272b7  mov     rdi, [rcx]
0x1800272ba  mov     rsi, rdx
0x1800272bd  mov     rbx, rcx
0x1800272c0  test    rdi, rdi
0x1800272c3  jz      short loc_1800272E1
0x1800272c5  lea     rcx, [rsp+28h+arg_0]; this
0x1800272ca  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800272cf  mov     rcx, rdi; pti
0x1800272d2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800272d7  lea     rcx, [rsp+28h+arg_0]; this
0x1800272dc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800272e1  mov     [rbx], rsi
0x1800272e4  mov     rbx, [rsp+28h+arg_8]
0x1800272e9  mov     rsi, [rsp+28h+arg_10]
0x1800272ee  add     rsp, 20h
0x1800272f2  pop     rdi
0x1800272f3  retn
```
