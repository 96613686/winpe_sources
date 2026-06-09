# _wsl::util::CreateProcThreadAttributeList_::_1_::dtor$0

- ea: `0x18000c1b2`
- end: `0x18000c1d8`
- name: `_wsl::util::CreateProcThreadAttributeList_::_1_::dtor$0`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180009de8`
- `0x18000c1b2`

## pseudocode

```c
__int64 __fastcall wsl::util::CreateProcThreadAttributeList_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&void wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&void wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>>();
  }
  return result;
}

```

## disassembly

```asm
0x18000c1b2  push    rbp
0x18000c1b4  sub     rsp, 20h
0x18000c1b8  mov     rbp, rdx
0x18000c1bb  mov     eax, [rbp+20h]
0x18000c1be  and     eax, 1
0x18000c1c1  test    eax, eax
0x18000c1c3  jz      short loc_18000C1D2
0x18000c1c5  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000c1c9  mov     rcx, [rbp+28h]
0x18000c1cd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6AXPEAU1@@Z$1?DeleteProcThreadAttributeList@util@wsl@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void (*)(_PROC_THREAD_ATTRIBUTE_LIST *),&wsl::util::DeleteProcThreadAttributeList(_PROC_THREAD_ATTRIBUTE_LIST *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>>(void)
0x18000c1d2  add     rsp, 20h
0x18000c1d6  pop     rbp
0x18000c1d7  retn
```
