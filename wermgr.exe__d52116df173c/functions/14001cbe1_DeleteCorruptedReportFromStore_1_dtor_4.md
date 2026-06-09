# _DeleteCorruptedReportFromStore_::_1_::dtor$4

- ea: `0x14001cbe1`
- end: `0x14001cbed`
- name: `_DeleteCorruptedReportFromStore_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140004b68`

## pseudocode

```c
void __fastcall DeleteCorruptedReportFromStore_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  CIniParser::~CIniParser((CIniParser *)(a2 + 224));
}

```

## disassembly

```asm
0x14001cbe1  lea     rcx, [rdx+0E0h]; this
0x14001cbe8  jmp     ??1CIniParser@@QEAA@XZ; CIniParser::~CIniParser(void)
```
