# _LOG_WRITER::LOG_WRITER_::_1_::dtor$4

- ea: `0x18000edae`
- end: `0x18000edc3`
- name: `_LOG_WRITER::LOG_WRITER_::_1_::dtor$4`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000edbc`

## pseudocode

```c
void __fastcall LOG_WRITER::LOG_WRITER_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  STRA::~STRA((STRA *)(*(_QWORD *)(a2 + 48) + 496LL));
}

```

## disassembly

```asm
0x18000edae  mov     rcx, [rdx+30h]
0x18000edb5  add     rcx, 1F0h
0x18000edbc  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
