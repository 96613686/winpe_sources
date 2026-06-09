# wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void_(__cdecl_)(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE___)_&WTConfigCiFreePrivateData_void_(__cdecl_)(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE___)_noexcept_&NewProviderData_::_unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void_(__cdecl_)(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE___)_&WTConfigCiFreePrivateData_void_(__cdecl_)(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE___)_noexcept_&NewProviderData_

- ea: `0x180020ab4`
- end: `0x180020ac4`
- name: `wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void_(__cdecl_)(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE___)_&WTConfigCiFreePrivateData_void_(__cdecl_)(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE___)_noexcept_&NewProviderData_::_unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void_(__cdecl_)(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE___)_&WTConfigCiFreePrivateData_void_(__cdecl_)(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE___)_noexcept_&NewProviderData_`
- size: `16`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18003f77c`
- `0x18003f85f`
- `0x1800404b5`
- `0x1800404eb`

## import_xrefs

- `WINTRUST!WTConfigCiFreePrivateData` at `0x180020ab8`
- `WINTRUST!WTConfigCiFreePrivateData` at `0x180020ab8`

## pseudocode

```c
__int64 __fastcall wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_::_unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_(
        __int64 a1)
{
  return WTConfigCiFreePrivateData(a1);
}

```

## disassembly

```asm
0x180020ab4  sub     rsp, 28h
0x180020ab8  call    cs:__imp_WTConfigCiFreePrivateData
0x180020abe  nop
0x180020abf  add     rsp, 28h
0x180020ac3  retn
```
