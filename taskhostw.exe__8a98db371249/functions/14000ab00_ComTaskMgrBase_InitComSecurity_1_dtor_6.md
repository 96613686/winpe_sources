# _ComTaskMgrBase::InitComSecurity_::_1_::dtor$6

- ea: `0x14000ab00`
- end: `0x14000ab0c`
- name: `_ComTaskMgrBase::InitComSecurity_::_1_::dtor$6`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400028b0`

## pseudocode

```c
void __fastcall ComTaskMgrBase::InitComSecurity_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  ATL::CSid::~CSid((ATL::CSid *)(a2 + 304));
}

```

## disassembly

```asm
0x14000ab00  lea     rcx, [rdx+130h]; this
0x14000ab07  jmp     ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
```
