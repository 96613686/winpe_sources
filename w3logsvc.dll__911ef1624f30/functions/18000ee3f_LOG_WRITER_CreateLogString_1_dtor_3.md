# _LOG_WRITER::CreateLogString_::_1_::dtor$3

- ea: `0x18000ee3f`
- end: `0x18000ee51`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$3`
- size: `18`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ee4a`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 248));
}

```

## disassembly

```asm
0x18000ee3f  lea     rcx, [rdx+0F0h]
0x18000ee46  add     rcx, 8
0x18000ee4a  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
