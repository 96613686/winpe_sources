# wistd::__function::__func<`wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &)'::`2'::_lambda_1_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vector deleting destructor'(uint)

- ea: `0x18000ba80`
- end: `0x18000baab`
- name: `??_E?$__func@V_lambda_1_@?1???$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@2@@Z@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@UEAAPEAXI@Z`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x18000ba80`
- `0x180010334`

## pseudocode

```c
_QWORD *__fastcall wistd::__function::Z::$$A6AJPEA_W_KPEA_K::Z::__func<`wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>'::`2'::_lambda_1_,AJPEAXPEAUHINSTANCE__,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &>::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &wistd::__function::__base<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000ba80  push    rbx
0x18000ba82  sub     rsp, 20h
0x18000ba86  lea     rax, ??_7?$__base@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__base<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18000ba8d  mov     rbx, rcx
0x18000ba90  mov     [rcx], rax
0x18000ba93  test    dl, 1
0x18000ba96  jz      short loc_18000BAA2
0x18000ba98  mov     edx, 18h; unsigned __int64
0x18000ba9d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000baa2  mov     rax, rbx
0x18000baa5  add     rsp, 20h
0x18000baa9  pop     rbx
0x18000baaa  retn
```
