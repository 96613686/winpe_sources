# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>>(void)

- ea: `0x180009de8`
- end: `0x180009ded`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6AXPEAU1@@Z$1?DeleteProcThreadAttributeList@util@wsl@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `5`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000c1b2`
- `0x18000c2be`

## callees

- `0x180009df4`

## pseudocode

```c
// attributes: thunk
__int64 wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&void wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&void wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>>()
{
  return wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&void wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&void wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>();
}

```

## disassembly

```asm
0x180009de8  jmp     ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6AXPEAU1@@Z$1?DeleteProcThreadAttributeList@util@wsl@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
```
