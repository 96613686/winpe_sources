# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)

- ea: `0x18004b96c`
- end: `0x18004b9be`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004a840`
- `0x18004d4d8`

## callees

- `0x180017434`
- `0x1800174b8`
- `0x18004b96c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b998`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b998`

## pseudocode

```c
void **__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        void **a1,
        void **a2)
{
  void *v4; // rsi
  void *v5; // rbp
  char v7; // [rsp+50h] [rbp+8h] BYREF

  if ( a1 != a2 )
  {
    v4 = *a1;
    v5 = *a2;
    if ( *a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
      CoTaskMemFree(v4);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
    }
    *a1 = v5;
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18004b96c  push    rbx
0x18004b96e  push    rbp
0x18004b96f  push    rsi
0x18004b970  push    rdi
0x18004b971  sub     rsp, 28h
0x18004b975  mov     rdi, rdx
0x18004b978  mov     rbx, rcx
0x18004b97b  cmp     rcx, rdx
0x18004b97e  jz      short loc_18004B9B2
0x18004b980  mov     rsi, [rcx]
0x18004b983  mov     rbp, [rdx]
0x18004b986  test    rsi, rsi
0x18004b989  jz      short loc_18004B9A8
0x18004b98b  lea     rcx, [rsp+48h+arg_0]; this
0x18004b990  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004b995  mov     rcx, rsi; pv
0x18004b998  call    cs:__imp_CoTaskMemFree
0x18004b99e  lea     rcx, [rsp+48h+arg_0]; this
0x18004b9a3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004b9a8  mov     [rbx], rbp
0x18004b9ab  mov     qword ptr [rdi], 0
0x18004b9b2  mov     rax, rbx
0x18004b9b5  add     rsp, 28h
0x18004b9b9  pop     rdi
0x18004b9ba  pop     rsi
0x18004b9bb  pop     rbp
0x18004b9bc  pop     rbx
0x18004b9bd  retn
```
