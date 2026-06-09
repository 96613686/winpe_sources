# _LOG_WRITER::CreateLogString_::_1_::dtor$4

- ea: `0x18000ee57`
- end: `0x18000ee69`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$4`
- size: `18`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ee62`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 328));
}

```

## disassembly

```asm
0x18000ee57  lea     rcx, [rdx+0F0h]
0x18000ee5e  add     rcx, 58h ; 'X'
0x18000ee62  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
