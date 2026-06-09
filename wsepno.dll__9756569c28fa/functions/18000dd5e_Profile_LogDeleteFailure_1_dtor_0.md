# _Profile_LogDeleteFailure_::_1_::dtor$0

- ea: `0x18000dd5e`
- end: `0x18000dd6a`
- name: `_Profile_LogDeleteFailure_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005234`

## pseudocode

```c
void __fastcall Profile_LogDeleteFailure_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ProfNotifEventLog::~ProfNotifEventLog((ProfNotifEventLog *)(a2 + 80));
}

```

## disassembly

```asm
0x18000dd5e  lea     rcx, [rdx+50h]; this
0x18000dd65  jmp     ??1ProfNotifEventLog@@QEAA@XZ; ProfNotifEventLog::~ProfNotifEventLog(void)
```
