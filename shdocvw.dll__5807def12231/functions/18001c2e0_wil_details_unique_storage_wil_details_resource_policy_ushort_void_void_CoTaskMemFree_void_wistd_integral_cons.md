# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18001c2e0`
- end: `0x18001c32d`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013dd8`
- `0x180013e78`

## callees

- `0x180005540`
- `0x180005560`
- `0x18001c2e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c30a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c30a`

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
0x18001c2e0  mov     [rsp+arg_8], rbx
0x18001c2e5  mov     [rsp+arg_10], rsi
0x18001c2ea  push    rdi
0x18001c2eb  sub     rsp, 20h
0x18001c2ef  mov     rdi, [rcx]
0x18001c2f2  mov     rsi, rdx
0x18001c2f5  mov     rbx, rcx
0x18001c2f8  test    rdi, rdi
0x18001c2fb  jz      short loc_18001C31A
0x18001c2fd  lea     rcx, [rsp+28h+arg_0]; this
0x18001c302  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001c307  mov     rcx, rdi; pv
0x18001c30a  call    cs:__imp_CoTaskMemFree
0x18001c310  lea     rcx, [rsp+28h+arg_0]; this
0x18001c315  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001c31a  mov     [rbx], rsi
0x18001c31d  mov     rbx, [rsp+28h+arg_8]
0x18001c322  mov     rsi, [rsp+28h+arg_10]
0x18001c327  add     rsp, 20h
0x18001c32b  pop     rdi
0x18001c32c  retn
```
