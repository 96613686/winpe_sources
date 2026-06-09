# _ComTaskMgrBase::InitComSecurity_::_1_::dtor$0

- ea: `0x14000aaa0`
- end: `0x14000aaac`
- name: `_ComTaskMgrBase::InitComSecurity_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400073ec`

## pseudocode

```c
void __fastcall ComTaskMgrBase::InitComSecurity_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CSecurityDesc::~CSecurityDesc((ATL::CSecurityDesc *)(a2 + 88));
}

```

## disassembly

```asm
0x14000aaa0  lea     rcx, [rdx+58h]; this
0x14000aaa7  jmp     ??1CSecurityDesc@ATL@@UEAA@XZ; ATL::CSecurityDesc::~CSecurityDesc(void)
```
