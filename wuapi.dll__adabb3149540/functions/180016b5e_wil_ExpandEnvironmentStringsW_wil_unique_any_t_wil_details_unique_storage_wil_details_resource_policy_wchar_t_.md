# _wil::ExpandEnvironmentStringsW_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_wchar_t___void_(__cdecl_)(void__)_&CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__wchar_t___wchar_t___0_std::nullptr_t______256__::_1_::dtor$0

- ea: `0x180016b5e`
- end: `0x180016b84`
- name: `_wil::ExpandEnvironmentStringsW_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_wchar_t___void_(__cdecl_)(void__)_&CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__wchar_t___wchar_t___0_std::nullptr_t______256__::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x18000aa88`
- `0x180016b5e`

## pseudocode

```c
void __fastcall wil::ExpandEnvironmentStringsW_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_wchar_t___void____cdecl___void_____CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__wchar_t___wchar_t___0_std::nullptr_t______256__::_1_::dtor_0(
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
0x180016b5e  push    rbp
0x180016b60  sub     rsp, 20h
0x180016b64  mov     rbp, rdx
0x180016b67  mov     eax, [rbp+20h]
0x180016b6a  and     eax, 1
0x180016b6d  test    eax, eax
0x180016b6f  jz      short loc_180016B7E
0x180016b71  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x180016b75  mov     rcx, [rbp+28h]
0x180016b79  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>(void)
0x180016b7e  add     rsp, 20h
0x180016b82  pop     rbp
0x180016b83  retn
```
