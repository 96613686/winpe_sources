# _LOG_WRITER::ExpandDirPathAndCreateLowestDirectory_::_1_::dtor$1

- ea: `0x18000efe2`
- end: `0x18000eff0`
- name: `_LOG_WRITER::ExpandDirPathAndCreateLowestDirectory_::_1_::dtor$1`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000efe9`

## pseudocode

```c
void __fastcall LOG_WRITER::ExpandDirPathAndCreateLowestDirectory_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 64));
}

```

## disassembly

```asm
0x18000efe2  lea     rcx, [rdx+40h]
0x18000efe9  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
