# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180004658`
- end: `0x1800046a4`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800025b4`
- `0x180003628`
- `0x1800044e8`
- `0x1800065fc`
- `0x180006678`
- `0x18000984c`

## callees

- `0x180004658`
- `0x180007148`
- `0x1800073c8`
- `0x1800079c0`

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
0x180004658  mov     [rsp+arg_8], rbx
0x18000465d  mov     [rsp+arg_10], rsi
0x180004662  push    rdi
0x180004663  sub     rsp, 20h
0x180004667  mov     rdi, [rcx]
0x18000466a  mov     rsi, rdx
0x18000466d  mov     rbx, rcx
0x180004670  test    rdi, rdi
0x180004673  jz      short loc_180004691
0x180004675  lea     rcx, [rsp+28h+arg_0]; this
0x18000467a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000467f  mov     rcx, rdi; pti
0x180004682  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180004687  lea     rcx, [rsp+28h+arg_0]; this
0x18000468c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180004691  mov     [rbx], rsi
0x180004694  mov     rbx, [rsp+28h+arg_8]
0x180004699  mov     rsi, [rsp+28h+arg_10]
0x18000469e  add     rsp, 20h
0x1800046a2  pop     rdi
0x1800046a3  retn
```
