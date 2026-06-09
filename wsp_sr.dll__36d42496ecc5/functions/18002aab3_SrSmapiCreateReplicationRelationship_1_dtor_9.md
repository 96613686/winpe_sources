# _SrSmapiCreateReplicationRelationship_::_1_::dtor$9

- ea: `0x18002aab3`
- end: `0x18002aabf`
- name: `_SrSmapiCreateReplicationRelationship_::_1_::dtor$9`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a50`

## pseudocode

```c
__int64 SrSmapiCreateReplicationRelationship_::_1_::dtor_9()
{
  return std::vector<std::wstring>::~vector<std::wstring>();
}

```

## disassembly

```asm
0x18002aab3  lea     rcx, [rdx+98h]
0x18002aaba  jmp     ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
