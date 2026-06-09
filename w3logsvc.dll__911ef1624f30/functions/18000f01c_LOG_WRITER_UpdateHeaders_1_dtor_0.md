# _LOG_WRITER::UpdateHeaders_::_1_::dtor$0

- ea: `0x18000f01c`
- end: `0x18000f02a`
- name: `_LOG_WRITER::UpdateHeaders_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f023`

## pseudocode

```c
void __fastcall LOG_WRITER::UpdateHeaders_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 48));
}

```

## disassembly

```asm
0x18000f01c  lea     rcx, [rdx+30h]
0x18000f023  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
