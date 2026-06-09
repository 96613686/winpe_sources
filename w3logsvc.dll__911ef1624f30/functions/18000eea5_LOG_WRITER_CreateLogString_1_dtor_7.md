# _LOG_WRITER::CreateLogString_::_1_::dtor$7

- ea: `0x18000eea5`
- end: `0x18000eeba`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$7`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000eeb3`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 760));
}

```

## disassembly

```asm
0x18000eea5  lea     rcx, [rdx+0F0h]
0x18000eeac  add     rcx, 208h
0x18000eeb3  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
