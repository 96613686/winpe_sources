# _LOG_WRITER::CreateLogString_::_1_::dtor$5

- ea: `0x18000ee6f`
- end: `0x18000ee84`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$5`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ee7d`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 408));
}

```

## disassembly

```asm
0x18000ee6f  lea     rcx, [rdx+0F0h]
0x18000ee76  add     rcx, 0A8h
0x18000ee7d  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
