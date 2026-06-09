# _LOG_WRITER::CreateLogString_::_1_::dtor$12

- ea: `0x18000ef2c`
- end: `0x18000ef41`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$12`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ef3a`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_12(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 1288));
}

```

## disassembly

```asm
0x18000ef2c  lea     rcx, [rdx+0F0h]
0x18000ef33  add     rcx, 418h
0x18000ef3a  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
