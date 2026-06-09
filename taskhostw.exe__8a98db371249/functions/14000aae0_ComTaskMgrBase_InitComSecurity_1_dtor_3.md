# _ComTaskMgrBase::InitComSecurity_::_1_::dtor$3

- ea: `0x14000aae0`
- end: `0x14000aaec`
- name: `_ComTaskMgrBase::InitComSecurity_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140002250`

## pseudocode

```c
void __fastcall ComTaskMgrBase::InitComSecurity_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  ATL::CDacl::~CDacl((void **)(a2 + 112));
}

```

## disassembly

```asm
0x14000aae0  lea     rcx, [rdx+70h]; this
0x14000aae7  jmp     ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
```
