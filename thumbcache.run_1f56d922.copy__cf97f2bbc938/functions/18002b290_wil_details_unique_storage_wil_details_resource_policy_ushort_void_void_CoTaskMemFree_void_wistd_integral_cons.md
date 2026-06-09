# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18002b290`
- end: `0x18002b2df`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003184`
- `0x180011094`

## callees

- `0x18001f73c`
- `0x18002b290`
- `0x18002d4f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b2cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b2cd`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CoTaskMemFree(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18002b290  mov     [rsp+arg_8], rbx
0x18002b295  mov     [rsp+arg_10], rsi
0x18002b29a  push    rdi
0x18002b29b  sub     rsp, 20h
0x18002b29f  mov     rdi, [rcx]
0x18002b2a2  mov     rsi, rdx
0x18002b2a5  mov     rbx, rcx
0x18002b2a8  test    rdi, rdi
0x18002b2ab  jnz     short loc_18002B2C0
0x18002b2ad  mov     [rbx], rsi
0x18002b2b0  mov     rbx, [rsp+28h+arg_8]
0x18002b2b5  mov     rsi, [rsp+28h+arg_10]
0x18002b2ba  add     rsp, 20h
0x18002b2be  pop     rdi
0x18002b2bf  retn
0x18002b2c0  lea     rcx, [rsp+28h+arg_0]; this
0x18002b2c5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002b2ca  mov     rcx, rdi; pv
0x18002b2cd  call    cs:__imp_CoTaskMemFree
0x18002b2d3  lea     rcx, [rsp+28h+arg_0]; this
0x18002b2d8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002b2dd  jmp     short loc_18002B2AD
```
