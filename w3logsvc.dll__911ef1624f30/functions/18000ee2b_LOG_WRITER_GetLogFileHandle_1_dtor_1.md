# _LOG_WRITER::GetLogFileHandle_::_1_::dtor$1

- ea: `0x18000ee2b`
- end: `0x18000ee39`
- name: `_LOG_WRITER::GetLogFileHandle_::_1_::dtor$1`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ee32`

## pseudocode

```c
void __fastcall LOG_WRITER::GetLogFileHandle_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 184));
}

```

## disassembly

```asm
0x18000ee2b  lea     rcx, [rdx+0B8h]
0x18000ee32  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
