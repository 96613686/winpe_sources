# _LOG_WRITER::CreateLogString_::_1_::dtor$13

- ea: `0x18000ef47`
- end: `0x18000ef5c`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$13`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000ef55`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_13(__int64 a1, __int64 a2)
{
  STRA::~STRA((STRA *)(a2 + 1600));
}

```

## disassembly

```asm
0x18000ef47  lea     rcx, [rdx+0F0h]
0x18000ef4e  add     rcx, 550h
0x18000ef55  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
