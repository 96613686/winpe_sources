# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180017ca4`
- end: `0x180017cf0`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180014acc`
- `0x180014b7c`
- `0x180016094`
- `0x18001614c`
- `0x180016238`
- `0x180016628`

## callees

- `0x1800104fc`
- `0x1800106b8`
- `0x180014f94`
- `0x180017ca4`

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
0x180017ca4  mov     [rsp+arg_8], rbx
0x180017ca9  mov     [rsp+arg_10], rsi
0x180017cae  push    rdi
0x180017caf  sub     rsp, 20h
0x180017cb3  mov     rdi, [rcx]
0x180017cb6  mov     rsi, rdx
0x180017cb9  mov     rbx, rcx
0x180017cbc  test    rdi, rdi
0x180017cbf  jz      short loc_180017CDD
0x180017cc1  lea     rcx, [rsp+28h+arg_0]; this
0x180017cc6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180017ccb  mov     rcx, rdi; pti
0x180017cce  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180017cd3  lea     rcx, [rsp+28h+arg_0]; this
0x180017cd8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180017cdd  mov     [rbx], rsi
0x180017ce0  mov     rbx, [rsp+28h+arg_8]
0x180017ce5  mov     rsi, [rsp+28h+arg_10]
0x180017cea  add     rsp, 20h
0x180017cee  pop     rdi
0x180017cef  retn
```
