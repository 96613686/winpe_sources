# _SrSmapiCreateReplicationGroup_::_1_::dtor$4

- ea: `0x18002aa35`
- end: `0x18002aa41`
- name: `_SrSmapiCreateReplicationGroup_::_1_::dtor$4`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a50`

## pseudocode

```c
__int64 SrSmapiCreateReplicationGroup_::_1_::dtor_4()
{
  return std::vector<std::wstring>::~vector<std::wstring>();
}

```

## disassembly

```asm
0x18002aa35  lea     rcx, [rdx+68h]
0x18002aa3c  jmp     ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
