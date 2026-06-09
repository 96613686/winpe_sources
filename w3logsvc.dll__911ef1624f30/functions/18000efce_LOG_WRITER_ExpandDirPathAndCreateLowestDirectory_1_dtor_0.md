# _LOG_WRITER::ExpandDirPathAndCreateLowestDirectory_::_1_::dtor$0

- ea: `0x18000efce`
- end: `0x18000efdc`
- name: `_LOG_WRITER::ExpandDirPathAndCreateLowestDirectory_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000efd5`

## pseudocode

```c
void __fastcall LOG_WRITER::ExpandDirPathAndCreateLowestDirectory_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 120));
}

```

## disassembly

```asm
0x18000efce  lea     rcx, [rdx+78h]
0x18000efd5  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
