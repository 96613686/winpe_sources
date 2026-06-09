# _ComTaskMgrBase::InitComSecurity_::_1_::dtor$5

- ea: `0x14000aac0`
- end: `0x14000aacc`
- name: `_ComTaskMgrBase::InitComSecurity_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400028b0`

## pseudocode

```c
void __fastcall ComTaskMgrBase::InitComSecurity_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  ATL::CSid::~CSid((ATL::CSid *)(a2 + 176));
}

```

## disassembly

```asm
0x14000aac0  lea     rcx, [rdx+0B0h]; this
0x14000aac7  jmp     ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
```
