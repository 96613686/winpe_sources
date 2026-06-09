# _CThreadInfo::GetAllTheText_::_1_::dtor$0

- ea: `0x18001a70f`
- end: `0x18001a71b`
- name: `_CThreadInfo::GetAllTheText_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800103b4`

## pseudocode

```c
void __fastcall CThreadInfo::GetAllTheText_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  IAdvancedTextRange::~IAdvancedTextRange((IAdvancedTextRange *)(a2 + 56));
}

```

## disassembly

```asm
0x18001a70f  lea     rcx, [rdx+38h]; this
0x18001a716  jmp     ??1IAdvancedTextRange@@QEAA@XZ; IAdvancedTextRange::~IAdvancedTextRange(void)
```
