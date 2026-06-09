# __GetStoreInstallPath_::_1_::dtor$5

- ea: `0x18000c119`
- end: `0x18000c125`
- name: `__GetStoreInstallPath_::_1_::dtor$5`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800068a4`

## pseudocode

```c
__int64 __fastcall _GetStoreInstallPath_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x18000c119  lea     rcx, [rdx+60h]
0x18000c120  jmp     ??1?$com_ptr_t@UIApplicationDataStatics@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(void)
```
