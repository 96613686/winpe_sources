# _SrSmapiCreateReplicationRelationship_::_1_::dtor$9

- ea: `0x18002af81`
- end: `0x18002af8d`
- name: `_SrSmapiCreateReplicationRelationship_::_1_::dtor$9`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a90`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicationRelationship_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  return std::vector<std::wstring>::~vector<std::wstring>(a2 + 152);
}

```

## disassembly

```asm
0x18002af81  lea     rcx, [rdx+98h]
0x18002af88  jmp     ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
