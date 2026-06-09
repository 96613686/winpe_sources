# _CDevNode::GetSymbolicLink_::_1_::dtor$0

- ea: `0x180010814`
- end: `0x180010820`
- name: `_CDevNode::GetSymbolicLink_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path`

## callees

- `0x180004124`

## pseudocode

```c
void __fastcall CDevNode::GetSymbolicLink_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::vector<unsigned char>::~vector<unsigned char>(a2 + 56);
}

```

## disassembly

```asm
0x180010814  lea     rcx, [rdx+38h]
0x18001081b  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
