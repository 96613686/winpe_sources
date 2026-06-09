# _LOG_WRITER::CreateLogString_::_1_::dtor$15

- ea: `0x18000ef7d`
- end: `0x18000ef92`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$15`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000ef8b`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_15(__int64 a1, __int64 a2)
{
  STRA::~STRA((STRA *)(a2 + 1776));
}

```

## disassembly

```asm
0x18000ef7d  lea     rcx, [rdx+0F0h]
0x18000ef84  add     rcx, 600h
0x18000ef8b  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
