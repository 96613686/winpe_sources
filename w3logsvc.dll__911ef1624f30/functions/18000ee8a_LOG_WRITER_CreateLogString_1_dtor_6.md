# _LOG_WRITER::CreateLogString_::_1_::dtor$6

- ea: `0x18000ee8a`
- end: `0x18000ee9f`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$6`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ee98`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 584));
}

```

## disassembly

```asm
0x18000ee8a  lea     rcx, [rdx+0F0h]
0x18000ee91  add     rcx, 158h
0x18000ee98  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
