# _SrSmapiCreateReplicationRelationship_::_1_::dtor$5

- ea: `0x18002af4b`
- end: `0x18002af57`
- name: `_SrSmapiCreateReplicationRelationship_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a64`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicationRelationship_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 464);
}

```

## disassembly

```asm
0x18002af4b  lea     rcx, [rdx+1D0h]
0x18002af52  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
