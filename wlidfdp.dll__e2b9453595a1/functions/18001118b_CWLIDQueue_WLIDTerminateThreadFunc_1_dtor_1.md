# _CWLIDQueue::WLIDTerminateThreadFunc_::_1_::dtor$1

- ea: `0x18001118b`
- end: `0x180011197`
- name: `_CWLIDQueue::WLIDTerminateThreadFunc_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000578c`

## pseudocode

```c
void __fastcall CWLIDQueue::WLIDTerminateThreadFunc_::_1_::dtor_1(__int64 a1, __int64 a2, int a3)
{
  CTraceFuncVoidW::~CTraceFuncVoidW((MsaTracingInternal **)(a2 + 96), a2, a3);
}

```

## disassembly

```asm
0x18001118b  lea     rcx, [rdx+60h]; this
0x180011192  jmp     ??1CTraceFuncVoidW@@QEAA@XZ; CTraceFuncVoidW::~CTraceFuncVoidW(void)
```
