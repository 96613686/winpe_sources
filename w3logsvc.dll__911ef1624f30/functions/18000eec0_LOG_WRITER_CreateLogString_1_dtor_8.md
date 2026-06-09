# _LOG_WRITER::CreateLogString_::_1_::dtor$8

- ea: `0x18000eec0`
- end: `0x18000eed5`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$8`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000eece`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 848));
}

```

## disassembly

```asm
0x18000eec0  lea     rcx, [rdx+0F0h]
0x18000eec7  add     rcx, 260h
0x18000eece  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
