# _SrSmapiCreateReplicationRelationship_::_1_::dtor$7

- ea: `0x18002a85b`
- end: `0x18002a867`
- name: `_SrSmapiCreateReplicationRelationship_::_1_::dtor$7`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a24`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicationRelationship_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 400);
}

```

## disassembly

```asm
0x18002a85b  lea     rcx, [rdx+190h]
0x18002a862  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
