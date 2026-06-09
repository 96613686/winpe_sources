# _LOG_WRITER::CreateLogString_::_1_::dtor$17

- ea: `0x18000efb3`
- end: `0x18000efc8`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$17`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000efc1`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_17(__int64 a1, __int64 a2)
{
  STRA::~STRA((STRA *)(a2 + 1952));
}

```

## disassembly

```asm
0x18000efb3  lea     rcx, [rdx+0F0h]
0x18000efba  add     rcx, 6B0h
0x18000efc1  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
