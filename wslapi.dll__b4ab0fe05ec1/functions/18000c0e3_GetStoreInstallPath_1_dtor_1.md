# __GetStoreInstallPath_::_1_::dtor$1

- ea: `0x18000c0e3`
- end: `0x18000c0ef`
- name: `__GetStoreInstallPath_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800068a4`

## pseudocode

```c
__int64 __fastcall _GetStoreInstallPath_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>((__int64 *)(a2 + 104));
}

```

## disassembly

```asm
0x18000c0e3  lea     rcx, [rdx+68h]
0x18000c0ea  jmp     ??1?$com_ptr_t@UIApplicationDataStatics@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(void)
```
