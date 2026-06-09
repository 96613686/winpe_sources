# _LOG_WRITER::LOG_WRITER_::_1_::dtor$1

- ea: `0x18000ed60`
- end: `0x18000ed72`
- name: `_LOG_WRITER::LOG_WRITER_::_1_::dtor$1`
- size: `18`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ed6b`

## pseudocode

```c
void __fastcall LOG_WRITER::LOG_WRITER_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(*(_QWORD *)(a2 + 48) + 72LL));
}

```

## disassembly

```asm
0x18000ed60  mov     rcx, [rdx+30h]
0x18000ed67  add     rcx, 48h ; 'H'
0x18000ed6b  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
