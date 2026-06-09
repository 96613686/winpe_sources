# _SrSmapipCreateReplicationRelationshipSetReturn_::_1_::dtor$1

- ea: `0x18002b10a`
- end: `0x18002b116`
- name: `_SrSmapipCreateReplicationRelationshipSetReturn_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a64`

## pseudocode

```c
__int64 __fastcall SrSmapipCreateReplicationRelationshipSetReturn_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 64));
}

```

## disassembly

```asm
0x18002b10a  mov     rcx, [rdx+40h]
0x18002b111  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
