# _LOG_WRITER::LOG_WRITER_::_1_::dtor$0

- ea: `0x18000ed48`
- end: `0x18000ed5a`
- name: `_LOG_WRITER::LOG_WRITER_::_1_::dtor$0`
- size: `18`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ed53`

## pseudocode

```c
void __fastcall LOG_WRITER::LOG_WRITER_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(*(_QWORD *)(a2 + 48) + 16LL));
}

```

## disassembly

```asm
0x18000ed48  mov     rcx, [rdx+30h]
0x18000ed4f  add     rcx, 10h
0x18000ed53  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
