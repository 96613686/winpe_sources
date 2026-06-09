# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)

- ea: `0x180008678`
- end: `0x1800086aa`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180007f04`
- `0x180008a48`
- `0x180008bd8`
- `0x180008ea0`
- `0x1800090ac`
- `0x1800093ec`

## callees

- `0x180008678`
- `0x180009130`

## pseudocode

```c
_QWORD *__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        _QWORD *a1,
        _QWORD *a2)
{
  if ( a1 != a2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a1,
      *a2);
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180008678  mov     [rsp+arg_0], rbx
0x18000867d  push    rdi
0x18000867e  sub     rsp, 20h
0x180008682  mov     rdi, rdx
0x180008685  mov     rbx, rcx
0x180008688  cmp     rcx, rdx
0x18000868b  jz      short loc_18000869C
0x18000868d  mov     rdx, [rdx]
0x180008690  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180008695  mov     qword ptr [rdi], 0
0x18000869c  mov     rax, rbx
0x18000869f  mov     rbx, [rsp+28h+arg_0]
0x1800086a4  add     rsp, 20h
0x1800086a8  pop     rdi
0x1800086a9  retn
```
