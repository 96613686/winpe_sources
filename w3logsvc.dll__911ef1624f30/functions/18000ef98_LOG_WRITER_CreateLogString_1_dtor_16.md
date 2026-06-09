# _LOG_WRITER::CreateLogString_::_1_::dtor$16

- ea: `0x18000ef98`
- end: `0x18000efad`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$16`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000efa6`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_16(__int64 a1, __int64 a2)
{
  STRA::~STRA((STRA *)(a2 + 1864));
}

```

## disassembly

```asm
0x18000ef98  lea     rcx, [rdx+0F0h]
0x18000ef9f  add     rcx, 658h
0x18000efa6  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
