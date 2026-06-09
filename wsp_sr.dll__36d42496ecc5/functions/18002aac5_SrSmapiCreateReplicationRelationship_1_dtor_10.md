# _SrSmapiCreateReplicationRelationship_::_1_::dtor$10

- ea: `0x18002aac5`
- end: `0x18002aad1`
- name: `_SrSmapiCreateReplicationRelationship_::_1_::dtor$10`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a50`

## pseudocode

```c
__int64 SrSmapiCreateReplicationRelationship_::_1_::dtor_10()
{
  return std::vector<std::wstring>::~vector<std::wstring>();
}

```

## disassembly

```asm
0x18002aac5  lea     rcx, [rdx+80h]
0x18002aacc  jmp     ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
