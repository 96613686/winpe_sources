# _CThreadInfo::GetEmbeddedImageStreams_::_1_::dtor$1

- ea: `0x18001a733`
- end: `0x18001a73f`
- name: `_CThreadInfo::GetEmbeddedImageStreams_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800103b4`

## pseudocode

```c
void __fastcall CThreadInfo::GetEmbeddedImageStreams_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  IAdvancedTextRange::~IAdvancedTextRange((IAdvancedTextRange *)(a2 + 160));
}

```

## disassembly

```asm
0x18001a733  lea     rcx, [rdx+0A0h]; this
0x18001a73a  jmp     ??1IAdvancedTextRange@@QEAA@XZ; IAdvancedTextRange::~IAdvancedTextRange(void)
```
