# _LOG_WRITER::CreateLogString_::_1_::dtor$11

- ea: `0x18000ef11`
- end: `0x18000ef26`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$11`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ef1f`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 1168));
}

```

## disassembly

```asm
0x18000ef11  lea     rcx, [rdx+0F0h]
0x18000ef18  add     rcx, 3A0h
0x18000ef1f  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
