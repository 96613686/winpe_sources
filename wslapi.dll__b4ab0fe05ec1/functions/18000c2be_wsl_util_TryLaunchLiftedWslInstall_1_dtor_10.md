# _wsl::util::TryLaunchLiftedWslInstall_::_1_::dtor$10

- ea: `0x18000c2be`
- end: `0x18000c2ca`
- name: `_wsl::util::TryLaunchLiftedWslInstall_::_1_::dtor$10`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180009de8`

## pseudocode

```c
__int64 wsl::util::TryLaunchLiftedWslInstall_::_1_::dtor_10()
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&void wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&void wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>>();
}

```

## disassembly

```asm
0x18000c2be  lea     rcx, [rdx+50h]
0x18000c2c5  jmp     ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6AXPEAU1@@Z$1?DeleteProcThreadAttributeList@util@wsl@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>>(void)
```
