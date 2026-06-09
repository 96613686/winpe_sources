# _SrSmapiCreateReplicationRelationship_::_1_::dtor$8

- ea: `0x18002aaa1`
- end: `0x18002aaad`
- name: `_SrSmapiCreateReplicationRelationship_::_1_::dtor$8`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a24`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicationRelationship_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 368);
}

```

## disassembly

```asm
0x18002aaa1  lea     rcx, [rdx+170h]
0x18002aaa8  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
