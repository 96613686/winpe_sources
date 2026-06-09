# _CProfileTask_OnMigrate::LogSuccess_::_1_::dtor$0

- ea: `0x18000dd04`
- end: `0x18000dd10`
- name: `_CProfileTask_OnMigrate::LogSuccess_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180005234`

## pseudocode

```c
void __fastcall CProfileTask_OnMigrate::LogSuccess_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ProfNotifEventLog::~ProfNotifEventLog((ProfNotifEventLog *)(a2 + 64));
}

```

## disassembly

```asm
0x18000dd04  lea     rcx, [rdx+40h]; this
0x18000dd0b  jmp     ??1ProfNotifEventLog@@QEAA@XZ; ProfNotifEventLog::~ProfNotifEventLog(void)
```
