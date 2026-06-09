# _DataCollectorCreate_::_1_::dtor$3

- ea: `0x14001cdeb`
- end: `0x14001cdf7`
- name: `_DataCollectorCreate_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140004d54`

## pseudocode

```c
void __fastcall DataCollectorCreate_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  tlx::scoped_coinitialize::~scoped_coinitialize((tlx::scoped_coinitialize *)(a2 + 272));
}

```

## disassembly

```asm
0x14001cdeb  lea     rcx, [rdx+110h]; this
0x14001cdf2  jmp     ??1scoped_coinitialize@tlx@@QEAA@XZ; tlx::scoped_coinitialize::~scoped_coinitialize(void)
```
