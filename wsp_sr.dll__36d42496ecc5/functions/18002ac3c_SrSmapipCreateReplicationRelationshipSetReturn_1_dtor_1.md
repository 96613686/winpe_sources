# _SrSmapipCreateReplicationRelationshipSetReturn_::_1_::dtor$1

- ea: `0x18002ac3c`
- end: `0x18002ac48`
- name: `_SrSmapipCreateReplicationRelationshipSetReturn_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a24`

## pseudocode

```c
__int64 __fastcall SrSmapipCreateReplicationRelationshipSetReturn_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 64));
}

```

## disassembly

```asm
0x18002ac3c  mov     rcx, [rdx+40h]
0x18002ac43  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
