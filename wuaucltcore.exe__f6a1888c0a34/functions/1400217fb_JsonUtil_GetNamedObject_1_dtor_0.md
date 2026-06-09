# _JsonUtil::GetNamedObject_::_1_::dtor$0

- ea: `0x1400217fb`
- end: `0x140021807`
- name: `_JsonUtil::GetNamedObject_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000648c`

## pseudocode

```c
__int64 __fastcall JsonUtil::GetNamedObject_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IRemoteUHProcessHost,wil::err_returncode_policy>::~com_ptr_t<IRemoteUHProcessHost,wil::err_returncode_policy>((__int64 *)(a2 + 72));
}

```

## disassembly

```asm
0x1400217fb  lea     rcx, [rdx+48h]
0x140021802  jmp     ??1?$com_ptr_t@UIRemoteUHProcessHost@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IRemoteUHProcessHost,wil::err_returncode_policy>::~com_ptr_t<IRemoteUHProcessHost,wil::err_returncode_policy>(void)
```
