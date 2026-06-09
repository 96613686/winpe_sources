# _wil::ExpandEnvironmentStringsW_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_unsigned_short___void_(__cdecl_)(void__)_&CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__unsigned_short___unsigned_short___0_std::nullptr_t______256__::_1_::dtor$0

- ea: `0x14000ad3e`
- end: `0x14000ad64`
- name: `_wil::ExpandEnvironmentStringsW_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_unsigned_short___void_(__cdecl_)(void__)_&CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__unsigned_short___unsigned_short___0_std::nullptr_t______256__::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x14000884c`
- `0x14000ad3e`

## pseudocode

```c
void __fastcall wil::ExpandEnvironmentStringsW_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_unsigned_short___void____cdecl___void_____CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__unsigned_short___unsigned_short___0_std::nullptr_t______256__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(*(void ***)(a2 + 64));
  }
}

```

## disassembly

```asm
0x14000ad3e  push    rbp
0x14000ad40  sub     rsp, 20h
0x14000ad44  mov     rbp, rdx
0x14000ad47  mov     eax, [rbp+20h]
0x14000ad4a  and     eax, 1
0x14000ad4d  test    eax, eax
0x14000ad4f  jz      short loc_14000AD5E
0x14000ad51  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x14000ad55  mov     rcx, [rbp+40h]
0x14000ad59  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14000ad5e  add     rsp, 20h
0x14000ad62  pop     rbp
0x14000ad63  retn
```
