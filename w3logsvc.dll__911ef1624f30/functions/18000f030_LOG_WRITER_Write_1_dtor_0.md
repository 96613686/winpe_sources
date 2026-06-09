# _LOG_WRITER::Write_::_1_::dtor$0

- ea: `0x18000f030`
- end: `0x18000f03e`
- name: `_LOG_WRITER::Write_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000f037`

## pseudocode

```c
void __fastcall LOG_WRITER::Write_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRA::~STRA((STRA *)(a2 + 32));
}

```

## disassembly

```asm
0x18000f030  lea     rcx, [rdx+20h]
0x18000f037  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
