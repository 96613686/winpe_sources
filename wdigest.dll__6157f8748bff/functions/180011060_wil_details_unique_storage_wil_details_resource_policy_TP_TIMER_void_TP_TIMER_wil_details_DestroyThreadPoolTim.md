# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180011060`
- end: `0x1800110ac`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000f294`
- `0x180010920`
- `0x180010e40`
- `0x180010f6c`
- `0x1800117c8`
- `0x180011848`

## callees

- `0x180010f28`
- `0x180010f48`
- `0x180011060`
- `0x180014980`

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
0x180011060  mov     [rsp+arg_8], rbx
0x180011065  mov     [rsp+arg_10], rsi
0x18001106a  push    rdi
0x18001106b  sub     rsp, 20h
0x18001106f  mov     rdi, [rcx]
0x180011072  mov     rsi, rdx
0x180011075  mov     rbx, rcx
0x180011078  test    rdi, rdi
0x18001107b  jz      short loc_180011099
0x18001107d  lea     rcx, [rsp+28h+arg_0]; this
0x180011082  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011087  mov     rcx, rdi; pti
0x18001108a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18001108f  lea     rcx, [rsp+28h+arg_0]; this
0x180011094  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180011099  mov     [rbx], rsi
0x18001109c  mov     rbx, [rsp+28h+arg_8]
0x1800110a1  mov     rsi, [rsp+28h+arg_10]
0x1800110a6  add     rsp, 20h
0x1800110aa  pop     rdi
0x1800110ab  retn
```
