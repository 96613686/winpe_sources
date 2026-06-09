# _CAANapEnforcementClientCallback::RemoveConnection_::_1_::dtor$0

- ea: `0x18000b2fd`
- end: `0x18000b309`
- name: `_CAANapEnforcementClientCallback::RemoveConnection_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002c94`

## pseudocode

```c
void __fastcall CAANapEnforcementClientCallback::RemoveConnection_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)(a2 + 80));
}

```

## disassembly

```asm
0x18000b2fd  lea     rcx, [rdx+50h]; this
0x18000b304  jmp     ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
```
