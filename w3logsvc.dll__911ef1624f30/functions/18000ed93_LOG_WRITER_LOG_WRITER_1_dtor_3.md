# _LOG_WRITER::LOG_WRITER_::_1_::dtor$3

- ea: `0x18000ed93`
- end: `0x18000eda8`
- name: `_LOG_WRITER::LOG_WRITER_::_1_::dtor$3`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000eda1`

## pseudocode

```c
void __fastcall LOG_WRITER::LOG_WRITER_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  STRA::~STRA((STRA *)(*(_QWORD *)(a2 + 48) + 184LL));
}

```

## disassembly

```asm
0x18000ed93  mov     rcx, [rdx+30h]
0x18000ed9a  add     rcx, 0B8h
0x18000eda1  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
