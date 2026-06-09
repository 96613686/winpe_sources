# _CProfileTask_OnMigrate::LogSuccess_::_1_::dtor$2

- ea: `0x18000dd3a`
- end: `0x18000dd46`
- name: `_CProfileTask_OnMigrate::LogSuccess_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180004d50`

## pseudocode

```c
void __fastcall CProfileTask_OnMigrate::LogSuccess_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CAccountDisplayString::~CAccountDisplayString((CAccountDisplayString *)(a2 + 192));
}

```

## disassembly

```asm
0x18000dd3a  lea     rcx, [rdx+0C0h]; this
0x18000dd41  jmp     ??1CAccountDisplayString@@QEAA@XZ; CAccountDisplayString::~CAccountDisplayString(void)
```
