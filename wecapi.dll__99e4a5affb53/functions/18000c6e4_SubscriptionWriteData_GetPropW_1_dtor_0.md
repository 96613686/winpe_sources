# _SubscriptionWriteData::GetPropW_::_1_::dtor$0

- ea: `0x18000c6e4`
- end: `0x18000c6f0`
- name: `_SubscriptionWriteData::GetPropW_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b514`

## pseudocode

```c
void __fastcall SubscriptionWriteData::GetPropW_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Buffer::~Buffer((Buffer *)(a2 + 32));
}

```

## disassembly

```asm
0x18000c6e4  lea     rcx, [rdx+20h]; this
0x18000c6eb  jmp     ??1Buffer@@QEAA@XZ; Buffer::~Buffer(void)
```
