# _LOG_WRITER::Write_::_1_::dtor$0_0

- ea: `0x18000f044`
- end: `0x18000f052`
- name: `_LOG_WRITER::Write_::_1_::dtor$0_0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f04b`

## pseudocode

```c
void __fastcall LOG_WRITER::Write_::_1_::dtor_0_0(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 32));
}

```

## disassembly

```asm
0x18000f044  lea     rcx, [rdx+20h]
0x18000f04b  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
