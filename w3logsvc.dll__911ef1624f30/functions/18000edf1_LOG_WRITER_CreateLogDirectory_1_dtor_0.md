# _LOG_WRITER::CreateLogDirectory_::_1_::dtor$0

- ea: `0x18000edf1`
- end: `0x18000edff`
- name: `_LOG_WRITER::CreateLogDirectory_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000edf8`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogDirectory_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 248));
}

```

## disassembly

```asm
0x18000edf1  lea     rcx, [rdx+0F8h]
0x18000edf8  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
