# _WslSession::s_Create_::_1_::dtor$5

- ea: `0x18000c19c`
- end: `0x18000c1ac`
- name: `_WslSession::s_Create_::_1_::dtor$5`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800068a4`

## pseudocode

```c
__int64 __fastcall WslSession::s_Create_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>((__int64 *)(*(_QWORD *)(a2 + 32) + 16LL));
}

```

## disassembly

```asm
0x18000c19c  mov     rcx, [rdx+20h]
0x18000c1a3  add     rcx, 10h
0x18000c1a7  jmp     ??1?$com_ptr_t@UIApplicationDataStatics@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(void)
```
