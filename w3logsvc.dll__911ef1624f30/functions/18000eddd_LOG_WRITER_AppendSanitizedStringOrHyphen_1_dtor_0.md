# _LOG_WRITER::AppendSanitizedStringOrHyphen_::_1_::dtor$0

- ea: `0x18000eddd`
- end: `0x18000edeb`
- name: `_LOG_WRITER::AppendSanitizedStringOrHyphen_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000ede4`

## pseudocode

```c
void __fastcall LOG_WRITER::AppendSanitizedStringOrHyphen_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRA::~STRA((STRA *)(a2 + 40));
}

```

## disassembly

```asm
0x18000eddd  lea     rcx, [rdx+28h]
0x18000ede4  jmp     cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
```
