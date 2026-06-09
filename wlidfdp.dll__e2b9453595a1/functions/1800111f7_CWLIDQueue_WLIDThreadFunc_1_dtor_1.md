# _CWLIDQueue::WLIDThreadFunc_::_1_::dtor$1

- ea: `0x1800111f7`
- end: `0x180011203`
- name: `_CWLIDQueue::WLIDThreadFunc_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009de4`

## pseudocode

```c
void __fastcall CWLIDQueue::WLIDThreadFunc_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CAutoCoInitialize::~CAutoCoInitialize((CAutoCoInitialize *)(a2 + 40));
}

```

## disassembly

```asm
0x1800111f7  lea     rcx, [rdx+28h]; this
0x1800111fe  jmp     ??1CAutoCoInitialize@@QEAA@XZ; CAutoCoInitialize::~CAutoCoInitialize(void)
```
