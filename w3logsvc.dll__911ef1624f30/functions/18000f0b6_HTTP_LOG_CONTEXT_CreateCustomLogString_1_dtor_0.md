# _HTTP_LOG_CONTEXT::CreateCustomLogString_::_1_::dtor$0

- ea: `0x18000f0b6`
- end: `0x18000f0c4`
- name: `_HTTP_LOG_CONTEXT::CreateCustomLogString_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f0bd`

## pseudocode

```c
void __fastcall HTTP_LOG_CONTEXT::CreateCustomLogString_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 40));
}

```

## disassembly

```asm
0x18000f0b6  lea     rcx, [rdx+28h]
0x18000f0bd  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
