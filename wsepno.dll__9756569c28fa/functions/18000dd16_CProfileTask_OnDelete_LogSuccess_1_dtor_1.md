# _CProfileTask_OnDelete::LogSuccess_::_1_::dtor$1

- ea: `0x18000dd16`
- end: `0x18000dd22`
- name: `_CProfileTask_OnDelete::LogSuccess_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180004d50`

## pseudocode

```c
void __fastcall CProfileTask_OnDelete::LogSuccess_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CAccountDisplayString::~CAccountDisplayString((CAccountDisplayString *)(a2 + 176));
}

```

## disassembly

```asm
0x18000dd16  lea     rcx, [rdx+0B0h]; this
0x18000dd1d  jmp     ??1CAccountDisplayString@@QEAA@XZ; CAccountDisplayString::~CAccountDisplayString(void)
```
