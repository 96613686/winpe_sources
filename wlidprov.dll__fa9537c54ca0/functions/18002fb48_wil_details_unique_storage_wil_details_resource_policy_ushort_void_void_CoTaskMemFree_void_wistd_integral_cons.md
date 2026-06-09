# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18002fb48`
- end: `0x18002fb95`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002859c`
- `0x18003d980`
- `0x18003dae0`

## callees

- `0x1800205d8`
- `0x180020784`
- `0x18002fb48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb72`

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
0x18002fb48  mov     [rsp+arg_8], rbx
0x18002fb4d  mov     [rsp+arg_10], rsi
0x18002fb52  push    rdi
0x18002fb53  sub     rsp, 20h
0x18002fb57  mov     rdi, [rcx]
0x18002fb5a  mov     rsi, rdx
0x18002fb5d  mov     rbx, rcx
0x18002fb60  test    rdi, rdi
0x18002fb63  jz      short loc_18002FB82
0x18002fb65  lea     rcx, [rsp+28h+arg_0]; this
0x18002fb6a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002fb6f  mov     rcx, rdi; pv
0x18002fb72  call    cs:__imp_CoTaskMemFree
0x18002fb78  lea     rcx, [rsp+28h+arg_0]; this
0x18002fb7d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002fb82  mov     [rbx], rsi
0x18002fb85  mov     rbx, [rsp+28h+arg_8]
0x18002fb8a  mov     rsi, [rsp+28h+arg_10]
0x18002fb8f  add     rsp, 20h
0x18002fb93  pop     rdi
0x18002fb94  retn
```
