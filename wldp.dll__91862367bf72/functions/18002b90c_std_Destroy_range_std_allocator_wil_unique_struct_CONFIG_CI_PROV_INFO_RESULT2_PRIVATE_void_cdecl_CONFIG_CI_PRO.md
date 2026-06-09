# std::_Destroy_range_std::allocator_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void_(__cdecl_)(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE___)_&WTConfigCiFreePrivateData_void_(__cdecl_)(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE___)_noexcept_&NewProviderData_____

- ea: `0x18002b90c`
- end: `0x18002b941`
- name: `std::_Destroy_range_std::allocator_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void_(__cdecl_)(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE___)_&WTConfigCiFreePrivateData_void_(__cdecl_)(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE___)_noexcept_&NewProviderData_____`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180015118`
- `0x18001e1d4`
- `0x18001e6b8`
- `0x180020378`
- `0x18002bf30`
- `0x18002c104`
- `0x18002c154`
- `0x18002d7f4`

## callees

- `0x18002b90c`

## import_xrefs

- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002b924`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002b924`

## pseudocode

```c
__int64 __fastcall std::_Destroy_range_std::allocator_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      result = WTConfigCiFreePrivateData(v3);
      v3 += 232;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x18002b90c  cmp     rcx, rdx
0x18002b90f  jz      short locret_18002B940
0x18002b911  mov     [rsp+arg_0], rbx
0x18002b916  push    rdi
0x18002b917  sub     rsp, 20h
0x18002b91b  mov     rdi, rdx
0x18002b91e  mov     rbx, rcx
0x18002b921  mov     rcx, rbx
0x18002b924  call    cs:__imp_WTConfigCiFreePrivateData
0x18002b92a  add     rbx, 0E8h
0x18002b931  cmp     rbx, rdi
0x18002b934  jnz     short loc_18002B921
0x18002b936  mov     rbx, [rsp+28h+arg_0]
0x18002b93b  add     rsp, 20h
0x18002b93f  pop     rdi
0x18002b940  retn
```
