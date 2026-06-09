# _wil::K32GetModuleFileNameExW_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_wchar_t___void_(__cdecl_)(void__)_&CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__wchar_t___wchar_t___0_std::nullptr_t______128__::_1_::dtor$0

- ea: `0x140021713`
- end: `0x140021739`
- name: `_wil::K32GetModuleFileNameExW_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_wchar_t___void_(__cdecl_)(void__)_&CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__wchar_t___wchar_t___0_std::nullptr_t______128__::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x14000b774`
- `0x140021713`

## pseudocode

```c
void __fastcall wil::K32GetModuleFileNameExW_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_wchar_t___void____cdecl___void_____CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__wchar_t___wchar_t___0_std::nullptr_t______128__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>(*(void ***)(a2 + 40));
  }
}

```

## disassembly

```asm
0x140021713  push    rbp
0x140021715  sub     rsp, 20h
0x140021719  mov     rbp, rdx
0x14002171c  mov     eax, [rbp+20h]
0x14002171f  and     eax, 1
0x140021722  test    eax, eax
0x140021724  jz      short loc_140021733
0x140021726  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x14002172a  mov     rcx, [rbp+28h]
0x14002172e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>(void)
0x140021733  add     rsp, 20h
0x140021737  pop     rbp
0x140021738  retn
```
