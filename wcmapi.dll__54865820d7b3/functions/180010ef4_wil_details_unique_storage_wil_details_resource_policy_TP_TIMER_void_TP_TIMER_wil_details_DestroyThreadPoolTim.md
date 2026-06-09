# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180010ef4`
- end: `0x180010f41`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `77`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000bff4`
- `0x18000c0a4`
- `0x18000ec14`
- `0x18000ed2c`
- `0x18000f170`
- `0x180016420`

## callees

- `0x18000bd50`
- `0x18000c264`
- `0x18000cc44`
- `0x180010ef4`

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
0x180010ef4  mov     [rsp+arg_8], rbx
0x180010ef9  mov     [rsp+arg_10], rsi
0x180010efe  push    rdi
0x180010eff  sub     rsp, 20h
0x180010f03  mov     rdi, [rcx]
0x180010f06  mov     rsi, rdx
0x180010f09  mov     rbx, rcx
0x180010f0c  test    rdi, rdi
0x180010f0f  jz      short loc_180010F2D
0x180010f11  lea     rcx, [rsp+28h+arg_0]; this
0x180010f16  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180010f1b  mov     rcx, rdi; pti
0x180010f1e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180010f23  lea     rcx, [rsp+28h+arg_0]; this
0x180010f28  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180010f2d  mov     [rbx], rsi
0x180010f30  mov     rbx, [rsp+28h+arg_8]
0x180010f35  mov     rsi, [rsp+28h+arg_10]
0x180010f3a  add     rsp, 20h
0x180010f3e  pop     rdi
0x180010f3f  retn
```
