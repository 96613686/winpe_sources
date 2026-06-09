# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180012608`
- end: `0x180012654`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000cc38`
- `0x18000cce8`
- `0x18000f8a8`
- `0x18000f994`
- `0x18000fa8c`
- `0x18000fefc`

## callees

- `0x18000c888`
- `0x18000cea8`
- `0x18000d490`
- `0x180012608`

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
0x180012608  mov     [rsp+arg_8], rbx
0x18001260d  mov     [rsp+arg_10], rsi
0x180012612  push    rdi
0x180012613  sub     rsp, 20h
0x180012617  mov     rdi, [rcx]
0x18001261a  mov     rsi, rdx
0x18001261d  mov     rbx, rcx
0x180012620  test    rdi, rdi
0x180012623  jz      short loc_180012641
0x180012625  lea     rcx, [rsp+28h+arg_0]; this
0x18001262a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001262f  mov     rcx, rdi; pti
0x180012632  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180012637  lea     rcx, [rsp+28h+arg_0]; this
0x18001263c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180012641  mov     [rbx], rsi
0x180012644  mov     rbx, [rsp+28h+arg_8]
0x180012649  mov     rsi, [rsp+28h+arg_10]
0x18001264e  add     rsp, 20h
0x180012652  pop     rdi
0x180012653  retn
```
