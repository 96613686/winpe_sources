# _CWLIDQueue::WLIDTerminateThreadFunc_::_1_::dtor$0

- ea: `0x1800111d3`
- end: `0x1800111df`
- name: `_CWLIDQueue::WLIDTerminateThreadFunc_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009de4`

## pseudocode

```c
void __fastcall CWLIDQueue::WLIDTerminateThreadFunc_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CAutoCoInitialize::~CAutoCoInitialize((CAutoCoInitialize *)(a2 + 88));
}

```

## disassembly

```asm
0x1800111d3  lea     rcx, [rdx+58h]; this
0x1800111da  jmp     ??1CAutoCoInitialize@@QEAA@XZ; CAutoCoInitialize::~CAutoCoInitialize(void)
```
