# _wsl::util::TryLaunchLiftedWslInstall_::_1_::dtor$11

- ea: `0x18000c2d0`
- end: `0x18000c2dc`
- name: `_wsl::util::TryLaunchLiftedWslInstall_::_1_::dtor$11`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180009e10`

## pseudocode

```c
__int64 __fastcall wsl::util::TryLaunchLiftedWslInstall_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  return wil::unique_struct<_PROCESS_INFORMATION,void (*)(_PROCESS_INFORMATION *),&void wil::details::CloseProcessInformation(_PROCESS_INFORMATION *),std::nullptr_t,0>::~unique_struct<_PROCESS_INFORMATION,void (*)(_PROCESS_INFORMATION *),&void wil::details::CloseProcessInformation(_PROCESS_INFORMATION *),std::nullptr_t,0>(a2 + 616);
}

```

## disassembly

```asm
0x18000c2d0  lea     rcx, [rdx+268h]
0x18000c2d7  jmp     ??1?$unique_struct@U_PROCESS_INFORMATION@@P6AXPEAU1@@Z$1?CloseProcessInformation@details@wil@@YAX0@Z$$T$0A@@wil@@QEAA@XZ; wil::unique_struct<_PROCESS_INFORMATION,void (*)(_PROCESS_INFORMATION *),&wil::details::CloseProcessInformation(_PROCESS_INFORMATION *),std::nullptr_t,0>::~unique_struct<_PROCESS_INFORMATION,void (*)(_PROCESS_INFORMATION *),&wil::details::CloseProcessInformation(_PROCESS_INFORMATION *),std::nullptr_t,0>(void)
```
