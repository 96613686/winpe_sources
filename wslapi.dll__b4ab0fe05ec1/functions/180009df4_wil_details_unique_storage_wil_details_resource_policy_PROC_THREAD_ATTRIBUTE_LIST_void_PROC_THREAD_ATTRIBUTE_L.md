# wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)

- ea: `0x180009df4`
- end: `0x180009e0a`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6AXPEAU1@@Z$1?DeleteProcThreadAttributeList@util@wsl@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(wsl::util **, struct _PROC_THREAD_ATTRIBUTE_LIST *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009de8`
- `0x18000a054`

## callees

- `0x180009df4`
- `0x180009f94`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&void wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&void wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(
        wsl::util **a1,
        struct _PROC_THREAD_ATTRIBUTE_LIST *a2)
{
  wsl::util *v2; // rcx

  v2 = *a1;
  if ( v2 )
    wsl::util::DeleteProcThreadAttributeList(v2, a2);
}

```

## disassembly

```asm
0x180009df4  sub     rsp, 28h
0x180009df8  mov     rcx, [rcx]; this
0x180009dfb  test    rcx, rcx
0x180009dfe  jz      short loc_180009E05
0x180009e00  call    ?DeleteProcThreadAttributeList@util@wsl@@YAXPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z; wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *)
0x180009e05  add     rsp, 28h
0x180009e09  retn
```
