# _LOG_WRITER::CreateLogString_::_1_::dtor$14

- ea: `0x18000ef62`
- end: `0x18000ef77`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$14`
- size: `21`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000ef70`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_14(__int64 a1, __int64 a2)
{
  STRA::~STRA((STRA *)(a2 + 1688));
}

```

## disassembly

```asm
0x18000ef62  lea     rcx, [rdx+0F0h]
0x18000ef69  add     rcx, 5A8h
0x18000ef70  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
