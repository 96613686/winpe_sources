# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1800195b8`
- end: `0x180019605`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `77`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180015d4c`
- `0x180015dfc`
- `0x180017904`
- `0x1800179c8`
- `0x180017ac0`
- `0x180017ec8`

## callees

- `0x18001136c`
- `0x1800114c4`
- `0x180016234`
- `0x1800195b8`

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
0x1800195b8  mov     [rsp+arg_8], rbx
0x1800195bd  mov     [rsp+arg_10], rsi
0x1800195c2  push    rdi
0x1800195c3  sub     rsp, 20h
0x1800195c7  mov     rdi, [rcx]
0x1800195ca  mov     rsi, rdx
0x1800195cd  mov     rbx, rcx
0x1800195d0  test    rdi, rdi
0x1800195d3  jz      short loc_1800195F1
0x1800195d5  lea     rcx, [rsp+28h+arg_0]; this
0x1800195da  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800195df  mov     rcx, rdi; pti
0x1800195e2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800195e7  lea     rcx, [rsp+28h+arg_0]; this
0x1800195ec  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800195f1  mov     [rbx], rsi
0x1800195f4  mov     rbx, [rsp+28h+arg_8]
0x1800195f9  mov     rsi, [rsp+28h+arg_10]
0x1800195fe  add     rsp, 20h
0x180019602  pop     rdi
0x180019603  retn
```
