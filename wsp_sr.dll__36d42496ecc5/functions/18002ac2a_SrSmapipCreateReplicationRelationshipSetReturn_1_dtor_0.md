# _SrSmapipCreateReplicationRelationshipSetReturn_::_1_::dtor$0

- ea: `0x18002ac2a`
- end: `0x18002ac36`
- name: `_SrSmapipCreateReplicationRelationshipSetReturn_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a24`

## pseudocode

```c
__int64 __fastcall SrSmapipCreateReplicationRelationshipSetReturn_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 72));
}

```

## disassembly

```asm
0x18002ac2a  mov     rcx, [rdx+48h]
0x18002ac31  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
