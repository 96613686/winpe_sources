# _SrSmapiCreateReplicationRelationship_::_1_::dtor$11

- ea: `0x18002afa5`
- end: `0x18002afb1`
- name: `_SrSmapiCreateReplicationRelationship_::_1_::dtor$11`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a64`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicationRelationship_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 112));
}

```

## disassembly

```asm
0x18002afa5  mov     rcx, [rdx+70h]
0x18002afac  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
