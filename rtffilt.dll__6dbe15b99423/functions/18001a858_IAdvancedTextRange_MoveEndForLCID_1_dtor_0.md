# _IAdvancedTextRange::MoveEndForLCID_::_1_::dtor$0

- ea: `0x18001a858`
- end: `0x18001a864`
- name: `_IAdvancedTextRange::MoveEndForLCID_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800103b4`

## pseudocode

```c
void __fastcall IAdvancedTextRange::MoveEndForLCID_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  IAdvancedTextRange::~IAdvancedTextRange((IAdvancedTextRange *)(a2 + 64));
}

```

## disassembly

```asm
0x18001a858  lea     rcx, [rdx+40h]; this
0x18001a85f  jmp     ??1IAdvancedTextRange@@QEAA@XZ; IAdvancedTextRange::~IAdvancedTextRange(void)
```
