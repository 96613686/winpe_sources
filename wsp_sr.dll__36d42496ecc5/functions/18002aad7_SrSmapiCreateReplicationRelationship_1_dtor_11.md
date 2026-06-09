# _SrSmapiCreateReplicationRelationship_::_1_::dtor$11

- ea: `0x18002aad7`
- end: `0x18002aae3`
- name: `_SrSmapiCreateReplicationRelationship_::_1_::dtor$11`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a24`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicationRelationship_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 112));
}

```

## disassembly

```asm
0x18002aad7  mov     rcx, [rdx+70h]
0x18002aade  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
