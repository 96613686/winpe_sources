# _SrSmapiCreateReplicationRelationship_::_1_::dtor$6

- ea: `0x18002af5d`
- end: `0x18002af69`
- name: `_SrSmapiCreateReplicationRelationship_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a64`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicationRelationship_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 432);
}

```

## disassembly

```asm
0x18002af5d  lea     rcx, [rdx+1B0h]
0x18002af64  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
