# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x180009130`
- end: `0x18000917d`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: `void __fastcall(void **, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008570`
- `0x180008678`

## callees

- `0x180003338`
- `0x180003584`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000915a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000915a`

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
0x180009130  mov     [rsp+arg_8], rbx
0x180009135  mov     [rsp+arg_10], rsi
0x18000913a  push    rdi
0x18000913b  sub     rsp, 20h
0x18000913f  mov     rdi, [rcx]
0x180009142  mov     rsi, rdx
0x180009145  mov     rbx, rcx
0x180009148  test    rdi, rdi
0x18000914b  jz      short loc_18000916A
0x18000914d  lea     rcx, [rsp+28h+arg_0]; this
0x180009152  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180009157  mov     rcx, rdi; pv
0x18000915a  call    cs:__imp_CoTaskMemFree
0x180009160  lea     rcx, [rsp+28h+arg_0]; this
0x180009165  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000916a  mov     [rbx], rsi
0x18000916d  mov     rbx, [rsp+28h+arg_8]
0x180009172  mov     rsi, [rsp+28h+arg_10]
0x180009177  add     rsp, 20h
0x18000917b  pop     rdi
0x18000917c  retn
```
