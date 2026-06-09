# _LOG_WRITER::CreateLogString_::_1_::dtor$9

- ea: `0x18000eedb`
- end: `0x18000eef0`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$9`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000eee9`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 968));
}

```

## disassembly

```asm
0x18000eedb  lea     rcx, [rdx+0F0h]
0x18000eee2  add     rcx, 2D8h
0x18000eee9  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
