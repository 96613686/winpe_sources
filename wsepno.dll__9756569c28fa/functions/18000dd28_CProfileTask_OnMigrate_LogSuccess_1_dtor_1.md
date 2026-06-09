# _CProfileTask_OnMigrate::LogSuccess_::_1_::dtor$1

- ea: `0x18000dd28`
- end: `0x18000dd34`
- name: `_CProfileTask_OnMigrate::LogSuccess_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180004d50`

## pseudocode

```c
void __fastcall CProfileTask_OnMigrate::LogSuccess_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CAccountDisplayString::~CAccountDisplayString((CAccountDisplayString *)(a2 + 200));
}

```

## disassembly

```asm
0x18000dd28  lea     rcx, [rdx+0C8h]; this
0x18000dd2f  jmp     ??1CAccountDisplayString@@QEAA@XZ; CAccountDisplayString::~CAccountDisplayString(void)
```
