# _LOG_WRITER::LOG_WRITER_::_1_::dtor$2

- ea: `0x18000ed78`
- end: `0x18000ed8d`
- name: `_LOG_WRITER::LOG_WRITER_::_1_::dtor$2`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000ed86`

## pseudocode

```c
void __fastcall LOG_WRITER::LOG_WRITER_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  STRA::~STRA((STRA *)(*(_QWORD *)(a2 + 48) + 128LL));
}

```

## disassembly

```asm
0x18000ed78  mov     rcx, [rdx+30h]
0x18000ed7f  add     rcx, 80h
0x18000ed86  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
