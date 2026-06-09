# _SrSmapiCreateReplicationRelationship_::_1_::dtor$7

- ea: `0x18002ad28`
- end: `0x18002ad34`
- name: `_SrSmapiCreateReplicationRelationship_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a64`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicationRelationship_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 400);
}

```

## disassembly

```asm
0x18002ad28  lea     rcx, [rdx+190h]
0x18002ad2f  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
