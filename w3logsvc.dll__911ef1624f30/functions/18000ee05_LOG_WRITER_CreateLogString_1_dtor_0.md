# _LOG_WRITER::CreateLogString_::_1_::dtor$0

- ea: `0x18000ee05`
- end: `0x18000ee11`
- name: `_LOG_WRITER::CreateLogString_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800021c4`

## pseudocode

```c
void __fastcall LOG_WRITER::CreateLogString_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  LOG_WRITER::ETWLogData::~ETWLogData((LOG_WRITER::ETWLogData *)(a2 + 240));
}

```

## disassembly

```asm
0x18000ee05  lea     rcx, [rdx+0F0h]; this
0x18000ee0c  jmp     ??1ETWLogData@LOG_WRITER@@QEAA@XZ; LOG_WRITER::ETWLogData::~ETWLogData(void)
```
