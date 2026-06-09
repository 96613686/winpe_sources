# _LOG_WRITER::GetLogFileHandle_::_1_::dtor$0

- ea: `0x18000eff6`
- end: `0x18000f004`
- name: `_LOG_WRITER::GetLogFileHandle_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000effd`

## pseudocode

```c
void __fastcall LOG_WRITER::GetLogFileHandle_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 128));
}

```

## disassembly

```asm
0x18000eff6  lea     rcx, [rdx+80h]
0x18000effd  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
