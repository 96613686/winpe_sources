# _CWLIDQueue::WLIDThreadFunc_::_1_::dtor$2

- ea: `0x180011209`
- end: `0x180011215`
- name: `_CWLIDQueue::WLIDThreadFunc_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000578c`

## pseudocode

```c
void __fastcall CWLIDQueue::WLIDThreadFunc_::_1_::dtor_2(__int64 a1, __int64 a2, int a3)
{
  CTraceFuncVoidW::~CTraceFuncVoidW((MsaTracingInternal **)(a2 + 112), a2, a3);
}

```

## disassembly

```asm
0x180011209  lea     rcx, [rdx+70h]; this
0x180011210  jmp     ??1CTraceFuncVoidW@@QEAA@XZ; CTraceFuncVoidW::~CTraceFuncVoidW(void)
```
