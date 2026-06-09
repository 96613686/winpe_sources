# _SrSmapiCreateReplicationGroup_::_1_::dtor$4

- ea: `0x18002af03`
- end: `0x18002af0f`
- name: `_SrSmapiCreateReplicationGroup_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a90`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicationGroup_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::vector<std::wstring>::~vector<std::wstring>(a2 + 104);
}

```

## disassembly

```asm
0x18002af03  lea     rcx, [rdx+68h]
0x18002af0a  jmp     ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
