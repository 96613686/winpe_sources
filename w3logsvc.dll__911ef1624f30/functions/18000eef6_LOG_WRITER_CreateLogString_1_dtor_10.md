# _LOG_WRITER::CreateLogString_::_1_::dtor$10

- ea: `0x18000eef6`
- end: `0x18000ef0b`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$10`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ef04`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 1048));
}

```

## disassembly

```asm
0x18000eef6  lea     rcx, [rdx+0F0h]
0x18000eefd  add     rcx, 328h
0x18000ef04  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
