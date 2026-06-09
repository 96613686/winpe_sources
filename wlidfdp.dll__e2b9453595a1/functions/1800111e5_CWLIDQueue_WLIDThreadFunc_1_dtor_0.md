# _CWLIDQueue::WLIDThreadFunc_::_1_::dtor$0

- ea: `0x1800111e5`
- end: `0x1800111f1`
- name: `_CWLIDQueue::WLIDThreadFunc_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009dd8`

## pseudocode

```c
__int64 __fastcall CWLIDQueue::WLIDThreadFunc_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return CAutoRefPtr<CWLIDItem>::~CAutoRefPtr<CWLIDItem>(a2 + 136);
}

```

## disassembly

```asm
0x1800111e5  lea     rcx, [rdx+88h]
0x1800111ec  jmp     ??1?$CAutoRefPtr@VCWLIDItem@@@@QEAA@XZ; CAutoRefPtr<CWLIDItem>::~CAutoRefPtr<CWLIDItem>(void)
```
