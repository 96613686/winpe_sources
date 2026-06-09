# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1800186b0`
- end: `0x1800186fe`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `78`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018304`
- `0x1800183d8`
- `0x1800185b0`
- `0x1800187e8`
- `0x180018868`
- `0x180020330`

## callees

- `0x1800184a0`
- `0x180018524`
- `0x1800186b0`
- `0x18001e2c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v4; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v4 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x1800186b0  mov     [rsp+arg_8], rbx
0x1800186b5  mov     [rsp+arg_10], rsi
0x1800186ba  push    rdi
0x1800186bb  sub     rsp, 20h
0x1800186bf  mov     rsi, rdx
0x1800186c2  mov     rbx, rcx
0x1800186c5  mov     rdi, [rcx]
0x1800186c8  test    rdi, rdi
0x1800186cb  jz      short loc_1800186EB
0x1800186cd  lea     rcx, [rsp+28h+arg_0]; this
0x1800186d2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800186d7  nop
0x1800186d8  mov     rcx, rdi; pti
0x1800186db  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800186e0  nop
0x1800186e1  lea     rcx, [rsp+28h+arg_0]; this
0x1800186e6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800186eb  mov     [rbx], rsi
0x1800186ee  mov     rbx, [rsp+28h+arg_8]
0x1800186f3  mov     rsi, [rsp+28h+arg_10]
0x1800186f8  add     rsp, 20h
0x1800186fc  pop     rdi
0x1800186fd  retn
```
