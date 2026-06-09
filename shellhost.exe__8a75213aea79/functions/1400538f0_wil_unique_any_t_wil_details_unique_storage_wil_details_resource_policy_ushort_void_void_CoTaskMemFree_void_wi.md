# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)

- ea: `0x1400538f0`
- end: `0x140053942`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140051114`
- `0x14005e4f4`

## callees

- `0x14000a7b0`
- `0x14000a834`
- `0x1400538f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005391c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005391c`

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
0x1400538f0  push    rbx
0x1400538f2  push    rbp
0x1400538f3  push    rsi
0x1400538f4  push    rdi
0x1400538f5  sub     rsp, 28h
0x1400538f9  mov     rdi, rdx
0x1400538fc  mov     rbx, rcx
0x1400538ff  cmp     rcx, rdx
0x140053902  jz      short loc_140053936
0x140053904  mov     rsi, [rcx]
0x140053907  mov     rbp, [rdx]
0x14005390a  test    rsi, rsi
0x14005390d  jz      short loc_14005392C
0x14005390f  lea     rcx, [rsp+48h+arg_0]; this
0x140053914  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140053919  mov     rcx, rsi; pv
0x14005391c  call    cs:__imp_CoTaskMemFree
0x140053922  lea     rcx, [rsp+48h+arg_0]; this
0x140053927  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14005392c  mov     [rbx], rbp
0x14005392f  mov     qword ptr [rdi], 0
0x140053936  mov     rax, rbx
0x140053939  add     rsp, 28h
0x14005393d  pop     rdi
0x14005393e  pop     rsi
0x14005393f  pop     rbp
0x140053940  pop     rbx
0x140053941  retn
```
